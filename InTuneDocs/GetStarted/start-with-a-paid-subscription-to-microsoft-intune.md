---
# required metadata

title: Guia de início rápido do Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Guia de início rápido do Intune
Este guia de início rápido orienta você ao longo das etapas de configuração de uma assinatura paga do Microsoft Intune, para que você possa a começar de modo fácil e rápido a gerenciar dispositivos móveis e computadores Windows em uso pela sua organização. Você poderá seguir cada etapa na ordem ou simplesmente ignorar se uma etapa não for aplicável às suas necessidades de negócios ou seu ambiente específico.

>[!NOTE]
>Este artigo se concentra na configuração do Intune como um serviço autônomo. Como alternativa, se estiver usando Microsoft System Center Configuration Manager para gerenciar computadores e servidores, você poderá [estender o Configuration Manager para gerenciar dispositivos móveis](https://technet.microsoft.com/library/jj884158.aspx) conectando o Intune com o Configuration Manager em uma implantação híbrida do MDM para gerenciar também dispositivos móveis.

As etapas neste guia de início rápido compartilham muitas das mesmas etapas que estão no [Guia de avaliação do Intune](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune). No entanto, após sua avaliação, e quando estiver pronto para começar a gerenciar seus dispositivos móveis, você precisará tratar de diversos requisitos adicionais. Eles variam dependendo de suas necessidades de negócios e infraestrutura de rede atuais:

-   Sincronização de contas locais do Active Directory com o Intune e o Active Directory do Azure

-   Atualizando registros de domínio público e de serviço DNS com seu registrador de domínios

-   Personalizando recursos do Intune para uso em produção

>[!TIP]
>Se você adquirir, pelo menos, 150 licenças para Microsoft Intune em um plano qualificado, você pode usar o "Benefício do FastTrack Center", um serviço no qual os especialistas da Microsoft trabalharão com você para deixar o ambiente pronto para o Intune. Consulte a [Microsoft Intune Service Benefit Description (Descrição do Benefício do Serviço do Microsoft Intune)](https://technet.microsoft.com/library/mt228265.aspx).


## Antes de começar
Use este guia quando estiver começando a usar uma assinatura paga e estiver pronto para implantar o Intune e fazer alterações em sua infraestrutura de rede existente. Isso pode variar de simplesmente adicionar ou atualizar seus registros DNS internos e externos até sincronizar suas contas de usuários existentes do Active Directory com o Azure Active Directory. Seja qual for a combinação de recursos de gerenciamento de dispositivos móveis do Intune pela qual decidir, você precisará planejar cuidadosamente como o Intune vai interagir com seus serviços e componentes de rede existentes. Especificamente, você deve examinar:

-   **Como você gerenciará a identidade do usuário**: para a maioria das organizações de grande e médio porte, conectar os serviços de diretório existentes ao Intune por meio do Azure Active Directory é a maneira recomendada e mais conveniente para gerenciar a identidade do usuário com o Intune. Isso é especialmente verdadeiro se você já usa outros serviços em nuvem da Microsoft, como o Office 365 ou o Exchange Online. Sincronizar suas contas de usuário existentes usando o [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594) é a maneira rápida e fácil de conectar seu Active Directory local ao Azure Active Directory e configurar uma experiência de autenticação de logon único para seus usuários.

-   **Como o DNS será afetado**: se quiser usar seu próprio nome de domínio em vez do domínio padrão onmicrosoft.com que você recebe ao assinar o Intune pela primeira vez, serão necessárias algumas atualizações de registro DNS público. Atualizações do registro DNS são necessárias para que os dispositivos móveis possam localizar o serviço do Intune e garantir que o serviço de gerenciamento para sua assinatura funcione corretamente para gerenciar todos os dispositivos em uso pela sua organização.

## Tenha os seguintes itens à disposição
Pronto para começar? Você precisará dos seguintes itens para começar a usar sua assinatura paga do Intune:

### Um dispositivo com navegador da Web habilitado para Silverlight
Você precisará dele para acessar o console de administração do Intune, no qual gerenciará dispositivos, aplicativos e políticas. Você também precisará de um navegador da Web para acessar o portal da empresa baseado na web quando não estiver acessando o aplicativo do portal da empresa de um dispositivo móvel. Para facilitar, você pode usar a configuração “modo de privacidade” no mesmo navegador que usa para a administração do Intune (por exemplo: no Internet Explorer, é possível clicar em **Ferramentas** &gt; **Navegação InPrivate**)).

>[!TIP]
>Devido a esse requisito, não há suporte para o navegador Microsoft Edge para acessar o console de administração do Intune.


### Certificados para dispositivos móveis
Se for gerenciar dispositivos iOS ou Windows Phone com o Intune, você precisará de certificados e contas para recuperar esses certificados. Você não precisará de nenhum certificado adicional para gerenciar dispositivos Android.

- Nenhum certificado é necessário para usuários do **Windows Phone 8.1** que instalam o aplicativo do portal da empresa da Loja. No entanto, um [certificado de assinatura de código Symantec](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do) é necessário para **Windows Phone 8.0** ou para usar o Intune para implantar o aplicativo do portal da empresa em dispositivos Windows Phone 8.1.

>[!NOTE]
>Este guia de início rápido pressupõe que seus usuários obtenham o aplicativo do Portal da Empresa pela Loja em um dispositivo Windows Phone 8.1 ou posterior. Para obter informações sobre o suporte ao Windows Phone 8.0, consulte [Set up Windows Phone 8.0 management with Microsoft Intune (Configurar o gerenciamento do Windows Phone 8,0 com o Microsoft Intune)](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune).

- Não há requisitos de certificado para **computadores Windows** ou **dispositivos Windows RT** ao registrar computadores Windows como dispositivos ou [instalar o cliente de computador Windows para o Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune).

- Para dispositivos **iOS** ou **Mac OS X**, você precisará solicitar um certificado do Apple Push Notification Service, conforme descrito na etapa 3 em [Configurar gerenciamento do iOS e Mac com o Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

### Próximas etapas
É hora de começar a usar o Guia de início rápido do Intune!

>[!div class="step-by-step"]
[**Entrar no Intune** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)


<!--HONumber=May16_HO1-->


