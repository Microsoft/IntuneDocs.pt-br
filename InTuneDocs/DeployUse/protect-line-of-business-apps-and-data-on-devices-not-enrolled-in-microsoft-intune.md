---
title: "Proteger aplicativos LOB em dispositivos não registrados | Microsoft Intune"
description: "Este tópico descreve como preparar seus aplicativos de linha de negócios personalizados para que você possa aplicar políticas de gerenciamento de aplicativo móvel que podem ajudar a evitar a perda de dados."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9bf5764d1e1bd73fd62e5033b2309fc8d5a912e4
ms.openlocfilehash: bc5d1b429157e6a6b24f4eb319be50b635466317


---

# <a name="protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune"></a>Proteger aplicativos de linha de negócios e dados em dispositivos não registrados no Microsoft Intune

Políticas de Gerenciamento de aplicativos móveis (MAM) ajudam a proteger dados da empresa, restringindo ações que poderiam vazar dados da empresa e impor requisitos de acesso de dados, como o PIN do aplicativo. Para aplicar políticas MAM nos aplicativos de linha de negócios iOS e/ou Android, você deve primeiro encapsular o aplicativo com a Ferramenta de Disposição do Aplicativo do Microsoft Intune.  Disposição de aplicativo é o processo de aplicação de uma camada de gerenciamento para um aplicativo móvel sem exigir nenhuma alteração ao aplicativo subjacente.  Depois que o aplicativo é disposto, você pode aplicar políticas MAM a ele e distribuí-lo aos seus usuários finais.  

Este tópico explica as etapas necessárias para aplicar políticas MAM em aplicativos que são acessados em **dispositivos de propriedade dos funcionários que não são gerenciados** e dispositivos que são gerenciados por uma **solução de MDM (gerenciamento de dispositivo móvel) de terceiros**.  Para preparar os aplicativos de linha de negócios que são executados em **dispositivos registrados no Intune MDM**, consulte [Decidir como preparar os aplicativos para gerenciamento de aplicativos móveis com o Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).


##  <a name="step-1-prepare-the-app"></a>Etapa 1: preparar o aplicativo
Antes de aplicar as políticas MAM a um aplicativo, você deve primeiro encapsular o aplicativo com a Ferramenta de Disposição do Aplicativo do Microsoft Intune.  Para obter instruções sobre como baixar e usar a ferramenta de disposição do aplicativo, consulte as seguintes páginas:

- [Preparar aplicativos iOS para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)
- [Preparar aplicativos Android para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

>[!IMPORTANT]  
>Esta versão da ferramenta de disposição do aplicativo, que dá suporte a dispositivos não registrados no Intune, tem suporte para iOS e está disponível na visualização pública para Android. É possível baixar a ferramenta de [neste repositório GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) para iOS e [neste repositório GitHub](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview) para Android.

## <a name="step-2-add-the-app"></a>Etapa 2: adicionar o aplicativo

Para associar seu aplicativo de linha de negócios com as políticas de MAM, você deve adicionar os detalhes do aplicativo para sua assinatura/locatário do Intune usando as seguintes etapas:

1. No [portal do Azure](https://portal.azure.com/), vá para **Gerenciamento de aplicativos móveis do Intune > Configurações** e escolha **Aplicativos de linha de negócios**.

  ![Captura de tela da folha de configurações com a opção linha de negócios](../media/mam-azure-portal-lob-on-settings.png)

2. Na folha **Aplicativos da linha de negócios**, escolha **Adicionar um aplicativo personalizado**.

  ![Captura de tela da folha de aplicativos da linha de negócios com o botão Adicionar aplicativo personalizado na parte superior](../media/mam-azure-portal-add-lob-app-action.png)
3.  Forneça um nome para o aplicativo, o identificador de pacote em um campo Identificador de aplicativo e a plataforma (iOS ou Android).

  ![Captura de tela da folha Adicionar um aplicativo personalizado](../media/mam-azure-portal-add-app-details.png) Esta etapa ajuda a criar uma lista exclusiva do seu aplicativo.  O aplicativo também será exibido na lista de aplicativos de destino de uma política MAM do seu locatário, conforme descrito na próxima etapa.

## <a name="step-3-apply-mam-policies"></a>Etapa 3: aplicar políticas MAM
Depois dos metadados do aplicativo serem carregados para o serviço, o aplicativo aparecerá na lista de aplicativos.  Agora você pode [criar uma nova política ou uma política existente](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) e aplicá-la no aplicativo de linha de negócios adicionado na etapa 2.

>[!IMPORTANT]
>Você deve direcionar a política MAM aos usuários que pretendem usar o aplicativo encapsulado.  Os usuários que não têm essa política implantada não poderão usar o aplicativo.


  ![Captura de tela da folha Lista de destino de aplicativos com o novo aplicativo de linha de negócios exibido](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>Etapa 4: distribuir o aplicativo
Você pode implantar aplicativos para seus usuários finais das seguintes maneiras:
* Para dispositivos registrados em uma solução de MDM de terceiros, você pode distribuir os aplicativos por meio de sua solução de MDM.
* Para dispositivos não gerenciados por qualquer solução de MDM, você precisará de uma solução personalizada. Os usuários finais têm que baixar e instalar o aplicativo em seu dispositivo.

## <a name="changing-the-metadata"></a>Mudando os metadados
Se você precisar alterar os detalhes do aplicativo, como o nome do aplicativo ou o identificador de pacote, você deverá [remover o aplicativo](#remove-apps) e [adicioná-lo](#step-2-add-the-app) com os novos metadados.

##  <a name="remove-apps"></a>Remover aplicativos
Você pode remover um aplicativo de linha de negócios da lista de aplicativos.  Isso removerá o aplicativo da lista e removerá a associação com políticas MAM, mas não removerá ou desinstalará o aplicativo do dispositivo do usuário final.  

1.  No [portal do Azure](https://portal.azure.com/), vá para **Gerenciamento de aplicativos móveis do Intune > Configurações**.  Na folha **Configurações**, escolha **Linha de negócios** para abrir a lista de aplicativos existentes.  
2.  Selecione o aplicativo que você deseja remover e escolha o menu **(…) contexto**.

  ![Captura de tela da folha de aplicativos da linha de negócios com reticências](../media/mam-azure-portal-lob-context-menu.png)
3.  Escolha **Excluir Aplicativo** para excluir o aplicativo.

  ![Captura de tela da folha linha de negócios com a opção de exclusão do aplicativo](../media/mam-azure-portal-delete-app.png)

  Isso removerá os aplicativos da lista de aplicativos da linha de negócios e da lista de destino de aplicativos na política MAM.



<!--HONumber=Nov16_HO2-->


