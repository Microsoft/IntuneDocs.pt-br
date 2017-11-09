---
title: "Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo | Microsoft Docs"
titlesuffix: Azure portal
description: "Saiba como usar as políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 750ce7dbb0dccf08757e076826e2d3650b6e6ab5
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Você pode usar políticas de configuração de aplicativo com aplicativos gerenciados que dão suporte ao SDK de Aplicativo do Intune mesmo em dispositivos que não estão registrados. 

1. Entre no Portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** + **Intune**.
3. Selecione a carga de trabalho de **Aplicativos móveis**.
4. Clique em **Políticas de configuração de aplicativo**, no grupo **Gerenciar** e, em seguida, clique em **Adicionar**.
5. Defina os seguintes detalhes:
    - **Nome**  
      O nome do perfil que será exibido no Portal do Azure.
    - **Descrição**  
      A descrição do perfil que será exibida no Portal do Azure.
    - **Tipo de registro de dispositivo**  
      Selecione **Gerenciar aplicativos**.
6. Selecione **Aplicativo associado** para escolher o aplicativo que pretende configurar. Selecione o aplicativo na lista de aplicativos que foram aprovados e sincronizados com o Intune.
7. Para cada definição de configuração com suporte no aplicativo, digite o **Nome** e o **Valor** e clique nas reticências (**...** ).  
    Para excluir uma configuração, clique nas reticências (**...** ) e selecione **Excluir**.  
    Aplicativos habilitados para SDK de Aplicativo do Intune dão suporte a configurações de pares chave e valor. Consulte a documentação para cada aplicativo para obter mais informações sobre quais configurações de chave e valor têm suporte.  
    Além disso, você pode usar os tokens que serão preenchidos dinamicamente com os dados gerados pelo aplicativo.

## <a name="configuration-values-using-tokens"></a>Valores de configuração usando tokens

Determinados tokens podem ser gerados e enviados para o aplicativo gerenciado pelo Intune. Por exemplo, se sua configuração de aplicativo puder usar uma configuração de email, você poderá adicionar um email dinâmico usando um token. Digite o nome esperado pelo aplicativo no campo **Nome** e, em seguida, digite `\{\{mail\}\}` no campo de **Valor**.

O Intune dá suporte aos seguintes tipos de token nas definições de configuração:

- \{\{userprincipalname\}\} – (Exemplo: **John@contoso.com**)
- \{\{mail\}\} – (Exemplo: **John@contoso.com**)
- \{\{partialupn\}\} – (Exemplo: **Samuel**)
- \{\{accountid\}\} – (Exemplo: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} – (Exemplo: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} – (Exemplo: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} – (Exemplo: **Samuel Ferreira**)
- \{\{PrimarySMTPAddress\}\} – (Exemplo: testuser@ad.domain.com) 


> [!Note]  
> Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.