---
title: Tutorial – usar o Programa de registro de dispositivos ou Apple Business Manager para registrar dispositivos iOS no Intune
titleSuffix: Microsoft Intune
description: Neste tutorial, você configurará recursos de registro de dispositivos corporativos da Apple do Apple Business Manager para registrar dispositivos iOS no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Apple's corporate device enrollment features so that corporate devices can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e006ce1be5a19d0557ef0a5d6046afea2c13986
ms.sourcegitcommit: dde4b8788e96563edeab63f612347fa222d8ced0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135171"
---
# <a name="tutorial-use-apples-corpoate-device-enrollment-features-in-apple-business-manager-abm-to-enroll-ios-devices-in-intune"></a>Tutorial: Usar recursos do Registro de dispositivos corporativos da Apple no ABM (Apple Business Manager) para registrar dispositivos iOS no Intune
Os recursos de registro de dispositivos no Apple Business Manager simplificam o registro de dispositivos. O Intune também dá suporte ao portal DEP (Programa de registro de dispositivos) da Apple, o qual é mais antigo, mas incentivamos você a experimentar um novo começo com o Apple Business Manager. Com o Microsoft Intune e o Registro de dispositivos corporativos da Apple, os dispositivos são registrados automaticamente com segurança na primeira vez em que o usuário liga o dispositivo. Assim, você pode enviar dispositivos para vários usuários sem a necessidade de configurar cada dispositivo individualmente. 

