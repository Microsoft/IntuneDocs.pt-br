---
title: Usar extensões de mobilidade Zebra em dispositivos Android no Microsoft Intune – Azure | Microsoft Docs
description: Use o Microsoft Intune para gerenciar e usar dispositivos Zebra que executam o Android com extensões de mobilidade da Zebra (MX). Consulte todas as etapas, incluindo o aplicativo de Portal da empresa, carregar o aplicativo, atribua a função de administrador do dispositivo, criar um perfil de StageNow e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa2734247569245794bce7fe1de68c8b20c6091f
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490597"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Use e gerencie dispositivos Zebra com extensões de mobilidade Zebra no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune inclui um conjunto avançado de recursos, incluindo gerenciamento de aplicativos e definir configurações do dispositivo. Essas configurações e recursos internos são usadas para gerenciar dispositivos Android fabricados pela Zebra Technologies, também conhecido como "dispositivos de Zebra".

Se você quiser personalizar ou adicionar mais configurações de Zebra específicas, você também pode usar Zebra **extensões de mobilidade (MX)** nesses dispositivos. 

Esse recurso aplica-se a:

- Android

Sua empresa pode usar dispositivos Zebra para varejo no chão de fábrica e muito mais. Por exemplo, você é um varejista e o seu ambiente incluir milhares de dispositivos móveis de Zebra usados pelos vendedores. Intune pode ajudar a gerenciar esses dispositivos como parte de sua solução MDM (gerenciamento) do dispositivo móvel.

Usando o Intune, você pode registrar dispositivos Zebra para implantar seus aplicativos de linha de negócios para os dispositivos. Perfis de "Configuração do dispositivo" permitem que você crie perfis MX para gerenciar as configurações específicas da Zebra.

Este artigo mostra como usar extensões de mobilidade da Zebra (MX) em dispositivos Zebra no Microsoft Intune.

## <a name="before-you-begin"></a>Antes de começar

