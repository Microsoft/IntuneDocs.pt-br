---
# required metadata

title: Inicie uma avaliação do Microsoft Intune e implante políticas de PIN iOS | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Inicie uma avaliação do Microsoft Intune e implante políticas de PIN iOS
Estas instruções passo a passo ajudarão você a configurar uma avaliação do Intune e configurar uma política de PIN para dispositivos iOS. Para obter uma lista das outras tarefas de avaliação comuns do Intune que você pode tentar, consulte [Common Microsoft Intune evaluation tasks (Tarefas de avaliação comuns do Microsoft Intune)](common-microsoft-intune-evaluation-tasks.md).



## Examinar os pré-requisitos para essa tarefa

-   Computador Windows com o Internet Explorer - para realizar tarefas administrativas

-   Dispositivo iOS 7.1 ou posterior para testes de validação de políticas do usuário

-   Telefone para autenticar-se durante a inscrição da avaliação

## Criar uma conta de avaliação gratuita do Intune
> [!NOTE]
> Se você já tiver uma assinatura do Intune, ignore esta seção e vá para a próxima seção.

1.  Usando um computador Windows, clique com o botão direito do mouse em **Internet Explorer** (IE) e selecione **Navegação InPrivate**.

    ![Comece a navegação InPrivate](../media/30-day-trial-walkthrus/30day-start-trial-1-InPrivate.png)

2.  Vá para o [Portal Inscrição do Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1), forneça as informações solicitadas e clique em **Avançar**.

    ![Registre-se em uma conta](../media/30-day-trial-walkthrus/30day-start-trial-2-abt-you.png)

3.  Insira uma ID de usuário e senha para sua conta de administrador e clique em **Avançar**. Você usará essa ID para fazer logon no portal do Intune para fazer suas tarefas de administração.

    ![Crie uma ID](../media/30-day-trial-walkthrus/30day-start-trial-3-createID.png)

4.  Insira seu número de telefone celular e clique em **Enviar texto** para validar seu número.

    ![Valide seus detalhes](../media/30-day-trial-walkthrus/30day-start-trial-4-textme.png)

5.  Salve as informações mostradas na tela e, em seguida, clique em **Você está pronto para começar...**..

    ![Pronto para começar](../media/30-day-trial-walkthrus/30day-start-trial-5-ReadyToGo.png)

## Criar um usuário de teste

1.  Usando um computador Windows, clique em **Iniciar** para ir para a página de gerenciamento de usuário.

    ![Vá para a página de gerenciamento de usuário](../media/30-day-trial-walkthrus/30day-crt-user-6-click-start.png)

2.  Clique no botão **+** para adicionar um usuário.

    ![Adicionar um usuário](../media/30-day-trial-walkthrus/30day-crt-user-7-click-plus.png)

3.  Na página **Criar Nova Conta de Usuário**:

    1.  Forneça as informações de usuário de teste.

    2.  Selecione a opção **Digitar Senha**.

    3.  Desmarque a caixa de seleção **Fazer essa pessoa alterar as senhas na próxima vez que entrar**.

    4.  Clique em **Criar**.

    ![Criar uma nova conta de usuário](../media/30-day-trial-walkthrus/30day-crt-user-8-add-user-info.png)

4.  Na página de confirmação de criação de usuário, clique em **Fechar**.

    ![Página de confirmação de criação de usuário](../media/30-day-trial-walkthrus/30day-crt-user-9-close-confirm.png)

5.  Clique no botão **Atualizar** para ver o usuário de teste que você criou.

    ![Confirmação de conta](../media/30-day-trial-walkthrus/30day-crt-user-10-refresh-user.png)

## Configurar uma política de PIN do iOS para o usuário de teste

