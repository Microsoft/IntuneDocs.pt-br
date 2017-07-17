---
title: "Registrar dispositivos iOS – Programa de registro de dispositivos"
titleSuffix: Intune on Azure
description: Saiba como registrar dispositivos iOS de propriedade corporativa usando o Programa de registro de dispositivos.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f509f5332b2f8b5f6745816f8795a9a54c10ce2d
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Configurar o registro de dispositivo iOS com o Programa de registro de dispositivos
<a id="set-up-ios-device-enrollment-with-device-enrollment-program" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico ajuda os administradores de TI a habilitar o registro de dispositivos iOS comprados por meio do [DEP (Programa de registro de dispositivos)](https://deploy.apple.com) da Apple. O Microsoft Intune pode implantar um perfil de registro “sem fio” em dispositivos iOS comprados por meio do DEP. O administrador nunca precisa tocar em nenhum dispositivo gerenciado. Um perfil de DEP contém as configurações de gerenciamento que são aplicadas aos dispositivos durante o registro, incluindo opções do Assistente de Configuração.

Para habilitar o registro de DEP, você pode usar ambos os portais do Intune e do Apple DEP. Uma lista ou um número de pedido de compra dos seus dispositivos DEP também é necessário para poder atribuí-los ao Intune para gerenciamento no Portal da Apple.

>[!NOTE]
>O registro DEP não pode ser usado com o [gerenciador de registro de dispositivos](device-enrollment-manager-enroll.md).

**Etapas para habilitar programas de registro da Apple**
1. [Obter um token Apple DEP e atribuir dispositivos](#get-the-apple-dep-certificate)
2. [Criar um perfil de registro](#create-anapple-enrollment-profile)
3. [Sincronize dispositivos gerenciados por DEP](#sync-dep-managed-devices)
4. [Atribuir o perfil DEP a dispositivos](#assign-a-dep-profile-to-devices)
5. [Distribuir dispositivos para usuários](#distribute-devices-to-users)

## Obter o token Apple DEP
<a id="get-the-apple-dep-token" class="xliff"></a>

Antes de poder registrar dispositivos iOS de propriedade corporativa com o DEP (Programa de registro de dispositivos) da Apple, você precisa de um token DEP (.p7m) da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos de sua empresa que fazem parte do DEP. Ele também permite que o Intune realize carregamentos de perfis de registro para a Apple e atribua dispositivos a esses perfis.

> [!NOTE]
> Se seu locatário Intune migrou do console clássico do Intune para o portal do Azure e você excluiu um token de DEP da Apple no console de administração do Intune durante o período de migração, o token de DEP pode ter sido restaurado para sua conta do Intune. Você pode excluir o token de DEP novamente no portal do Azure.

**Pré-requisitos**
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Inscrição no [Programa de registro de dispositivos da Apple](http://deploy.apple.com)

**Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token de DEP da Apple.**<br>
1. No Portal do Intune, escolha **Registro de dispositivo** e, em seguida, **Registro da Apple** e **Token do Programa de Registro**.
![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple.](./media/enrollment-program-token-add.png)
2. Selecione **Baixar sua chave pública** para baixar e salvar a chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.
![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/enrollment-program-token-download.png)

**Etapa 2. Criar e baixar um token Apple DEP.**<br>
Selecione **Criar um token por meio do Programa de registro de dispositivos da Apple** para abrir o Portal do Programa de Implantação da Apple e entrar com sua ID da Apple da empresa. Você pode usar essa ID da Apple para renovar seu token de DEP.
  ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple.](./media/enrollment-program-token-create.png)

  ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/enrollment-program-token-sign.png)
   1.  No [portal de Programas de Implantação](https://deploy.apple.com) da Apple, selecione **Começar** para **Programa de registro de dispositivos**.
   ![Captura de tela do Programa de Registro clicando em Iniciar para o Programa de registro de dispositivos.](./media/enrollment-program-token-started.png)
   2. Na página **Gerenciar Servidores**, escolha **Adicionar servidor MDM**.
   3. Insira o **Nome do servidor MDM** e escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.

   ![Captura de tela da adição de um nome do servidor MDM para DEP e, em seguida, clique em Avançar.](./media/enrollment-program-token-add-server.png)
   4.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta, indicando abre a caixa de diálogo, indicando **Carregar sua chave pública**. Escolha **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.
   ![Captura de tela da escolha do botão de arquivo de chave pública e, em seguida, clique em Avançar.](./media/enrollment-program-token-choose-file.png)
   4.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** mostra um link **Seu Token do Servidor**. Baixe o arquivo do token (.p7m) do servidor em seu computador e escolha **Concluído**.
   ![Captura de tela da escolha do botão de arquivo de chave pública e, em seguida, clique em Avançar.](./media/enrollment-program-token-your-token.png)
   5. Acesse **Programas de Implantação** &gt; **Programa de Registro de Dispositivos** &gt; **Gerenciar Dispositivos**.
   6. Em **Escolher dispositivos por**, especifique como os dispositivos são identificados:
    - **Número de série**
    - **Número do pedido**
    - **Carregar o arquivo CSV**.

   ![Captura de tela que especifica de especificação para escolher dispositivos pelo número de série, definindo a ação de escolha como Atribuir ao servidor e selecionando o nome do servidor.](./media/enrollment-program-token-specify-serial.png)

   7. Para **Escolher Ação**, selecione **Atribuir ao Servidor**, selecione o &lt;Nome do Servidor&gt; especificado para o Microsoft Intune e, em seguida, clique em **OK**. O Portal da Apple atribui os dispositivos especificados para o servidor do Intune para gerenciamento e exibe **Atribuição Concluída**.

   No Portal da Apple, acesse **Programas de Implantação** &gt; **Programa de registro de dispositivos** &gt; **Exibir o Histórico de Atribuição** para ver uma lista de dispositivos e sua atribuição de servidor MDM.

**Etapa 3. Insira a ID da Apple usada para criar o token de programa de registro.**<br>No Portal do Intune, forneça a ID da Apple para referência futura. Use essa ID para renovar seu token de programa de registro para evitar a necessidade de registrar novamente todos os seus dispositivos.
![Captura de tela da especificação da ID da Apple usada para criar o token de programa de registro e navegar para o token do programa de registro.](./media/enrollment-program-token-apple-id.png)
**Etapa 4. Navegue apara o token do programa de registro a ser carregado.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados. O Intune sincroniza automaticamente com a Apple para ver a sua conta de programa de registro.

## Criar um perfil de registro da Apple
<a id="create-an-apple-enrollment-profile" class="xliff"></a>

Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No portal do Intune, escolha **Registro de dispositivo** e, depois, **Registro da Apple**.
2. Em **Programa de Registro para a Apple**, selecione **Perfis de Programa de Registro** e, em seguida, selecione **Criar** na folha **Perfis de Programa de Registro**.
![Captura de tela da escolha do link de criação para criar um novo perfil de programa de registro.](./media/enrollment-program-profile-create.png)
3. Na folha **Criar Perfil de Registro**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes.
![Captura de tela da especificação de nome, descrição e, em seguida, escolha de Registrar com a afinidade de usuário para um novo perfil de programa de registro.](./media/enrollment-program-profile-name.png)
Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil são registrados com ou sem a afinidade de usuário.

 - **Registrar com a afinidade do usuário** – O usuário é afiliado aos dispositivos durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa. Escolha **afinidade de usuário** para dispositivos que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos.

<<<<<<< HEAD
 > [!NOTE]
 > A MFA (Autenticação Multifator) não funciona durante o registro em dispositivos gerenciados por programa de registro com a afinidade de usuário. Após o registro, a MFA funciona conforme o esperado nesses dispositivos. Novos usuários que precisam alterar a senha ao se conectarem pela primeira vez não podem receber uma solicitação durante o registro em dispositivos. Além disso, os usuários com senhas expiradas não receberão uma solicitação para redefinir a senha durante o registro e deverão redefinir a senha em um dispositivo diferente.

 >[!NOTE]
 >O gerenciamento de programa de registro com afinidade de usuário requer que [WS-Trust 1.3 Username/Mixed endpoint](https://technet.microsoft.com/library/adfs2-help-endpoints) esteja habilitado para solicitar tokens do usuário. [Saiba mais sobre o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
=======
    >[!NOTE]
    >O DEP com afinidade de usuário requer que o [ponto de extremidade nome do usuário/misto WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints) esteja habilitado para solicitar um token de usuário. [Saiba mais sobre o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
>>>>>>> 0c3fe0dee88e8ef4d8ad8ad28c0f8957831dd5b3

 - **Inscrever sem afinidade do utilizador** – O dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.

4. Selecione **Configurações de Gerenciamento de Dispositivo** para definir as seguintes configurações de perfil: ![Captura de tela da escolha do modo de gerenciamento com registro bloqueado Supervisado, permitindo definir o emparelhamento para negar todos e o Apple Configurator Certificates esmaecido para um novo perfil do programa de registro.](./media/enrollment-program-profile-mode.png)
    - **Supervisionado** – Um modo de gerenciamento que habilita mais opções de gerenciamento e desabilitou o Bloqueio de Ativação por padrão. Se você deixar a caixa de seleção, terá recursos de gerenciamento limitados.

    - **Registro bloqueado** – (Requer o Modo de Gerenciamento = Supervisionado) Desabilita as configurações de iOS que podem permitir a remoção do perfil de gerenciamento. Se você deixar a caixa de seleção em branco, permitirá que o perfil de gerenciamento seja removido do menu Configurações. Esse item é definido durante a ativação e não pode ser alterado sem uma redefinição de fábrica.

    - **Permitir Emparelhamento** – Especifica se os dispositivos iOS podem sincronizar com computadores. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

    - **Certificados do Apple Configurator** – Se que você escolheu **Permitir Apple Configurator por certificado** em **Permitir Emparelhamento**, selecione um Certificado do Apple Configurator para ser importado.

  Selecione **Salvar**.

5. Selecione **Configurações do Assistente de Instalação** para definir as seguintes configurações de perfil: ![Captura de tela da escolha de definir configurações com as configurações disponíveis para um novo perfil do programa de registro.](./media/enrollment-program-profile-settings.png)
    - **Nome do Departamento** – Aparece quando os usuários tocam em **Sobre a Configuração** durante a ativação.

    - **Telefone do Departamento** – Aparece quando o usuário clica no botão Precisa de Ajuda durante a ativação.
    - **Opções do Assistente de Instalação** – Essas configurações opcionais podem ser configuradas no menu **Configurações** do iOS.
        - **Senha** - Solicitar senha durante a ativação. Sempre exija uma senha, a menos que o dispositivo esteja protegido ou tenha o acesso controlado de alguma outra maneira (ou seja, o modo de quiosque que restringe o dispositivo a um aplicativo).
        - **Serviços de Localização** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Restaurar** - Se habilitado, o Assistente de Instalação solicitará o backup do iCloud durante a ativação
        - **ID da Apple** – se estiver habilitado, o iOS solicitará aos usuários uma ID da Apple quando o Intune tentar instalar um aplicativo sem uma ID. Uma ID da Apple é necessária para baixar aplicativos na App Store iOS, incluindo aqueles instalados pelo Intune.
        - **Termos e Condições** - Se habilitado, o Assistente de Instalação solicitará que os usuários aceitem os termos e as condições da Apple durante a ativação
        - **ID de Toque** – Se habilitada, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Apple Pay** – Se habilitado, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Zoom** – Se habilitado, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Siri** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Dados de Diagnóstico** – Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação

    Selecione **Salvar**.
9. Para salvar as configurações de perfil, selecione **Criar** na folha **Criar Perfil de Registro**. O perfil de registro aparece na lista de Perfis de Registro do Programa de Registro da Apple.

## Sincronizar dispositivos gerenciados
<a id="sync-managed-devices" class="xliff"></a>
Agora que o Intune tem permissão para gerenciar seus dispositivos, você pode sincronizar o Intune com o Apple para ver os dispositivos gerenciados no Portal do Intune.

1. No Portal do Intune, escolha **Registro de Dispositivo** &gt; **Registro da Apple** &gt; **Dispositivos do Programa de Registro**.
2. Em **Dispositivos do Programa de Registro**, selecione **Sincronização**. A folha **Sincronização** é exibida.
![Captura de tela do nó Dispositivos de Programa de Registro selecionado com o link de Sincronização escolhido.](./media/enrollment-program-device-sync.png)
3. Na folha **Sincronizar**, selecione **Solicitar Sincronização**. A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.
![Captura de tela da folha Sincronização com o link Sincronização da solicitação escolhido.](./media/enrollment-program-device-request-sync.png)
    Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:
     -  Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Intune atualiza cada número de série que a Apple atribuiu ao Intune, tenha o número de série sido sincronizado anteriormente ou não. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
     -  Qualquer solicitação de sincronização tem 15 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.
4. No espaço de trabalho dos Dispositivos do Programa de Registro, escolha **Atualizar** para ver seus dispositivos.

## Atribuir um perfil de registro aos dispositivos
<a id="assign-an-enrollment-profile-to-devices" class="xliff"></a>
Os dispositivos gerenciados pelo Intune devem receber um perfil de programa de registro antes de serem registrados.

>[!NOTE]
>Você também pode atribuir números de série aos perfis na folha **Números de Série da Apple**.

1. No portal do Intune, escolha **Registro de dispositivo** > **Registro da Apple** e, em seguida, selecione **Perfis do Programa de Registro**.
2. Na lista de **Perfis do Programa de Registro**, selecione o perfil que você deseja atribuir aos dispositivos e, em seguida, selecione **Atribuir dispositivos**.
![Captura de tela da folha Sincronização com o link Sincronização da solicitação escolhido.](./media/enrollment-program-device-assign.png)
3. Selecione **Atribuir** e, em seguida, selecione os dispositivos que você deseja atribuir a esse perfil. Filtre para exibir os dispositivos disponíveis:
  - **não atribuído**
  - **qualquer**
  - **&lt;nome do perfil&gt;**
4. Selecionar os dispositivos que deseja atribuir. A caixa de seleção acima da coluna selecionará até 1000 dispositivos listados e, em seguida, clique em **Atribuir**. Para registrar mais de 1000 dispositivos, repita as etapas de atribuição até que todos os dispositivos sejam atribuídos a um perfil de registro.

  ![Captura de tela do botão Atribuir para atribuir o perfil do programa de registro no Portal do Intune](media/dep-profile-assignment.png)

## Experiência do usuário final com os dispositivos gerenciados
<a id="end-user-experience-with-managed-devices" class="xliff"></a>

Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune. Se o dispositivo tiver sido ativado e estiver em uso, o perfil não poderá ser aplicado até que o dispositivo volte à redefinição de fábrica. Quando o dispositivo iOS gerenciados pelo programa de registro é ligado, o usuário vê o seguinte:  

1. **Configurar dispositivo iOS** – Você pode escolher entre as seguintes opções:
  - **Configurar como novo dispositivo**
  - **Restaurar do Backup do iCloud**
  - **Restaurar do Backup do iTunes**
2. Os usuários serão informados que a **Microsoft configurará seu dispositivo automaticamente.** Os detalhes de configuração adicionais a seguir também estão disponíveis:

  **A configuração permite à Microsoft gerenciar este dispositivo por conexão sem fio.**

  **Um administrador pode ajudar você a configurar as contas de email e rede, instalar e configurar aplicativos e gerenciar as configurações remotamente.**

  **Um administrador pode desabilitar recursos, instalar e remover aplicativos, monitorar e restringir o tráfego de Internet e apagar remotamente esse dispositivo.**

  **A configuração é fornecida por:<br> MicrosoftIntune iOS Team<br> One Microsoft Way, Redmond, WA 98052 (EUA)**

3. O nome de usuário e senha corporativo ou de estudante são solicitados dos usuários.
4. A ID da Apple é solicitada dos usuários. Uma ID da Apple é necessária para instalar o aplicativo de Portal da Empresa do Intune e outros aplicativos. Depois que as credenciais são fornecidas, o dispositivo instala um perfil de gerenciamento que não pode ser removido. O perfil de gerenciamento do Intune é exibido em **Configurações** > **Geral** > **Gerenciamento de Dispositivo** no dispositivo.

Os usuários agora podem concluir a configuração seus dispositivos da empresa usando o Portal da Empresa do Intune ou o Assistente de Instalação da Apple.
