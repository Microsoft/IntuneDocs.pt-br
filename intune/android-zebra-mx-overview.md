---
title: Usar o Zebra Mobility Extensions em dispositivos Android no Microsoft Intune – Azure | Microsoft Docs
description: Use o Microsoft Intune para gerenciar e usar dispositivos Zebra que executam o Android com o Zebra MX (Mobility Extensions). Veja todas as etapas, incluindo a instalação do aplicativo do Portal da Empresa, a execução do sideload do aplicativo, a atribuição da função de administrador de dispositivo, a criação de um perfil StageNow e mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2019
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
ms.openlocfilehash: 69814b91978aa3cd74c4dc239b099883ae402af9
ms.sourcegitcommit: b0cf661145ccc6e3518db620af199786a623a0d9
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64764777"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Usar e gerenciar dispositivos Zebra com o Zebra Mobility Extensions no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune conta com um conjunto avançado de recursos, incluindo o gerenciamento de aplicativos e a configuração do dispositivo. Esses recursos internos e configurações são usados para gerenciar dispositivos Android fabricados pela Zebra Technologies, também conhecidos como “dispositivos Zebra”.

Em dispositivos Android, use os perfis **MX (Mobility Extensions)** para personalizar ou adicionar mais configurações específicas da Zebra.

Este artigo mostra como usar o Zebra MX (Mobility Extensions) em dispositivos Zebra no Microsoft Intune.

Esse recurso aplica-se a:

- Android

Sua empresa pode usar dispositivos Zebra para varejo, no chão da fábrica e mais. Por exemplo, você já é um varejista e seu ambiente inclui milhares de dispositivos móveis Zebra usados por vendedores. O Intune pode ajudar a gerenciar esses dispositivos como parte da solução MDM (gerenciamento de dispositivo móvel).

Usando o Intune, é possível registrar dispositivos Zebra para implantar seus aplicativos de linha de negócios nos dispositivos. Os perfis de “Configuração de dispositivo” permitem que você crie perfis MX para gerenciar suas configurações específicas da Zebra.

## <a name="before-you-begin"></a>Antes de começar

