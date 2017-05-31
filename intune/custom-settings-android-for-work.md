---
title: "Configurações de perfil personalizadas do Intune para Android for Work"
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: aprenda a criar configurações de perfil personalizadas do Intune para dispositivos com Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: cd81e911dd1ab7c5d166ee14f2e184ebd54a18df
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a>Criar configurações de perfil personalizadas do Intune para dispositivos com Android for Work

Use a política de configuração personalizada do Android for Work do Intune para atribuir configurações OMA-URI, que podem ser usadas para controlar funcionalidades em dispositivos Android for Work. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você atribua configurações do Android que não são configuráveis com as políticas do Intune. No momento, o Intune dá suporte a um número limitado de políticas personalizadas do Android. Consulte os exemplos neste tópico para descobrir quais políticas podem ser configuradas.

## <a name="create-a-custom-profile"></a>Criar um perfil personalizado

1. Use as instruções em [Como definir configurações personalizadas do dispositivo](custom-settings-configure.md) para começar.
2. Na folha **Configurações personalizadas do OMA-URI**, escolha **Adicionar** para adicionar uma nova configuração.
3. Na folha **Adicionar Linha**, configure o seguinte:
    - **Nome** - insira um nome exclusivo para as configurações personalizadas do Android for Work para ajudar a identificá-las no portal do Intune.
    - **Descrição** - forneça uma descrição que dê uma visão geral da política personalizada do Android e outras informações relevantes que o ajudarão a localizá-la.
    - **OMA-URI** - insira o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Tipo de dados** – Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha entre **Cadeia de caracteres**, **Cadeia de caracteres (arquivo XML)**, **Data e hora**, **Inteiro**, **Ponto flutuante**, **Booliano** ou **Base64 (arquivo)**.
    - **Valor** - especifique o valor a ser associado ao OMA-URI especificado anteriormente. O método usado para fornecer esse valor varia de acordo com o tipo de dados selecionado. Por exemplo, se você escolher **Data e hora**, selecionará o valor de um seletor de data.
4. Quando terminar, escolha OK para retornar para às **Configurações Personalizadas de OMA-URI** e, em seguida, adicione mais configurações ou escolha **Criar** para criar o perfil personalizado.


## <a name="example"></a>Exemplo

Neste exemplo, você criará um perfil personalizado que pode ser usado para restringir a permissão de ações de copiar e colar entre aplicativos pessoais e de trabalho em dispositivos gerenciados com Android for Work.

1. Use o procedimento neste tópico para criar um perfil personalizado do Android for Work usando os seguintes valores:
    - **Nome** - insira "Bloquear copiar e colar" ou o texto de sua escolha.
    - **Descrição** - insira "Bloqueia copiar/colar entre aplicativos pessoais e de trabalho" ou o texto de sua escolha.
    - **OMA-URI** - insira **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
    - **Tipo de dados** - selecione **Booliano** para indicar se o valor para esse OMA-URI é **True** ou **False**.
    - **Valor** -selecione **True**.
2. A configuração deve ficar semelhante a esta imagem.
![Bloquear copiar e colar para Android for Work.](./media/custom-policy-afw-copy-paste.png)
3. Agora, quando você atribui esse perfil personalizado aos dispositivos Android for Work que você gerencia, as ações de copiar e colar serão bloqueadas entre aplicativos nos perfis de trabalho e pessoais.