Neste tutorial, você aprenderá a:
> [!div class="checklist"]
> * Obter um token do registro de dispositivos da Apple
> * Sincronizar dispositivos gerenciados ao Intune
> * Criar um perfil de registro
> * Atribuir um perfil de registro aos dispositivos

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos
- Dispositivos comprados no [Apple Business Manager](https://business.apple.com) ou no [Programa de registro de dispositivos da Apple](http://deploy.apple.com)
- Defina a [autoridade de gerenciamento de dispositivo móvel](mdm-authority-set.md)
- Obtenha um [certificado push de MDM da Apple](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-device-enrollment-token"></a>Obter um token do registro de dispositivos da Apple
Antes de registrar dispositivos iOS com recursos de registro corporativo da Apple, você precisará de um arquivo de token (.PEM) do registro de dispositivos da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos Apple de sua empresa. Ele também permite que o Intune carregue perfis de registro para a Apple e atribua novos dispositivos a esses perfis.

Você pode usar o portal do DEP ou do ABM para criar um token do registro de dispositivos. Você também pode usar os portais do DEP para atribuir dispositivos ao Intune para gerenciamento.

1. No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens do Programa de Registro** > **Adicionar**.

2. Conceder permissão à Microsoft para enviar informações de usuário e dispositivo para a Apple selecionando **Eu concordo**.

   ![Captura de tela do painel do Token de Programa de Registro no workspace de Certificados da Apple para baixar a chave pública.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Escolha **Baixar sua chave pública** para baixar e salvar o arquivo da chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do ABM ou do DEP.

4. Escolha **Criar um token para o Programa de registro de dispositivos da Apple** para abrir o Portal do Programa de Implantação da Apple e entrar com sua ID da Apple da empresa. Você pode usar essa ID da Apple para renovar seu token de DEP.

5.  No [Portal de Programas de Implantação](https://deploy.apple.com) da Apple, escolha **Começar** para **Programa de registro de dispositivos**. O processo pode ser um pouco diferente do que as etapas a seguir no [Apple Business Manager](https://business.apple.com).

4. Na página **Gerenciar Servidores**, escolha **Adicionar servidor MDM**.

5. Para **Nome do Servidor MDM**, insira *TestMDMServer* e, em seguida, escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.

6. A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta, indicando abre a caixa de diálogo, indicando **Carregar sua chave pública**. Selecione **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.

6. Vá para **Programas de Implantação** > **Programa de Registro de Dispositivos** > **Gerenciar Dispositivos**.
7. Em **Escolher Dispositivos Por**, escolha **Número de Série**. <!--ask Tiffany about this-->

8. Para **Escolher Ação**, escolha **Atribuir ao Servidor**, escolha o &lt;ServerName&gt; especificado para o Microsoft Intune e escolha **OK**. O Portal da Apple atribui os dispositivos especificados para o servidor do Intune para gerenciamento e exibe **Atribuição Concluída**.

   No Portal da Apple, acesse **Programas de Implantação** &gt; **Programa de registro de dispositivos** &gt; **Exibir o Histórico de Atribuição** para ver uma lista de dispositivos e sua atribuição de servidor MDM.

9. Para referência futura, no Intune, no portal do Azure, forneça a ID Apple usada para criar esse token.

    ![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/device-enrollment-program-enroll-ios/image03.png)

10. Na caixa **Token da Apple**, navegue até o arquivo de certificado (.pem), escolha **Abrir** e, em seguida, escolha **Criar**. 

11. Se você quiser aplicar marcas de escopo para limitar quais administradores têm acesso a esse token, selecione os escopos.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple
Agora que você instalou o token, pode criar um perfil de registro para dispositivos iOS de propriedade corporativa. Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.

2. Selecione o token que você acabou de instalar, escolha **Perfis** > **Criar perfil**.

3. Em **Criar perfil**, insira *TestDEPProfile* para **Nome** e *Teste DEP para dispositivos iOS* para **Descrição**. Os usuários não veem esses detalhes.

4. Escolha **iOS** em **Plataforma**.

5. Determine se você deseja que os dispositivos sejam registrados com ou sem **Afinidade de Usuário**. A Afinidade de Usuário foi projetada para dispositivos que serão usados por usuários específicos. Se seus usuários desejarem usar o Portal da Empresa para serviços como instalar aplicativos, escolha **Registrar com Afinidade de Usuário**. Se os usuários não precisarem do Portal da Empresa ou se você desejar provisionar o dispositivo para muitos usuários, escolha **Registrar sem Afinidade de Usuário**.

6. Se você optar por registrar com afinidade de usuário, determine se você deseja autenticar com o Portal da Empresa ou o Assistente de Configuração da Apple. Se você quiser usar a autenticação multifator, permitir que os usuários alterem suas senhas após a primeira entrada ou solicitar que os usuários redefinam suas senhas expiradas durante o registro, escolha **Sim** em **Autenticar com o Portal da Empresa em vez do Assistente de Configuração da Apple**. Se você se sentir confortável usando a autenticação HTTP básica fornecida pela Apple por meio do Assistente de Configuração da Apple, escolha **Não**.

7. Se você optar por se registrar com afinidade de usuário e autenticar-se via Portal da Empresa, determine se você gostaria de instalar o Portal da Empresa com o Apple VPP (Volume Purchase Program). Se você instalar o Portal da Empresa com um token VPP, o usuário não precisará inserir uma ID da Apple e senha para baixar o Portal da Empresa da loja de aplicativos durante o registro. Escolha **Usar Token:** em **Instalar o Portal da Empresa com o VPP** para selecionar um token VPP que tem licenças gratuitas do Portal da Empresa disponíveis. Se você não quiser usar o VPP para implantar o Portal da Empresa, escolha **Não usar VPP** em **Instalar o Portal da Empresa com o VPP**. 

8. Se você optar por registrar com afinidade de usuário, autenticar com o Portal da Empresa e instalar o Portal da Empresa com o VPP, decida se deseja executar o Portal da empresa no modo de aplicativo único até a autenticação. Essa configuração permite que você assegure que o usuário não terá acesso a outros aplicativos até que tenha concluído o registro corporativo. Se você desejar impedir que o usuário acesse esse fluxo até o registro ser concluído, escolha **Sim** em **Executar o Portal da Empresa no modo de aplicativo único até a autenticação**. 

9. Escolha **Configurações de Gerenciamento de Dispositivos** e escolha **Sim** em **Supervisionado**. Dispositivos supervisionados lhe oferecem a maioria das opções de gerenciamento para dispositivos iOS corporativos.

10. Escolha **Sim** em **Registro bloqueado** para garantir que os usuários não possam remover o gerenciamento do dispositivo corporativo. 

11. Escolha uma opção em **Sincronizar com Computadores** para determinar se os dispositivos iOS poderão sincronizar com computadores.

12. Por padrão, a Apple nomeia o dispositivo com o tipo de dispositivo (ou seja, iPad). Se você quiser fornecer um modelo de nome diferente, escolha **Sim** em **Aplicar modelo de nome de dispositivo**. Insira o nome que você deseja aplicar aos dispositivos, em que as cadeias de caracteres *{{SERIAL}}* e *{{DEVICETYPE}}* substituirão o número de série de cada dispositivo e o tipo do dispositivo. Caso contrário, escolha **Não** em **Aplicar modelo de nome de dispositivo**.

13. Selecione **OK**.

14. Escolha **Personalização do Assistente de Instalação** e insira *Departamento de tutorial* para **Nome do Departamento**. Essa cadeia de caracteres é o que os usuários veem quando tocam em **Sobre a configuração** durante a ativação do dispositivo.

15. Em **Telefone do Departamento**, insira um número de telefone. Esse número é exibido quando os usuários tocam no botão **Precisa de ajuda** durante a ativação.

16. Você pode **Mostram** ou **Ocultar** uma série de telas durante a ativação do dispositivo. Para a mais perfeita experiência de registro, defina todas as telas como **Ocultar**.

17. Escolha **OK** > **Criar**.

## <a name="sync-managed-devices-to-intune"></a>Sincronizar dispositivos gerenciados ao Intune

Depois de configurar um token do programa de registro com o portal DEP, ABM ou ASM e atribuir os dispositivos ali existentes ao servidor de MDM, você pode esperar aguardar a sincronização desses dispositivos com o serviço do Intune ou efetuar push de uma sincronização manualmente. Sem uma sincronização manual, dispositivos podem levar até 24 horas para aparecer no portal do Azure.

1. No Intune, no portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista > **Dispositivos** > **Sincronizar**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Atribuir um perfil de registro aos dispositivos iOS

Atribua um perfil do Programa de Registro aos dispositivos antes de registrá-los. Esses dispositivos estão sincronizados com o Intune da Apple e precisam ser atribuídos ao token adequado do servidor no portal DEP, ABM ou ASM.

1. No Intune, no portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha seu token na lista.
2. Escolha **Dispositivos**> escolha dispositivos na lista > **Atribuir perfil**.
3. Em **Atribuir perfil**, escolha um perfil para os dispositivos e, em seguida, escolha **Atribuir**.

## <a name="distribute-devices-to-users"></a>Distribuir dispositivos para usuários

Você configurou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos de DEP. Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune.

## <a name="next-steps"></a>Próximas etapas

Você pode encontrar mais informações sobre outras opções disponíveis para registrar dispositivos iOS.

> [!div class="nextstepaction"]
> [Artigo detalhado sobre o registro no DEP do iOS](device-enrollment-program-enroll-ios.md)

<!--commenting out because inaccurate>
## Clean up resources
<!--If you don't want to use iOS corporate enrolled devices anymore, you can delete them.>
<!--- If the devices are enrolled in Intune, you must first [delete them from the Azure Active Directory portal](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).>
