---
title: "Registrar dispositivos iOS – Programa de registro de dispositivos"
titlesuffix: Azure portal
description: Saiba como registrar dispositivos iOS de propriedade corporativa usando o Programa de registro de dispositivos.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2f472c144e9bcda965486f8e88d38aa9d27df165
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Registrar automaticamente dispositivos iOS com o Programa de registro de dispositivos da Apple

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico ajuda você a habilitar o registro de dispositivos iOS comprados por meio do [DEP (Programa de registro de dispositivos)](https://deploy.apple.com) da Apple. Você pode habilitar o registro de DEP para um grande número de dispositivos sem nunca tocá-los. Você pode enviar dispositivos como iPhones e iPads diretamente aos usuários. Quando o usuário liga o dispositivo, o Assistente de Configuração é executado com as configurações predefinidas e o dispositivo é registrado no gerenciamento.

Para habilitar o registro de DEP, você pode usar ambos os portais do Intune e do Apple DEP. É necessária uma lista de números de série ou um número de ordem de compra para que você possa atribuir os dispositivos ao Intune para gerenciamento. Você cria perfis de registro de DEP que contém configurações aplicadas aos dispositivos durante o registro.

A propósito, o registro de DEP não funciona com o [gerenciador de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>O que é o modo supervisionado?
A Apple apresentou o modo supervisionado no iOS 5. Um dispositivo iOS no modo supervisionado pode ser gerenciado com mais controles. Assim, é especialmente útil para dispositivos corporativos. O Intune dá suporte ao configurar dispositivos para o modo supervisionado como parte do Programa de registro de dispositivos (DEP) da Apple. 

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Pré-requisitos
- Dispositivos comprados no [Programa de registro de dispositivos da Apple](http://deploy.apple.com)
- [Autoridade MDM](mdm-authority-set.md)
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)

> [!NOTE]
> A MFA (autenticação multifator) não funciona durante o registro de DEP configurado para a afinidade do usuário. Após o registro, a MFA funciona conforme o esperado nos dispositivos. Os dispositivos não podem exibir uma solicitação aos usuários que precisam alterar sua senha quando entrarem pela primeira vez. Além disso, os usuários com senhas expiradas não receberão uma solicitação para redefinir a senha durante o registro. Os usuários devem usar um dispositivo diferente para redefinir a senha.

## <a name="get-the-apple-dep-token"></a>Obter o token Apple DEP

Antes que possa registrar dispositivos iOS o DEP, você precisa de um arquivo de token (.p7m) do DEP da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos do DEP de sua empresa. Ele também permite que o Intune carregue perfis de registro para a Apple e atribua novos dispositivos a esses perfis.

Você pode usar o portal de DEP da Apple para criar um token de DEP. Você também pode usar o portal de DEP para atribuir dispositivos ao Intune para gerenciamento.

> [!NOTE]
> Caso exclua o token do Portal Clássico do Intune antes de migrar para o Azure, o Intune poderá restaurar um token de DEP da Apple. Você pode excluir o token de DEP novamente no portal do Azure. Você pode excluir o token de DEP novamente no portal do Azure.

**Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token de DEP da Apple.**<br>

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Token do Programa de Registro**.

  ![Captura de tela mostrando o painel do Token do Programa de Registro, no espaço de trabalho de Certificados da Apple.](./media/enrollment-program-token-add.png)

2. Escolha **Baixar sua chave pública** para baixar e salvar o arquivo da chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.

  ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/enrollment-program-token-download.png)

**Etapa 2. Criar e baixar um token Apple DEP.**<br>
1. Escolha **Criar um token por meio do Programa de registro de dispositivos da Apple** para abrir o Portal do Programa de Implantação da Apple e entrar com sua ID da Apple da empresa. Você pode usar essa ID da Apple para renovar seu token de DEP.
2.  No [Portal de Programas de Implantação](https://deploy.apple.com) da Apple, escolha **Começar** para **Programa de registro de dispositivos**.

3. Na página **Gerenciar Servidores**, escolha **Adicionar servidor MDM**.
4. Insira o **Nome do servidor MDM** e escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.

   ![Captura de tela da adição de um nome do servidor MDM para DEP e, em seguida, clique em Avançar.](./media/enrollment-program-token-add-server.png)

5. A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta, indicando abre a caixa de diálogo, indicando **Carregar sua chave pública**. Escolha **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.  


7. Acesse **Programas de Implantação** &gt; **Programa de Registro de Dispositivos** &gt; **Gerenciar Dispositivos**.
8. Em **Escolher dispositivos por**, especifique como os dispositivos são identificados:
    - **Número de série**
    - **Número do pedido**
    - **Carregar o arquivo CSV**.

   ![Captura de tela que especifica de especificação para escolher dispositivos pelo número de série, definindo a ação de escolha como Atribuir ao servidor e selecionando o nome do servidor.](./media/enrollment-program-token-specify-serial.png)

9. Para **Escolher Ação**, escolha **Atribuir ao Servidor**, escolha o &lt;ServerName&gt; especificado para o Microsoft Intune e escolha **OK**. O Portal da Apple atribui os dispositivos especificados para o servidor do Intune para gerenciamento e exibe **Atribuição Concluída**.

   No Portal da Apple, acesse **Programas de Implantação** &gt; **Programa de registro de dispositivos** &gt; **Exibir o Histórico de Atribuição** para ver uma lista de dispositivos e sua atribuição de servidor MDM.

**Etapa 3. Insira a ID da Apple usada para criar o token de programa de registro.**<br>No Intune no Portal do Azure, forneça a ID da Apple para referência futura. Use essa ID para renovar seu token de programa de registro no futuro para evitar a necessidade de registrar novamente todos os seus dispositivos.

![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/enrollment-program-token-apple-id.png)

**Etapa 4. Navegue apara o token do programa de registro a ser carregado.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados. O Intune sincroniza automaticamente com a Apple para ver a sua conta de programa de registro.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple

Agora que você instalou o token, pode criar um perfil de registro para dispositivos do DEP. Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple**.
2. Em **Programa de Registro da Apple**, escolha **Perfis do Programa de Registro** > **Criar**.
3. Em **Criar Perfil de Registro**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes. Você pode usar esse campo **Nome** para criar um grupo dinâmico no Azure Active Directory. Use o nome do perfil para definir o parâmetro enrollmentProfileName para atribuir dispositivos com este perfil de registro. Saiba mais sobre os [grupos dinâmicos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

  Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil são registrados com ou sem um usuário atribuído.

 - **Registrar com afinidade do usuário** – escolha para dispositivos que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos. A afinidade de usuário requer [ponto de extremidade nome do usuário/misto WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Registrar sem afinidade do usuário** – escolha para dispositivos não afiliados com um único usuário. Use para dispositivos que executam tarefas sem acessar os dados de usuário local. Aplicativos como o aplicativo de Portal da Empresa não funcionam.

4. Escolha **Configurações de Gerenciamento de Dispositivo** para definir as seguintes configurações de perfil:

  ![Captura de tela mostrando a escolha do Modo de Gerenciamento. O dispositivo apresenta as seguintes configurações: supervisionado, registro bloqueado e permitir emparelhamento definido como negar todos. O recurso Certificados do Apple Configurator está desabilitado para um novo perfil do Programa de Registro.](./media/enrollment-program-profile-mode.png)
    - **Supervisionado** – Um modo de gerenciamento que habilita mais opções de gerenciamento e desabilitou o Bloqueio de Ativação por padrão. Se você deixar a caixa de seleção, terá recursos de gerenciamento limitados. A Microsoft recomenda usar o DEP como o mecanismo para habilitar o modo supervisionado, especialmente para as empresas que implantam grandes números de dispositivos iOS.

 > [!NOTE]
 > Configurar um dispositivo para o modo supervisionado não pode ser feito usando o Intune depois de um dispositivo ter sido registrado. Após o registro, a única maneira de habilitar o modo supervisionado é conectando um dispositivo iOS a um Mac com um cabo USB e usando o Apple Configurator. Isso redefinirá o dispositivo e o configurará no modo supervisionado. Saiba mais sobre isso nos [documentos do Apple Configurator](http://help.apple.com/configurator/mac/2.3). Um dispositivo supervisionado informará que "Este iPhone é gerenciado por Contoso." na tela de bloqueio e "Este iPhone é supervisionado. A Contoso pode monitorar o tráfego de Internet e localizar este dispositivo." em **Configurações** > **Geral** > **Sobre**.

    - **Registro bloqueado** – (Requer o Modo de gerenciamento = Supervisionado) Desabilita as configurações de iOS que podem permitir a remoção do perfil de gerenciamento. Se você deixar a caixa de seleção em branco, permitirá que o perfil de gerenciamento seja removido do menu Configurações. Depois de registrar o dispositivo, não é possível alterar esta configuração sem restaurar as configurações de fábrica.

  - **Habilitar iPad compartilhado** – o Programa de Registro de Dispositivos da Apple não dá suporte a iPad compartilhado.

    - **Permitir Emparelhamento** – Especifica se os dispositivos iOS podem sincronizar com computadores. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

    - **Certificados do Apple Configurator** – Se que você escolheu **Permitir Apple Configurator por certificado** em **Permitir Emparelhamento**, escolha um Certificado do Apple Configurator para ser importado.

  Selecione **Salvar**.

5. Escolha as **Configurações do Assistente de Configuração** para definir as seguintes configurações de perfil:

  ![Captura de tela mostrando a escolha das definições de configuração com as configurações disponíveis para um novo perfil do Programa de Registro.](./media/enrollment-program-profile-settings.png)
    - **Nome do Departamento** – Aparece quando os usuários tocam em **Sobre a Configuração** durante a ativação.

    - **Telefone do Departamento** – Exibido quando o usuário clica no botão **Precisa de ajuda** durante a ativação.
    - **Opções do Assistente de Instalação** – Essas configurações opcionais podem ser configuradas no menu **Configurações** do iOS.
        - **Senha**
        - **Serviços de Localização**
        - **Restaurar**
        - **ID Apple**
        - **Termos e Condições**
        - **ID de Toque**
        - **Apple Pay**
        - **Zoom**
        - **Siri**
        - **Dados de diagnóstico**

    Selecione **Salvar**.

9. Para salvar as configurações de perfil, escolha **Criar** na folha **Criar Perfil de Registro**. O perfil de registro aparece na lista de Perfis de Registro do Programa de Registro da Apple.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados
Agora que o Intune tem permissão para gerenciar seus dispositivos, você pode sincronizar o Intune com a Apple para ver os dispositivos gerenciados no Intune no Portal do Azure.

1. No Intune, no Portal do Azure, escolha **Registro de Dispositivo** > **Registro da Apple** > **Dispositivos do Programa de Registro** > **Sincronizar**. A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.

  ![Captura de tela mostrando o nó Dispositivos do Programa de Registro selecionado e o Link de Sincronização escolhido.](./media/enrollment-program-device-sync.png)
  
2. Na folha **Sincronizar**, escolha **Solicitar Sincronização**. A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.

  ![Captura de tela mostrando a folha Sincronização com o link Solicitar sincronização escolhido.](./media/enrollment-program-device-request-sync.png)

  Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:
     -  Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Microsoft Intune atualiza todos os números de série da Apple atribuídos à nossa plataforma. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
     -  Qualquer solicitação de sincronização tem 15 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.
     - O Intune sincroniza dispositivos novos e removidos com a Apple a cada 24 horas.

3. No espaço de trabalho dos Dispositivos do Programa de Registro, escolha **Atualizar** para ver seus dispositivos.

## <a name="assign-an-enrollment-profile-to-devices"></a>Atribuir um perfil de registro aos dispositivos
Atribua um perfil do Programa de Registro aos dispositivos antes de registrá-los.

>[!NOTE]
>Você também pode atribuir números de série aos perfis na folha **Números de Série da Apple**.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** e escolha **Perfis do Programa de Registro**.
2. Na lista de **Perfis do Programa de Registro**, escolha o perfil que você deseja atribuir aos dispositivos e, em seguida, escolha **Atribuir dispositivos**.

 ![Captura de tela de Atribuições de Dispositivo com Atribuir sendo selecionado.](./media/enrollment-program-device-assign.png)

3. Escolha **Atribuir** e, em seguida, escolha os dispositivos que você deseja atribuir a esse perfil. Filtre para exibir os dispositivos disponíveis:
  - **não atribuído**
  - **qualquer**
  - **&lt;nome do perfil&gt;**
4. Escolha os dispositivos que deseja atribuir. A caixa de seleção acima da coluna seleciona até mil dispositivos relacionados; em seguida, clique em **Atribuir**. Para registrar mais de 1000 dispositivos, repita as etapas de atribuição até que todos os dispositivos sejam atribuídos a um perfil de registro.

  ![Captura de tela do botão Atribuir para atribuir o perfil do programa de registro no Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a>Distribuir dispositivos
Você habilitou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos de DEP. Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune. Os dispositivos sem afinidade de usuário requerem uma licença de dispositivo. Um dispositivo ativado só pode ser aplicado a um perfil de registro após restaurar as respectivas configurações de fábrica.

Consulte [Registre seu dispositivo iOS no Intune com o Programa de registro de dispositivos](/intune-user-help/enroll-your-device-dep-ios). 
