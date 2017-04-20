---
title: "Pré-requisitos para políticas de MAM | Microsoft Docs"
description: "Este tópico descreve os pré-requisitos para a configuração de usuários antes de criar políticas de gerenciamento de aplicativo móvel."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a85b9f603e022b3296cb16754effd06087074a72
ms.openlocfilehash: 9759c1331a3fb5308e1dbc53564059618a8ef45c
ms.lasthandoff: 04/01/2017


---

# <a name="get-ready-to-configure-app-protection-policies-in-the-azure-portal"></a>Prepare-se para configurar as políticas de proteção do aplicativo no portal do Azure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico descreve os pré-requisitos e as etapas que você deve concluir **antes** de criar políticas de proteção de aplicativo no portal do Azure.

Para compreender como as políticas de proteção de aplicativo do Intune podem proteger os dados da empresa, consulte [Proteger aplicativos e dados usando políticas de proteção de aplicativo](protect-apps-and-data-with-microsoft-intune.md).

## <a name="what-is-the-azure-portal"></a>O que é o portal do Azure?

O portal do Azure é o novo console de administração para criar políticas de proteção de aplicativo. Ele dá suporte aos seguintes cenários de MAM:
- Dispositivos registrados no Intune
- Dispositivos gerenciados por outra solução de gerenciamento de dispositivo móvel (MDM)
- Dispositivos que não são gerenciados por uma solução de MDM (BYOD)

No momento, o **console do administração do Intune** e o **portal do Azure** permitem configurar políticas de proteção de aplicativo.  Considere o seguinte:

* As políticas que você cria no **portal do Azure** têm suporte para **todos os cenários de MAM** listados acima. O **console do administrador do Intune** dá suporte apenas à criação de políticas do **dispositivos registrados e gerenciados pelo Intune**.

* Talvez você não veja todas as configurações de política de aplicativo no console de administração do Intune, uma vez que **novas configurações** só podem ser adicionadas ao **portal do Azure**.

* Se você criar políticas de proteção de aplicativo no console do administrador do Intune **e** no Portal do Azure, a política no **portal do Azure será aplicada aos aplicativos e implantada para usuários**.
    * As políticas de proteção de aplicativo criadas no console de administração do Intune não podem ser importadas no Portal do Azure.  As políticas de proteção de aplicativo devem ser recriadas no Portal do Azure.


* Atualmente, outros **recursos de gerenciamento de aplicativos**, como implantar aplicativos e políticas de configuração de aplicativos, só estão disponíveis no **console de administração do Intune**.


Se você for novo no portal do Azure, leia o tópico [Portal do Azure para políticas de proteção de aplicativo do Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) para obter as noções básicas de como usar o portal do Azure.

Para obter instruções sobre como criar uma política de aplicativo no console de administração do Intune, consulte [Configurar e implantar políticas de proteção de aplicativo no console do Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  <a name="supported-platforms"></a>Plataformas com suporte
- iOS 8.1 ou posterior
- Android 4 ou posterior
- Windows 10

>[!NOTE]
>Começando com a versão 1703, políticas de proteção de aplicativos podem ser definidas para dispositivos Windows 10 no MAM sem o cenário de registro. Para obter detalhes, consulte [Proteger seus dados empresariais usando a WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  <a name="supported-apps"></a>Aplicativos com suporte
* **Aplicativos Microsoft:** esses aplicativos têm o SDK de Aplicativo do Intune interno e não exigem nenhum processamento adicional antes de aplicar as políticas de proteção de aplicativo.
Para ver a lista completa de aplicativos da Microsoft com suporte, vá para a [Galeria de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) na página de parceiros de aplicativos do Microsoft Intune. Clique em um aplicativo para ver os cenários e plataformas com suporte e para ver se o aplicativo dá suporte a várias identidades ou não.

* **Aplicativos de linha de negócios da organização:** é necessário preparar esses aplicativos para incluir o SDK de Aplicativo do Intune antes que seja possível aplicar as políticas de proteção de aplicativo.

  * Para dispositivos que são gerenciados pelo Intune, consulte [Decide how to prepare apps for MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) (Decidir como preparar os aplicativos para MAM).

  * Para dispositivos não gerenciados (como dispositivos do funcionário) ou gerenciados por outra solução de gerenciamento de dispositivo móvel, consulte [Proteger aplicativos de linha de negócios e dados em dispositivos não registrados no Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## <a name="prerequisites"></a>Pré-requisitos

-   **Uma assinatura do Microsoft Intune**. Os usuários precisam de licenças do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para obter aplicativos que têm políticas de proteção de aplicativo.
Você já tem uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se estiver usando o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para gerenciar seus dispositivos. Você também terá uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se tiver adquirido uma licença do EMS (Enterprise Mobility Suite). Se estiver tentando [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]conferir os recursos de MAM, será possível obter uma conta de avaliação na [página do Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Para verificar se você tem uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] no portal do Office, acesse a página **Cobrança**.  Se você tiver uma assinatura, verá [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] como **Ativo** nas assinaturas.

-   **Uma assinatura do Office 365**, que é necessária para o seguinte:

  - Para aplicar políticas de proteção de aplicativo a aplicativos com suporte a várias identidades.

  - Para criar contas corporativas do SharePoint Online e Exchange Online. Não há suporte para o Exchange e o SharePoint locais.

-   **Instalação do Skype for Business Online para autenticação moderna**. Para obter mais informações, consulte [Habilitar a autenticação moderna](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure AD (Azure Active Directory) para criar usuários. O Azure AD autentica os usuários quando eles abrem o aplicativo e inserem suas credenciais de trabalho.

    > [!NOTE]
    > Grupos de usuários devem ser configurados no Azure AD. Grupos de usuários do Intune não podem ser usados para implantar políticas de proteção de aplicativo no portal do Azure.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Criar usuários e atribuir licenças do Microsoft Intune

1.  Entre no [portal do Office](http://portal.office.com) com suas credenciais de administrador.

2.  Adicione usuários, conforme descrito na seção **Etapas para realizar uma avaliação de 30 dias do Intune** do [Guia de avaliação do Intune](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) e, em seguida, atribua as licenças do Intune. Para conceder a um usuário a capacidade de acessar o portal do Office, o portal do Azure AD e o Portal do Azure, atribua a função de **Administrador Global** ao usuário.

5.  Políticas de proteção de aplicativo são implantadas ema grupos de usuários no Azure Active Directory. Para criar grupos de usuários para as políticas de proteção de aplicativo, crie um grupo de usuários, conforme descrito na seção **Criar um grupo de usuários** de [Criar grupos para organizar usuários e dispositivos de assinatura de avaliação](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).

### <a name="assign-roles-to-non-global-admin-users"></a>Atribua funções a usuários administradores não globais

Os administradores globais têm acesso ao [Portal do Azure](https://portal.azure.com).  Se você desejar que usuários que não são administradores globais possam configurar políticas e realizar outras tarefas de gerenciamento de aplicativo móvel, consulte o artigo [Usar atribuições de função para gerenciar acesso para seus recursos de assinatura do Azure](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/).

## <a name="next-steps"></a>Próximas etapas
[Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

