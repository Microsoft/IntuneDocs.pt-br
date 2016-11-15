---
title: "Registrar dispositivos iOS com o Assistente de Configuração | Microsoft Intune"
description: "Registre dispositivos iOS corporativos usando a ferramenta Apple Configurator para redefinir o dispositivo para as configurações de fábrica e prepará-lo para executar o Assistente de Configuração."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: bb94cb21bce5fb25c821b6a01d952ccba2f94834


---

# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a>Registrar dispositivos iOS com o Apple Configurator usando o Assistente de Configuração
O Intune dá suporte ao registro de dispositivos iOS corporativos usando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) em execução em um computador Mac. Esse processo redefine o dispositivo para as configurações de fábrica e o prepara para executar o Assistente de Configuração instalando as políticas da empresa para o novo usuário do dispositivo.

## <a name="setup-assistant-enrollment-for-ios-devices-with-microsoft-intune"></a>Registro do Assistente de Configuração para dispositivos iOS com o Microsoft Intune
Usando o Apple Configurator, você pode redefinir um dispositivo iOS para as configurações de fábrica e prepará-lo para ser configurado para o novo usuário do dispositivo. Esse método requer que você conecte o dispositivo iOS a um computador Mac via USB para configurar o registro corporativo e supõe que você esteja usando o Apple Configurator 2.0. A maioria dos cenários exige que a política aplicada ao dispositivo iOS inclua **afinidade do usuário** para habilitar o aplicativo Portal da Empresa do Intune.

**Pré-requisitos**
* [Registro do iOS habilitado](set-up-ios-and-mac-management-with-microsoft-intune.md) instalando um certificado de APNs
* Acesso físico a dispositivos iOS&mdash;os dispositivos devem ser redefinidos para as configurações de fábrica sem proteção de senha
* Números de série do dispositivo&mdash;consulte [Como obter um número de série do iOS](https://support.apple.com/en-us/HT204308)
* Cabos de conexão USB
* Um computador Mac com o [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


1.  **Criar grupos de dispositivos móveis** (opcional).
    Se sua empresa exige grupos de dispositivos móveis para ajudar a gerenciar dispositivos, crie esses grupos. Para saber mais, consulte [Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

2.  **Criar um perfil para dispositivos**.
    Um perfil de registro de dispositivos define as configurações aplicadas a um grupo de dispositivos. As etapas a seguir mostram como criar um perfil de registro de dispositivo para dispositivos iOS registrados usando o Apple Configurator.

    1.  No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Política** &gt; **Registro do Dispositivo Corporativo** e selecione **Adicionar**.
    ![Criar perfil de registro do dispositivo](../media/pol-sa-corp-enroll.png)

    2.  Insira os detalhes para os perfis de dispositivo:

        -   **Nome**&mdash;O nome do perfil de registro do dispositivo (não é visível para os usuários).

        -   **Descrição**&mdash;Uma descrição do perfil de registro do dispositivo (não é visível para os usuários).

        -   **Detalhes de Registro**&mdash;Especifica como os dispositivos são registrados.

            -   **Solicitar afinidade do usuário**&mdash;O dispositivo deve ser afiliado a um usuário durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa. A **afinidade do usuário** deve ser configurada para dispositivos gerenciados por DEP que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos.

            -   **Sem afinidade do usuário**&mdash;O dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.

        -   **Pré-atribuição de grupo de dispositivos**&mdash;Todos os dispositivos implantados nesse perfil pertencerão inicialmente a esse grupo. Você pode reatribuir dispositivos após o registro.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

        -  **Programa de Registro de Dispositivo**&mdash;O DEP (Programa de Registro de Dispositivo) da Apple não pode ser usado com o registro do Assistente de Configuração. Verifique se a alternância está definida como **desligado**.

    3.  Clique em **Salvar Perfil** para adicionar o perfil.

3.  **Adicionar dispositivos iOS para registro com o Assistente de Configuração**.
    No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os dispositivos de propriedade corporativa** &gt; **Todos os Dispositivos** e escolha **Adicionar dispositivos**. Você pode adicionar dispositivos de duas maneiras:

    ![Caixa de diálogo Adicionar dispositivos](../media/pol-SA-enroll-iOS-SetupAssistant.png)

    -   **Carregar um arquivo CSV contendo números de série**&mdash;Crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, com limite de 5.000 dispositivos ou 5 MB por arquivo csv.

        |||
        |-|-|
        |&lt;Nº de série 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
        |&lt;Nº de série 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|
        Quando visualizado em um editor de texto, esse arquivo .csv aparece como:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Adicionar manualmente os detalhes do dispositivo**&mdash;Insira o número de série e os detalhes de até cinco dispositivos.

    > [!NOTE]
    > Se, posteriormente, você precisar remover dispositivos corporativos do gerenciamento do Intune, será necessário remover o número de série do dispositivo do Intune no grupo **Por número de série do iOS** em **Dispositivos corporativos pré-registrados** para desabilitar o registro do dispositivo. Se o Intune executar um procedimento de recuperação de desastres quando ou próximo à época em que você remover os números de série, você precisará confirmar que apenas os números de série de dispositivos ativos estão presentes nesse grupo.

    Escolha **Avançar**.

4.  **Selecionar dispositivos para registrar**.
    Confirme os dispositivos a serem registrados. Não é possível importar os números de série já registrados ou registrados por outros meios. Escolha **Avançar** para continuar.

5.  **Atribuir perfil**.
    Especifique o perfil para atribuir a dispositivos adicionados na lista de perfis disponíveis, examine os **Detalhes do perfil de registro**e escolha **Concluir**. Dispositivos adicionados manualmente podem ser atribuídos a qualquer perfil de registro.

6.  **Exportar um perfil para ser implantado em dispositivos iOS**.
    No [Console de administração do Microsoft Intune](http://manage.microsoft.com), vá até **Política** &gt; **Registro de Dispositivo Corporativo** e selecione o perfil a ser implantado nos dispositivos móveis. Escolha **Exportar** na barra de tarefas. Copie e salve a **URL do perfil**. Você fará o upload no Apple Configurator posteriormente para definir o perfil do Intune utilizado pelos dispositivos iOS.
    Para dar suporte ao Apple Configurator 2, a URL do Perfil 2.0 deve ser editada. Para fazer isso, substitua este código:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Por este código:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Você carregará essa URL do perfil para o serviço Apple DEP usando o Apple Configurator no procedimento a seguir para definir o perfil do Intune utilizado pelos dispositivos iOS.



7.  **Preparar o dispositivo com o Apple Configurator**.
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

8.  **Distribuir dispositivos**.
    Os dispositivos agora estão prontos para registro corporativo. Desligue os dispositivos e distribua-os para os usuários. Quando os usuários ligarem seus dispositivos, o Assistente de Configuração será iniciado.



### <a name="see-also"></a>Consulte também
[Pré-requisitos para registrar dispositivos](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO1-->


