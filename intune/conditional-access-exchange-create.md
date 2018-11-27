---
title: Criar política de acesso condicional do Exchange
titlesuffix: Microsoft Intune
description: Configurar o acesso condicional do Exchange local e do Exchange Online Dedicado herdado no Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 0a539000153ad45b5256e4e63086fa72fee44947
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186070"
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Criar uma política de acesso condicional para o Exchange local e o Exchange Online Dedicado herdado

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra como configurar o acesso condicional para o Exchange local com base na conformidade do dispositivo.

Se você tiver um ambiente do Exchange Online Dedicado e precisar descobrir se ele está na configuração nova ou herdada, entre em contato com seu gerente de conta. Para controlar o acesso ao email para Exchange local ou para seu ambiente herdado do Exchange Online dedicado, configure o acesso condicional ao Exchange local no Intune.

## <a name="before-you-begin"></a>Antes de começar

Antes de poder configurar o acesso condicional, verifique o seguinte:

- A versão do Exchange deve ser **Exchange 2010 SP1 ou posterior**. Há suporte para a matriz de CAS (Servidor de Acesso de Cliente) do servidor Exchange.

- É preciso usar o [conector do Exchange local do Exchange Active Sync](exchange-connector-install.md), que conecta o Intune ao Exchange local.

    >[!IMPORTANT]
    >O conector do Exchange local é específico ao seu locatário do Intune e não pode ser usado com nenhum outro locatário. Agora, o Intune é compatível com vários conectores do Exchange locais por assinatura. Se você tiver mais de uma organização do Exchange local, poderá configurar um conector separado para cada organização do Exchange.

- O conector para uma organização do Exchange local pode ser instalado em qualquer computador, desde que o computador seja capaz de se comunicar com o servidor do Exchange.

- Esse conector dá suporte a **ambiente de CAS do Exchange**. Tecnicamente, você pode instalar o conector no servidor de CAS do Exchange diretamente se desejar, mas isso não é recomendável, pois ele aumenta a carga no servidor. Ao configurar o conector, você deve configurá-lo para que ele se comunique com um dos servidores de CAS do Exchange.

- O **Exchange ActiveSync** precisa ser configurado com autenticação baseada em certificado ou com entrada de credenciais de usuário.

- Quando políticas de acesso condicionais são configuradas e direcionadas ao usuário, antes de um usuário se conectar ao email, o **dispositivo** usado deve:
    - Estar **registrado** no Intune ou em um computador ingressado no domínio.
    - **Registrado no Azure Active Directory**. Além disso, a ID do Exchange ActiveSync do cliente deve estar registrada com o Azure Active Directory.
<br></br>
- O DRS (Serviço de Registro de Dispositivos) do Azure AD será ativado automaticamente para clientes do Intune e do Office 365. Clientes que já implantaram o Serviço de Registro de Dispositivos do ADFS não veem os dispositivos registrados no Active Directory local. **Isso não se aplica a computadores Windows e dispositivos do Windows Phone**.

- **Estar em conformidade** com qualquer política de conformidade do dispositivo implantada nesse dispositivo.

- Se o dispositivo não atender às configurações de acesso condicional, uma das mensagens a seguir será apresentada ao usuário quando ele entrar:
    - Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa, registrar o dispositivo e ativar o email. Esse processo também associa a ID do Exchange ActiveSync do dispositivo ao registro do dispositivo no Azure Active Directory.
    - Se o dispositivo não estiver em conformidade, será exibida uma mensagem que direcionará o usuário ao site do Portal da Empresa do Intune ou ao aplicativo Portal da Empresa, no qual ele poderá encontrar informações sobre o problema e como corrigi-lo.

### <a name="support-for-mobile-devices"></a>Suporte para dispositivos móveis

- Windows Phone 8.1 e posterior
- Aplicativo de email nativo no iOS.
- Clientes de email EAS, como Gmail no Android 4 ou versões posteriores.
- **Dispositivos de perfil de trabalho do Android** de clientes de email EAS: há suporte apenas para os aplicativos **Gmail** e **Nine Work for Android Enterprise** no **perfil de trabalho** em dispositivos de perfil de trabalho do Android. Para obter acesso condicional para trabalhar com perfis de trabalho do Android, implante um perfil de email para os aplicativos Gmail ou Nine Work for Android Enterprise e implante esses aplicativos como uma instalação obrigatória.

> [!NOTE]
> Não há suporte para o Microsoft Outlook para Android e iOS por meio do conector local do Exchange. Se você quiser aproveitar as políticas de Acesso Condicional do Azure Active Directory e as Políticas de Proteção de Aplicativo do Intune com o Outlook para iOS e Android em suas caixas de correio locais, consulte [Usando a Autenticação Moderna Híbrida com o Outlook para iOS e Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth). 

