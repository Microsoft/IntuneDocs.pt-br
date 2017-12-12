---
title: "Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo | Microsoft Docs"
titlesuffix: Azure portal
description: "Saiba como usar as políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b4ccc107521ae7f199ad2b37b86b573995e83c4d
ms.sourcegitcommit: 3285b08f1a290d6f3be3bb1cfdf40508c27c53ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

É possível usar políticas de configuração do aplicativo com aplicativos gerenciados que dão suporte ao SDK de Aplicativo do Intune, mesmo em dispositivos que não estão registrados. 

1. Entre no Portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** + **Intune**.
3. Selecione a carga de trabalho de **Aplicativos móveis**.
4. Escolha **Políticas de configuração do aplicativo** no grupo **Gerenciar** e escolha **Adicionar**.
5. Defina os seguintes detalhes:
    - **Nome**  
      O nome do perfil que será exibido no Portal do Azure.
    - **Descrição**  
      A descrição do perfil que será exibida no Portal do Azure.
    - **Tipo de registro de dispositivo**  
      Selecione **Gerenciar aplicativos**.
6. Selecione **Aplicativo associado** para escolher o aplicativo que pretende configurar. Selecione o aplicativo na lista de aplicativos que foram aprovados e sincronizados com o Intune.
7. Para cada configuração compatível no aplicativo, digite o **Nome** e **Valor** e escolha as reticências (**…**).  
    Para excluir uma configuração, escolha as reticências (**…**) e selecione **Excluir**.  
    Os aplicativos habilitados pelo SDK de Aplicativo do Intune dão suporte a configurações em pares chave-valor. Para saber mais sobre quais configurações de chave-valor são compatíveis, consulte a documentação para cada aplicativo.  
    Além disso, você pode usar os tokens que serão preenchidos dinamicamente com os dados gerados pelo aplicativo.

## <a name="configuration-values-for-using-tokens"></a>Valores de configuração para usar tokens

O Intune pode gerar determinados tokens e enviá-los ao aplicativo gerenciado. Por exemplo, se sua configuração de aplicativo puder usar uma configuração de email, será possível adicionar um email dinâmico usando um token. Digite o nome esperado pelo aplicativo no campo **Nome** e, em seguida, digite `\{\{mail\}\}` no campo de **Valor**.

O Intune dá suporte aos seguintes tipos de token nas definições de configuração:

- \{\{userprincipalname\}\}—por exemplo, **John@contoso.com**
- \{\{mail\}\}—por exemplo, **John@contoso.com**
- \{\{partialupn\}\}—por exemplo, **João**
- \{\{accountid\}\}—por exemplo, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{userid\}\}—por exemplo, **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—por exemplo, **João Silva**
- \{\{PrimarySMTPAddress\}\}— por exemplo, **testuser@ad.domain.com** 


> [!Note]  
> Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.