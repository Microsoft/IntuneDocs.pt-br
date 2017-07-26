---
title: "Proteger aplicativos LOB em dispositivos não registrados"
description: "Este tópico descreve como preparar seus aplicativos de linha de negócios personalizados para que você possa aplicar políticas de gerenciamento de aplicativo móvel que podem ajudar a evitar a perda de dados."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1627627ab1744f963d738dcedde6a772bb3ae663
ms.sourcegitcommit: 5eb209ae48173ddfdbbab131f12f3ac3498dcd87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2017
---
# <a name="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune"></a>Proteger aplicativos de linha de negócios e dados em dispositivos não registrados no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Políticas de gerenciamento de aplicativos móveis (MAM) ajudam a proteger dados da empresa, restringindo ações que poderiam vazar dados da empresa e impor requisitos de acesso de dados, como o PIN do aplicativo. Para aplicar políticas de MAM nos aplicativos de linha de negócios iOS e Android, você deve primeiro encapsular o aplicativo com a Ferramenta de Encapsulamento de Aplicativo do Microsoft Intune. O encapsulamento de aplicativo é o processo de aplicação de uma camada de gerenciamento a um aplicativo móvel sem exigir nenhuma alteração nele e de sua distribuição aos usuários.  

Este tópico explica as etapas necessárias para aplicar políticas de MAM a aplicativos que os usuários acessam em **dispositivos de propriedade dos funcionários que não são gerenciados** e dispositivos gerenciados por uma **solução de MDM (gerenciamento de dispositivo móvel) de terceiros**.  Para preparar os aplicativos de linha de negócios executados em **dispositivos registrados no Intune MDM**, consulte [Decidir como preparar os aplicativos para gerenciamento de aplicativos móveis com o Microsoft Intune](/intune/apps-prepare-mobile-application-management).


##  <a name="step-1-prepare-the-app"></a>Etapa 1: preparar o aplicativo

Antes de aplicar as políticas de MAM a um aplicativo, você deve primeiro encapsular o aplicativo usando a Ferramenta de Disposição de Aplicativo do Microsoft Intune para [iOS](prepare-ios-apps-for-mo/intune/apps-prepare-mobile-application-managementoid](/intune/app-wrapper-prepare-android) ou usar o [SDK do Aplicativo do Intune](/intune/app-sdk) para integrar manualmente os recursos de Proteção de Aplicativo do Intune.

Para saber mais sobre como usar a Ferramenta de Encapsulamento de Aplicativos em relação ao SDK, consulte [Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune](/intune/apps-prepare-mobile-application-management).

## <a name="step-2-add-the-app"></a>Etapa 2: adicionar o aplicativo

Para associar seu aplicativo de linha de negócios com as políticas de MAM, é necessário adicionar os detalhes do aplicativo à sua assinatura/locatário do Intune usando as seguintes etapas:

1. No [portal do Azure](https://portal.azure.com/), vá para **Gerenciamento de aplicativos móveis do Intune** > **Configurações** e escolha **Aplicativos de linha de negócios**.

  ![Captura de tela da folha de configurações com a opção linha de negócios](../media/mam-azure-portal-lob-on-settings.png)

2. Na folha **Aplicativos da linha de negócios**, escolha **Adicionar um aplicativo personalizado**.

  ![Captura de tela da folha de aplicativos da linha de negócios com o botão Adicionar aplicativo personalizado na parte superior](../media/mam-azure-portal-add-lob-app-action.png)
3.  Nomeie o aplicativo, o identificador de pacote em um campo Identificador de aplicativo e a plataforma (iOS ou Android).

  ![Captura de tela da folha Adicionar um aplicativo personalizado](../media/mam-azure-portal-add-app-details.png)

  Esta etapa ajuda a criar uma lista exclusiva de seu aplicativo. O aplicativo também será exibido na lista de aplicativos de destino de uma política de MAM do seu locatário, conforme descrito na próxima etapa.

## <a name="step-3-apply-mam-policies"></a>Etapa 3: aplicar políticas MAM
Depois dos metadados do aplicativo serem carregados para o serviço, o aplicativo aparecerá na lista de aplicativos. Agora, é possível [criar uma nova política ou usar uma política existente](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) e aplicá-la ao aplicativo de linha de negócios adicionado na etapa 2.

>[!IMPORTANT]
>Você deve direcionar a política MAM aos usuários que pretendem usar o aplicativo encapsulado.  Os usuários que não têm essa política implantada não poderão usar o aplicativo.


  ![Captura de tela da folha Lista de destino de aplicativos com o novo aplicativo de linha de negócios exibido](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>Etapa 4: distribuir o aplicativo
É possível implantar aplicativos para seus usuários das seguintes maneiras:
* Para dispositivos registrados em uma solução de MDM de terceiros, você pode distribuir os aplicativos por meio de sua solução de MDM.
* Para dispositivos que não são gerenciados por qualquer solução de MDM, uma solução personalizada será necessária. Os usuários devem baixar e instalar o aplicativo em seu dispositivo.

## <a name="change-the-metadata"></a>Alterar os metadados
Se você precisar alterar os detalhes do aplicativo, como o nome do aplicativo ou o identificador de pacote, será necessário [remover o aplicativo](#remove-apps) e [adicioná-lo](#step-2-add-the-app) com os novos metadados.

##  <a name="remove-apps"></a>Remover aplicativos
É possível remover um aplicativo de linha de negócios da lista de aplicativos. Isso removerá o aplicativo da lista e removerá a associação com políticas de MAM, mas não removerá ou desinstalará o aplicativo do dispositivo do usuário.  

1.  No [portal do Azure](https://portal.azure.com/), vá para **Gerenciamento de aplicativos móveis do Intune** > **Configurações**. Na folha **Configurações**, escolha **Linha de negócios** para abrir a lista de aplicativos existentes.  
2.  Escolha o aplicativo que você deseja remover e escolha o menu **(…) contexto**.

  ![Captura de tela da folha de aplicativos da linha de negócios com reticências](../media/mam-azure-portal-lob-context-menu.png)
3.  Escolha **Excluir Aplicativo** para excluir o aplicativo.

  ![Captura de tela da folha linha de negócios com a opção de exclusão do aplicativo](../media/mam-azure-portal-delete-app.png)

  Isso removerá os aplicativos da lista de aplicativos da linha de negócios e da lista de destino de aplicativos na política de MAM.
