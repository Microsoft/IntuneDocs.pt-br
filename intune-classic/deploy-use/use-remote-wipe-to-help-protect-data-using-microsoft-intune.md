---
title: Usar o apagamento remoto para ajudar a proteger dados
description: O Intune fornece recursos de apagamento completo e apagamento seletivo para remover dados corporativos confidenciais e remover o acesso a muitos recursos corporativos.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 036899c5e438355cc10da8ab2bd47ec0830c9946
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="help-protect-your-data-with-full-or-selective-wipe-using-microsoft-intune"></a>Ajude a proteger os dados com apagamento completo ou seletivo usando o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Você pode apagar os aplicativos e dados de dispositivos gerenciados pelo Intune que não são mais necessários, que estão sendo realocados ou estão ausentes. Para isso, o Intune fornece funcionalidades de apagamento completo e apagamento seletivo. Os usuários também podem emitir um comando de apagamento remoto de dados no dispositivo do aplicativo de Portal da Empresa do Intune em dispositivos privados registrados no Intune.

  > [!NOTE]
  > Este tópico trata apenas do apagamento de dispositivos gerenciados pelo gerenciamento de dispositivo móvel do Intune. Você também pode usar o [portal do Azure](https://portal.azure.com) para [apagar dados da empresa dos aplicativos](wipe-managed-company-app-data-with-microsoft-intune.md). Você também pode [desativar computadores gerenciados com o software cliente do Intune](retire-a-windows-pc-with-microsoft-intune.md).

## <a name="full-wipe"></a>Apagamento completo

O **Apagamento Completo** restaura um dispositivo para suas configurações padrão de fábrica, removendo todas as configurações e os dados da empresa e do usuário. O dispositivo é removido do Intune. O apagamento completo é útil para redefinir um dispositivo antes de fornecê-lo a um novo usuário ou quando o dispositivo é roubado ou perdido.  **Tenha cuidado ao selecionar o apagamento completo. Os dados no dispositivo não podem ser recuperados**.


> [!Warning]
> Dispositivos Windows 10 RTM (dispositivos anteriores ao Windows 10 versão 1511) com menos de 4 GB de RAM podem se tornar inacessíveis se forem apagados. Para acessar um dispositivo Windows 10 que parou de responder, você pode inicializar o dispositivo de uma unidade USB.

### <a name="remotely-wipe-a-device-from-the-intune-administrator-console"></a>Apague um dispositivo remotamente usando o Console Administração do Intune

1.  Selecione os dispositivos a serem apagados. Você pode encontrá-los por usuário ou por dispositivo.

    -   **Por usuário:**

        1.  No [Console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Usuários**.

        2.  Escolha o nome do usuário cujo dispositivo móvel deseja apagar. Escolha **Exibir Propriedades**.

        3.  Na página **Propriedades** do usuário, escolha **Dispositivos** e selecione o nome do dispositivo móvel que deseja apagar. Para selecionar vários dispositivos, use Ctrl + clique.

    -   **Por dispositivo:**

        1.  No [Console do administrador do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos Móveis**.

         ![Iniciando uma operação de desativação ou apagamento](../media/dev-sa-wipe.png)

        2.  Clique em **Dispositivos** e escolha o nome do dispositivo móvel que deseja apagar. Para selecionar vários dispositivos, use Ctrl + clique.

2.  Escolher **Desativar/Apagar**.

3.  É exibida uma mensagem de confirmação, perguntando se você deseja desativar o dispositivo.

    -   Para realizar um **Apagamento seletivo**, que remove somente aplicativos e dados da empresa, escolha **Sim**.

    -   Para executar um **Apagamento completo**, que apaga todos os aplicativos e dados e retorna o dispositivo para as configurações padrão de fábrica, escolha **Apague o dispositivo antes de desativá-lo**. Essa ação se aplica a todas as plataformas, exceto Windows 8.1. **Não é possível recuperar dados removidos por um apagamento completo**.

Se o dispositivo estiver ligado e conectado, leva menos de 15 minutos para que um comando de apagamento seja propagado para todos os tipos de dispositivo.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Para excluir dispositivos no portal do Active Directory do Azure

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
|Email|N/A. Consulte o item do Outlook.|Os perfis de email provisionados usando o Intune são removidos e o email armazenado em cache no dispositivo é excluído.|
|Outlook|Emails recebidos pelo aplicativo do Microsoft Outlook para Android serão removidos, mas somente se o Outlook estiver protegido pelas políticas MAM. Caso contrário, o Outlook não será apagado ao cancelar o registro.|Emails recebidos pelo aplicativo do Microsoft Outlook para Android serão removidos, mas somente se o Outlook estiver protegido pelas políticas MAM. Caso contrário, o Outlook não será apagado ao cancelar o registro.|
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

## <a name="wipe-encryption-file-system-efs-enabled-content"></a>Apagar conteúdo habilitado para EFS (sistema de arquivos com criptografia)
O apagamento seletivo de conteúdo criptografados com EFS é suportado pelo Windows 8.1 e Windows RT 8.1. Os pontos a seguir se aplicam a um apagamento seletivo de conteúdo habilitado para EFS:

-   Somente os aplicativos e dados protegidos por EFS que usam o mesmo domínio de Internet como a conta do Intune são apagados seletivamente. Para obter mais informações, consulte [Apagamento Seletivo do Windows para Gerenciamento de Dados do Dispositivo](http://technet.microsoft.com/library/dn486874.aspx).

-   Se houver que qualquer alteração feita no domínio associado ao EFS, as alterações podem levar até 48 horas para que os aplicativos e dados usando o novo domínio possam ser apagados seletivamente.

-   Todos os domínios registrados com o Intune serão apagados.

Os dados e os aplicativos que atualmente têm suporte apagamento seletivo do EFS são:

-   Aplicativo de email para o Windows

-   Pastas de trabalho

-   Pastas e arquivos criptografados pelo EFS. Para obter mais informações, consulte as [Práticas recomendadas para Encrypting File System](http://support.microsoft.com/kb/223316).

-   Se sua organização mantém sua identidade no Active Directory, ele deve usar a ferramenta de sincronização de diretório (DirSync) para sincronizar informações em AAD para que o apagamento seletivo do EFS funcione corretamente.  Para obter mais informações sobre o DirSync, consulte o [Cenário de sincronização de diretório](http://technet.microsoft.com/library/dn441212.aspx) na documentação do Azure Active Directory.

## <a name="monitor-retire-wipe-and-delete-actions"></a>Monitorar ações de desativamento, apagamento e exclusão
Para obter um relatório dos dispositivos que foram desativados, apagados ou excluídos:

1.  No [Console de administração do Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Histórico de Dispositivo**.

2.  Forneça uma data de início e uma de término para o relatório e escolha **Exibir Relatório**.

Este relatório também mostra quem executou a ação.

### <a name="see-also"></a>Consulte também
[Desativar dispositivos](retire-devices-from-microsoft-intune-management.md)

[Apagamento seletivo do Windows para o gerenciamento de dados de dispositivos](http://technet.microsoft.com/library/dn486874.aspx)
