---
title: Configurar o acesso do aplicativo ao Exchange Online | Microsoft Docs
description: "Este tópico descreve como você pode configurar uma política de acesso condicional para aplicativos MAM."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 49b5b50016e2b36a7ad88fdf0a4e3ae2153290ba


---

# <a name="create-an-exchange-online-conditional-access-to-only-allow-apps-supported-by-mam"></a>Crie um acesso condicional para o Exchange Online para permitir apenas aplicativos com suporte para MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico fornece instruções passo a passo sobre como configurar o acesso condicional para o Exchange Online para permitir apenas aplicativos móveis com suporte para políticas de gerenciamento de aplicativos móveis (MAM) do Intune.


## <a name="create-an-exchange-online-policy"></a>Criar uma política do Exchange Online
1.  Entre no [portal do Azure](https://portal.azure.com) que inclui o recurso de acesso do aplicativo. Caso você seja novo na experiência do portal do Azure, leia o tópico [Portal do Azure para políticas de MAM](azure-portal-for-microsoft-intune-mam-policies.md).

2.  Escolha **Procurar > Intune > Folha de gerenciamento de aplicativos móveis do Intune > Configurações** e na seção **acesso condicional**, escolha **Exchange Online**.

  ![Captura de tela da folha de configurações mostrando a seção acesso condicional com a opção Exchange Online em destaque](../media/mam-ca-settings-exo.png)

3.  Na folha **Aplicativos permitidos**, escolha a opção **Permitir aplicativos que dão suporte às políticas de aplicativo do Intune** para permitir que somente aplicativos com suporte para as políticas de MAM do Intune acessem o Exchange Online. Ao selecionar essa opção, a lista de aplicativos com suporte é exibida.

  >[!NOTE]
  >Todos os clientes de email do Exchange Active Sync, incluindo os de email interno no iOS e no Android que se conectam ao Exchange Online, serão impedidos de enviar ou receber emails. Em vez disso, os usuários receberão um único email informando que eles precisam usar o aplicativo de email do Outlook. 
4.   Para aplicar essa política aos usuários, abra a folha **Grupos de usuários com restrições** e escolha **Adicionar grupo de usuário**. Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.

  ![Captura de tela da folha grupos de usuários com restrições com a opção adicionar grupo de usuários em destaque](../media/mam-ca-add-user-group.png)

5.  Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política. Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos. Na folha **Exchange Online**, escolha **Grupos de usuários isentos**. Escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários. Selecione os grupos que você deseja isentar dessa política.  

## <a name="modify-an-existing-policy"></a>Modifique uma política existente
### <a name="add-or-delete-user-groups"></a>Adicione ou exclua grupos de usuários

Para **excluir um grupo de usuários** da lista de **grupos de usuários com restrições**, abra a folha **Grupos de usuários com restrições**, realce o grupo de usuários que você deseja excluir e, em seguida, clique em **reticências(...)** para ver a opção **Excluir**. Escolha **Excluir** para remover o grupo de usuários da lista. Você pode seguir o mesmo procedimento para remover um grupo de usuários da lista do **grupo de usuários isentos**.


## <a name="next-steps"></a>Próximas etapas
[Bloquear aplicativos que não têm autenticação moderna](block-apps-with-no-modern-authentication.md)
### <a name="see-also"></a>Consulte também
[Proteger dados de aplicativos com políticas de MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


