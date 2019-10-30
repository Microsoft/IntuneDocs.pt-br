---
title: Criar perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Adicionar ou configurar um perfil de configuração de dispositivo no Microsoft Intune. Selecione o tipo de plataforma, defina as configurações e adicione uma marca de escopo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 97227d5ca75b3584cb4e603a16601b2a22deb919
ms.sourcegitcommit: 1a5b185acd27954b10b6d59409d82eb80fd71284
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72681453"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Criar um perfil de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Perfis de dispositivo permitem que você adicione e defina as configurações e, em seguida, envie essas configurações por push para dispositivos em sua organização. [Aplicar recursos e configurações em seus dispositivos usando perfis de dispositivo](device-profiles.md) apresenta mais detalhes, incluindo o que você pode fazer.

Este artigo:

- Lista as etapas para criar um perfil.
- Mostra como adicionar uma marca de escopo para "filtrar" o perfil.
- Descreve as regras de aplicabilidade em dispositivos Windows 10 e mostra como criar uma regra.
- Lista os tempos de ciclo de atualização de check-in quando os dispositivos recebem os perfis e atualizações de perfil.

## <a name="create-the-profile"></a>Criar o perfil

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Selecione **Configuração do dispositivo**. Você tem as seguintes opções:

    - **Visão geral**: Lista o status dos perfis e fornece detalhes adicionais sobre os perfis que você atribuiu a usuários e dispositivos.
    - **Gerenciar**: Crie perfis de dispositivo, carregue [scripts personalizados do PowerShell](../apps/intune-management-extension.md) a serem executados no perfil e adicione planos de dados a dispositivos usando o [eSIM](esim-device-configuration.md).
    - **Monitorar**: Verifique o status de um perfil quanto ao êxito ou falha, além de exibir logs sobre os perfis.
    - **Configuração**: Adicione uma autoridade de certificação SCEP ou PFX ou habilite o [Telecom Expense Management](telecom-expenses-monitor.md) no perfil.

3. Selecione **Perfis** > **Criar Perfil**. Insira as seguintes propriedades:

   - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um nome de perfil bom é **perfil de email do WP para toda a empresa**.
   - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
   - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:  

       - **Android**
       - **Android Enterprise**
       - **iOS/iPadOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 e posterior**
       - **Windows 10 e posterior**

   - **Tipo de perfil**: Selecione o tipo de configurações que deseja criar. A lista dependerá da **plataforma** escolhida.
   - **Configurações**: Os artigos a seguir descrevem as configurações de cada tipo de perfil:

       - [Modelos Administrativos](administrative-templates-windows.md)
       - [Personalizado](../custom-settings-configure.md)
       - [Otimização de Entrega](../delivery-optimization-windows.md)
       - [Recursos de dispositivo](../device-features-configure.md)
       - [Restrições de dispositivo](device-restrictions-configure.md)
       - [Atualização de edição e opção de modo](edition-upgrade-configure-windows-10.md)
       - [Educação](education-settings-configure.md)
       - [Email](email-settings-configure.md)
       - [Endpoint protection](../protect/endpoint-protection-configure.md)
       - [Proteção de identidade](../protect/identity-protection-configure.md)  
       - [Quiosque](kiosk-settings.md)
       - [Certificado PKCS](../protect/certficates-pfx-configure.md)
       - [Certificado importado PKCS](../protect/certificates-imported-pfx-configure.md)
       - [Certificado SCEP](../protect/certificates-scep-configure.md)
       - [Certificado confiável](../protect/certificates-configure.md)
       - [Políticas de atualização](../software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](../protect/advanced-threat-protection.md)
       - [Proteção de Informações do Windows](../protect/windows-information-protection-configure.md)

     Por exemplo, se você selecionar **iOS/iPadOS** como a plataforma, as opções de tipo de perfil serão semelhantes ao seguinte perfil:

     ![Criar perfil do iOS no Intune](./media/device-profile-create/create-device-profile.png)

4. Quando terminar, selecione **OK** > **Criar** para salvar as alterações. O perfil é criado e exibido na lista.

## <a name="scope-tags"></a>Marcas de escopo

Depois de adicionar as configurações, você também poderá adicionar uma marca de escopo ao perfil. As marcas de escopo atribuem e filtram políticas para grupos específicos, como RH ou Todos os funcionários de US-NC.

Saiba mais sobre marcas de escopo e o que você pode fazer em [Usar RBAC e marcas de escopo para TI distribuído](../fundamentals/scope-tags.md).

### <a name="add-a-scope-tag"></a>Adicionar uma marca de escopo

1. Selecione **Escopo (Marcas)** .
2. Selecione **Adicionar** para criar uma nova marca de escopo. Ou, selecione uma marca de escopo existente na lista.
3. Selecione **OK** para salvar suas alterações.

