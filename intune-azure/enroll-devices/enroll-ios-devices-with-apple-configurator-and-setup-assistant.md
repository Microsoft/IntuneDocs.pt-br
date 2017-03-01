---
title: "Registrar dispositivos iOS – Apple Configurator-Assistente de Configuração | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: aprenda a usar o Apple Configurator para registrar dispositivos iOS corporativos com o Assistente de Configuração."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 888e7b7af7dcca4154f67a1de781eb7908d9a187
ms.lasthandoff: 02/15/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>Registrar dispositivos iOS com o Apple Configurator e o Assistente de Configuração 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

O Intune dá suporte ao registro de dispositivos iOS corporativos usando o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) em execução em um computador Mac. Esse processo redefine o dispositivo para as configurações de fábrica e o prepara para executar o Assistente de Configuração, instalando as políticas da empresa para o novo usuário do dispositivo.

>[!NOTE]
>Esse método de registro não pode ser usado com o método de [gerenciador de registro de dispositivos](enroll-devices-using-device-enrollment-manager.md).

Usando o Apple Configurator, você pode redefinir um dispositivo iOS para as configurações de fábrica e prepará-lo para ser configurado para o novo usuário do dispositivo. Esse método requer que você conecte o dispositivo iOS a um computador Mac via USB para configurar o registro corporativo e supõe que você esteja usando o Apple Configurator 2.0. A maioria dos cenários exige que a política aplicada ao dispositivo iOS inclua afinidade do usuário para habilitar o aplicativo no Portal da Empresa do Intune.

Outros métodos de registrar dispositivos iOS são descritos em [Escolher como registrar dispositivos iOS no Intune](choose-ios-enrollment-method.md).

## <a name="prerequisites"></a>Pré-requisitos

Preencha os seguintes pré-requisitos antes de configurar o registro do dispositivo iOS:

