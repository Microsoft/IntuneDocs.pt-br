---
title: Registrar dispositivos iOS/iPadOS – Programa de registro de dispositivos
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos iOS/iPadOS de propriedade corporativa usando o Programa de registro de dispositivos.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a1eca1f8911e9c6aae3b3725cf15f04d954c5f48
ms.sourcegitcommit: 6608dc70d01376e0cd90aa620a2fe01337f6a2f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260309"
---
# <a name="automatically-enroll-iosipados-devices-with-apples-device-enrollment-program"></a>Registrar automaticamente dispositivos iOS/iPadOS com o Programa de registro de dispositivos da Apple

Configure o Intune para registrar dispositivos iOS/iPadOS comprados por meio do [DEP (Programa de registro de dispositivos)](https://deploy.apple.com) da Apple. O DEP permite registrar um grande número de dispositivos sem nunca precisar tocá-los. Dispositivos como iPhones, iPads e MacBooks podem ser enviados diretamente aos usuários. Quando o usuário liga o dispositivo, o Assistente de Configuração, que inclui a experiência pronta para uso típica de produtos da Apple, é executado com configurações predefinidas e o dispositivo é registrado no gerenciamento.

Para habilitar o registro de DEP, é necessário usar o Intune e um dos seguintes portais: ASM (Apple School Manager) e ABM (Apple Business Manager). É necessária uma lista de números de série ou um número de ordem de compra para que você possa atribuir os dispositivos ao Intune para gerenciamento no ABM/ASM. Você cria perfis de registro de DEP no Intune que contêm configurações que são aplicadas aos dispositivos durante o registro. Observe que o registro de DEP não pode ser usado com uma conta do [gerenciador de registro de dispositivos](device-enrollment-manager-enroll.md).

> [!NOTE]
> O DEP define as configurações de dispositivo que não podem ser removidas pelo usuário final. Portanto, antes de [migrar para DEP](../fundamentals/migration-guide-considerations.md), o dispositivo deve ser apagado para retornar a um estado pronto para uso (novo).

## <a name="dep-and-the-company-portal"></a>DEP e o Portal da Empresa

Os registros de DEP não são compatíveis com a versão da loja de aplicativos do aplicativo Portal da Empresa. Você pode conceder aos usuários acesso ao aplicativo Portal da Empresa em um dispositivo de DEP. Talvez você queira fornecer esse acesso para permitir que os usuários escolham quais aplicativos corporativos desejam usar nos próprios dispositivos ou usem a autenticação moderna para concluir o processo de registro. 

Para habilitar a autenticação moderna durante o registro, envie por push o aplicativo para o dispositivo usando **Instalar o Portal da Empresa com o VPP** (Volume Purchase Program) no perfil do DEP. Para saber mais, confira [Registrar automaticamente dispositivos iOS/iPadOS com o Programa de registro de dispositivos da Apple](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile).

Para habilitar o Portal da Empresa para atualizar automaticamente e fornecer o aplicativo Portal da Empresa em dispositivos já registrados com o DEP, implante o aplicativo Portal da Empresa por meio do Intune como um aplicativo VPP (Volume Purchase Program) necessário com uma [política de configuração de aplicativo](../apps/app-configuration-policies-use-ios.md) aplicada.

Observação: durante o registro de dispositivo automatizado, enquanto o Portal da Empresa está sendo executado no modo de aplicativo único, clicar no link “Saiba mais” resulta em uma mensagem de erro devido ao modo de aplicativo único. Após a conclusão do registro, você poderá exibir mais informações no CP quando o dispositivo não estiver mais no modo de aplicativo único. 

## <a name="what-is-supervised-mode"></a>O que é o modo supervisionado?

A Apple apresentou o modo supervisionado no iOS/iPadOS 5. Um dispositivo iOS/iPadOS no modo supervisionado pode ser gerenciado com mais controles, como bloquear captura de tela e bloquear a instalação de aplicativos da App Store. Assim, é especialmente útil para dispositivos corporativos. O Intune dá suporte ao configurar dispositivos para o modo supervisionado como parte do Programa de registro de dispositivos (DEP) da Apple.

A compatibilidade com dispositivos DEP não supervisionados foi preterida no iOS/iPadOS 11. No iOS/iPadOS 11 e posterior, os dispositivos configurados com o DEP devem sempre ser supervisionados. O sinalizador is_supervised do DEP será ignorado em uma versão futura do iOS/iPadOS.

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
- [Autoridade de MDM (Gerenciamento de Dispositivo Móvel)](../fundamentals/mdm-authority-set.md)
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Obtenha um token DEP da Apple

Antes que possa registrar dispositivos iOS/iPadOS o DEP, você precisa de um arquivo de token (.p7m) do DEP da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos do DEP de sua empresa. Ele também permite que o Intune carregue perfis de registro para a Apple e atribua novos dispositivos a esses perfis.

Você usa o portal do Apple Business Manager ou do Apple School Manager para criar um token. Também pode usar o portal do ABM/ASM para atribuir dispositivos ao Intune para gerenciamento.

> [!NOTE]
> Caso exclua o token do Portal Clássico do Intune antes de migrar para o Azure, o Intune poderá restaurar um token de DEP da Apple. Você pode excluir o token de DEP novamente no portal do Azure.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token.

1. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **iOS** > **Registro do iOS** > **Tokens do programa de registro** > **Adicionar**.

    ![Obtenha um token do programa de registro.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Conceder permissão à Microsoft para enviar informações de usuário e dispositivo para a Apple selecionando **Eu concordo**.

> [!NOTE]
> Depois de progredir além da etapa 2 para baixar o certificado de chave pública do Intune, não feche o assistente nem navegue para fora desta página. Isso invalidará o certificado que você baixou e será necessário repetir esse processo. Se você encontrar essa situação, o mais comum será que o botão Criar na guia Revisar + criar esteja esmaecido e que você não possa concluir o processo.

   ![Captura de tela do painel do Token de Programa de Registro no workspace de Certificados da Apple para baixar a chave pública.](./media/device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Escolha **Baixar sua chave pública** para baixar e salvar o arquivo da chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Etapa 2. Use a chave para baixar um token da Apple.

1. Escolha **Criar um token para o Programa de registro de dispositivos da Apple** para abrir o Portal do Programa de Implantação da Apple e entrar com sua ID da Apple da empresa. Você pode usar essa ID da Apple para renovar seu token de DEP.
2. No [Portal de Programas de Implantação](https://deploy.apple.com) da Apple, escolha **Começar** para **Programa de registro de dispositivos**.

3. Na página **Gerenciar Servidores**, escolha **Adicionar servidor MDM**.
4. Insira o **Nome do servidor MDM** e escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.

5. A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta, indicando abre a caixa de diálogo, indicando **Carregar sua chave pública**. Selecione **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.

6. Vá para **Programas de Implantação** &gt; **Programa de Registro de Dispositivos** &gt; **Gerenciar Dispositivos**.
7. Em **Escolher dispositivos por**, especifique como os dispositivos são identificados:
    - **Número de série**
    - **Número do pedido**
    - **Carregar o arquivo CSV**.

   ![Captura de tela que especifica de especificação para escolher dispositivos pelo número de série, definindo a ação de escolha como Atribuir ao servidor e selecionando o nome do servidor.](./media/device-enrollment-program-enroll-ios/enrollment-program-token-specify-serial.png)

8. Para **Escolher Ação**, escolha **Atribuir ao Servidor**, escolha o &lt;ServerName&gt; especificado para o Microsoft Intune e escolha **OK**. O Portal da Apple atribui os dispositivos especificados para o servidor do Intune para gerenciamento e exibe **Atribuição Concluída**.

   No portal da Apple, acesse **Programas de implantação** &gt; **Programa de registro de dispositivos** &gt; **Exibir o histórico de atribuição** para ver uma lista de dispositivos e sua atribuição de servidor MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Etapa 3. Salve a ID da Apple usada para criar esse token.

No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), forneça a ID da Apple para referência futura.

![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token-and-choose-scope-tags"></a>Etapa 4. Carregue seu token e escolha as marcas de escopo.

1. Na caixa **Token da Apple**, navegue até o arquivo de certificado (.pem) e escolha **Abrir**.
2. Se você quiser aplicar [marcas de escopo](../fundamentals/scope-tags.md) a esse token DEP, escolha **Escopo (marcas)** e escolha as marcas de escopo desejadas. As marcas de escopo aplicadas a um token serão herdadas pelos perfis e dispositivos adicionados a esse token.
3. Escolha **Criar**.

Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS/iPadOS enviando por push políticas para os dispositivos móveis registrados. O Intune sincroniza automaticamente com a Apple para ver a sua conta de programa de registro.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple

Agora que você instalou o token, pode criar um perfil de registro para dispositivos do DEP. Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro. Há um limite de 100 perfis de registro por token de DEP.

> [!NOTE]
> Os dispositivos serão bloqueados se não houver licenças suficientes do Portal da Empresa para um token VPP ou se o token tiver expirado. O Intune exibirá um alerta quando um token estiver prestes a expirar ou faltar licenças.
 

1. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **iOS** > **Registro do iOS** > **Tokens do programa de registro**.
2. Selecione um token, escolha **Perfis** > **Criar perfil** > **iOS**.

    ![Criar uma captura de tela de perfil.](./media/device-enrollment-program-enroll-ios/image04.png)

3. Na página **Noções Básicas**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes. Você pode usar esse campo **Nome** para criar um grupo dinâmico no Azure Active Directory. Use o nome do perfil para definir o parâmetro enrollmentProfileName para atribuir dispositivos com este perfil de registro. Saiba mais sobre os [grupos dinâmicos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices).

    ![Nome e descrição do perfil.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Selecione **Avançar: Configurações de Gerenciamento de Dispositivos**.

5. Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil devem ser registrados com ou sem um usuário atribuído.
    - **Registrar com dispositivo de afinidade do usuário** – Escolha esta opção para dispositivos que pertencem a usuários e que desejam usar o Portal da Empresa para serviços como a instalação de aplicativos. Se estiver usando o ADFS e o perfil de registro tiver a opção **Autenticar com o Portal da Empresa em vez de usar o Assistente de Configuração** definida como **Não**, será obrigatório [Nome de usuário/Ponto de extremidade misto do WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints) [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Registrar sem afinidade do usuário** – escolha esta opção para dispositivos não afiliados com um único usuário. Use esta opção para dispositivos que não acessam dados de usuário local. Aplicativos como o Portal da Empresa não funcionam.

5. Se você tiver escolhido **Registrar com Afinidade de Usuário**, poderá permitir que os usuários façam a autenticação com o Portal da Empresa em vez do Assistente de Configuração da Apple.

    ![Faça a autenticação com o Portal da Empresa.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Se você quiser realizar algum dos procedimentos a seguir, defina **Selecione o local em que os usuários precisam se autenticar** para **Portal da Empresa**.
    >    - Usar autenticação multifator
    >    - Solicitar aos usuários que precisam alterar a senha quando entram pela primeira vez
    >    - solicitar que os usuários redefinam suas senhas expiradas durante o registro
    >
    > Essas opções não têm suporte na autenticação com o Assistente de Configuração da Apple.

6. Se você escolher **Portal da Empresa** para **Selecione o local em que os usuários precisam se autenticar**, use um token VPP para instalar automaticamente o Portal da Empresa no dispositivo. Nesse caso, o usuário não precisa fornecer uma ID da Apple. Para instalar o Portal da Empresa com um token de VPP, escolha um token em **Instalar o Portal da Empresa com o VPP**. Requer que o Portal da Empresa já tenha sido adicionado ao token VPP. Para garantir que o aplicativo do Portal da Empresa continue a ser atualizado após o registro, configure uma implantação de aplicativo no Intune (Intune>Aplicativos Cliente). Para que a interação do usuário não seja necessária, convém ter o Portal da Empresa como um aplicativo VPP do iOS/iPadOS, torná-lo um aplicativo obrigatório e usar o licenciamento de dispositivo para a atribuição. Verifique se o token não expira e se você tem licenças do dispositivo suficientes para o aplicativo de Portal da Empresa. Se o token expirar ou as licenças acabarem, o Intune instalará em seu lugar o Portal da Empresa da App Store e solicitará a ID da Apple. 

    > [!NOTE]
    > Quando **Selecione o local em que os usuários precisam se autenticar** estiver definido para **Portal da Empresa**, realize o processo de registro do dispositivo nas primeiras 24 horas depois que o portal da empresa for baixado para o dispositivo de DEP. Caso contrário, o registro poderá falhar, e será necessário fazer uma redefinição de fábrica para registrar o dispositivo.
    
    ![Captura de tela da instalação do Portal da Empresa com o VPP.](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. Se você escolheu **Configurar Assistente** para **Selecione o local em que os usuários precisam se autenticar**, mas também quer usar o Acesso Condicional ou implantar aplicativos da empresa nos dispositivos, instale o Portal da Empresa nos dispositivos. Para isso, escolha **Sim** para **Instalar o Portal da Empresa**.  Caso você queira que os usuários recebam o Portal da Empresa sem que precisem se autenticar na loja de aplicativos, escolha **Instalar o Portal da Empresa com o VPP** e selecione um token VPP. Verifique se o token não expira e se você tem licenças do dispositivo suficientes para o aplicativo de Portal da Empresa para implantar corretamente.

8. Se você escolheu um token para **Instalar o Portal da Empresa com o VPP**, é possível bloquear o dispositivo no Modo de Aplicativo Único (especificamente, o aplicativo Portal da Empresa) logo após a conclusão do Assistente de Configuração. Escolha **Sim** para **Executar Portal da Empresa no Modo de Aplicativo Único até a autenticação** para definir essa opção. Para usar o dispositivo, o usuário precisa primeiro se autenticar usando o Portal da Empresa.

    Não há suporte para a autenticação multifator em um dispositivo único bloqueado no Modo de Aplicativo Único. Essa limitação existe porque o dispositivo não pode alternar para um aplicativo diferente a fim de concluir o segundo fator de autenticação. Portanto, se você quiser uma autenticação multifator em um dispositivo de Modo de Aplicativo Único, o segundo fator precisará estar em um dispositivo diferente.

    Só há suporte para esse recurso no iOS/iPadOS 11.3.1 e posterior.

   ![Captura de tela de um modo de aplicativo único.](./media/device-enrollment-program-enroll-ios/single-app-mode.png)

9. Se quiser que os dispositivos que usam esse perfil sejam supervisionados, escolha **Sim** para **Supervisionado**.

    ![Captura de tela Configurações de Gerenciamento de Dispositivos.](./media/device-enrollment-program-enroll-ios/supervisedmode.png)

    Os dispositivos **supervisionados** permitem mais opções de gerenciamento e desabilitam o Bloqueio de Ativação por padrão. A Microsoft recomenda o uso do DEP como o mecanismo para habilitar o modo supervisionado, especialmente se você estiver implantando grandes números de dispositivos iOS/iPadOS.

    Os usuários são notificados de que seus dispositivos são supervisionados de duas maneiras:

   - A tela de bloqueio diz: "Este iPhone é gerenciado pela Contoso."
   - A tela **Configurações** > **Geral** > **Sobre** diz: "Este iPhone é supervisionado. A Contoso pode monitorar o tráfego de Internet e localizar este dispositivo."

     > [!NOTE]
     > Um dispositivo registrado sem supervisão só pode ser redefinido para supervisionado usando o Apple Configurator. A redefinição do dispositivo dessa maneira requer conectar um dispositivo iOS/iPadOS a um Mac com um cabo USB. Saiba mais sobre isso nos [documentos do Apple Configurator](http://help.apple.com/configurator/mac/2.3).

10. Escolha se deseja registro bloqueado para dispositivos que usam esse perfil. O **Registro bloqueado** desabilita as configurações de iOS/iPadOS que permitem a remoção do perfil de gerenciamento do menu **Configurações**. Depois que o dispositivo é registrado, não é possível alterar essa configuração sem apagar o dispositivo. Esses dispositivos devem ter o Modo de Gerenciamento **Supervisionado** configurado como *Sim*. 

11. Escolha se deseja que os dispositivos que usam esse perfil possam **Sincronizar com computadores**. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

12. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em Certificados do Apple Configurator para importar.

13. Você pode especificar um formato de nomenclatura para os dispositivos, que será aplicado automaticamente quando eles forem registrados e em cada check-in sucessivo. Para criar um modelo de nomenclatura, selecione **Sim** em **Aplicar modelo de nome do dispositivo**. Em seguida, na caixa **Modelo de Nome do Dispositivo**, digite o modelo a ser usado para os nomes que usam esse perfil. Especifique um modelo de formato que inclua o tipo de dispositivo e o número de série. 

14. Escolha **Avançar: Personalização do Assistente de Configuração**.

15. Na página **Personalização do Assistente de Configuração**, defina as seguintes configurações de perfil: ![Personalização do Assistente de Configuração.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Configurações de departamento | Descrição |
    |---|---|
    | <strong>Nome do Departamento</strong> | Aparece quando os usuários tocam em <strong>Sobre a Configuração</strong> durante a ativação. |
    |    <strong>Telefone do Departamento</strong>     | Aparece quando o usuário clica no botão <strong>Precisa de Ajuda</strong> durante a ativação. |

    Você pode optar por ocultar as telas do Assistente de Configuração no dispositivo durante a configuração do usuário.
    - Se você escolher **Ocultar**, a tela não será exibida durante a instalação. Depois de configurar o dispositivo, o usuário pode ainda entrar no menu **Configurações** para configurar o recurso.
    - Se você escolher **Mostrar**, a tela será exibida durante a instalação. O usuário pode, às vezes, ignorar a tela sem executar uma ação. No entanto, é possível ir mais tarde para o menu **Configurações** do dispositivo para configurar o recurso. 


    | Configurações de tela do Assistente de Instalação | Se você escolher **Mostrar**, durante a instalação, o dispositivo… |
    |------------------------------------------|------------------------------------------|
    | <strong>Senha</strong> | Solicitará ao usuário uma senha. Sempre exija uma senha para dispositivos não protegidos, a menos que o acesso seja controlado de alguma outra maneira (por exemplo, o modo de quiosque que restringe o dispositivo a um aplicativo). |
    | <strong>Serviços de Localização</strong> | Solicitará ao usuário sua localização. |
    | <strong>Restaurar</strong> | Exibirá a tela Aplicativos e Dados. Esta tela fornece aos usuários a opção de restaurar ou transferir dados do Backup do iCloud quando eles configuram o dispositivo. |
    | <strong>iCloud e ID da Apple</strong> | Dará ao usuário as opções de entrar com a ID da Apple e usar o iCloud.                         |
    | <strong>Termos e Condições</strong> | Exigirá que o usuário aceite os termos e condições da Apple. |
    | <strong>ID de Toque</strong> | Dará ao usuário a opção de configurar a identificação por impressão digital para o dispositivo. |
    | <strong>Apple Pay</strong> | Dará ao usuário a opção de configurar o Apple Pay no dispositivo. |
    | <strong>Zoom</strong> | Dará ao usuário a opção para aplicar zoom na exibição quando ele configurar o dispositivo. |
    | <strong>Siri</strong> | Dará ao usuário a opção de configurar o Siri. |
    | <strong>Dados de diagnóstico</strong> | Exibirá a tela Diagnóstico para o usuário. Esta tela fornece ao usuário a opção de enviar dados de diagnóstico para a Apple. |
    | <strong>Exibir Tom</strong> | Forneça ao usuário a opção de ativar a configuração Exibir Tom. |
    | <strong>Privacidade</strong> | Exiba a tela Privacidade para o usuário. |
    | <strong>Migração do Android</strong> | Forneça ao usuário a opção de migrar a data de um dispositivo Android. |
    | <strong>iMessage e FaceTime</strong> | Fornecerá ao usuário a opção de configurar o iMessage e o FaceTime. |
    | <strong>Integração</strong> | Exiba telas informativas de integração para educação do usuário, como Folha de Rosto, Multitarefa e Centro de Controle. |
    | <strong>Migração de Relógio</strong> | Forneça ao usuário a opção de migrar dados de um dispositivo de relógio. |
    | <strong>Tempo da Tela</strong> | Exiba a tela Tempo da Tela. |
    | <strong>Atualização de Software</strong> | Exiba a tela de atualização de software obrigatória. |
    | <strong>Instalação de SIM</strong> | Forneça ao usuário a opção de adicionar um plano de celular. |
    | <strong>Aparência</strong> | Exibirá a tela Aparência para o usuário. |
    | <strong>Idioma expresso</strong>| Exibirá a tela Idioma Expresso para o usuário. |
    | <strong>Idioma preferencial</strong> | Dará aos usuários a opção de escolher o **Idioma preferencial**. |
    | <strong>Migração de dispositivo para dispositivo</strong> | Fornecerá ao usuário a opção de migrar dados de um dispositivo antigo para este dispositivo.|
    

16. Escolha **Avançar** para acessar a página **Examinar + Criar**.

17. Para salvar o perfil, escolha **Criar**.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados
Agora que o Intune tem permissão para gerenciar seus dispositivos, você pode sincronizar o Intune com a Apple para ver os dispositivos gerenciados no Intune no Portal do Azure.

1. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos**>**iOS**>**Registro do iOS**>**Tokens do programa de registro** &gt; escolha um token na lista &gt; **Dispositivos**>**Sincronizar**. ![Captura de tela do nó Dispositivos do Programa de Registro e do Link de Sincronização.](./media/device-enrollment-program-enroll-ios/image06.png)

   Para seguir os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:
   - Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Intune busca a lista atualizada completa de números de série atribuído ao servidor Apple MDM conectado ao Intune. Se um dispositivo de DEP for excluído do portal do Intune, será preciso remover a atribuição dele do servidor MDM da Apple no portal do DEP. Se a atribuição não for removida, ele não será importado novamente para o Intune até que a sincronização completa seja executada.   
   - A sincronização é executada automaticamente a cada 24 horas. Você também pode sincronizar clicando no botão **Sincronizar** (não mais do que uma vez a cada 15 minutos). Todas as solicitações de sincronização têm 15 minutos para conclusão. O botão **Sincronizar** fica desativado até que a sincronização seja concluída. Essa sincronização atualizará o status do dispositivo existente e importará novos dispositivos atribuídos ao servidor MDM da Apple.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Atribuir um perfil de registro aos dispositivos
Atribua um perfil do Programa de Registro aos dispositivos antes de registrá-los.

>[!NOTE]
>Você também pode atribuir números de série aos perfis na folha **Números de Série da Apple**.

1. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **iOS** > **Registro do iOS** > **Tokens do programa de registro** &gt; escolha um token na lista.
2. Escolha **Dispositivos**> escolha dispositivos na lista > **Atribuir perfil**.
3. Em **Atribuir perfil**, escolha um perfil para os dispositivos e, em seguida, escolha **Atribuir**.

### <a name="assign-a-default-profile"></a>Atribuir um perfil padrão

Você pode escolher um perfil padrão a ser aplicado a todos os dispositivos que se registrem com um token específico.

1. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **iOS** > **Registro do iOS** > **Tokens do programa de registro** &gt; escolha um token na lista.
2. Escolha **Definir como Perfil Padrão**, selecione um perfil na lista suspensa e escolha **Salvar**. Este perfil será aplicado a todos os dispositivos registrados com o token.

## <a name="distribute-devices"></a>Distribuir dispositivos
Você habilitou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos de DEP. Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune. Os dispositivos sem afinidade de usuário requerem uma licença de dispositivo. Um dispositivo ativado só poderá receber um perfil de registro depois que for apagado.

Confira [Registrar seu dispositivo iOS/iPadOS no Intune com o Programa de registro de dispositivos](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>Renovar um token DEP  
1. Acesse deploy.apple.com.  
2. Em **Gerenciar Servidores**, escolha o servidor MDM associado ao arquivo de token que você deseja renovar.
3. Escolha **Gerar Novo Token**.

    ![Captura de tela de geração de novo token.](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. Escolha **Token do Seu Servidor**.  
5. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **iOS** > **Registro do iOS** > **Tokens do programa de registro** &gt; escolha o token.
    ![Captura de tela de tokens do programa de registro.](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. Escolha **Renovar token** e insira a ID da Apple usada para criar o token original.  
    ![Captura de tela de geração de novo token.](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Carregue o token recém-baixado.  
9. Escolha **Renovar token**. Você verá a confirmação de renovação do token.   
    ![Captura de tela de confirmação.](./media/device-enrollment-program-enroll-ios/confirmation.png)
