---
title: Criar perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Adicionar ou configurar um perfil de configuração de dispositivo no Microsoft Intune. Selecione o tipo de plataforma, defina as configurações e adicione uma marca de escopo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c6ece37a4ff6eceaa4df735f365453a4bc7d88
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59570397"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Criar um perfil de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Perfis de dispositivo permitem que você adicione e defina as configurações e, em seguida, envie essas configurações por push para dispositivos em sua organização. [Aplicar recursos e configurações em seus dispositivos usando perfis de dispositivo](device-profiles.md) apresenta mais detalhes, incluindo o que você pode fazer.

Este artigo:

- Lista as etapas para criar um perfil.
- Mostra como adicionar uma marca de escopo para "filtrar" o perfil.
- Lista os tempos de ciclo de atualização de check-in quando os dispositivos recebem os perfis e atualizações de perfil.

## <a name="create-the-profile"></a>Criar o perfil

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Intune**.

2. Selecione **Configuração do dispositivo**. Você tem as seguintes opções:

    - **Visão geral**: Lista o status dos perfis e fornece detalhes adicionais sobre os perfis que você atribuiu a usuários e dispositivos.
    - **Gerenciar**: Crie perfis de dispositivo, carregue [scripts personalizados do PowerShell](intune-management-extension.md) a serem executados no perfil e adicione planos de dados a dispositivos usando o [eSIM](esim-device-configuration.md).
    - **Monitorar**: Verifique o status de um perfil quanto ao êxito ou falha, além de exibir logs sobre os perfis.
    - **Configuração**: Adicione uma autoridade de certificação SCEP ou PFX ou habilite o [Telecom Expense Management](telecom-expenses-monitor.md) no perfil.

3. Selecione **Perfis** > **Criar Perfil**. Insira as seguintes propriedades:

   - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um nome de perfil bom é **perfil de email do WP para toda a empresa**.
   - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
   - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 e posterior**
       - **Windows 10 e posterior**

   - **Tipo de perfil**: Selecione o tipo de configurações que deseja criar. A lista dependerá da **plataforma** escolhida.
   - **Configurações**: Os artigos a seguir descrevem as configurações de cada tipo de perfil:

       - [Modelos Administrativos](administrative-templates-windows.md)
       - [Personalizado](custom-settings-configure.md)
       - [Otimização de Entrega](delivery-optimization-windows.md)
       - [Recursos de dispositivo](device-features-configure.md)
       - [Restrições de dispositivo](device-restrictions-configure.md)
       - [Atualização de edição e opção de modo](edition-upgrade-configure-windows-10.md)
       - [Educação](education-settings-configure.md)
       - [Email](email-settings-configure.md)
       - [Endpoint protection](endpoint-protection-configure.md)
       - [Proteção de identidade](identity-protection-configure.md)  
       - [Quiosque](kiosk-settings.md)
       - [Certificado PKCS](certficates-pfx-configure.md)
       - [Certificado SCEP](certificates-scep-configure.md)
       - [Certificado confiável](certificates-configure.md)
       - [Políticas de atualização](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](advanced-threat-protection.md)
       - [Proteção de Informações do Windows](windows-information-protection-configure.md)

     Por exemplo, se você selecionar **iOS** para a plataforma, as opções de tipo de perfil serão semelhantes ao seguinte perfil:

     ![Criar perfil do iOS no Intune](./media/create-device-profile.png)

4. Quando terminar, selecione **OK** > **Criar** para salvar as alterações. O perfil é criado e exibido na lista.

## <a name="scope-tags"></a>Marcas de escopo

Depois de adicionar as configurações, você também poderá adicionar uma marca de escopo ao perfil. As marcas de escopo atribuem e filtram políticas para grupos específicos, como RH ou Todos os funcionários de US-NC.

Saiba mais sobre marcas de escopo e o que você pode fazer em [Usar RBAC e marcas de escopo para TI distribuído](scope-tags.md).

### <a name="add-a-scope-tag"></a>Adicionar uma marca de escopo

1. Selecione **Escopo (Marcas)**.
2. Selecione **Adicionar** para criar uma nova marca de escopo. Ou, selecione uma marca de escopo existente na lista.
3. Selecione **OK** para salvar suas alterações.

## <a name="refresh-cycle-times"></a>Tempos de ciclo de atualização

O Intune usa os ciclos de atualização a seguir para verificar se há atualizações nos perfis de configuração:

| Plataforma | Ciclo de atualização|
| --- | --- |
| iOS | A cada 6 horas |
| macOS | A cada 6 horas |
| Android | A cada 8 horas |
| Computadores Windows 10 registrados como dispositivos | A cada 8 horas |
| Windows Phone | A cada 8 horas |
| Windows 8.1 | A cada 8 horas |

Se o dispositivo for recém-registrado, a frequência de execução do check-in será maior:

| Plataforma | Frequência |
| --- | --- |
| iOS | A cada 15 minutos por 6 horas e, então, a cada 6 horas |  
| macOS | A cada 15 minutos por 6 horas e, então, a cada 6 horas | 
| Android | A cada 3 minutos por 15 minutos e, então, a cada 15 minutos por 2 horas e, então, a cada 8 horas | 
| Computadores Windows 10 registrados como dispositivos | A cada 3 minutos por 30 minutos e, então, a cada 8 horas | 
| Windows Phone | A cada 5 minutos por 15 minutos e, então, a cada 15 minutos por 2 horas e, então, a cada 8 horas | 
| Windows 8.1 | A cada 5 minutos por 15 minutos e, então, a cada 15 minutos por 2 horas e, então, a cada 8 horas | 

A qualquer momento, os usuários podem abrir o aplicativo Portal da Empresa e sincronizar o dispositivo para verificar imediatamente atualizações de perfil.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
