---
title: Configurações de perfil personalizadas do Intune para perfis de trabalho Android
titlesuffix: Microsoft Intune
description: Saiba como criar configurações de perfil personalizadas do Microsoft Intune para dispositivos de perfil de trabalho Android.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 109c50acf194598017aa507a0979ad3b9298de9e
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905284"
---
# <a name="create-intune-custom-profile-settings-for-android-work-profile-devices"></a>Criar configurações de perfil personalizadas do Intune para dispositivos de perfil de trabalho Android

Use a política de configuração personalizada do perfil de trabalho Android do Intune para atribuir configurações de OMA-URI que podem ser usadas para controlar recursos em dispositivos de perfil de trabalho Android. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você atribua configurações do Android que não são configuráveis com as políticas do Intune. No momento, o Intune dá suporte a um número limitado de políticas personalizadas do Android. Confira os exemplos neste artigo para descobrir quais políticas você pode configurar.

## <a name="create-a-custom-profile"></a>Criar um perfil personalizado

1. Use as instruções em [Como definir configurações personalizadas do dispositivo](custom-settings-configure.md) para começar. Para **Plataforma** escolha **Android Enterprise** e para **Tipo de perfil** escolha **Personalizado**.
2. Na folha **Configurações personalizadas do OMA-URI**, escolha **Adicionar** para adicionar uma nova configuração.
3. Na folha **Adicionar Linha**, configure o seguinte:
    - **Nome** – insira um nome exclusivo para as configurações personalizadas do perfil de trabalho Android para ajudar a identificá-las no Portal do Azure.
    - **Descrição** - forneça uma descrição que dê uma visão geral da política personalizada do Android e outras informações relevantes que o ajudarão a localizá-la.
    - **OMA-URI** - insira o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Tipo de dados** – Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha entre **Cadeia de caracteres**, **Cadeia de caracteres (arquivo XML)**, **Data e hora**, **Inteiro**, **Ponto flutuante**, **Booliano** ou **Base64 (arquivo)**.
    - **Valor** - especifique o valor a ser associado ao OMA-URI especificado anteriormente. O método usado para fornecer esse valor varia de acordo com o tipo de dados selecionado. Por exemplo, se você escolher **Data e hora**, selecionará o valor de um seletor de data.
4. Quando terminar, escolha OK para retornar para às **Configurações Personalizadas de OMA-URI** e, em seguida, adicione mais configurações ou escolha **Criar** para criar o perfil personalizado.


## <a name="example"></a>Exemplo

Neste exemplo, você criará um perfil personalizado que pode ser usado para restringir a permissão das ações de copiar e colar entre aplicativos pessoais e de trabalho em dispositivos de perfil de trabalho Android.

1. Use o procedimento neste artigo para criar um perfil personalizado para dispositivos de perfil de trabalho Android usando os seguintes valores:
    - **Nome** - insira "Bloquear copiar e colar" ou o texto de sua escolha.
    - **Descrição** - insira "Bloqueia copiar/colar entre aplicativos pessoais e de trabalho" ou o texto de sua escolha.
    - **OMA-URI** - insira **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
    - **Tipo de dados** - selecione **Booliano** para indicar se o valor para esse OMA-URI é **True** ou **False**.
    - **Valor** -selecione **True**.
2. A configuração deve ficar semelhante a esta imagem.
![Bloquear ações de copiar e colar para o perfil de trabalho Android.](./media/custom-policy-afw-copy-paste.png)
3. Agora, ao atribuir esse perfil personalizado aos dispositivos de perfil de trabalho Android que você gerencia, as ações de copiar e colar serão bloqueadas entre aplicativos nos perfis de trabalho e pessoais.