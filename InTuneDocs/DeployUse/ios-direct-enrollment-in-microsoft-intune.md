---
# required metadata

title: Registro direto para dispositivos iOS com o Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos iOS diretamente usando o Apple Configurator
O Intune dá suporte ao registro de dispositivos iOS corporativos usando a ferramenta [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) em execução em um computador Mac. Esse processo não redefine de fábrica o dispositivo e registra o dispositivo com uma política predefinida. Esse método é para dispositivos **Sem afinidade de usuário** e requer que você conecte por USB o dispositivo iOS a um computador Mac para configurar o registro corporativo. Não há suporte para o aplicativo Portal da empresa em dispositivos com registro direto. Esta diretriz presume que você está usando o Apple Configurator 2.0 em um computador Mac.

1.  **Criar um perfil para dispositivos**
    Um perfil de registro do dispositivo define as configurações aplicadas a dispositivos. Se você ainda não tiver, crie um perfil de registro para dispositivos iOS registrados usando o Apple Configurator.

    #### Para criar um perfil

    1.  No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Política** &gt; **Registro do Dispositivo Corporativo** e, em seguida, clique em **Adicionar...**.

        ![Criar página de perfil de registro do dispositivo](../media/pol-sa-corp-enroll.png)

    2.  Insira os detalhes para os perfis de dispositivo:

        -   **Nome** – Nome do perfil de registro do dispositivo. Não é visível para os usuários.

        -   **Descrição** - descrição do perfil de registro do dispositivo. Não é visível para os usuários.

        -   **Afiliação do usuário** – Especifica como os dispositivos são registrados. Para o Registro Direto, selecione **Sem afinidade de usuário**.

        -   **Pré-atribuição de grupo de dispositivos** – todos os dispositivos implantados nesse perfil pertencerão inicialmente a esse grupo. Você pode reatribuir dispositivos após o registro.

    3.  Clique em **Salvar perfil** para adicionar o perfil.

2.  **Adicionar dispositivos iOS para registro com o Apple Configurator**
    No [Console de Administração do Microsoft Intune](http://manage.microsoft.com), acesse **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos Pré-registrados** &gt; **Por Número de Série do iOS** e clique em **Adicionar Dispositivos…**.

    ![Assistente de configuração do iOS](../media/pol-SA-enroll-iOS-SetupAssistant.png)

      Você pode adicionar dispositivos de duas maneiras:

    -   **Carregar um arquivo CSV contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, com limite de 5000 dispositivos ou 5 MB por arquivo csv.

        |||
        |-|-|
        |&lt;Nº de série 1&gt;|&lt;Detalhes do dispositivo nº 1&gt;|
        |&lt;Nº de série 2&gt;|&lt;Detalhes do dispositivo nº 2&gt;|
        Quando visualizado em um editor de texto, esse arquivo .csv aparece como:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Adicione manualmente os detalhes do dispositivo** - insira o número de série e detalhes de até cinco dispositivos e clique em **Avançar**.

    > [!NOTE]
    > Se, posteriormente, você precisar remover dispositivos da empresa do gerenciamento do Intune, será necessário remover o número de série do dispositivo do Intune no grupo de **Dispositivos da empresa** para desabilitar o registro do dispositivo.  Se o Intune executar um procedimento de recuperação de desastres quando ou próximo à época em que os números de série foram removidos, você precisará confirmar que apenas números de série de dispositivos ativos estão presentes nesse grupo.

3.  **Selecionar dispositivos para registrar**
    Confirme os dispositivos a serem registrados. Não é possível importar os números de série já registrados ou registrados por outros meios. Clique em **Próximo** para continuar.

4.  **Atribuir perfil**
    Especifique o perfil para atribuir a dispositivos adicionados na lista de perfis disponíveis, examine os **Detalhes do perfil de registro**e, em seguida, clique em **Concluir**. Dispositivos adicionados manualmente podem ser atribuídos a qualquer perfil de registro.

5.  **Selecionar um perfil para ser implantado a dispositivos iOS**
    No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Política** &gt; **Registro de Dispositivo Corporativo** e, em seguida selecione o perfil a ser implantado aos dispositivos móveis. Esse perfil deve ser o mesmo perfil que você atribuiu para implantar na etapa anterior. Clique em **Exportar…** na barra de tarefas. Clique em **Baixar Perfil** e salve o arquivo .mobileconfig baixado.

6.  **Transfira o arquivo**
    Copie o arquivo .mobileconfig baixado para um computador Mac.
    > [!NOTE]
    > A URL do perfil de registro é válida por duas semanas a partir de quando for exportada. Depois de duas semanas, você deve exportar uma nova URL de perfil de registro para registrar dispositivos iOS com o Assistente de Configuração.
7.  **Preparar o dispositivo com o Apple Configurator**
    Dispositivos iOS são conectados ao computador Mac e registrados para o gerenciamento de dispositivo móvel.

    1.  Em um computador Mac, inicie o **Apple Configurator 2.0**.

    2.  Conecte o dispositivo iOS ao computador Mac com um cabo USB. Feche as **Fotos**, **iTunes**, e outros aplicativos que são abertos com o dispositivo quando ele é detectado.

    3.  No Apple Configurator, clique uma vez no dispositivo iOS conectado e, em seguida, clique no botão **Adicionar**. As opções que podem ser adicionadas ao dispositivo aparecem na lista suspensa. Clique em **Perfis** .

    4.  Use o seletor de arquivos para selecionar o arquivo .mobileconfig exportado do Intune e, em seguida, clique em **Adicionar**. O perfil é adicionado ao dispositivo.  Se o dispositivo for **Sem supervisão**, a instalação necessitará da aceitação no dispositivo.

8.  **Instalar o perfil**
    Você está pronto para instalar o perfil no dispositivo iOS. O dispositivo já deve ter concluído o Assistente de Configuração e está pronto para uso.  Se o registro envolve as implantações de aplicativo, o dispositivo deve ter uma ID Apple configurada, pois as implantações de aplicativo exigirão que você tenha uma ID Apple conectada na Windows Store.

    ###### Concluindo a aceitação de perfil para dispositivos iOS sem supervisão

    1.  Desbloquear o dispositivo iOS.

    2.  Na caixa de diálogo **Instalar Perfil** para **Perfil de Gerenciamento**, toque em **Instalar**.

    3.  Forneça a **Senha do Dispositivo** ou **ID Apple**, se necessário.

    4.  Aceite o **Aviso** e toque em **Instalar**.

    5.  Aceite o **Aviso Remoto** e toque em **Confiar**.

    6.  Quando a caixa **Perfil Instalado** confirmar que o perfil foi **instalado**, clique em **Concluído**.

9. **Verificar perfil**
    No dispositivo iOS, inicie **Configurações** e vá para **Geral** &gt; **Gerenciamento de Dispositivo** &gt; **Perfil de Gerenciamento** &gt; e confirme se a instalação do perfil está listada, verifique as restrições de política de iOS e os aplicativos instalados. Aplicativos e restrições de política podem levar até 10 minutos para serem exibidos no dispositivo.

10. **Distribuir dispositivos**
    O dispositivo iOS agora está registrado com o Intune e é gerenciado.


### Consulte também
[Prepare-se para registrar dispositivos](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


