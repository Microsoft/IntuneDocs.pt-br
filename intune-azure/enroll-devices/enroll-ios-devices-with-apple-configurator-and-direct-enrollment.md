---
title: Registrar dispositivos iOS com o Apple Configurator e registro direto
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a usar o Apple Configurator para registrar dispositivos iOS corporativos com registro direto."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b464a07e701797d39b7f9f50d1854a9a2682ac8e
ms.openlocfilehash: 3208e964f2676ebcc1e54e29f039c4965c20238f
ms.lasthandoff: 03/01/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>Registrar dispositivos iOS com o Apple Configurator e registro direto 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

O Intune dá suporte ao registro de dispositivos iOS corporativos usando o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) em execução em um computador Mac. Esse processo não restaura as configurações de fábrica do dispositivo e registra o dispositivo com uma política predefinida. Esse método destina-se a dispositivos **sem afinidade de usuário** e requer que você conecte o dispositivo iOS por USB a um computador Mac para configurar o registro corporativo.

>[!NOTE]
>Esse método de registro não pode ser usado com o método de [gerenciador de registro de dispositivos](enroll-devices-using-device-enrollment-manager.md).

Ao registrar dispositivos iOS diretamente, você pode registrar um dispositivo sem adquirir o número de série do dispositivo. Você também pode nomear o dispositivo para fins de identificação antes de o Intune capturar o nome do dispositivo durante o registro. Não há suporte para o aplicativo de Portal da Empresa para dispositivos registrados diretamente. Esta diretriz presume que você está usando o Apple Configurator 2.0 em um computador Mac.

Outros métodos de registrar dispositivos iOS são descritos em [Escolher como registrar dispositivos iOS no Intune](choose-ios-enrollment-method.md).


## <a name="prerequisites"></a>Pré-requisitos

Preencha os seguintes pré-requisitos antes de configurar o registro do dispositivo iOS:

- [Configurar domínios](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Definir a Autoridade MDM](set-mdm-authority.md)
- [Criar grupos](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurar o Portal da Empresa](/intune-azure/manage-apps/company-portal-app)
- Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenha um certificado push de MDM da Apple](get-an-apple-mdm-push-certificate.md)
- Verifique se você tem acesso físico aos dispositivos iOS
- Obter os números de série do dispositivo (consulte [Como obter um número de série do iOS](https://support.apple.com//HT204308))
- Ter em mãos os cabos de conexão USB
- Verifique se você tem um computador Mac com [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) instalado

## <a name="create-an-apple-configurator-profile-for-devices"></a>Criar um perfil do Apple Configurator para dispositivos

Um perfil de registro de dispositivos define as configurações aplicadas a um grupo de dispositivos. As etapas a seguir mostram como criar um perfil de registro de dispositivo para dispositivos iOS registrados usando o Apple Configurator.

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha Intune, escolha **Registrar dispositivos** e escolha **Registro Apple**.

3. Em **Gerenciar configurações de registro do Apple Configurator**, selecione **Perfis de CA**.

4. Na folha **Perfis de registro do Apple Configurator**, selecione **Criar**.

5. Na folha **Criar Perfil de Registro**, insira um nome e uma descrição para o perfil.

6. Para **Afinidade de Usuário**, escolha **Registrar sem afinidade de usuário** para garantir que o dispositivo não esteja afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.

7. Selecione **Criar** para salvar o perfil.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Exporte um perfil como .mobileconfig para implantar em dispositivos iOS

1. Na folha **Exportar Perfil**, baixe o perfil de registro para o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) para envio por push diretamente como um perfil de gerenciamento para um dispositivo iOS conectado. Esse método não faz uma redefinição de fábrica do dispositivo.

2. Prepare o dispositivo com o Apple Configurator usando as etapas a seguir.

   a. Em um computador Mac, abra o Apple Configurator 2.0.

   b. Conecte o dispositivo iOS ao computador Mac com um cabo USB. Feche as Fotos, iTunes e outros aplicativos que são abertos com o dispositivo quando ele é detectado.

   c. No Apple Configurator, escolha o dispositivo iOS conectado e selecione o botão **Adicionar**. As opções que podem ser adicionadas ao dispositivo aparecem na lista suspensa. Escolha **Perfis**.

   d. Use o seletor de arquivos para selecionar o arquivo .mobileconfig exportado do Intune e escolha **Adicionar**. O perfil é adicionado ao dispositivo. Se o dispositivo for Sem supervisão, a instalação necessitará da aceitação no dispositivo.

3. Use as etapas a seguir para instalar o perfil no dispositivo iOS. O dispositivo já deve ter concluído o Assistente de Configuração e está pronto para uso. Se o registro envolve as implantações de aplicativo, o dispositivo deve ter uma ID Apple configurada, pois as implantações de aplicativo exigirão que você tenha uma ID Apple conectada na Windows Store.

   a. Desbloquear o dispositivo iOS.

   b. Na caixa de diálogo **Instalar perfil** para o **Perfil de gerenciamento**, escolha **Instalar**.

   c. Forneça a Senha do Dispositivo ou a ID da Apple, se necessário.

   d. Aceite o **Aviso** e escolha **Instalar**.

   e. Aceite o **Aviso Remoto** e escolha **Confiar**.

   f. Quando a caixa **Perfil Instalado** confirmar que o perfil foi Instalado, escolha **Concluído**.

4. No dispositivo iOS, abra **Configurações** e vá para **Geral** > **Gerenciamento de Dispositivo** > **Perfil de Gerenciamento**. Confirme que o perfil de instalação está listado, verifique as restrições de política do iOS e os aplicativos instalados. Aplicativos e restrições de política podem levar até 10 minutos para serem exibidos no dispositivo.

5. Distribuir dispositivos. O dispositivo iOS agora está registrado com o Intune e é gerenciado.

