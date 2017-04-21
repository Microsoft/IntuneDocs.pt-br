---
title: "Registrar dispositivos iOS com o Assistente de Configuração | Microsoft Docs"
description: "Registre dispositivos iOS corporativos usando a ferramenta Apple Configurator para redefinir o dispositivo para as configurações de fábrica e prepará-lo para executar o Assistente de Configuração."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 2a1a9bb4e49e997a6f152cadcf0c7a75b553cb42
ms.lasthandoff: 04/14/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a>Registrar dispositivos iOS com o Apple Configurator usando o Assistente de Configuração

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune dá suporte ao registro de dispositivos iOS corporativos usando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) em execução em um computador Mac. Esse processo redefine o dispositivo para as configurações de fábrica e o prepara para executar o Assistente de Configuração instalando as políticas da empresa para o novo usuário do dispositivo.

>[!NOTE]
>Esse método de registro não pode ser usado com o método de [gerenciador de registro de dispositivos](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

Usando o Apple Configurator, você pode redefinir um dispositivo iOS para as configurações de fábrica e prepará-lo para ser configurado para o novo usuário do dispositivo. Esse método requer que você conecte o dispositivo iOS a um computador Mac via USB para configurar o registro corporativo e supõe que você esteja usando o Apple Configurator 2.0. A maioria dos cenários exige que a política aplicada ao dispositivo iOS inclua **afinidade do usuário** para habilitar o aplicativo Portal da Empresa do Intune.

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-configurator-with-setup-assistant"></a>Pré-requisitos para registro de dispositivos iOS usando o Apple Configurator com o Assistente de Configuração

- [Instalar um certificado APNs](set-up-ios-and-mac-management-with-microsoft-intune.md)

- Certifique-se de que você tem acesso físico a dispositivos iOS&mdash;os dispositivos devem ser redefinidos para as configurações de fábrica, sem proteção de senha

- Obter números de série do dispositivo, &mdash;consulte [Como obter um número de série do iOS](https://support.apple.com/HT204308)

- Ter em mãos os cabos de conexão USB

- Ter um computador Mac com o [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


## <a name="steps-to-enroll-ios-devices-by-using-apple-configurator-with-setup-assistant"></a>Etapas para registro de dispositivos iOS usando o Apple Configurator com o Assistente de Configuração

As etapas a seguir explicam como registrar dispositivos iOS no "dia 0" usando o Apple Configurator com o Assistente de Configuração. Conforme os dispositivos forem adicionados e removidos da sua organização, você provavelmente repetirá algumas dessas etapas como adicionar ou remover números de série, conforme descrito abaixo.

### <a name="create-mobile-device-groups-optional"></a>Criar grupos de dispositivos móveis (opcional)

Se sua empresa exige grupos de dispositivos móveis para ajudar a gerenciar dispositivos, você pode opcionalmente criar esses grupos. Para saber mais, consulte [Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### <a name="create-a-profile-for-devices"></a>Criar um perfil para dispositivos

Um perfil de registro de dispositivos define as configurações aplicadas a um grupo de dispositivos.

1. No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Política** &gt; **Registro do Dispositivo Corporativo** e selecione **Adicionar**.

  ![Criar perfil de registro do dispositivo](../media/pol-sa-corp-enroll.png)

2. Insira os detalhes para os perfis de dispositivo:

   -   **Nome**&mdash;O nome do perfil de registro do dispositivo (não é visível para os usuários).

   -   **Descrição**&mdash;Uma descrição do perfil de registro do dispositivo (não é visível para os usuários).

   -   **Detalhes de Registro**&mdash;Especifica como os dispositivos são registrados.

       -   **Solicitar afinidade do usuário**&mdash;O dispositivo deve ser afiliado a um usuário durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa. A **afinidade do usuário** deve ser configurada para dispositivos gerenciados por DEP que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos.

       -   **Sem afinidade do usuário**&mdash;O dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.

   -   **Pré-atribuição de grupo de dispositivos**&mdash;Todos os dispositivos implantados nesse perfil pertencerão inicialmente a esse grupo. Você pode reatribuir dispositivos após o registro.

   > [!Important]
   > As atribuições de grupo serão movidas do Intune para o Azure Active Directory. Depois que sua conta do Intune receber a atualização aplicável, você não verá a opção **Atribuir dispositivos ao grupo a seguir**. [Saiba mais](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).

   -  **Programa de Registro de Dispositivo**&mdash;O DEP (Programa de Registro de Dispositivo) da Apple não pode ser usado com o registro do Assistente de Configuração. Verifique se a alternância está definida como **desligado**.

3.  Clique em **Salvar Perfil** para adicionar o perfil.

### <a name="add-ios-devices-to-enroll-with-setup-assistant"></a>Adicionar dispositivos iOS para registro com o Assistente de Configuração

1. No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os dispositivos de propriedade corporativa** &gt; **Todos os Dispositivos** e escolha **Adicionar dispositivos**.

   Você pode adicionar dispositivos de duas maneiras:

   ![Caixa de diálogo Adicionar dispositivos](../media/pol-SA-enroll-iOS-SetupAssistant.png)

   -  **Carregar um arquivo CSV contendo números de série**&mdash;Crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, com limite de 5.000 dispositivos ou 5 MB por arquivo csv.

    |||
    |-|-|
    |&lt;Nº de série 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
    |&lt;Nº de série 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|

  Quando visualizado em um editor de texto, esse arquivo .csv aparece como:

    ```
    0000000,PO 1234
    111111111,PO 1234
    ```

  -  **Adicionar manualmente os detalhes do dispositivo**&mdash;Insira o número de série e quaisquer observações ou detalhes de até 15 dispositivos.

  No painel **Examinar Dispositivos**, você pode confirmar os números de série. Você também pode decidir se deseja substituir os **Detalhes** para números de série que estão sendo importados novamente ou você pode desmarcar a caixa **Substituir** para preservar os detalhes atuais.

> [!NOTE]
> No console do administrador do Intune existente, os administradores podem aceitar detalhes associados de um CSV carregado e substituir os detalhes existentes para números de série individuais. No novo Portal do Azure, você só poderá substituir os detalhes de todos os números de série ou ignorar os novos detalhes para todos os números de série.

> [!NOTE]
> Se, posteriormente, você desejar remover dispositivos corporativos do gerenciamento do Intune, será necessário ir até **Por número de série do iOS** em **Dispositivos corporativos pré-registrados** e remover o número de série do dispositivo do Intune para desabilitar o registro do dispositivo. Se o Intune executar um procedimento de recuperação de desastre quando ou próximo à época em que você remover os números de série, você precisará confirmar que apenas os números de série de dispositivos ativos estão presentes nesse grupo.

2. Escolha **Avançar**.

3. Selecione os dispositivos a serem registrados. Não é possível importar os números de série já registrados ou registrados por outros meios. Escolha **Avançar** para continuar.

### <a name="assign-a-profile"></a>Atribuir um perfil

Especifique o perfil para atribuir a dispositivos adicionados na lista de perfis disponíveis, examine os **Detalhes do perfil de registro**e escolha **Concluir**. Dispositivos adicionados manualmente podem ser atribuídos a qualquer perfil de registro.

> [!Important]
> Atualmente, o Intune permite designar um perfil de registro do dispositivo "padrão", o que significa que novos números de série são automaticamente atribuídos a esse perfil padrão quando você sincroniza os novos números de série com o serviço de DEP da Apple. Quando seu locatário for migrado para o novo portal do Azure em um futuro próximo, você não poderá definir um perfil padrão e ter números de série atribuídos automaticamente a esse perfil. Em vez disso, você precisará atribuir números de série a um perfil. [Saiba mais](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-ios-devices-using-device-enrollment-program)

### <a name="export-a-profile-to-deploy-to-ios-devices"></a>Exportar um perfil para ser implantado em dispositivos iOS

1. No [Console de administração do Microsoft Intune](http://manage.microsoft.com), vá até **Política** &gt; **Registro de Dispositivo Corporativo** e selecione o perfil a ser implantado nos dispositivos móveis.

2. Escolha **Exportar** na barra de tarefas. Copie e salve a **URL do perfil**. Você fará o upload no Apple Configurator posteriormente para definir o perfil do Intune utilizado pelos dispositivos iOS.

  Para dar suporte ao Apple Configurator 2, a URL do Perfil 2.0 deve ser editada. Para fazer isso, substitua este código:

  ```
  https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
  ```
  Por este código:

  ```
  https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
  ```

   Você carregará essa URL do perfil para o serviço Apple DEP usando o Apple Configurator no procedimento a seguir para definir o perfil do Intune utilizado pelos dispositivos iOS.

### <a name="prepare-the-device-with-apple-configurator"></a>Preparar o dispositivo com o Apple Configurator

Dispositivos iOS são conectados ao computador Mac e registrados para o gerenciamento de dispositivo móvel.

1.  Em um computador Mac, abra o **Apple Configurator 2**. Na barra de menus, selecione **Apple Configurator 2** e clique em **Preferências**.

   > [!WARNING]
   > Os dispositivos serão redefinidos para as configurações de fábrica durante o processo de registro. Como melhor prática, redefina o dispositivo e ligue-o. Os dispositivos devem estar na tela **Olá** quando você conectar o dispositivo.

2. No painel de preferências, selecione **Servidores** e escolha o símbolo de mais (+) para inicializar o assistente do Servidor MDM. Escolha **Avançar**.

3. Insira o **Nome** e a **URL do Registro** para o servidor MDM da etapa 6 em Registro do Assistente de Configuração para dispositivos iOS com o Microsoft Intune. Para URL de Registro, insira a URL do perfil de registro exportada do Intune. Escolha **Avançar**.  

   Você pode desconsiderar com segurança um aviso indicando "URL do servidor não verificada". Para continuar, clique em **Avançar** até que o assistente seja concluído.

4.  Conecte os dispositivos móveis iOS ao computador Mac com um adaptador USB.

    > [!WARNING]
    > Os dispositivos serão redefinidos para as configurações de fábrica durante o processo de registro. Como melhor prática, redefina o dispositivo e ligue-o. Os dispositivos devem estar na tela **Olá** quando você iniciar o Assistente de Configuração.

5.  Selecione **Preparar**. No painel Preparar o Dispositivo iOS, selecione **Manual** e escolha **Avançar**.

6. No painel Registrar no Servidor MDM, selecione o nome do servidor que você criou e escolha **Avançar**.

7. No painel Supervisionar Dispositivos, selecione o nível de supervisão e escolha **Avançar**.

8. No painel Criar uma Organização, escolha **Organização** ou crie uma nova organização e escolha **Avançar**.

9. No painel Configurar o Assistente de Instalação do iOS, escolha as etapas que serão apresentadas ao usuário e escolha **Preparar**. Se solicitado, autentique para atualizar as configurações de confiança.  

10. Quando o dispositivo iOS concluir a preparação, desconecte o cabo USB.  

### <a name="distribute-devices"></a>Distribuir dispositivos

Os dispositivos agora estão prontos para registro corporativo. Desligue os dispositivos e distribua-os para os usuários. Quando os usuários ligarem seus dispositivos, o Assistente de Configuração será iniciado.

>[!NOTE]
>Se uma usuária tentar registrar um dispositivo DEP, mas tiver ultrapassado seu limite de dispositivos, o registro falhará silenciosamente sem avisar o usuário.


### <a name="see-also"></a>Consulte também
[Pré-requisitos para registrar dispositivos](prerequisites-for-enrollment.md)

