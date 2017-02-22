---
title: "Política de acesso condicional local do Exchange | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: como você pode configurar o acesso condicional local do Exchange e o Exchange Online Dedicado herdado no Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581f9be824ea883fd0208abc3b2ecc09174cb911
ms.openlocfilehash: a80d6a19948291cc80e42ad5a9a2f016effb2f37


---

# <a name="how-to-create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune-azure-preview"></a>Como criar uma política de acesso condicional para Exchange local e Exchange Online Dedicado herdado na versão prévia do Microsoft Intune Azure


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Este tópico explica o processo de configuração de acesso condicional para Exchange local com base na conformidade do dispositivo.

Se você tiver um ambiente do Exchange Online Dedicado e precisar descobrir se ele está na configuração nova ou herdada, entre em contato com seu gerente de conta. Para controlar o acesso ao email para Exchange local ou para seu ambiente herdado do Exchange Online dedicado, configure o acesso condicional ao Exchange local no Intune.

## <a name="prerequisites"></a>Pré-requisitos

**Antes** de poder configurar o acesso condicional, verifique o seguinte:

- A versão do Exchange deve ser **Exchange 2010 ou posterior**. Há suporte para a matriz de CAS (Servidor de Acesso de Cliente) do servidor Exchange.
- É preciso usar o **Exchange Connector local do Exchange Active Sync**, que conecta o Intune ao Microsoft Exchange On-Premises. Para obter detalhes sobre o conector, consulte <link>

  - O Exchange Connector local disponível para você no console do Intune é específico ao seu locatário do Intune e não pode ser usado com nenhum outro locatário. Você também deve garantir que o Exchange Connector do seu locatário esteja instalado em **apenas um computador**.

Esse conector deve ser baixado do console de administração do Intune. Para obter informações sobre como configurar o Exchange Connector local, consulte <link to new topic>

O conector pode ser instalado em qualquer computador, desde que o computador seja capaz de se comunicar com o servidor Exchange.

- Esse conector dá suporte a **ambiente de CAS do Exchange**. Você pode tecnicamente instalar o conector no servidor de CAS do Exchange diretamente se desejar, mas não é recomendável, pois ele aumenta a carga no servidor. Ao configurar o conector, você deve configurá-lo para que ele se comunique com um dos servidores de CAS do Exchange.
- O **Exchange ActiveSync** deve ser configurado com autenticação baseada em certificado ou em entrada de credenciais de usuário.

Quando políticas de acesso condicionais são configuradas e direcionadas ao usuário, antes de um usuário se conectar ao email, o **dispositivo** usado deve:

- Estar **registrado** no Intune ou em um computador ingressado no domínio.
- **Registrado no Azure Active Directory**. Além disso, a ID do Exchange ActiveSync do cliente deve estar registrada com o Azure Active Directory.

O AAD DRS será ativado automaticamente para clientes do Intune e do Office 365. Clientes que já tiverem implantado o Serviço de Registro de Dispositivos do ADFS não verão dispositivos registrados no seu Active Directory local. **Isso não se aplica a computadores Windows e dispositivos do Windows Phone**.

- **Em conformidade** com as políticas de conformidade do Intune implantadas nesse dispositivo.

Se o dispositivo não atender às configurações de acesso condicional, uma das mensagens a seguir será apresentara ao usuário quando ele fizer logon:

- Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa, registrar o dispositivo e ativar o email. Esse processo também associa a ID do Exchange ActiveSync do dispositivo ao registro do dispositivo no Azure Active Directory.
- Se o dispositivo não estiver em conformidade, será exibida uma mensagem que direcionará o usuário ao site do Portal da Empresa do Intune ou ao aplicativo Portal da Empresa, no qual ele poderá encontrar informações sobre o problema e como corrigi-lo.

## <a name="support-for-mobile-devices"></a>Suporte para dispositivos móveis

- Windows Phone 8.1 e posterior
- Aplicativo de email nativo no iOS.
- Clientes de email EAS, como Gmail no Android 4 ou versões posteriores.
- Clientes de email EAS com **dispositivos Android for Work:** há suporte somente para os aplicativos **Gmail** e **Nine Work** do **perfil de trabalho** em dispositivos Android for Work. Para obter acesso condicional ao Android para Trabalho, é necessário implantar um perfil de email para os aplicativos Gmail ou Nine Work e implantá-los como uma instalação obrigatória.