## <a name="applicability-rules"></a>Regras de aplicabilidade

Aplica-se a:

- Windows 10 e posterior

As regras de aplicabilidade permitem aos administradores definir como destino os dispositivos de um grupo que atenda a critérios específicos. Por exemplo, você cria um perfil de restrições de dispositivo que se aplica ao grupo **Todos os dispositivos Windows 10**. E você quer atribuir esse perfil apenas a dispositivos com Windows 10 Enterprise.

Para executar essa tarefa, crie uma **regra de aplicabilidade**. Essas regras são úteis para os seguintes cenários:

- Você usa o Windows 10 Education. No Bellows College, você deseja direcionar para todos os dispositivos com Windows 10 Education entre RS3 e RS4.
- Você deseja direcionar para todos os usuários de Recursos Humanos da Contoso, mas somente com dispositivos Windows 10 Professional ou Enterprise.

Para abordar esses cenários, você pode:

- Criar um grupo de dispositivos que inclua todos os dispositivos do Bellows College. No perfil, adicione uma regra de aplicabilidade a ser aplicada se a versão mínima do sistema operacional for `16299` e a versão máxima for `17134`. Atribua esse perfil ao grupo de dispositivos do Bellows College.

  Quando atribuído, o perfil se aplica a dispositivos entre as versões mínima e máxima inseridas. Os dispositivos que não estejam entre as versões mínima e máxima inseridas exibem o status **Não aplicável**.

- Crie um grupo de usuários que inclua todos os usuários de RH (Recursos Humanos) da Contoso. No perfil, adicione uma regra de aplicabilidade a ser aplicada a dispositivos com Windows 10 Professional ou Enterprise. Atribua esse perfil ao grupo de usuários de RH.

  Quando atribuído, o perfil se aplica a dispositivos com Windows 10 Professional ou Enterprise. Os dispositivos que não executam essas edições exibem o status **Não aplicável**.

- Se houver dois perfis com as mesmas configurações, o perfil será aplicado sem regra de aplicabilidade. 

  Por exemplo, o Perfil A é direcionado ao grupo de dispositivos Windows 10, habilita o BitLocker e não tem uma regra de aplicabilidade. Já o Perfil B é direcionado ao mesmo grupo de dispositivos Windows 10, habilita o BitLocker e tem uma regra de aplicabilidade para aplicar esse perfil somente ao Windows 10 Enterprise.

  Quando os dois perfis são atribuídos, o Perfil A é aplicado, porque ele não tem uma regra de aplicabilidade. 

Quando você atribui o perfil aos grupos, as regras de aplicabilidade agem como um filtro e são direcionadas apenas aos dispositivos que atendem aos seus critérios.

### <a name="add-a-rule"></a>Adicionar uma regra

1. Selecione **Regras de Aplicabilidade**. Você pode escolher **Regra**, **Propriedade** e **Edição do Sistema Operacional**:

    ![Adicionar uma regra de aplicabilidade a um perfil de configuração de dispositivo no Microsoft Intune](./media/device-profile-create/applicability-rules.png)

2. Em **Regra**, escolha se deseja incluir ou excluir usuários ou grupos. Suas opções:

    - **Atribuir perfil se**: incluir usuários ou grupos que atendem aos critérios inseridos.
    - **Não atribuir perfil se**: excluir usuários ou grupos que atendem aos critérios inseridos.

3. Em **Propriedade**, escolha um filtro. Suas opções: 

    - **Edição do Sistema Operacional**: na lista, marque as edições do Windows 10 que você deseja incluir (ou excluir) em sua regra.
    - **Versão do Sistema Operacional**: insira os números da versão **mínima** e **máxima** do Windows 10 que você deseja incluir (ou excluir) em sua regra. Os dois valores são obrigatórios.

      Por exemplo, você pode inserir `10.0.16299.0` (RS3 ou 1709) como a versão mínima e `10.0.17134.0` (RS4 ou 1803) como a versão máxima. Ou você pode ser mais específico e inserir `10.0.16299.001` como a versão mínima, e `10.0.17134.319` como a versão máxima.

4. Selecione **Adicionar** para salvar as alterações.

## <a name="refresh-cycle-times"></a>Tempos de ciclo de atualização

O Microsoft Intune usa diferentes ciclos de atualização para verificar se há atualizações nos perfis de configuração. Se o registro do dispositivo for recente, a frequência de execução da verificação será maior. Os [ciclos de atualização de política e perfil](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) descrevem os tempos de atualização estimados.

A qualquer momento, os usuários podem abrir o aplicativo Portal da Empresa e sincronizar o dispositivo para verificar imediatamente atualizações de perfil.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