- Verifique se você tem a versão mais recente do aplicativo da área de trabalho StageNow da Zebra Technologies.
- Marque [matriz de recursos MX completa da Zebra](http://techdocs.zebra.com/mx/compatibility) (abre o site da Zebra) para confirmar se os perfis criados são compatíveis com a versão MX, a versão do SO e o modelo do dispositivo.
- Certos dispositivos, como dispositivos TC20/25, não são compatíveis com todos os recursos de MX disponíveis no StageNow. Marque a [matriz de recursos da Zebra](http://techdocs.zebra.com/mx/tc2x/) (abre o site da Zebra) para receber informações de suporte atualizadas.

## <a name="step-1-install-the-latest-company-portal-app"></a>Etapa 1: instalar o aplicativo do Portal da Empresa mais recente

No dispositivo, acesse a Google Play Store, baixe e instale o aplicativo do Portal da Empresa do Intune da Microsoft. Quando instalado do Google Play, o aplicativo do Portal da Empresa recebe atualizações e correções automaticamente.

Se o Google Play não estiver disponível, baixe o [Portal da Empresa do Microsoft Intune para Android](https://www.microsoft.com/download/details.aspx?id=49140) (abre outro site da Microsoft) e execute [sideload](#sideload-the-company-portal-app) (neste artigo). Quando instalado dessa maneira, o aplicativo não recebe atualizações nem correções automaticamente. Você deve atualizar o aplicativo e aplicar patch dele regularmente.

### <a name="sideload-the-company-portal-app"></a>Sideload do aplicativo do Portal da Empresa

“Sideload” é quando você não usa o Google Play para instalar um aplicativo. Para executar o aplicativo do Portal da Empresa, use StageNow. 

As etapas a seguir oferecem uma visão geral. Para saber mais, confira a documentação da Zebra. [Registrar-se em um MDM usando StageNow](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (abre o site da Zebra) pode ser um bom recurso.

1. No StageNow, crie um perfil para **Registrar-se em um MDM**.
2. Na **Implantação**, escolha baixar o arquivo do agente MDM.
3. Defina as etapas **Dar Suporte ao Aplicativo** e **Baixar Configuração** como **Não**.
4. Em **Baixar o MDM**, selecione **Transferir/copiar arquivo**. Adicione a origem e o destino do APK (pacote do Android) do Portal da Empresa.
5. Em **Iniciar MDM**, deixe os valores padrão no estado em que se encontram. Adicione os seguintes detalhes:

    - **Nome do pacote**: `com.microsoft.windowsintune.companyportal`
    - **Nome da classe**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

Continue publicando o perfil e consuma-o com o aplicativo StageNow no dispositivo. O aplicativo do Portal da Empresa é instalado e aberto no dispositivo.

> [!TIP]
> Para saber mais sobre o StageNow e o que ele faz, confira [Processo de preparo do dispositivo Android para StageNow](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (abre o site da Zebra).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>Etapa 2: confirmar se o aplicativo do Portal da Empresa tem a função de administrador de dispositivo

O aplicativo do Portal da Empresa exige a função Administrador de Dispositivo para gerenciar dispositivos Android. Para ativar a função de Administrador de Dispositivo, alguns dispositivos Zebra incluem uma interface do usuário no dispositivo. Se o dispositivo incluir uma interface do usuário, o aplicativo do Portal da Empresa solicitará que o usuário final conceda a função de Administrador de Dispositivo durante o [registro](#step-3-enroll-the-device-in-to-intune) (neste artigo).

Se uma interface do usuário não estiver disponível, use o **DevAdmin Manager** no StageNow para criar um perfil que concede manualmente a função de Administrador de Dispositivo ao aplicativo do Portal da Empresa.

As etapas a seguir oferecem uma visão geral. Para saber mais, confira a documentação da Zebra. 
[Definir modo de troca de bateria como administrador de dispositivo](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (abre o site da Zebra) pode ser um bom recurso.

1. No StageNow, crie um perfil e selecione **Modo Xpert**.
2. Adicione o **DevAdmin Manager** ao perfil.
3. Defina **Ação de Administrador de Dispositivo** como **Ativar como Administrador de Dispositivo**.
4. Defina **Nome do Pacote do Administrador de Dispositivo** como `com.microsoft.windowsintune.companyportal`.
5. Defina **Nome de Classe do Administrador de Dispositivo** como `com.microsoft.omadm.client.PolicyManagerReceiver`.

Continue publicando o perfil e consuma-o com o aplicativo StageNow no dispositivo. O aplicativo do Portal da Empresa recebe a função de Administrador de Dispositivo.

## <a name="step-3-enroll-the-device-in-to-intune"></a>Etapa 3: registrar o dispositivo no Intune

Após concluir as duas primeiras etapas, o aplicativo do Portal da Empresa será instalado no dispositivo. O dispositivo está pronto para ser registrado no Intune.

[Registre os dispositivos Android](android-enroll.md) lista as etapas. Se você tiver muitos dispositivos Zebra, será conveniente usar uma [conta do DEM (gerenciador de registros de dispositivo)](device-enrollment-manager-enroll.md). Usar uma conta do DEM também remove a opção para cancelar o registro do aplicativo do Portal da Empresa para que os usuários não possam cancelar o registro do dispositivo facilmente.

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>Etapa 4: criar um perfil de gerenciamento de dispositivo no StageNow

Use o StageNow para criar um perfil que define as configurações que você deseja gerenciar no dispositivo. Para saber mais, confira a documentação da Zebra. [Perfis](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (abre o site da Zebra) pode ser um bom recurso.

Quando você cria o perfil no StageNow, na última etapa, selecione **Exportar para o MDM**. Isso gera um arquivo XML. Salve esse arquivo. Ele será necessário em uma etapa futura.

> [!TIP]
> É recomendável testar o perfil antes de implantá-lo em dispositivos em sua organização. Para testar, na última etapa, ao criar perfis com o StageNow em seu computador, use as opções **Testar**. Em seguida, consuma o arquivo gerado pelo StageNow com o aplicativo StageNow no dispositivo. 
> 
> O aplicativo StageNow no dispositivo mostra os logs gerados quando você testa o perfil. [Use os logs do StageNow nos dispositivos Zebra que executam o Android no Intune](android-zebra-mx-logs-troubleshoot.md) tem informações sobre como usar os logs do StageNow para entender os erros.

> [!NOTE]
> Se você referencia aplicativos e atualiza pacotes ou outros arquivos em seu perfil do StageNow, convém que o dispositivo receba essas atualizações. Para obter as atualizações, o dispositivo deve se conectar ao servidor de implantação do StageNow quando o perfil é aplicado. 
> 
> Ou é possível usar recursos internos no Intune para obter essas alterações, incluindo: 
> - Recursos de gerenciamento de aplicativo para [adicionar](apps-add.md), [implantar](apps-deploy.md), atualizar e [monitorar](apps-monitor.md) aplicativos.
> - Gerenciar [atualizações do sistema e do aplicativo](device-restrictions-android-for-work.md#device-owner-only) em dispositivos que executam o Android Enterprise

Após testar o arquivo, a próxima etapa será implantar o perfil em dispositivos que usam o Intune.

> [!NOTE]
> Implante um perfil em cada dispositivo. Se houver vários perfis do StageNow, implante nos dispositivos e, em seguida, exporte os perfis do StageNow e combine as configurações em um único arquivo XML antes de adicioná-lo ao Intune. 
> 
> Não convém ter duas configurações que definem a mesma propriedade no mesmo arquivo XML. A meta é evitar conflitos entre configurações no dispositivo.

## <a name="step-5-create-a-profile-in-intune"></a>Etapa 5: criar um perfil no Intune

No Intune, crie um perfil de configuração do dispositivo:

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do Dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição:** insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: selecione **Android**.
    - **Tipo de perfil**: selecione **Perfil do MX (apenas Zebra)**.

4. No **Perfil do MX no formato .xml**, adicione o arquivo de perfil XML [exportado do StageNow](#step-4-create-a-device-management-profile-in-stagenow) (neste artigo).
5. Selecione **OK** > **Criar** para salvar suas alterações. A política é criada e mostrada na lista.

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Na próxima vez em que o dispositivo verificar se há atualizações de configuração, o perfil do MX será implantado nele. Os dispositivos sincronizam com o Intune quando são registrados e, depois, a cada oito horas aproximadamente. Também é possível [forçar uma sincronização no Intune](device-sync.md). Ou, no dispositivo, abra o **aplicativo do Portal da Empresa** > **Configurações** > **Sincronizar**. 

> [!TIP]
> - Por motivos de segurança, você não verá o texto XML do perfil após salvá-lo. O texto é criptografado e você só verá asteriscos (`****`). Para sua referência, é recomendável salvar cópias dos perfis do MX antes de adicioná-los ao Intune.
> 
> - Para atualizar um perfil após atribuí-lo aos dispositivos Zebra, crie um arquivo XML do StageNow atualizado, edite o perfil do Intune existente e adicione o novo arquivo XML do StageNow. Esse novo arquivo substitui a política do StageNow anterior no perfil.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
- [Usar logs do StageNow para solucionar problemas de dispositivos Zebra](android-zebra-mx-logs-troubleshoot.md).
