---
title: Apagamento completo ou seletivo em dispositivos usando o Intune
titleSuffix: Intune on Azure
description: "Saiba como fazer um apagamento seletivo dos dados da empresa em um dispositivo ou um apagamento completo para redefinir o dispositivo para as configurações de fábrica."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44d1695b3f0297276376fb9cb4367c1411aa31b2
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="use-full-or-selective-wipe"></a>Usar o apagamento completo ou seletivo

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Você pode apagar os aplicativos e dados de dispositivos gerenciados pelo Intune que não são mais necessários, que estão sendo realocados ou estão ausentes. Para isso, o Intune fornece funcionalidades de apagamento completo e apagamento seletivo. Os usuários também podem emitir um comando de apagamento remoto de dados no dispositivo do aplicativo de Portal da Empresa do Intune em dispositivos privados registrados no Intune.

  > [!NOTE]
  > Este tópico trata apenas do apagamento de dispositivos gerenciados pelo gerenciamento de dispositivo móvel do Intune. Você também pode usar o [portal do Azure](https://portal.azure.com) para [apagar dados da empresa dos aplicativos](https://docs.microsoft.com/intune-classic/deploy-use/wipe-managed-company-app-data-with-microsoft-intune). Você também pode [desativar computadores gerenciados com o software cliente do Intune](https://docs.microsoft.com/intune-classic/deploy-use/retire-a-windows-pc-with-microsoft-intune).

## <a name="full-wipe"></a>Apagamento completo

O **Apagamento Completo** restaura um dispositivo para suas configurações padrão de fábrica, removendo todas as configurações e os dados da empresa e do usuário. O dispositivo é removido do Intune. O apagamento completo é útil para redefinir um dispositivo antes de fornecê-lo a um novo usuário ou quando o dispositivo é roubado ou perdido.  **Tenha cuidado ao selecionar o apagamento completo. Os dados no dispositivo não podem ser recuperados**.


> [!Warning]
> Dispositivos Windows 10 RTM (dispositivos anteriores ao Windows 10 versão 1511) com menos de 4 GB de RAM podem se tornar inacessíveis se forem apagados. Para acessar um dispositivo Windows 10 que parou de responder, você pode inicializar o dispositivo de uma unidade USB.


**Para realizar uma apagamento completo (redefinição de fábrica) de um dispositivo**:

1.  Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.

2.  Escolha o nome do dispositivo que você deseja apagar.

3.  Na folha que mostra o nome do dispositivo, escolha **Redefinição de fábrica** e selecione **Sim** para confirmar o apagamento.

Se o dispositivo estiver ligado e conectado, leva menos de 15 minutos para que um comando de apagamento seja propagado para todos os tipos de dispositivo.

### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Para excluir dispositivos no portal do Active Directory do Azure

1.  Navegue até [http://aka.ms/accessaad](http://aka.ms/accessaad) ou clique em **Administrador** &gt; **Azure AD** de [https://portal.office.com](https://portal.office.com).

2.  Faça logon com sua ID da organização usando o link no lado esquerdo da página.

3.  Se não tiver uma, crie uma assinatura do Azure. Isso não deverá exigir um cartão de crédito ou pagamento se você tiver uma conta paga (clique no link de assinatura **Register your free Azure Active Directory** [Registrar seu Azure Active Directory gratuito]).

4.  Selecione **Active Directory** e selecione sua organização.

5.  Selecione a guia **Usuários** .

6.  Selecione o usuário cujos dispositivos que deseja excluir.

7.  Escolha **Dispositivos**.

8.  Remova os dispositivos conforme apropriado, como aqueles que não estão mais em uso, ou aqueles que têm definições imprecisas.


## <a name="selective-wipe"></a>Apagamento seletivo

O **apagamento seletivo** remove os dados da empresa, incluindo dados de MAM (gerenciamento de aplicativo móvel), quando aplicável, configurações e perfis de email do dispositivo. O apagamento seletivo deixa os dados pessoais do usuário no dispositivo. O dispositivo é removido do Intune. As tabelas a seguir descrevem quais dados são removidos e o efeito nos dados que permaneceram no dispositivo após o apagamento seletivo. (As tabelas são organizadas por plataforma).

**iOS**

|Tipo de dados|iOS|
|-------------|-------|
|Aplicativos da empresa e dados associados instalados pelo Intune|Aplicativos são desinstalados. Dados de aplicativo da empresa são removidos.<br /><br />Os dados dos aplicativos da Microsoft que usam o gerenciamento de aplicativos móveis são removidos. O aplicativo não é removido.|
|Configurações|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|
|Configurações do perfil de certificado|Certificados são removidos e revogados.|
|Agente de gerenciamento|O perfil de gerenciamento é removido.|
|Email|Os perfis de email provisionados usando o Intune são removidos e o email armazenado em cache no dispositivo é excluído.|
|Outlook|Mensagens de email recebidas pelo aplicativo Microsoft Outlook para iOS são removidas.|
|Sair do Active Directory do Azure (AAD)|O registro no AAD é removido.|
|Contatos | Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos.  Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. <br /> <br />Atualmente, há suporte somente para aplicativo do Outlook.

**Android**

|Tipo de dados|Android|Android Samsung KNOX Standard|
|-------------|-----------|------------------------|
|Links da Web|Removidos.|Removidos.|
|Aplicativos Google Play não gerenciados|Aplicativos e dados permanecem instalados.|Aplicativos e dados permanecem instalados.|
|Aplicativos de linha de negócios não gerenciados|Aplicativos e dados permanecem instalados.|Os aplicativos são desinstalados e dados locais do aplicativo são removidos como resultado. Nenhum dado fora do aplicativo (por exemplo, em um cartão SD) é removido.|
|Aplicativos Google Play gerenciados|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados, mas não são removidos.|
|Aplicativos de linha de negócios gerenciadas|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|Dados de aplicativo são removidos. O aplicativo não é removido. Dados protegidos pela criptografia de MAM fora do aplicativo (por exemplo, um cartão SD) permanecem criptografados e inutilizáveis, mas não são removidos.|
|Configurações|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|Removidos.|
|Configurações do perfil de certificado|Certificados revogados, mas não removidos.|Certificados removidos e revogados.|
|Agente de gerenciamento|O privilégio de administrador do dispositivo é revogado.|O privilégio de administrador do dispositivo é revogado.|
|Email|N/D (não há suporte para perfis de email em dispositivos Android)|Os perfis de email provisionados usando o Intune são removidos e o email armazenado em cache no dispositivo é excluído.|
|Outlook|Mensagens de email recebidas pelo aplicativo Microsoft Outlook para Android são removidas.|Mensagens de email recebidas pelo aplicativo Microsoft Outlook para Android são removidas.|
|Sair do Active Directory do Azure (AAD)|Registro no AAD removido.|Registro no AAD removido.|
|Contatos | Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos.  Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. <br /> <br />Atualmente, há suporte somente para aplicativo do Outlook.|Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos.  Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. <br /> <br />Atualmente, há suporte somente para aplicativo do Outlook.

**Android for Work**

Executar a limpeza seletiva em um dispositivo Android para Trabalho remove todos os dados, os aplicativos e as configurações no perfil de trabalho nesse dispositivo. Isso desativa o dispositivo de gerenciamento com o Intune. Não há suporte para o apagamento completo no Android para Trabalho.

**Windows**

|Tipo de dados|Windows 8.1 (MDM) e Windows RT 8.1|Windows RT|Windows Phone 8 e Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Aplicativos da empresa e dados associados instalados pelo Intune|Arquivos protegidos por EFS terão sua chave revogada e o usuário não conseguirá abrir os arquivos.|Não removerão aplicativos da empresa.|Aplicativos instalados originalmente por meio do portal da empresa são desinstalados. Dados de aplicativo da empresa são removidos.|Os aplicativos são desinstalados e a chaves de sideload são removidas.|
|Configurações|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|As configurações definidas pela política do Intune deixam de ser impostas e os usuários podem alterar as configurações.|
|Configurações dos perfis de Wi-Fi e VPN|Removidos.|Removidos.|Não há suporte.|Removidos.|
|Configurações do perfil de certificado|Certificados removidos e revogados.|Certificados removidos e revogados.|Não há suporte.|Certificados removidos e revogados.|
|Email|Remove o email habilitado para EFS, que inclui o aplicativo Mail para emails e anexos do Windows.|Não há suporte.|Os perfis de email provisionados usando o Intune são removidos e o email armazenado em cache no dispositivo é excluído.|Remove o email habilitado para EFS, que inclui o aplicativo Mail para emails e anexos do Windows. Remove contas de email que foram provisionadas pelo Intune.|
|Sair do Active Directory do Azure (AAD)|Não.|Não.|Registro no AAD removido.|Não aplicável. O Windows 10 não dá suporte ao apagamento seletivo de dispositivos associados ao Azure Active Directory.|

**Para realizar um apagamento seletivo**:

1.  Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.

2.  Escolha o nome do dispositivo que você deseja apagar.

3.  Na folha que mostra o nome do dispositivo, escolha **Remover dados da emp...** (significa Remover dados da empresa) e escolha **Sim** para confirmar o apagamento.

Se o dispositivo estiver ligado e conectado, leva menos de 15 minutos para que um comando de apagamento seja propagado para todos os tipos de dispositivo.
