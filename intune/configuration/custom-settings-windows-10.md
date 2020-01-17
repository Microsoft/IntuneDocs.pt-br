---
title: Adicionar configurações personalizadas de dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil personalizado para usar as configurações de OMA-URI para dispositivos que executam o Windows 10 no Microsoft Intune. Use um perfil personalizado para adicionar configurações personalizadas.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9e3d2784e0242498fbae43ab61034a5be31b0952
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206764"
---
# <a name="use-custom-settings-for-windows-10-devices-in-intune"></a>Usar configurações personalizadas para dispositivos Windows 10 no Intune

Usando o Microsoft Intune, você pode adicionar ou criar configurações personalizadas para dispositivos Windows 10 usando "perfis personalizados". Perfis personalizados são um recurso no Intune. Eles são projetados para adicionar configurações e recursos de dispositivos que não são internos ao Intune.

Os perfis personalizados do Windows 10 usam as configurações do OMA-URI (Open Mobile Alliance Uniform Resource Identifier) para definir os diversos recursos. Essas configurações geralmente são usadas pelos fabricantes de dispositivos móveis para controlar os recursos do dispositivo. 

O Windows 10 disponibiliza várias configurações de CSP (Provedor de Serviço de Configuração), como [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Se você estiver procurando uma configuração específica, lembre-se de que o [perfil de restrição de dispositivo do Windows 10](device-restrictions-windows-10.md) inclui várias configurações internas. Dessa forma, talvez você não precise inserir valores personalizados.

Este artigo mostra:

- Como criar um perfil personalizado para dispositivos Windows 10
- Inclui uma lista das configurações OMA-URI recomendadas
- Apresenta um exemplo de um perfil personalizado que abre uma conexão VPN

## <a name="create-the-profile"></a>Criar o perfil

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um bom nome de perfil é o **perfil personalizado do Windows 10**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Windows 10 e posterior**.
    - **Tipo de perfil**: selecione **personalizado**.

4. Em **Configurações personalizadas de OMA-URI**, selecione **Adicionar**. Insira as seguintes configurações:

    - **Nome**: Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e demais detalhes importantes.
    - **OMA-URI** (diferencia maiúsculas de minúsculas): insira o OMA-URI que você deseja usar como uma configuração.
    - **Tipo de dados**: selecione o tipo de dados que você usará para essa configuração de OMA-URI. Suas opções:

        - Cadeia de caracteres
        - Cadeia de caracteres (arquivo XML)
        - Data e Hora
        - Inteiro
        - Ponto flutuante
        - Booliano
        - Base64 (arquivo)

    - **Valor**: insira o valor de dados que você deseja associar ao OMA-URI inserido. O valor depende do tipo de dados selecionado. Por exemplo, se você selecionar **Data e hora**, selecione o valor em um seletor de data.

    Depois de adicionar algumas configurações, você pode selecionar **Exportar**. **Exportar** cria uma lista de todos os valores que você adicionou em um arquivo de valores separados por vírgulas (.csv).

5. Selecione **OK** para salvar suas alterações. Continue a adicionar mais configurações conforme necessário.
6. Quando terminar, escolha **OK** > **Criar** para criar o perfil do Intune. Após a conclusão, seu perfil será mostrado na lista **Dispositivos – Perfis de configuração**.

## <a name="example"></a>Exemplo

No exemplo a seguir, a configuração **Conectividade/AllowVPNOverCellular** está habilitada. Essa configuração permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede celular.

![Exemplo de política personalizada que contém as configurações de VPN](./media/custom-settings-windows-10/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Localizar as políticas que você pode configurar

Há uma lista completa de todos os CSPs (provedores de serviço de configuração) compatíveis com o Windows 10 na [Referência de provedor de serviços de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Nem todas as configurações são compatíveis com todas as versões do Windows 10. A [Referência de provedor de serviços de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) informa quais versões são compatíveis com cada CSP.

Além disso, o Intune não dá suporte a todas as configurações listadas em [Referência do provedor de serviço de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference). Para saber se o Intune é compatível com a configuração desejada, abra o artigo dessa configuração. Cada página de configuração mostra a operação com suporte correspondente. Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar**, **Substituir** ou **Obter**. Se o valor retornado pela operação **Get** não corresponder ao valor fornecido pelas operações **Add** ou **Replace**, o Intune relatará um erro de conformidade.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