- [Configurar domínios](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Definir a Autoridade MDM](set-mdm-authority.md)
- [Criar grupos](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurar o Portal da Empresa](/intune-azure/manage-apps/company-portal-app.md)
- Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenha um certificado push de MDM da Apple](get-an-apple-mdm-push-certificate.md)
- Verifique se você tem acesso físico aos dispositivos iOS
- Obter os números de série do dispositivo (consulte [Como obter um número de série do iOS](https://support.apple.com//HT204308))
- Ter em mãos os cabos de conexão USB
- Verifique se você tem um computador Mac com [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) instalado
- [Adicionar números de série do Apple Configurator](add-apple-configurator-serial-numbers.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Criar um perfil do Apple Configurator para dispositivos

Um perfil de registro de dispositivos define as configurações aplicadas a um grupo de dispositivos. As etapas a seguir mostram como criar um perfil de registro de dispositivo para dispositivos iOS registrados usando o Apple Configurator.

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha Intune, escolha **Registrar dispositivos** e escolha **Registro Apple**.

3. Em **Gerenciar configurações de registro do Apple Configurator**, selecione **Perfis de CA**.

4. Na folha **Perfis de registro do Apple Configurator**, selecione **Criar**.

5. Na folha **Criar Perfil de Registro**, insira um nome e uma descrição para o perfil.

6. Para **Afinidade do Usuário**, escolha se os dispositivos com esse perfil serão registrados com ou sem afinidade do usuário.

   - **Inscrever com afinidade do utilizador** – O dispositivo deve ser afiliado a um usuário durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa. A afinidade do usuário deve ser configurada para dispositivos gerenciados por DEP que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos.

   - **Inscrever sem afinidade do utilizador** – O dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.

7. Selecione **Criar** para salvar o perfil.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Atribuir números de série a um perfil do Apple Configurator

Depois de criar perfis do Apple Configurator, você poderá atribuir números de série do dispositivo aos perfis. Para poder atribuir números de série, você deverá adicioná-los primeiro ao Intune seguindo as etapas em [Adicionar números de série ao Apple Configurator](add-apple-configurator-serial-numbers.md).

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Atribuir números de série a perfis do Apple Configurator

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha **Perfis de Registro do Apple Configurator**, selecione o perfil ao qual você deseja atribuir números de série.

3. Na folha nomeada para o perfil, selecione **Números de Série** > **Atribuir**.

4. Selecione os números de série para os quais você deseja atribuir o perfil e selecione o botão **Atribuir**.

## <a name="export-the-profile-to-ios-devices"></a>Exportar o perfil para dispositivos iOS

Depois de criar o perfil e atribuir os números de série, você precisará exportar o perfil do Intune como uma URL ou um arquivo no formato descrito abaixo. Em seguida, você deverá importá-lo manualmente para o programa Apple Configurator em um Mac, quando então o programa Apple Configurator o implantará nos dispositivos.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Exportar um perfil usando o Assistente para configuração de registro

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha **Perfis de Registro do Apple Configurator**, escolha o perfil a ser exportado.

3. Na folha do perfil, selecione **Exportar Perfil**.

4. Copie a URL do perfil para o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) com o dispositivo iOS anexado. Você fará o upload no Apple Configurator posteriormente para definir o perfil do Intune utilizado pelos dispositivos iOS.

  Para dar suporte ao Apple Configurator 2, a URL do Perfil 2.0 deve ser editada. Para fazer isso, substitua este código:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Por este código:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Você carregará essa URL do perfil para o serviço Apple DEP usando o Apple Configurator no procedimento a seguir para definir o perfil do Intune utilizado pelos dispositivos iOS.

5. Carregue essa URL do perfil para o serviço Apple DEP usando o Apple Configurator para definir o perfil do Intune utilizado pelos dispositivos iOS.


    1.  Em um computador Mac, abra o **Apple Configurator 2**. Na barra de menus, selecione **Apple Configurator 2** e clique em **Preferências**.

         > [!WARNING]
         > Os dispositivos serão redefinidos para as configurações de fábrica durante o processo de registro. Como melhor prática, redefina o dispositivo e ligue-o. Os dispositivos devem estar na tela **Olá** quando você conectar o dispositivo.

    2. No painel de **preferências**, selecione **Servidores** e escolha o símbolo de mais (+) para inicializar o assistente do Servidor MDM. Escolha **Avançar**.

    3. Insira o **Nome** e a **URL do Registro** para o servidor MDM da etapa 6 em Registro do Assistente de Configuração para dispositivos iOS com o Microsoft Intune. Para URL de Registro, insira a URL do perfil de registro exportada do Intune. Escolha **Avançar**.  

       Você pode desconsiderar com segurança um aviso indicando "URL do servidor não verificada". Para continuar, clique em **Avançar** até que o assistente seja concluído.

    4.  Conecte os dispositivos móveis iOS ao computador Mac com um adaptador USB.

        > [!WARNING]
        > Os dispositivos serão redefinidos para as configurações de fábrica durante o processo de registro. Como melhor prática, redefina o dispositivo e ligue-o. Os dispositivos devem estar na tela **Olá** quando você iniciar o Assistente de Configuração.

    5.  Selecione **Preparar**. No painel **Preparar o Dispositivo iOS**, selecione **Manual** e, em seguida, selecione **Avançar**.

    6. No painel **Registrar no Servidor MDM**, selecione o nome do servidor que você criou e escolha **Avançar**.

    7. No painel **Supervisionar Dispositivos**, selecione o nível de supervisão e, em seguida, selecione **Avançar**.

    8. No painel **Criar uma Organização**, escolha **Organização** ou crie uma nova organização e escolha **Avançar**.

    9. No painel **Configurar o Assistente de Instalação do iOS**, escolha as etapas que serão apresentadas ao usuário e escolha **Preparar**. Se solicitado, autentique para atualizar as configurações de confiança.  

    10. Quando o dispositivo iOS concluir a preparação, desconecte o cabo USB.  

6.  **Distribuir dispositivos**.
    Os dispositivos agora estão prontos para registro corporativo. Desligue os dispositivos e distribua-os para os usuários. Quando os usuários ligarem seus dispositivos, o Assistente de Configuração será iniciado.

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Como os usuários instalam e usam o Portal da Empresa em seus dispositivos

Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos. Assim que os usuários receberem seus dispositivos, eles deverão realizar várias etapas adicionais descritas abaixo para concluir o Assistente de Configuração e instalar o aplicativo do Portal da Empresa.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Como os usuários registram dispositivos iOS corporativos com afinidade de usuário

1. Quando os usuários ligam seus dispositivos, eles recebem uma solicitação para concluir o Assistente de Configuração. Durante a configuração, os usuários receberão uma solicitação por suas credenciais. Eles devem usar as credenciais (ou seja, o nome pessoal exclusivo ou UPN) associadas à assinatura do Intune.

2. Durante a configuração, os usuários receberão uma solicitação por uma ID Apple. Eles precisam fornecer uma ID Apple para permitir que o dispositivo instale o Portal da Empresa. Também podem fornecer a ID pelo menu de ajustes do iOS após a conclusão da instalação.

3. Após a conclusão da configuração, o dispositivo iOS deve instalar o aplicativo Portal da Empresa na App Store.

4. Agora, o usuário pode entrar no Portal da Empresa usando o UPN usado durante a configuração do dispositivo.

5. Após o logon, os usuários recebem uma solicitação para registrar seu dispositivo. A primeira etapa é identificar o dispositivo. O aplicativo apresenta uma lista de dispositivos iOS que já foram registrados pela empresa e atribuídos à conta do Intune do usuário. O usuário deve escolher o dispositivo correspondente. Se o dispositivo ainda não tiver sido registrado pela empresa, eles deverão escolher Novo dispositivo para continuar com o fluxo de registro padrão.

6. Na próxima tela, os usuários deverão confirmar o número de série do novo dispositivo. Os usuários podem tocar no link Confirmar o Número de Série para iniciar o aplicativo de Configurações para verificar o número de série. Os usuários deverão inserir os quatro últimos caracteres do número de série no aplicativo do Portal da Empresa.

    Essa etapa verifica se o dispositivo é o dispositivo corporativo registrado no Intune. Se o número de série no dispositivo não corresponder, o dispositivo incorreto terá sido selecionado. O usuário deve voltar à tela anterior e selecionar um dispositivo diferente.

7. Após a verificação do número de série, o aplicativo Portal da Empresa redirecionará para o site do Portal da Empresa a fim de finalizar o registro. Em seguida, o site solicita que os usuários retornem ao aplicativo.

Agora o registro foi concluído, e os usuários podem usar este dispositivo com o conjunto completo de recursos.

