---
title: Políticas de configuração de aplicativo do Microsoft Intune
titleSuffix: ''
description: Saiba como usar políticas de configuração de aplicativo em um dispositivo iOS ou Android no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cda0453009855d96e7c13e170ba908479a0773ea
ms.sourcegitcommit: 513e805bbea8bf652c2901dfc5460e34946077df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2019
ms.locfileid: "70160538"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Políticas de configuração de aplicativo do Microsoft Intune

As políticas de configuração de aplicativos podem ajudar a eliminar os problemas de instalação do aplicativo ao permitir que você atribua configurações a uma política atribuída aos usuários antes da execução do aplicativo. As configurações são então fornecidas automaticamente quando o aplicativo é configurado no dispositivo dos usuários finais e os usuários finais não precisam realizar nenhuma ação. As definições de configuração são exclusivas para cada aplicativo. 

Crie e use políticas de configuração de aplicativos para fornecer definições de configuração para aplicativos iOS ou Android. Essas definições de configuração permitem que um aplicativo seja personalizado usando uma [abordagem padrão do setor](https://www.appconfig.org/) de gerenciamento e configuração de aplicativos. As definições da política de configuração são usadas quando o aplicativo verifica se elas existem, normalmente, na primeira vez em que o aplicativo é executado. 

Por exemplo, uma configuração de aplicativos pode exigir que você especifique um dos seguintes detalhes:

- Um número de porta personalizado
- Configurações de idioma
- Configurações de segurança
- Configurações de identidade visual, como um logotipo da empresa

Se os usuários finais inserirem essas configurações, eles poderão fazer isso incorretamente. As políticas de configuração de aplicativos podem ajudar a fornecer consistência em toda a empresa e a reduzir as chamadas de assistência técnica dos usuários finais que tentam definir as configurações por conta própria. Com o uso das políticas de configuração de aplicativos, a adoção de novos aplicativos pode ser mais fácil e rápida.

Em última análise, os parâmetros de configuração disponíveis são decididos pelos desenvolvedores do aplicativo. A documentação do fornecedor do aplicativo deve ser examinada para verificar se um aplicativo dá suporte à configuração e quais configurações estão disponíveis. Para alguns aplicativos, o Intune populará as definições de configuração disponíveis. 

> [!NOTE]
> Na Google Play Store Gerenciada, os aplicativos que dão suporte à configuração serão marcados da seguinte maneira:
> 
> ![Captura de tela de um aplicativo configurado](./media/app-configuration-policy-overview/configured-app.png)
>
> Você só verá aplicativos da [Google Play Store Gerenciada](https://play.google.com/work), não da [Google Play Store](https://play.google.com/store/apps), ao usar Dispositivos Gerenciados como o Tipo de Registro para dispositivos Android. A Google Play Store Gerenciada, que você também pode conhecer como AfW (Android for Work) e Android Enterprise, são os aplicativos no Perfil de Trabalho que contêm as versões do aplicativo que dão suporte à configuração de aplicativos.

Você pode atribuir uma política de configuração de aplicativos a um grupo de usuários finais e dispositivos usando uma combinação de [atribuições de inclusão e exclusão](apps-inc-exl-assignments.md). Depois de adicionar uma política de configuração de aplicativo, você pode definir as atribuições para política de configuração de aplicativo. Ao definir as atribuições para a política, você pode optar por incluir ou excluir os [grupos](groups-add.md) de usuários finais para os quais a política se aplica. Ao optar por incluir um ou mais grupos, você pode optar por selecionar grupos específicos para incluir ou selecionar grupos internos. Os grupos internos incluem **Todos os Usuários**, **Todos os Dispositivos** e **Todos os Usuários + Todos os Dispositivos**.

Você tem duas opções para usar as políticas de configuração de aplicativos com o Intune:
- **Dispositivos gerenciados** – o dispositivo é gerenciado pelo Intune como o provedor de MDM (gerenciamento de dispositivo móvel). O aplicativo precisa ser projetado para dar suporte à configuração de aplicativos.
- **Aplicativos gerenciados** – um aplicativo desenvolvido para integrar o SDK de Aplicativo do Intune. Isso é conhecido como gerenciamento de aplicativo móvel sem registro ([MAM-WE](app-management.md#mobile-application-management-mam-basics)). Você também pode encapsular um aplicativo para implementar o SDK de Aplicativo do Intune e dar suporte a ele. Para obter mais informações sobre como encapsular esse aplicativo, confira [Preparar aplicativos de linha de negócios para políticas de proteção de aplicativos](apps-prepare-mobile-application-management.md).

    > [!NOTE]
    > Os aplicativos gerenciados do Intune farão o check-in com um intervalo de 30 minutos no status da Política de Configuração de Aplicativos do Intune, quando implantados em conjunto com uma Política de Proteção de Aplicativo do Intune. Se uma Política de Proteção de Aplicativo do Intune não for atribuída ao usuário, o intervalo de check-in da Política de Configuração de Aplicativos dos Intune será definido como 720 minutos.

## <a name="apps-that-support-app-configuration"></a>Aplicativos que dão suporte à configuração de aplicativo

### <a name="managed-devices"></a>Dispositivos gerenciados
Use políticas de configuração de aplicativos para aplicativos que dão suporte a elas. Para dar suporte à configuração de aplicativos no Intune, os aplicativos precisam ser escritos tendo em vista o suporte ao uso de configurações de aplicativo, conforme definido na [Comunidade do AppConfig](https://www.appconfig.org/members). Consulte o fornecedor do aplicativo para obter mais detalhes.

### <a name="managed-apps"></a>Aplicativos gerenciados
Prepare seus aplicativos de linha de negócios incorporando o [SDK de Aplicativo do Intune](app-sdk.md) no aplicativo ou encapsulando o aplicativo depois que ele for desenvolvido usando a [Ferramenta de Encapsulamento de Aplicativo do Intune](apps-prepare-mobile-application-management.md). O SDK de Aplicativo do Intune se esforça para minimizar a quantidade de alterações de código necessárias pelo desenvolvedor do aplicativo. Para obter mais informações, consulte a [Visão geral do SDK de Aplicativo do Intune](app-sdk.md). Para obter uma comparação entre o SDK de Aplicativo do Intune e a Ferramenta de Encapsulamento de Aplicativo do Intune, confira [Preparar aplicativos de linha de negócios para políticas de proteção do aplicativo](apps-prepare-mobile-application-management.md#feature-comparison).

A seleção da opção **Aplicativos gerenciados** como o **Tipo de Registro de Dispositivo** refere-se especificamente aos aplicativos configurados pelas políticas de configuração do Intune em um dispositivo que não está registrado no gerenciamento de dispositivo, enquanto a opção **Dispositivos gerenciados** se aplica aos aplicativos implantados por meio do canal MDM e, portanto, são gerenciados pelo Intune. Selecione a opção apropriada com base nessas descrições. 

![Tipo de registro do dispositivo](./media/app-configuration-policy-overview/device-enrollment-type.png)

> [!NOTE]
> Para aplicativos de várias identidades, como o Microsoft Outlook, as preferências do usuário podem ser consideradas. A Caixa de Entrada Destaques, por exemplo, respeitará a configuração do usuário e não alterará a configuração. Outros parâmetros permitem controlar se um usuário pode ou não alterar a configuração. Para obter mais informações, confira [Como implantar as definições de configuração de aplicativos para Outlook para iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

## <a name="validate-the-applied-app-configuration-policy"></a>Validar a política de configuração de aplicativos aplicada

Valide a política de configuração de aplicativos usando os três seguintes métodos:

   1. Visivelmente no dispositivo. O aplicativo de destino está apresentando o comportamento aplicado na política de Configuração de Aplicativos?
   2. Por meio dos Logs de Diagnóstico (confira a seção Logs de Diagnóstico abaixo).
   3. No portal do Intune. A seção **Monitor** de uma política pode fornecer o status relevante:

      ![Primeira captura de tela do status de instalação do dispositivo](./media/app-configuration-policy-overview/device-install-status-1.png)

      ![Segunda captura de tela do status de instalação do dispositivo](./media/app-configuration-policy-overview/device-install-status-2.png)

      Além disso, em **Intune** -> **Dispositivos** -> **Todos os Dispositivos**, no lado esquerdo da tela, a opção **Configuração de Aplicativos** exibirá todas as políticas atribuídas e seu estado:

      ![Captura de tela da configuração de aplicativos](./media/app-configuration-policy-overview/app-configuration.png)

## <a name="graph-api-support-for-app-configuration"></a>Suporte de API do Graph para configuração de aplicativo

Use a API do Graph para realizar tarefas de configuração de aplicativos. Para saber mais, confira [Configuração direcionada do MAM na referência da API do Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="troubleshooting"></a>Solução de problemas

### <a name="using-logs-to-show-a-configuration-parameter"></a>Como usar os logs para mostrar um parâmetro de configuração
Quando os logs mostram um parâmetro de configuração que é confirmado como estando aplicado, mas não parece funcionar, pode haver um problema com a implementação da configuração pelo desenvolvedor do aplicativo. Ao contatar o desenvolvedor do aplicativo primeiro ou verificar sua base de dados de conhecimento, talvez você não precise fazer uma chamada de suporte para a Microsoft. Se esse for um problema referente ao modo de tratamento da configuração em um aplicativo, ele precisará ser resolvido em uma versão atualizada futura do aplicativo.

## <a name="next-steps"></a>Próximas etapas

### <a name="managed-devices"></a>Dispositivos gerenciados

- Saiba como usar a configuração de aplicativo com seus dispositivos iOS.  Confira [Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md).
- Saiba como usar a configuração de aplicativo com seus dispositivos Android.  Consulte [Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplicativos gerenciados

- Saiba como usar a configuração de aplicativo com aplicativos gerenciados. Consulte [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](app-configuration-policies-managed-app.md).
