---
title: "Configurações personalizadas do Intune para dispositivos do Windows Holographic for Business"
titlesuffix: Azure portal
description: "Conheça as configurações que você pode usar em um perfil personalizado do Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Configurações de dispositivo personalizadas para dispositivos do Windows Holographic for Business no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Use o perfil **personalizado** do Microsoft Intune para Windows Holographic for Business para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows Holographic for Business disponibiliza muitas configurações de CSPs (Provedores de Serviço de Configuração). Para uma visão geral sobre CSP, consulte [Introdução aos CSPs (Provedores de Serviço de Configuração) para profissionais de TI](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Para CSPs específicos compatíveis com o Windows Holographic, consulte [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Se você estiver procurando uma configuração específica, lembre-se que o [perfil de restrição de dispositivo do Windows Holographic for Business](device-restrictions-windows-holographic.md) contém várias configurações internas e não necessita que você especifique valores personalizados.

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. Na folha **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.
3. Na folha **Configurações personalizadas do OMA-URI**, clique em **Adicionar** para adicionar um novo valor. Você também pode clicar em **Exportar** para criar uma lista de todos os valores configurados em um arquivo de valores separados por vírgulas (.csv).
4. Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir. Use a lista neste tópico para saber mais sobre as configurações que você pode usar:
    - **Nome da configuração** - insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição da configuração** - opcionalmente, insira uma descrição para a configuração.
    - **Tipo de dados** - escolha dentre:
        - **Cadeia de caracteres**
        - **Cadeia de caracteres (XML)**
        - **Data e hora**
        - **Inteiro**
        - **Ponto flutuante**
        - **Booliano**
    - **OMA-URI (com distinção entre maiúsculas e minúsculas)** - especifique o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Valor** - especifique o valor para associar ao OMA-URI que você inseriu.
5. Quando terminar, volte para a folha **Criar Perfil** e clique em **Criar**.
O perfil é criado e exibido na folha da lista de perfis.

## <a name="supported-custom-settings"></a>Configurações personalizadas compatíveis

O Windows Holographic for Business é compatível com as seguintes configurações personalizadas:


|Nome da configuração|OMA-URI|Tipo de dados  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Inteiro (0 – não é permitido, 1 – permitido)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Inteiro (0 – não é permitido, 1 – permitido)|



## <a name="how-to-find-the-policies-you-can-configure"></a>Como localizar as políticas que você pode configurar

Você pode encontrar uma lista completa de todos os CSPs (Provedores de Serviço de Configuração) compatíveis com o Windows Holographic em [CSPs compatíveis com o Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens). Nem todas as configurações são compatíveis com todas as versões do Windows Holographic. A tabela no tópico do Windows informa quais versões têm suporte para cada CSP.

Além disso, o Intune não dá suporte a todas as configurações listadas no tópico. Para saber se o Intune oferece suporte à configuração desejada, abra o tópico para essa configuração. Cada página de configuração mostra a operação de suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.


