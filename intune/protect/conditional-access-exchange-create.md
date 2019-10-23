---
title: Criar política de Acesso Condicional do Exchange
titleSuffix: Microsoft Intune
description: Configurar o Acesso Condicional do Exchange Local e do Exchange Online Dedicado herdado no Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.reviewer: stama
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c18da57282a190dec363e3dfbde5293f5228cb0b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504627"
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Criar uma política de Acesso Condicional para o Exchange local e o Exchange Online Dedicado herdado

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Este artigo mostra como configurar o Acesso Condicional para o Exchange local com base na conformidade do dispositivo.

Se você tiver um ambiente do Exchange Online Dedicado e precisar descobrir se ele está na configuração nova ou herdada, entre em contato com seu gerente de conta. Para controlar o acesso ao email para Exchange local ou para seu ambiente herdado do Exchange Online dedicado, configure o Acesso Condicional ao Exchange local no Intune.

## <a name="before-you-begin"></a>Antes de começar

Antes de poder configurar o Acesso Condicional, verifique se as seguintes configurações existem:

- Sua versão do Exchange é **Exchange 2010 SP1 ou posterior**. Há suporte para a matriz de CAS (Servidor de Acesso de Cliente) do servidor Exchange.

- Você precisa instalar e usar o [conector do Exchange local do Exchange Active Sync](exchange-connector-install.md), que conecta o Intune ao Exchange local.

    >[!IMPORTANT]  
    >O Intune é compatível com vários conectores do Exchange locais por assinatura.  No entanto, cada conector do Exchange local é específico a um único locatário do Intune e não pode ser usado com nenhum outro locatário.  Se você tiver mais de uma organização do Exchange local, poderá configurar um conector separado para cada organização do Exchange.

- O conector para uma organização do Exchange local pode ser instalado em qualquer computador, desde que o computador possa se comunicar com o servidor do Exchange.

- Esse conector dá suporte a **ambiente de CAS do Exchange**. O Intune dá suporte à instalação direta do conector no servidor CAS do Exchange, mas é recomendável instalá-lo em um computador separado devido à carga adicional que o conector coloca no servidor. Ao configurar o conector, você deve configurá-lo para que ele se comunique com um dos servidores de CAS do Exchange.

- O **Exchange ActiveSync** precisa ser configurado com autenticação baseada em certificado ou com entrada de credenciais de usuário.

- Quando políticas de Acesso Condicionais são configuradas e direcionadas ao usuário, antes de um usuário se conectar ao email, o **dispositivo** usado deverá:
  - Estar **registrado** no Intune ou em um computador ingressado no domínio.
  - **Registrado no Azure Active Directory**. Além disso, a ID do Exchange ActiveSync do cliente deve estar registrada com o Azure Active Directory.

- O DRS (Serviço de Registro de Dispositivos) do Azure AD será ativado automaticamente para clientes do Intune e do Office 365. Clientes que já implantaram o Serviço de Registro de Dispositivos do ADFS não veem os dispositivos registrados no Active Directory local. **Isso não se aplica a computadores Windows e dispositivos do Windows Phone**.

- **Estar em conformidade** com qualquer política de conformidade do dispositivo implantada nesse dispositivo.

- Se o dispositivo não atender às configurações de Acesso Condicional, uma das mensagens a seguir será apresentada ao usuário quando ele entrar:
  - Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, a mensagem será exibida com instruções sobre como instalar o aplicativo Portal da Empresa, registrar o dispositivo e ativar o email. Esse processo também associa a ID do Exchange ActiveSync do dispositivo ao registro do dispositivo no Azure Active Directory.
  - Se o dispositivo não estiver em conformidade, será exibida uma mensagem que direcionará o usuário ao site do Portal da Empresa do Intune ou ao aplicativo Portal da Empresa, no qual ele poderá encontrar informações sobre o problema e como corrigi-lo.

### <a name="support-for-mobile-devices"></a>Suporte para dispositivos móveis

- Windows Phone 8.1 e posterior
- Aplicativo de email nativo no iOS.
- Clientes de email EAS, como Gmail no Android 4 ou versões posteriores.
- **Dispositivos de perfil de trabalho do Android** de clientes de email EAS: Há suporte apenas para os aplicativos **Gmail** e **Nine Work for Android Enterprise** no **perfil de trabalho** em dispositivos de perfil de trabalho do Android. Para obter Acesso Condicional para trabalhar com perfis de trabalho do Android, implante um perfil de email para os aplicativos Gmail ou Nine Work for Android Enterprise e implante esses aplicativos como uma instalação obrigatória.

