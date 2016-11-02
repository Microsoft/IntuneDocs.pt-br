---
title: "Pré-requisitos para políticas de MAM | Microsoft Intune"
description: "Este tópico descreve os pré-requisitos e configuração dos usuários antes de ser possível criar políticas de gerenciamento de aplicativo móvel."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5778ccc632b72b3cca2593febeccbf7149591275
ms.openlocfilehash: 6d7843286369e2371ea204ac70d2e85e4c086d76


---

# Preparar-se para configurar políticas de gerenciamento de aplicativo móvel no portal do Azure
Este tópico descreve os pré-requisitos e as etapas que você deve concluir **antes** de criar políticas de MAM (gerenciamento de aplicativo móvel) no portal do Azure.

Para compreender como as políticas de MAM do Intune podem proteger os dados da empresa, consulte [Proteger aplicativos e dados usando políticas de gerenciamento de aplicativo móvel](protect-apps-and-data-with-microsoft-intune.md).

## O que é o portal do Azure?
O portal do Azure é o novo console de administração para criar políticas de MAM e dá suporte aos seguintes cenários de MAM:
- **Dispositivos registrados no Intune**
- **Dispositivos gerenciados por outra solução de MDM**
- **Dispositivos que não são gerenciados por uma solução de MDM (BYOD)**


No momento, o **console do administrador do Intune** e o **portal do Azure** permitem configurar políticas de MAM.  Considere o seguinte:

* As políticas que você cria no **portal do Azure** têm suporte para **todos os cenários de MAM** listados acima. O **console do administrador do Intune** dá suporte apenas à criação de políticas do **dispositivos registrados e gerenciados pelo Intune**.
* Talvez você não veja todas as configurações de política de MAM no console do administrador do Intune, uma vez que **novas configurações** só podem ser adicionadas ao **portal do Azure**.
* Se você criar políticas de MAM no console do administrador do Intune **e** no Portal do Azure, a política no **portal do Azure será aplicada aos aplicativos e implantada para usuários**.
    * As políticas de MAM criadas no console de administração do Intune não podem ser importadas no Portal do Azure.  As políticas de MAM devem ser recriadas no Portal do Azure.
* Outros **recursos de gerenciamento de aplicativos**, como implantar aplicativos e políticas de configuração de aplicativos, atualmente só estão disponíveis no **console do administrador do Intune**.


Se você for novo no portal do Azure, leia o tópico [Portal do Azure para políticas de MAM do Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) para obter uma visão geral rápida.

Para obter instruções sobre como criar uma política de MAM usando o console de administração do Intune, consulte [Configurar e implantar políticas de gerenciamento de aplicativos móveis no console do Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  Plataformas com suporte
- iOS 8.1 ou posterior

- Android 4 ou posterior

>[!NOTE]
>Dispositivos Windows não dão suporte a essas políticas de gerenciamento de aplicativo móvel. No entanto, quando registra dispositivos Windows 10 no Intune, você pode usar a Proteção de Informações do Windows, que oferece funcionalidades semelhantes. Para obter detalhes, consulte [Proteger seus dados empresariais usando a WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  Aplicativos com suporte
* **Aplicativos Microsoft:** esses aplicativos têm o SDK de Aplicativo do Intune interno e não exigem nenhum processamento adicional antes de aplicar as políticas de MAM.
Para ver a lista completa de aplicativos da Microsoft com suporte, vá para a [Galeria de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) na página de parceiros de aplicativos do Microsoft Intune. Clique em um aplicativo para ver os cenários e plataformas com suporte e para ver se o aplicativo dá suporte a várias identidades ou não.
* **Aplicativos de linha de negócios da sua organização:** eles requerem a preparação do aplicativo para incluir o SDK de Aplicativo do Intune antes que seja possível aplicar as políticas de MAM.

  * Para dispositivos que são gerenciados pelo Intune, consulte [Decide how to prepare apps for MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) (Decidir como preparar os aplicativos para MAM).
  * Para dispositivos que não são gerenciados (como dispositivos do funcionário) ou para dispositivos que são gerenciados por outra solução de gerenciamento de dispositivo móvel, consulte [Proteger aplicativos de linha de negócios e dados em dispositivos não registrados no Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## Pré-requisitos

-   Uma assinatura do Microsoft Intune.    Os usuários precisam de licenças do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para obter aplicativos que têm políticas de MAM.
Você já tem uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se estiver usando o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para gerenciar seus dispositivos.  Você também terá uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se tiver adquirido uma licença do EMS (Enterprise Mobility Suite). Se estiver experimentando o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para conferir os recursos de MAM, você poderá obter uma conta de avaliação na [Página do Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Para verificar se você tem uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], no portal do Office, vá para a página **Cobrança**.  Você deve ver [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] como **Ativo** nas assinaturas.

-   Uma assinatura do Office 365, que é necessária para o seguinte:
  - Para aplicar políticas de MAM a aplicativos com suporte a várias identidades.
  - Para criar contas corporativas do SharePoint Online e Exchange Online. Não há suporte para o Exchange e o SharePoint locais.
-   Instalação do Skype for Business Online para autenticação moderna. Para obter mais informações, consulte [Habilitar a autenticação moderna](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure AD (Azure Active Directory) para criar usuários. O Azure AD autentica os usuários quando eles abrem o aplicativo e inserem suas credenciais de trabalho.

    > [!NOTE]
    > Grupos de usuários devem ser configurado no Azure AD. Grupos de usuários do Intune não podem ser usados para implantar políticas de MAM no portal do Azure.

### Criar usuários e atribuir licenças do Microsoft Intune

1.  Entre no [portal do Office](http://portal.office.com) com suas credenciais de administrador.

2.  Adicione usuários conforme descrito na seção **Adicionar usuários** [deste](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-2) tópico e atribua licenças do Intune. Para conceder a um usuário a capacidade de acessar o portal do Office, o portal do Azure AD e o Portal do Azure, atribua a função de **Administrador Global** ao usuário.

5.  Políticas de MAM são implantadas para grupos de usuários no Active Directory do Azure. Para criar grupos de usuários para as políticas de MAM, crie um grupo de usuários, conforme descrito na seção **Criar um grupo de usuários** [neste](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) tópico.

### Usuários administradores não globais

Os administradores globais têm acesso ao [Portal do Azure](https://portal.azure.com).  Se quiser que usuários que não são administradores globais possam configurar políticas e realizar outras tarefas de gerenciamento de aplicativo móvel, você poderá atribuir a função de colaborador aos usuários. Para obter instruções detalhadas, consulte [Usar atribuições de função para gerenciar o acesso aos recursos de sua assinatura do Azure](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/).

---------------------------------

A tabela a seguir lista as funções e as permissões que podem ser atribuídas aos usuários administradores.

|||
|--|----|
|**Função**|**Permissões**|
|Administrador global (portal do Office 365)|Acesso ao portal do Office 365 e portal do Azure AD.<br /><br />Acesso ao Portal do Azure (pode realizar tarefas de gerenciamento de função e de aplicativo móvel).|
|Proprietário (Portal do Azure)|Acesso ao Portal do Azure (pode realizar tarefas de gerenciamento de função e de aplicativo móvel).|
|Colaborador (Portal do Azure)|Acesso ao Portal do Azure (pode realizar apenas tarefas de gerenciamento de aplicativo móvel).|




## Próximas etapas
[Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


