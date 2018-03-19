---
title: "Configurações personalizadas do Microsoft Intune para dispositivos que executam o Windows 10"
titlesuffix: 
description: "Conheça as configurações personalizadas que você pode definir em um perfil personalizado do Windows 10."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bb86d0f80a4d337e0ab63ae7f90d6c3541462d9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-10"></a>Configurações personalizadas de dispositivo do Microsoft Intune para dispositivos que executam o Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Use o perfil **personalizado** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos. O Windows 10 disponibiliza várias definições de CSP (Provedor de Serviço de Configuração), por exemplo o [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Se você estiver procurando uma determinada configuração, lembre-se de que o [perfil de restrição de dispositivo do Windows 10](device-restrictions-windows-10.md) contém várias configurações que são integradas ao Intune e não exigem que você especifique valores personalizados.

## <a name="configure-custom-settings"></a>Definir configurações personalizadas

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
1. No painel **Configurações personalizadas de OMA-URI**, clique em **Adicionar** para adicionar um novo valor. Você também pode clicar em **Exportar** para criar uma lista de todos os valores configurados em um arquivo de valores separados por vírgulas (.csv).
1. Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir. Veja a lista deste artigo para saber mais sobre as configurações que você pode usar:
    - **Nome** – Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição** – opcionalmente, insira uma descrição para a configuração.
    - **OMA-URI (com distinção entre maiúsculas e minúsculas)** - especifique o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Tipo de dados** - escolha dentre:
        - **Cadeia de caracteres**
        - **Cadeia de caracteres (XML)**
        - **Data e hora**
        - **Inteiro**
        - **Ponto flutuante**
        - **Booliano**
        - **Base64**
    - **Valor** – especifique o valor ou o arquivo a ser associado ao OMA-URI que você inseriu.
1. Quando terminar, selecione **OK**, volte para o painel **Criar perfil** e selecione **Criar**.
O perfil é criado e aparece no painel da lista de perfis.

## <a name="example"></a>Exemplo
Na captura de tela abaixo, a configuração **Connectivity/AllowVPNOverCellular** foi habilitada. Isso permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede de celular.

> ![Exemplo de política personalizada que contém as configurações de VPN](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Como localizar as políticas que você pode configurar

Você encontrará uma lista completa de todos os provedores de serviço de configuração (CSP) a que o Windows 10 dá suporte na [Referência do provedor do serviço de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) na biblioteca de documentação do Windows.

Nem todas as configurações são compatíveis com todas as versões do Windows 10. A tabela no artigo do Windows informa quais versões são compatíveis com cada CSP.

Além disso, o Intune não dá suporte a todas as configurações listadas no artigo. Para saber se o Intune é compatível com a configuração desejada, abra o artigo dessa configuração. Cada página de configuração mostra a operação de suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.