> [!NOTE]
> Não há suporte para o Microsoft Outlook para Android e iOS por meio do conector local do Exchange. Se você quiser aproveitar as políticas de Acesso Condicional do Azure Active Directory e as Políticas de Proteção de Aplicativo do Intune com o Outlook para iOS e Android em suas caixas de correio locais, consulte [Usando a Autenticação Moderna Híbrida com o Outlook para iOS e Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth). 

### <a name="support-for-pcs"></a>Suporte para computadores

O aplicativo nativo de **Email** do Windows 8.1 e versões posteriores (quando registrado no MDM com Intune)

## <a name="configure-exchange-on-premises-access"></a>Configurar o acesso local ao Exchange

Antes de poder usar o procedimento a seguir para configurar o controle de acesso local do Exchange, você deve instalar e configurar pelo menos um [conector do Exchange local do Intune](exchange-connector-install.md) para o Exchange local.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)

2. Vá para **Acesso ao Exchange** e selecione **Acesso ao Exchange local**. 

3. No painel **Acesso ao Exchange local**, escolha **Sim** para *Habilitar o controle de acesso do Exchange local*.

4. Em **Atribuição**, escolha **Selecionar grupos para incluir** e selecione um ou mais grupos para configurar o acesso. 

   Os membros dos grupos selecionados têm a política de Acesso Condicional para acesso ao Exchange local aplicada a eles. Os usuários que recebem essa política precisam registrar seus dispositivos no Intune e atender aos perfis de conformidade antes de poderem acessar o Exchange local.

5. Para excluir grupos, escolha **Selecionar grupos para excluir** e, em seguida, selecione um ou mais grupos isentos de requisitos para registrar dispositivos e ficar em conformidade com os perfis de conformidade antes de acessar o Exchange local. 

6. Depois, defina as configurações para o conector do Exchange local do Intune.  Em **Configurar** no **Painel de acesso do Exchange**, selecione **Conector local do Exchange ActiveSync** e selecione o conector para a organização do Exchange que você deseja configurar.

7. Em **Configurações**, escolha **Notificações do usuário** para modificar a mensagem de email padrão que será enviada aos usuários se o dispositivo deles não estiver em conformidade e se quiserem acessar o Exchange local. O modelo de mensagem usa a linguagem de marcação.  Também é possível ver a versão prévia de aparência da mensagem conforme você digita.
   > [!TIP]
   > Para saber mais sobre a linguagem de marcação, consulte este [artigo](https://en.wikipedia.org/wiki/Markup_language) da Wikipédia.
 
   Selecione **OK** para salvar suas edições e concluir a configuração de acesso ao Exchange local.

8. Em seguida, selecione **Configurações avançadas de acesso do Exchange Active Sync** para abrir o painel *Configurações avançadas de acesso do Exchange ActiveSync* no qual você configura as regras de acesso ao dispositivo:  

   - Para **Acesso de dispositivo não gerenciado**, defina a regra padrão global para acesso de dispositivos que não são afetados pelo Acesso Condicional ou outras regras:

     - **Permitir acesso**: todos os dispositivos podem acessar o Exchange local imediatamente. Os dispositivos que pertencem aos usuários nos grupos configurados como incluídos no procedimento anterior serão bloqueados se, posteriormente, forem avaliados como não compatíveis com as políticas ou não registrados no Intune.

     - **Bloquear acesso** e **Quarentena**: todos os dispositivos serão imediatamente impedidos de acessar o Exchange local inicialmente. Os dispositivos que pertencem aos usuários nos grupos configurados como incluídos no procedimento anterior obtêm acesso após o registro do dispositivo no Intune e são avaliados como compatíveis. 

       Dispositivos Android que *não* executam o Samsung Knox Standard não dão suporte a essa configuração e estão sempre bloqueados.

   -  Para **Exceções de plataforma de dispositivo**, selecione **Adicionar** e especifique os detalhes da plataforma conforme necessário para o seu ambiente. 
   
      Se a configuração **Acesso de dispositivo não gerenciado** estiver definida como **Bloqueado**, os dispositivos que estão registrados e em conformidade serão permitidos mesmo se houver uma exceção de plataforma para bloqueá-los.  
   
   Selecione **OK** para salvar suas edições.

9. Selecione **Salvar** para salvar a política de Acesso Condicional do Exchange.

Em seguida, crie uma política de conformidade e a atribua aos usuários do Intune para avaliar os dispositivos móveis deles. Confira [Introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="see-also"></a>Consulte também

[Solucionar problemas do Intune Exchange Connector local no Microsoft Intune](https://support.microsoft.com/help/4471887)