1.  Usando um computador Windows, defina a autoridade MDM como Intune:

    1.  Vá para [Console de Gerenciamento do Intune](http://manage.microsoft.com/), faça logon com sua conta de administrador e clique em **Começar a Gerenciar Dispositivos Móveis**. A página da autoridade de Gerenciamento de Dispositivo Móvel abre.

        ![Começar a usar o console do Intune](../media/30-day-trial-walkthrus/30day-cfg-pol-11-start-mg-mobl-dev.png)

    2.  Clique no link **Definir Autoridade de Gerenciamento de Dispositivo Móvel**.

        ![Defina a autoridade de gerenciamento de dispositivo móvel](../media/30-day-trial-walkthrus/30day-cfg-pol-12-link-set-mdm.png)

2.  Habilitar o registro de dispositivo iOS. Esse processo configura um certificado confiável entre os APNs (Apple Push Notification Service) e sua assinatura do Intune.

    1.  Clique em **Habilitar Plataforma iOS e Mac OS X**.

        ![Habilite o registro em iOS e Mac OS X](../media/30-day-trial-walkthrus/30day-cfg-pol-13-enbl-ios-plat.png)

    2.  Clique em **Baixar a Solicitação de Certificado APNs**.

        ![Baixe o certificado APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-14-dwnld-cert-reqst.png)

    3.  Especifique um nome de arquivo e um local para o CSR (Solicitação de Assinatura de Certificado) e, em seguida, clique em **Salvar**. Esse arquivo contém a chave pública que corresponde a uma chave privada mantida por sua assinatura do Intune.

        ![Especifique uma solicitação de assinatura de certificado](../media/30-day-trial-walkthrus/30day-cfg-pol-15-cert-name-loc.png)

    4.  Clique em **portal Apple Push Certificates** para abrir uma nova guia.

        ![Vá para a página de certificados APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-16-cert-portl-link.png)

    5.  Digite sua ID Apple de usuário e a senha e clique em **Entrar**. Essa ID pode ser aquela que você usa em seu dispositivo iOS para obter aplicativos da iOS App Store.

        ![Entre no Portal Certificados por Push da Apple](../media/30-day-trial-walkthrus/30day-cfg-pol-17-id-passw-signin.png)

    6.  Clique em **Criar um Certificado**.

        ![Crie um certificado APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-18-create-cert.png)

    7.  Leia os Termos de Uso da Apple, marque a caixa de seleção e clique em **Aceitar**.

        ![Aceite os termos](../media/30-day-trial-walkthrus/30day-cfg-pol-19-TOU.png)

    8.  Clique em **Procurar**.

        ![Navegue até o local em que você salvou o certificado](../media/30-day-trial-walkthrus/30day-cfg-pol-20-browse.png)

    9. Selecione o arquivo CSR que você salvou anteriormente e clique em **Abrir**.

        ![Abra o certificado](../media/30-day-trial-walkthrus/30day-cfg-pol-21-CSRfile-open.png)

    10. Clique no botão **Carregar**.

        ![Carregue o certificado](../media/30-day-trial-walkthrus/30day-cfg-pol-22-upld-reqst.png)

    11. Quando for solicitado a baixar um arquivo JSON, clique em **Salvar como**.

        ![Salve o arquivo JSON](../media/30-day-trial-walkthrus/30day-cfg-pol-23-json-saveas.png)

    12. Especifique um local para o arquivo JSON e clique em **Salvar**.

        ![Especifique onde o arquivo JSON deve ser salvo](../media/30-day-trial-walkthrus/30day-cfg-pol-24-json-save-loc.png)

        Se sua página não for redirecionada automaticamente depois de alguns segundos, clique em **Cancelar**.

        ![Cancele se a página não for redirecionada](../media/30-day-trial-walkthrus/30day-cfg-pol-25-json-pg-cancel.png)

    13. Para recuperar o arquivo de certificado recém-criado, clique em **Baixar**.

        ![Baixe o certificado](../media/30-day-trial-walkthrus/30day-cfg-pol-26-dwnld-retrv-cert.png)

    14. Quando for solicitado a baixar um arquivo PEM, clique em **Salvar como**.

        ![Baixe o arquivo PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-27-pem-saveas.png)

    15. Especifique um local para o arquivo PEM e clique em **Salvar**.

        ![Salve o arquivo PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-28-pem-save-loc.png)

    16. Volte para a guia Console de Gerenciamento do Intune e, em seguida, clique em **Carregar Certificado APNs**.

        ![Carregue o certificado APNs](../media/30-day-trial-walkthrus/30day-cfg-pol-29-upld-cert.png)

    17. Insira sua ID da Apple e clique em **Procurar**.

        ![Insira sua ID da Apple](../media/30-day-trial-walkthrus/30day-cfg-pol-30-app-id-browse.png)

    18. Selecione o arquivo PEM que acabou salvo e clique em **Abrir**.

        ![Abra o arquivo PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-31-sel-pem-open.png)

    19. Clique em **Carregar**.

        ![Carregue o arquivo PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-32-pem-upload.png)

        Seu certificado APNs agora está configurado.

        ![Configuração de certificado APNs concluída](../media/30-day-trial-walkthrus/30day-cfg-pol-33-apns-confgd.png)

3.  Crie um grupo de usuário de teste para o direcionamento de política:

    1.  No painel esquerdo, clique em **Grupos**.

        ![Abra os Grupos](../media/30-day-trial-walkthrus/30day-cfg-pol-34-clk-groups.png)

    2.  Na extremidade direita, clique em **Criar Grupo**.

        ![Criar um grupo](../media/30-day-trial-walkthrus/30day-cfg-pol-35-crt-group.png)

    3.  Forneça um nome de grupo, selecione **Todos os Usuários** como o grupo pai e clique **Avançar**.

        ![Selecione Todos os Usuários como o grupo pai](../media/30-day-trial-walkthrus/30day-cfg-pol-36-name-group.png)

    4.  No campo **Iniciar Associação de Grupo com**, selecione **Todos os Usuários no Grupo Pai**, e clique em **Concluir**.

        ![Inicie a associação de grupo com o grupo pai](../media/30-day-trial-walkthrus/30day-cfg-pol-37-all-users-group.png)

4.  Crie uma política PIN do iOS e direcione-a ao grupo de usuários de teste:

    1.  No painel esquerdo, clique em **Política**.

        ![Abra o espaço de trabalho de política](../media/30-day-trial-walkthrus/30day-cfg-pol-38-clk-policy.png)

    2.  Na extremidade direita, clique em **Adicionar Política**.

        ![Adicione uma política](../media/30-day-trial-walkthrus/30day-cfg-pol-39-add-policy.png)

    3.  Expanda o nó do iOS, selecione a linha **Configuração Geral** e, em seguida, clique em **Criar Política**.

        ![Criar uma política de configuração geral do iOS](../media/30-day-trial-walkthrus/30day-cfg-pol-40-gen_cfg_pol.png)

    4.  Digite um nome para a política, ative a opção **Requer uma Senha para Desbloquear Dispositivos Móveis**, e defina o **Tamanho Mínimo da Senha** para **4**.

        ![Defina configurações de senha](../media/30-day-trial-walkthrus/30day-cfg-pol-41-name-policy.png)

    5.  Para implantar a política, clique em **Sim**.

        ![Implante a política](../media/30-day-trial-walkthrus/30day-cfg-pol-42-yes-deploy-pol.png)

    6.  Clique no grupo de usuário criado anteriormente, clique em **Adicionar**, e clique em **OK**.

        ![Selecione o grupo para a política](../media/30-day-trial-walkthrus/30day-cfg-pol-43-add-pol-to-grp.png)

        Agora você tem uma política PIN do iOS direcionada ao seu grupo de usuários de teste.

        ![Instalação da política concluída](../media/30-day-trial-walkthrus/30day-cfg-pol-44-policy-applied.png)

## Validar se a política é aplicada em um dispositivo iOS

1.  Em um iPad, inicie a iOS App Store, instale a versão gratuita do aplicativo **Portal da Empresa do Microsoft Intune** e abra-o.

    ![Instalar o portal da empresa](../media/30-day-trial-walkthrus/30day-cfg-pol-45-cportal-installed.png)

2.  Digite seu nome de conta de usuário de teste e a senha e, em seguida, toque em **Entrar**.

    ![Forneça as suas credenciais](../media/30-day-trial-walkthrus/30day-cfg-pol-46-cportal-signin.png)

3.  Toque em **Registrar** para iniciar o registro do dispositivo no Intune.

    ![Inicie o registro](../media/30-day-trial-walkthrus/30day-cfg-pol-47-tap-enroll.jpg)

4.  Na tela **Instalar Perfil**, toque em **Instalar**.

    ![Instale um perfil](../media/30-day-trial-walkthrus/30day-cfg-pol-48-profile-install-1.jpg)

5.  No diálogo **Instalar Perfil**, toque em **Instalar**.

    ![Continue com a instalação do perfil](../media/30-day-trial-walkthrus/30day-cfg-pol-49-profile-install-2.jpg)

6.  Na tela **Aviso**, toque em **Instalar**.

    ![Aceita a mensagem de aviso](../media/30-day-trial-walkthrus/30day-cfg-pol-50-warning-install-3.png)

7.  No diálogo **Gerenciamento Remoto**, toque **Confiar**.

    ![Confie no gerenciamento remoto](../media/30-day-trial-walkthrus/30day-cfg-pol-51-remt-mgmt-trust.jpg)

8.  Quando o perfil de gerenciamento concluir a instalação, toque em **Concluído**. O registro agora está concluído.

    ![Registro completo](../media/30-day-trial-walkthrus/30day-cfg-pol-52-profile-done.jpg)

9. Quando o registro for concluído, toque em **OK** e, em seguida, feche o aplicativo Portal da Empresa.

    ![Toque em OK para fechar o aplicativo de Portal da Empresa](../media/30-day-trial-walkthrus/30day-cfg-pol-53-devc-enrolled-ok.png)

10. Quando for solicitada a configuração de uma senha, toque em **Continuar**.

    ![Aceite a solicitação para configurar a senha](../media/30-day-trial-walkthrus/30day-cfg-pol-54-passcode-req-cont.png)

11. Inserir sua senha, toque em **Continuar**, insira sua senha novamente e toque **Salvar**.

    ![Forneça uma senha](../media/30-day-trial-walkthrus/30day-cfg-pol-55-passcode-enter.jpg)

12. Pressione o botão Ligar/Desligar para bloquear seu iPad, deslize para desbloqueá-lo e você verá que será preciso inserir sua senha para desbloquear o dispositivo.

### Consulte também
[Guia de avaliação do Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md)


<!--HONumber=May16_HO1-->


