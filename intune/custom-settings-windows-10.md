---
title: Configurações personalizadas de dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Defina configurações personalizadas de OMA-URI em dispositivos que executam o Windows 10 usando um perfil personalizado no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdbb6643a4ee8aace0db22cd7f9189f7ac6445f0
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232819"
---
# <a name="custom-oma-uri-settings-for-windows-10-devices---intune"></a>Configurações personalizadas de OMA-URI para dispositivos Windows 10 – Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use o perfil **personalizado** do Microsoft Intune para o Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Essas configurações são usadas para controlar recursos nos dispositivos. O Windows 10 disponibiliza várias configurações de CSP (Provedor de Serviço de Configuração), como [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Se você estiver procurando uma configuração específica, lembre-se de que o [perfil de restrição de dispositivo do Windows 10](device-restrictions-windows-10.md) contém várias configurações internas do Intune e não exigem valores personalizados.

## <a name="configure-custom-settings"></a>Definir configurações personalizadas

1. Crie um perfil de configuração usando o tipo de perfil **Personalizado**. [Como definir configurações personalizadas de dispositivo](custom-settings-configure.md) lista as etapas.
2. Em **Configurações personalizadas de OMA-URI**, selecione **Adicionar** para criar uma configuração. Você também pode clicar em **Exportar** para criar uma lista de todos os valores configurados em um arquivo de valores separados por vírgulas (.csv).
3. Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir:

- **Nome**: insira um nome exclusivo para a configuração de OMA-URI para ajudar você a identificá-la na lista de configurações.
- **Descrição**: opcionalmente, insira uma descrição para a configuração.
- **OMA-URI (com diferenciação de maiúsculas e minúsculas)**: insira o OMA-URI para o qual você deseja fornecer uma configuração.
- **Tipo de dados**: escolha dentre:
  - **Cadeia de caracteres**
  - **Cadeia de caracteres (XML)**
  - **Data e hora**
  - **Inteiro**
  - **Ponto flutuante**
  - **Booliano**
  - **Base64**
- **Valor**: insira o valor ou o arquivo a ser associado ao OMA-URI inserido.

4. Quando terminar, selecione **OK**. Em **Criar perfil**, selecione **Criar**. O perfil será criado e será mostrado na lista de perfis.

## <a name="example"></a>Exemplo
No exemplo a seguir, a configuração **Conectividade/AllowVPNOverCellular** está habilitada. Essa configuração permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede celular.

![Exemplo de política personalizada que contém as configurações de VPN](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Localizar as políticas que você pode configurar

Você encontrará uma lista completa de todos os CSPs (provedores de serviço de configuração) aos quais o Windows 10 dá suporte na [Referência de provedor de serviços de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Nem todas as configurações são compatíveis com todas as versões do Windows 10. A [Referência de provedor de serviços de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) informa quais versões são compatíveis com cada CSP.

Além disso, o Intune não dá suporte a todas as configurações listadas. Para saber se o Intune é compatível com a configuração desejada, abra o artigo dessa configuração. Cada página de configuração mostra a operação de suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.