### <a name="support-for-pcs"></a>Suporte para computadores

O aplicativo nativo de **Email** do Windows 8.1 e versões posteriores (quando registrado com Intune)


## <a name="configure-exchange-on-premises-access"></a>Configurar o acesso local ao Exchange

1. Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.

1. Depois de entrar com êxito, você verá o **Painel do Azure**.

1. Escolha  **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

1. Escolha **Intune** e você verá o **Painel do Intune**.

1. Escolha **Acesso local**. O painel **Acesso local** mostra o status da política de acesso condicional e os dispositivos que são afetados por ela.

1. Em **Gerenciar**, escolha **Acesso ao Exchange local**.

1. No painel **Acesso local do Exchange**, escolha **Sim** para habilitar o controle de acesso local do Exchange.

    > [!NOTE]
    > Se você não tiver configurado o conector local do Exchange Active Sync, essa opção estará desabilitada.  Você primeiro deve instalar e configurar pelo menos um conector antes de habilitar o acesso condicional ao Exchange local. Para obter mais detalhes, consulte [Instalar o Intune On-premises Exchange Connector](exchange-connector-install.md)

1. Em **Atribuição**, escolha **Grupos Incluídos**.  Use o grupo de usuários de segurança que deve ter acesso condicional aplicado. Esta ação exigiria que os usuários registrem seus dispositivos no Intune e estejam em conformidade com os perfis de conformidade.

1. Se você desejar excluir certos grupos de usuários, poderá fazer isso escolhendo **Grupos Excluídos** e selecionando um grupo de usuários que você queira isentar da exigência de registro e conformidade do dispositivo.

1. Em **Configurações**, escolha **Notificações do usuário** para modificar a mensagem de email padrão. Esta mensagem é enviada para os usuários cujo dispositivo não está em conformidade e que desejam acessar o Exchange local. O modelo de mensagem usa a linguagem de marcação.  Também é possível ver a versão prévia de aparência da mensagem conforme você digita.
    > [!TIP]
    > Para saber mais sobre a linguagem de marcação, consulte este [artigo](https://en.wikipedia.org/wiki/Markup_language) da Wikipédia.

1. No painel **Configurações de acesso avançado do Exchange Active Sync**, defina a regra padrão global para acesso de dispositivos não gerenciados pelo Intune e para regras de nível de plataforma, conforme descrito nas próximas duas etapas.

1. Para um dispositivo que não é afetado pelo acesso condicional ou por outras regras, você pode optar por permitir que ele acesse o Exchange ou bloqueá-lo.

   - Quando você define esta opção para permitir o acesso, todos os dispositivos serão capazes de acessar o Exchange local imediatamente.  Dispositivos que pertencem aos usuários nos **Grupos Incluídos** serão bloqueados se forem avaliados posteriormente como não compatível com as políticas de conformidade ou não forem registrados no Intune.
   - Quando você define esta opção para bloquear o acesso, todos os dispositivos serão imediatamente impedidos de acessar o Exchange local inicialmente.  Dispositivos que pertencem a usuários dos **Grupos Incluídos** obtém acesso depois que o dispositivo for registrado no Intune e avaliado como em conformidade. Em dispositivos Android que não executam o Samsung Knox Standard, eles sempre serão bloqueados, pois não há suporte para essa configuração.

1. Em **Exceções de plataforma de dispositivo**, escolha **Adicionar** para especificar as plataformas. Se a configuração **acesso de dispositivo não gerenciado** estiver definida como **bloqueado**, os dispositivos que estão registrados e em conformidade serão permitidos mesmo se houver uma exceção de plataforma a ser bloqueada. Escolha **OK** para salvar as configurações.

1. No painel **Local**, clique em **Salvar** para salvar a política de acesso condicional.

## <a name="create-azure-ad-conditional-access-policies-in-intune"></a>Criar políticas de acesso condicional do Azure AD no Intune

A partir da versão 1704 do Intune, os administradores podem criar políticas de acesso condicional do Microsoft Azure AD no Portal do Azure no Intune, de modo que não seja mais necessário alternar entre as cargas de trabalho do Azure e do Intune.

> [!IMPORTANT]
> Você precisa ter uma licença Premium do Azure AD para criar políticas de acesso condicional do Azure AD no portal do Intune no Azure.

### <a name="to-create-azure-ad-conditional-access-policy"></a>Para criar uma política de acesso condicional do Azure AD

1. No **Painel do Intune**, escolha **Acesso condicional**.

2. No painel **Políticas**, escolha **Nova política** para criar a nova política de acesso condicional do Microsoft Azure AD.

## <a name="see-also"></a>Consulte também

[Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