- Certifique-se de que você tem a versão mais recente do aplicativo da área de trabalho StageNow da Zebra Technologies.
- Verifique [matriz de recursos MX completa da Zebra](http://techdocs.zebra.com/mx/compatibility) (abre o site de web da Zebra) para confirmar os perfis criados são compatíveis com a versão MX, versão do sistema operacional e modelo do dispositivo.
- Certos dispositivos, como dispositivos TC20/25, não oferecem suporte a todos os recursos disponíveis do MX no StageNow. Verifique [matriz de recursos da Zebra](http://techdocs.zebra.com/mx/tc2x/) (abre o site de web da Zebra) para obter informações de suporte atualizado.

## <a name="step-1-install-the-latest-company-portal-app"></a>Etapa 1: Instalar o aplicativo de Portal da empresa mais recente

No dispositivo, vá para o Google Play store, baixe e instale o aplicativo de Portal da empresa Intune da Microsoft. Quando instalado no Google Play, o aplicativo Portal da empresa obtém atualizações e correções automaticamente.

Se o Google Play não estiver disponível, baixe o [Portal de empresa do Microsoft Intune para Android](https://www.microsoft.com/download/details.aspx?id=49140) (abre outro site da Microsoft), e [sideload-](#sideload-the-company-portal-app) (neste artigo). Quando instalado dessa maneira, o aplicativo não recebe atualizações ou corrige automaticamente. Regularmente, você deve atualizar e corrigir o aplicativo manualmente.

### <a name="sideload-the-company-portal-app"></a>Sideload do aplicativo do Portal da Empresa

"Sideload" é quando você não usar o Google Play para instalar um aplicativo. Para carregar o aplicativo de Portal da empresa, use StageNow. 

As etapas a seguir fornecem uma visão geral. Para obter detalhes específicos, consulte a documentação da Zebra. [Registrar em um MDM usando StageNow](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (abre o site de web da Zebra) pode ser um bom recurso.

1. No StageNow, crie um perfil para **registrar em um MDM**.
2. Na **implantação**, opte por baixar o arquivo do agente MDM.
3. Defina a **aplicativo de suporte** e **configuração de Download** as etapas para **não**.
4. Na **Baixe o MDM**, selecione **arquivo de transferência/cópia**. Adicione a origem e destino do pacote Android de Portal da empresa (APK).
5. Na **MDM iniciar**, deixe os valores padrão como-está. Adicione os seguintes detalhes:

    - **Nome do pacote**: `com.microsoft.windowsintune.companyportal`
    - **Nome da classe**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

Continue para o perfil de publicação e consumi-lo com o aplicativo StageNow no dispositivo. O aplicativo de Portal da empresa é instalado e aberto no dispositivo.

> [!TIP]
> Para obter mais informações sobre StageNow e o que ele faz, consulte [preparação de dispositivo StageNow Android](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (abre o site de web da Zebra).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>Etapa 2: Confirmar que o aplicativo de Portal da empresa tem a função de administrador do dispositivo

O aplicativo de Portal da empresa requer administrador do dispositivo para gerenciar dispositivos Android. Para ativar a função de administrador do dispositivo, alguns dispositivos Zebra incluem uma interface de usuário (IU) no dispositivo. Se o dispositivo inclui uma interface do usuário, o aplicativo de Portal da empresa solicita que o usuário final para conceder o administrador do dispositivo durante [registro](#step-3-enroll-the-device-in-to-intune) (neste artigo).

Se uma interface do usuário não estiver disponível, use o **DevAdmin Manager** no StageNow para criar um perfil que concede manualmente o administrador do dispositivo para o aplicativo de Portal da empresa.

As etapas a seguir fornecem uma visão geral. Para obter detalhes específicos, consulte a documentação da Zebra. 
[Definir o modo de troca de bateria como administrador do dispositivo](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (abre o site da Zebra) pode ser um bom recurso.

1. No StageNow, crie um perfil e selecione **Xpert modo**.
2. Adicione **DevAdmin Manager** ao perfil.
3. Definir **ação de administração do dispositivo** à **ativar administrador do dispositivo como**.
4. Definir **nome do pacote de administração de dispositivo** para `com.microsoft.windowsintune.companyportal`.
5. Definir **nome de classe do administrador do dispositivo** para `com.microsoft.omadm.client.PolicyManagerReceiver`.

Continue para o perfil de publicação e consumi-lo com o aplicativo StageNow no dispositivo. O aplicativo de Portal da empresa é concedido a função de administrador do dispositivo.

## <a name="step-3-enroll-the-device-in-to-intune"></a>Etapa 3: Registrar o dispositivo no Intune

Depois de concluir as duas primeiras etapas, o aplicativo de Portal da empresa é instalado no dispositivo. O dispositivo está pronto para ser registrado no Intune.

[Registrar dispositivos Android](android-enroll.md) lista as etapas. Se você tiver muitos dispositivos Zebra, talvez você queira usar um [conta de Gerenciador de registro de dispositivo](device-enrollment-manager-enroll.md).

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>Etapa 4: Criar um perfil de gerenciamento de dispositivo no StageNow

Use StageNow para criar um perfil que define as configurações que você deseja gerenciar no dispositivo. Para obter detalhes específicos, consulte a documentação da Zebra. [Perfis](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (abre o site da Zebra) pode ser um bom recurso.

Quando você cria o perfil no StageNow, na última etapa, selecione **exportar para o MDM**. Isso gera um arquivo XML. Salve esse arquivo. Você precisará dele em uma etapa posterior.

> [!TIP]
> É recomendável testar o perfil antes de implantá-lo em dispositivos em sua organização. Para testar, na última etapa durante a criação de perfis com StageNow em seu computador, use o **testar** opções. Em seguida, consuma o arquivo gerado pelo StageNow com o aplicativo StageNow no dispositivo. 
> 
> O aplicativo StageNow no dispositivo mostra logs gerados quando você testar o perfil. [Use StageNow registra nos dispositivos Zebra que executam o Android no Intune](android-zebra-mx-logs-troubleshoot.md) tem informações sobre como usar logs StageNow para entender os erros.

> [!NOTE]
> Se você fazer referência a aplicativos, pacotes de atualização ou atualizar outros arquivos no seu perfil StageNow, deseja que o dispositivo para obter essas atualizações. Para obter as atualizações, o dispositivo deve se conectar ao servidor de implantação StageNow quando o perfil é aplicado. 
> 
> Ou, você pode usar recursos internos no Intune para obter essas alterações, incluindo: 
> - Recursos de gerenciamento de aplicativo para [adicione](apps-add.md), [implantar](apps-deploy.md), atualizar, e [monitor](apps-monitor.md) aplicativos.
> - Gerencie [atualizações do sistema e aplicativo](device-restrictions-android-for-work.md#device-owner-only) em dispositivos que executam o Android Enterprise

Depois de testar o arquivo, a próxima etapa é implantar o perfil para dispositivos usando o Intune.

> [!NOTE]
> Implante um perfil de cada dispositivo. Se houver vários perfis de StageNow que você deseja implantar nos dispositivos, em seguida, exportar perfis StageNow e combinar as configurações em um único arquivo XML antes de adicioná-lo ao Intune. 
> 
> Você não quer duas configurações que configuram a mesma propriedade no mesmo arquivo XML. O objetivo é evitar conflitos entre configurações do dispositivo.

## <a name="step-5-create-a-profile-in-intune"></a>Etapa 5: Criar um perfil do Intune

No Intune, crie um perfil de configuração do dispositivo:

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do Dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição:** insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: selecione **Android**.
    - **Tipo de perfil**: selecione **perfil MX (Zebra)**.

4. Na **perfil MX no formato. XML**, adicione o arquivo de perfil XML [exportado do StageNow](#step-4-create-a-device-management-profile-in-stagenow) (neste artigo).
5. Selecione **OK** > **Criar** para salvar suas alterações. A política é criada e mostrada na lista.

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Na próxima vez que o dispositivo verifica atualizações de configuração, o perfil de MX é implantado no dispositivo. Dispositivos de sincronização com o Intune quando o registro dos dispositivos e, em seguida, aproximadamente a cada 8 horas. Você também pode [forçar uma sincronização no Intune](device-sync.md). Ou, no dispositivo, abra o **aplicativo de Portal da empresa** > **configurações** > **sincronização**. 

> [!TIP]
> - Por motivos de segurança, você não verá o texto XML de perfil depois que você salvá-lo. O texto é criptografado, e você só verá asteriscos (`****`). Para referência, é recomendável salvar cópias dos perfis MX antes de adicioná-los ao Intune.
> 
> - Para atualizar um perfil depois que ele é atribuído a dispositivos Zebra, crie um arquivo XML StageNow atualizado, editar o perfil do Intune existente e adicionar o novo arquivo XML StageNow. Esse novo arquivo substituirá a política StageNow anterior no perfil.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

[Use StageNow logs para solucionar problemas de dispositivos Zebra](android-zebra-mx-logs-troubleshoot.md).
