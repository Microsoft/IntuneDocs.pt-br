---
title: Políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo
titleSuffix: Microsoft Intune
description: Saiba como configurar políticas para aplicativos gerenciados sem registro de dispositivo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 06c1119b474d82c4d00db3276179b962ff5b5a44
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755554"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

É possível usar políticas de configuração do aplicativo com aplicativos gerenciados que dão suporte ao SDK de Aplicativo do Intune, mesmo em dispositivos que não estão registrados. 

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Políticas de configuração de aplicativo** > **Adicionar** > **Aplicativos gerenciados**.
3. Na página **Conceitos Básicos**, configure os seguintes detalhes:
    - **Nome**: O nome do perfil que será exibido no Portal do Azure.
    - **Descrição**: A descrição do perfil que será exibida no Portal do Azure.
    - **Tipo de registro do dispositivo**: aplicativos gerenciados está selecionado.
4. Escolha **Selecionar aplicativos públicos** ou **Selecionar aplicativos personalizados** para escolher o aplicativo a ser configurado. Selecione o aplicativo na lista de aplicativos que foram aprovados e sincronizados com o Intune.
5. Clique em **Avançar** para exibir a página **Configurações**.
6. Para cada configuração compatível no aplicativo, digite o **Nome** e **Valor**. 

   Os aplicativos habilitados pelo SDK de Aplicativo do Intune dão suporte a configurações em pares chave-valor. Para saber mais sobre quais configurações de chave-valor são compatíveis, consulte a documentação para cada aplicativo. Observe que você pode usar tokens que serão preenchidos dinamicamente com os dados gerados pelo aplicativo. Para saber mais, confira [Valores de configuração para usar tokens](~/apps/app-configuration-policies-managed-app.md#configuration-values-for-using-tokens). Para obter informações sobre as definições da política de configuração do aplicativo Outlook para iOS, confira [Gerenciar a configuração do aplicativo Outlook para iOS com o Microsoft Intune](https://technet.microsoft.com/library/mt813789(v=exchg.150).aspx).

    Para excluir uma configuração, escolha as reticências ( **…** ) e selecione **Excluir**.  

7. Clique em **Avançar** para exibir a página **Atribuições**.
8. Clique em **Selecionar grupos para incluir**.
9. Escolha um grupo no painel **Selecionar grupos para incluir** e clique em **Selecionar**.
10. Clique em **Selecionar grupos para excluir** para exibir o painel relacionado.
11. Escolha os grupos que você deseja excluir e, em seguida, clique em **Selecionar**.

    >[!NOTE]
    >Ao adicionar um grupo, se nenhum outro grupo ainda tiver sido incluído para um determinado tipo de atribuição, ele será pré-selecionado e ficará inalterável para outros tipos de atribuição de inclusão. Assim, esse grupo que foi usado, não poderá ser usado como um grupo excluído.

12. Clique em **Avançar** para exibir a página **Revisar + criar**.
13. Clique em **Criar** para adicionar a política de configuração do aplicativo ao Intune.

## <a name="configuration-values-for-using-tokens"></a>Valores de configuração para usar tokens

O Intune pode gerar determinados tokens e enviá-los ao aplicativo gerenciado. Por exemplo, se sua configuração de aplicativo puder usar uma configuração de email, será possível adicionar um email dinâmico usando um token. Digite o nome esperado pelo aplicativo no campo **Nome** e, em seguida, digite `\{\{mail\}\}` no campo de **Valor**.

O Intune dá suporte aos seguintes tipos de token nas definições de configuração. Não há suporte para outros pares chave-valor personalizados.

- \{\{userprincipalname\}\} – por exemplo, John@contoso.com
- \{\{mail\}\} –por exemplo, John@contoso.com
- \{\{partialupn\}\} – por exemplo, João
- \{\{accountid\}\} – por exemplo, fc0dc142-71d8-4b12-bbea-bae2a8514c81
- \{\{userid\}\} – por exemplo, 3ec2c00f-b125-4519-acf0-302ac3761822
- \{\{username\}\} – exemplo, João Silva
- \{\{PrimarySMTPAddress\}\} – por exemplo, testuser@ad.domain.com

> [!Note]  
> Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.
