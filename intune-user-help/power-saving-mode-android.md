---
title: A otimização de energia está impedindo o acesso ao email | Microsoft Docs
description: Saiba como desligar a otimização de energia para o Android a fim de assegurar o recebimento de seu email.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/07/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 663da92e11befeae1f65467e887870a52640cbeb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a>O Outlook não sincroniza email gerenciado quando a otimização da bateria para Android está ativada

> [!IMPORTANT]
> Esse problema é documentado aqui porque temos recebido um maior número de relatórios de cliente sobre ele. Se depois de executar essas etapas você continuar a experimentar esse problema, entre em contato com [o suporte de sua empresa](https://portal.manage.microsoft.com#HelpDeskDialog) para obter ajuda adicional.

Registrar seu dispositivo no Intune permite que você obtenha acesso aos recursos da empresa. Um dos recursos mais comuns é o acesso a email. Um problema que vimos no acesso a email por meio do Outlook para dispositivos Android foi a quando a otimização da bateria é ativada. A otimização da bateria pode ser ativada automaticamente para tentar ajudar o seu dispositivo a permanecer ligado pelo máximo de tempo possível. A otimização da bateria é parcialmente capaz de ajudá-lo desse modo, porque ela tenta interromper downloads de email automáticos.

A equipe do Microsoft Intune está trabalhando ativamente em uma solução para esse problema. Uma maneira de impedir que o dispositivo entre no modo de baixa energia é assegurar que a bateria mantenha uma carga maior que 30%. Para impedir que o problema ocorra quando você entra no modo de baixa energia, você deve remover o Portal da Empresa e o Outlook da lista de aplicativos que são afetados pelas configurações de economia de energia e de otimização da bateria.

Há muitos dispositivos Android, os quais são feitos por vários fabricantes. Não é possível documentar as etapas exatas necessárias para cada dispositivo. Talvez seja necessário executar esta ação apenas em suas configurações de sistema ou também em determinadas configurações específicas do fabricante. Fornecemos alguns exemplos comuns de como você pode resolver esse problema em dispositivos Android.

## <a name="unmodified-android-devices"></a>Dispositivos Android não modificados

Muitos fabricantes adicionam modificações em seus dispositivos Android. Isso pode alterar determinadas maneiras em que você interage com o dispositivo, assim como os temas e notificações. A Google geralmente não faz esses tipos de modificações nos telefones deles. Por exemplo, em um dispositivo Google Pixel com Android 7.0 ou superior, você seguiria estas etapas para remover esses aplicativos de otimização da bateria:

1. Abra **Configurações**.
2. Toque em **Bateria** > **Mais** > **Otimização da bateria**.
3. Toque na seta para baixo e, em seguida, em **Não otimizada**.
4. Selecione os aplicativos do Portal da Empresa e do Outlook e desligue a otimização da bateria.

## <a name="samsung-devices"></a>Dispositivos Samsung

Para outros tipos de dispositivos Android, como dispositivos Samsung com Android 7.0 ou superior, você teria que seguir etapas diferentes para que os aplicativos do Portal da Empresa e do Outlook sejam removidos da otimização da bateria.

1. Abra **Configurações**.
2. Toque em **Menu (...)** > **Acesso especial** > **Otimizar o uso da bateria**.
3. Selecione **Todos os aplicativos** na lista suspensa.
4. **Desligue** a tecla de alternância ao lado dos aplicativos do Portal da Empresa e do Outlook para desligar a otimização da bateria.

Além disso, se você estiver usando um dispositivo Samsung que tem uma versão inferior do Android, você precisará seguir estas etapas para remover esses aplicativos do modo de economia de energia.

1. Abra **Configurações**.
2. Toque em **Manutenção do dispositivo** > **Bateria** > **Aplicativos sem monitoramento**.
3. Toque em **Adicionar aplicativos**.
4. Selecione os aplicativos do Portal da Empresa e do Outlook e toque em **Concluído**.

## <a name="oneplus-devices"></a>Dispositivos OnePlus

Outro exemplo de maneira diferente de localizar essas configurações é por meio de pesquisa nas configurações do sistema. Por exemplo, em um OnePlus 3 com Android 7.1.1, siga estas etapas: 

1. Abra **Configurações do Sistema**. 
2. Toque no botão **Pesquisa**. Isso parece uma lente de aumento na parte superior direita da tela. 
3. Digite **otimização da bateria** na pesquisa, selecione a opção **Otimização da Bateria** na tela **Configurações** que é exibida. 
4. Toque em **Bateria** > **Otimização da bateria**.
5. Selecione os aplicativos do Portal da Empresa e do Outlook e toque em **Não otimizar**. Toque em **Concluído**.

<!--On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization:
1. Open **Settings**.
2. Tap **Battery** > **Battery optimization**.
3. Select the Company Portal and Outlook apps, then select **Don’t optimize**. Tap **Done**.-->

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter suas informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
