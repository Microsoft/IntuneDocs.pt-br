---
title: Políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo
titlesuffix: Microsoft Intune
description: Saiba como configurar políticas para aplicativos gerenciados sem registro de dispositivo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cad4e1d6bcb47981dfb40a1146a3f5148724e08a
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43330085"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

É possível usar políticas de configuração do aplicativo com aplicativos gerenciados que dão suporte ao SDK de Aplicativo do Intune, mesmo em dispositivos que não estão registrados. 

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione a carga de trabalho **Aplicativos clientes**.
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
    
Os aplicativos habilitados pelo SDK de Aplicativo do Intune dão suporte a configurações em pares chave-valor. Para saber mais sobre quais configurações de chave-valor são compatíveis, consulte a documentação para cada aplicativo. Observe que você pode usar tokens que serão preenchidos dinamicamente com os dados gerados pelo aplicativo. Para obter informações sobre as definições da política de configuração do aplicativo Outlook para iOS, confira [Gerenciar a configuração do aplicativo Outlook para iOS com o Microsoft Intune](https://technet.microsoft.com/en-us/library/mt813789(v=exchg.150).aspx).

## <a name="configuration-values-for-using-tokens"></a>Valores de configuração para usar tokens

O Intune pode gerar determinados tokens e enviá-los ao aplicativo gerenciado. Por exemplo, se sua configuração de aplicativo puder usar uma configuração de email, será possível adicionar um email dinâmico usando um token. Digite o nome esperado pelo aplicativo no campo **Nome** e, em seguida, digite `\{\{mail\}\}` no campo de **Valor**.

O Intune dá suporte aos seguintes tipos de token nas definições de configuração. Não há suporte para outros pares chave-valor personalizados.

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
