---
title: Proteger o email para o Exchange local | Microsoft Docs
description: Proteja e controle o acesso ao email da empresa no Exchange local com acesso condicional.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3098a301550413a982d3ce9664646f7dfc0b1d1f
ms.contentlocale: pt-br
ms.lasthandoff: 05/31/2017


---

# <a name="protect-email-access-to-exchange-on-premises-and-legacy-exchange-online-dedicated-with-intune"></a>Proteger o acesso de email ao Exchange no Local e ao Exchange Online Dedicado herdado com o Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Você pode configurar o acesso a email do controle de acesso condicional para o Exchange Local ou para o ambiente herdado do Exchange Online Dedicado usando o Microsoft Intune.
Para saber mais sobre como o acesso condicional funciona, leia o artigo [Proteger acesso a email e a serviços do O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

> [!NOTE]
> Se você tiver um ambiente do Exchange Online Dedicado e precisar descobrir se ele está com a configuração nova ou herdada, contate seu gerente de conta.

## <a name="before-you-begin"></a>Antes de começar

Certifique-se de verificar o seguinte:

-   A versão do Exchange deve ser **Exchange 2010 ou posterior**. Há suporte para matrizes CAS (Servidor de Acesso para Cliente) do Exchange Server.

-   É necessário usar o [conector do Exchange local do Intune](intune-on-premises-exchange-connector.md), que conecta o Intune ao Exchange local. Isso lhe permite gerenciar dispositivos por meio do console do Intune.

    -   O Exchange Connector local disponível para você no console do Intune é específico ao seu locatário do Intune e não pode ser usado com nenhum outro locatário. Recomendamos que você verifique também se o Exchange Connector de seu locatário está instalado **em apenas um computador**.

        Baixe o conector por meio do console de administração do Intune. Para obter uma explicação sobre como configurar o Exchange Connector local, consulte [configure Exchange on-premises connector for on-premises or hosted Exchange](intune-on-premises-exchange-connector.md) (configurar o conector local do Exchange para Exchange local ou hospedado).

    -   É possível instalar o conector em qualquer computador, desde que o computador possa se comunicar com o Exchange Server.

    -   O conector dá suporte ao **ambiente de CAS do Exchange**. Tecnicamente, você poderá instalar o conector no servidor CAS do Exchange diretamente se desejar. No entanto, não recomendamos fazer isso, pois ele aumenta a carga no servidor. Ao configurar o conector, é necessário configurá-lo para se comunicar com um dos servidores CAS do Exchange.

-   É necessário configurar o **Exchange ActiveSync** com uma entrada de credencial de usuário ou de autenticação baseada em certificado.

### <a name="device-compliance-requirements"></a>Requisitos de conformidade do dispositivo

Ao configurar políticas de acesso condicional e direcioná-las a um usuário, antes que um usuário possa se conectar a seu email, o **dispositivo** usado deve ser/estar:

-  Um computador ingressado no domínio ou **registrado** no Intune.

-  **Registrado no Azure Active Directory**. Além disso, a ID do Exchange ActiveSync do cliente deve estar registrada com o Azure Active Directory.

  O serviço Registro do Dispositivo do Azure Active Directory é ativado automaticamente para clientes do Intune e Office 365. Clientes que já tiverem implantado o Serviço de Registro de Dispositivos do ADFS não verão dispositivos registrados no seu Active Directory local. **Isso não se aplica a computadores Windows e dispositivos do Windows Phone**.

-   **Em conformidade** com as políticas de conformidade do Intune implantadas nesse dispositivo.

### <a name="how-conditional-access-works-with-exchange-on-premises"></a>Como o acesso condicional funciona com o Exchange local

O diagrama a seguir ilustra o fluxo usado pelas políticas de acesso condicional para o Exchange no Local para decidir se os dispositivos serão permitidos ou bloqueados.

![Diagrama que mostra os pontos de decisão que determinam se um dispositivo tem acesso permitido ou bloqueado ao Exchange no Local](../media/ConditionalAccess8-2.png)

Se uma política de acesso condicional não for atendida, haverá uma janela de 10 minutos entre o bloqueio do dispositivo e o usuário receberá uma das seguintes mensagens de quarentena ao entrar:

- Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo Portal da Empresa, registrar o dispositivo e ativar o email. Esse processo também associa a ID do Exchange ActiveSync do dispositivo com o registro do dispositivo no Azure Active Directory.

-   Se o dispositivo não estiver em conformidade, será exibida uma mensagem que direcionará o usuário ao site do Portal da Empresa do Intune ou ao aplicativo Portal da Empresa, no qual ele poderá encontrar informações sobre o problema e como corrigi-lo.

## <a name="support-for-mobile-devices"></a>Suporte para dispositivos móveis
Há suporte para os recursos a seguir:
-   Windows Phone 8.1 e posterior.

-   O aplicativo de email nativo no iOS.

-   Clientes de email do Exchange ActiveSync, como Gmail no Android 4 ou posterior.
-   Clientes de email do Exchange ActiveSync em dispositivos **Android para Trabalho**: há suporte apenas aos aplicativos **Gmail** e **Nine Work** no **perfil de trabalho** em dispositivos Android para Trabalho. Para que o acesso condicional funcione com o Android para Trabalho, é necessário implantar um perfil de email para os aplicativos Gmail ou Nine Work e também implantá-los como uma instalação obrigatória. 

> [!NOTE]
> Não há suporte para o aplicativo Microsoft Outlook para Android e iOS.

## <a name="support-for-pcs"></a>Suporte para computadores
Há suporte para o seguinte:
-   O aplicativo de **Email** do Windows 8.1 e posterior (quando o computador é registrado no Intune).

##  <a name="configure-a-conditional-access-policy"></a>Configurar uma política de acesso condicional

1.  No [console de Administração do Microsoft Intune](https://manage.microsoft.com), selecione **Política** > **Acesso Condicional** > **Política do Exchange local**.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Configure a política com as configurações necessárias: ![Captura de tela da página de política do Exchange no Local](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **Bloqueie o acesso ao Exchange no Local em aplicativos de email se o dispositivo for não compatível ou não estiver registrado no Microsoft Intune:** ao marcar essa opção, os dispositivos não gerenciados pelo Intune ou que não estiverem em conformidade com uma política de conformidade não terão permissão para acessar os serviços do Exchange.

  - **Substituição de regra padrão – Sempre permitir que dispositivos registrados e em conformidade acessem o Exchange:** ao marcar essa opção, os dispositivos registrados no Intune e que estão em conformidade com as políticas de conformidade têm permissão para acessar o Exchange.
  Essa regra substitui a **Regra Padrão**, o que significa que, mesmo que você defina a **Regra Padrão** para colocar em quarentena ou bloquear o acesso, os dispositivos registrados e que estão em conformidade ainda poderão acessar o Exchange.

  - **Grupos de Destino**: selecione os grupos de usuários do Intune que devem registrar seus dispositivos no Intune antes de poderem acessar o Exchange.

  - **Grupos Isentos**: selecione os grupos de usuários do Intune que são isentos da política de acesso condicional. Os usuários dessa lista serão isentos mesmo se também estiverem na lista **Grupos de Destino**.

  - **Exceções de Plataforma**: escolha **Adicionar Regra** para configurar uma regra que define os níveis de acesso para as famílias e os modelos de dispositivos móveis especificados. Como esses dispositivos podem ser de qualquer tipo, também é possível configurar os tipos de dispositivos que não têm suporte no Intune.

  - **Regra Padrão:** para um dispositivo que não está coberto por nenhuma das outras regras, é possível optar por permitir que ele acesse o Exchange, bloqueie-o ou coloque-o em quarentena. Quando você define a regra para permitir o acesso, para dispositivos que estão registrados e são compatíveis, o acesso a email é concedido automaticamente para dispositivos iOS, Windows e Samsung KNOX. O usuário não precisa passar por nenhum processo para receber seus emails.
      - Em dispositivos Android que não executam o Samsung KNOX, os usuários recebem um email de quarentena, que inclui um passo a passo guiado para verificar o registro e a conformidade antes de poderem acessar o email. Se você definir a regra para bloquear o acesso ou colocar dispositivos em quarentena, todos os dispositivos serão impedidos de obter acesso ao Exchange, independentemente de já estarem registrados ou não no Intune. Para impedir que dispositivos registrados e em conformidade sejam afetados por essa regra, marque a caixa **Substituição de Regra Padrão**.
>[!TIP]
>Se sua intenção for primeiro bloquear todos os dispositivos antes de conceder acesso ao email, escolha a regra Bloquear acesso ou Colocar em quarentena. A regra padrão se aplica a todos os tipos de dispositivos – portanto, os tipos de dispositivo configurados como exceções da plataforma sem suporte no Intune também são afetados.

  - **Notificação do Usuário**: além do email de notificação enviado pelo Exchange, o Intune envia um email que contém etapas para desbloquear o dispositivo. Você pode editar a mensagem padrão para personalizá-la às suas necessidades. Caso o dispositivo do usuário esteja bloqueado antes que ele receba o email de notificação do Intune que contém instruções de correção (esse email é entregue na caixa de correio do Exchange do usuário), ele poderá usar um dispositivo desbloqueado ou outro método para acessar o Exchange e exibir a mensagem.
      - Isso é especialmente verdadeiro quando a **Regra Padrão** está definida como bloquear ou colocar em quarentena. Nesse caso, o usuário precisará acessar sua loja de aplicativos, baixar o aplicativo Portal da Empresa da Microsoft e registrar o dispositivo. Isso é aplicável a dispositivos iOS, Windows e Samsung KNOX. Para dispositivos que não executam o Samsung KNOX, é necessário enviar o email de quarentena para uma conta de email alternativa. O usuário precisa copiar o email em seu dispositivo bloqueado para concluir o processo de registro e conformidade.
  > [!NOTE]
  > Para que o Exchange possa enviar o email de notificação, é necessário especificar a conta usada para enviar o email de notificação.
  >
  > Para obter mais detalhes, consulte [Configurar conector do Exchange no Local para Exchange no Local ou hospedado](intune-on-premises-exchange-connector.md).

3.  Quando terminar, selecione **Salvar**.

-   Não é necessário implantar a política de acesso condicional, ela entra em vigor imediatamente.

-   Depois que um usuário configurar um perfil do Exchange ActiveSync, poderá levar de uma a três horas até que o dispositivo seja bloqueado (caso ele não seja gerenciado pelo Intune).

-   Se um usuário bloqueado registrar o dispositivo no Intune e corrigir a não conformidade, o acesso ao email será desbloqueado em até dois minutos.

-   Se o usuário cancelar o registro do Intune, poderá levar de uma a três horas até que o dispositivo seja bloqueado.

**Para ver alguns cenários de exemplo de como você poderá configurar uma política de acesso condicional para proteger o acesso ao dispositivo, consulte [Proteger o acesso a email – cenários de exemplo](restrict-email-access-example-scenarios.md).**

## <a name="next-steps"></a>Próximas etapas
-   [Proteger o acesso ao SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

-   [Proteger o acesso ao Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)