>[!NOTE]
>Não há suporte para o aplicativo Microsoft Outlook no Android e iOS.

> O Android para Trabalho está em processo de distribuição entre os locatários do Intune e o processo continuará durante os próximos meses.

Para obter mais informações sobre o status de suporte do Android for Work, leia o comunicado sobre o Android for Work na edição de outubro de 2016 de [O que há de novo no Microsoft Intune](https://docs.microsoft.com/en-us/intune/whats-new/whats-new-archive#october-2016).

## <a name="support-for-pcs"></a>Suporte para computadores

O aplicativo de **Email** do Windows 8.1 e versões posteriores (quando registrado com Intune)


## <a name="configure-exchange-on-premises-access"></a>Configurar o acesso local ao Exchange

1. Escolha a carga de trabalho **Acesso condicional** no Portal do Azure para abrir a folha Local.
2. A folha **Local** mostra o status da política de acesso condicional e os dispositivos que são afetados por ele.
3. Em **Gerenciar**, escolha **Acesso ao Exchange local**.
4. Na folha **Acesso local do Exchange**, escolha **Sim** para habilitar o controle de acesso local do Exchange.

  >[!NOTE]
  >Se você não tiver configurado o conector local do Exchange Active Sync, essa opção estará desabilitada.  Você primeiro deve instalar e configurar esse conector antes de habilitar o acesso condicional para o Exchange local. Para obter mais detalhes, consulte [Instalar o Intune On-premises Exchange Connector](install-intune-on-premises-exchange-connector.md)

5. Em **Atribuição**, escolha **Grupos Incluídos**.  Use o grupo de usuários de segurança que deve ter acesso condicional aplicado.  Isso exigiria que os usuários registrem seus dispositivos no Intune e estejam em conformidade com os perfis de conformidade.
6. Se você desejar excluir certos grupos de usuários, poderá fazer isso escolhendo **Grupos Excluídos** e selecionando um grupo de usuários que você quer isentar da exigência de registro e conformidade do dispositivo.
7. Em **Configurações**, escolha **Notificações do usuário** para modificar a mensagem de email padrão. Esta mensagem é enviada para os usuários cujo dispositivo não está em conformidade e que desejam acessar o Exchange local. O modelo de mensagem usa a linguagem de marcação.  Você também verá a versão prévia da aparência da mensagem conforme você digita. Para saber mais sobre a linguagem de marcação, consulte este [artigo](https://en.wikipedia.org/wiki/Markup_language) da Wikipédia.
8. Na folha **Configurações de acesso avançado do Exchange Active Sync**, defina a regra padrão global para acesso de dispositivos não gerenciados pelo Intune e para regras de nível de plataforma conforme descrito nas próximas duas etapas.
9. Para um dispositivo que não é afetado pelo acesso condicional ou por outras regras, você pode optar por permitir que ele acesse o Exchange ou bloqueá-lo.
  - Quando você define esta opção para permitir o acesso, todos os dispositivos serão capazes de acessar o Exchange local imediatamente.  Dispositivos que pertencem aos usuários nos **Grupos Incluídos** serão bloqueados se forem avaliados posteriormente como não compatível com as políticas de conformidade ou não forem registrados no Intune.
  - Quando você define esta opção para bloquear o acesso, todos os dispositivos serão imediatamente impedidos de acessar o Exchange local inicialmente.  Dispositivos que pertencem aos usuários dos **Grupos Incluídos** obterão acesso depois que o dispositivo for registrado no Intune e avaliado como em conformidade. Em dispositivos Android que não executam o Samsung KNOX Standard, eles sempre serão bloqueados, pois não dão suporte a essa configuração.
10. Em **Exceções de plataforma de dispositivo**, escolha **Adicionar** para especificar as plataformas. Se a configuração **Acesso de dispositivo não gerenciado** for definida como **Bloqueado**, os dispositivos que estão registrados e em conformidade serão permitidos mesmo se houver uma exceção de plataforma a ser bloqueada. Escolha **OK** para salvar as configurações.
11. Na folha **Local**, clique em **Salvar** para salvar a política de acesso condicional.



<!--HONumber=Feb17_HO1-->


