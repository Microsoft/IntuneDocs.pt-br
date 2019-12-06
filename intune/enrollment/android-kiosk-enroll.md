---
title: Configurar o registro do Intune para dispositivos dedicados com Android Enterprise
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos dedicados com Android Enterprise no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d4ff9126fec182d1e0d2f3eb75297ede8a632e2e
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390715"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-dedicated-devices"></a>Configurar o registro do Intune para dispositivos dedicados com Android Enterprise

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Android Enterprise dá suporte a dispositivos de propriedade corporativa para único uso, no estilo quiosque, com seu conjunto de soluções dedicado. Esses dispositivos são usados para uma finalidade única, como sinalização digital, impressão de tíquete ou gerenciamento de inventário, para mencionar apenas alguns. Os administradores bloqueiam o uso de um dispositivo a um conjunto limitado de aplicativos e links da Web. Isso também impede que os usuários adicionem outros aplicativos ou executem outras ações no dispositivo.

O Intune ajuda você a implantar aplicativos e configurações em dispositivos dedicados com Android Enterprise. Para obter detalhes específicos sobre o Android Enterprise, confira [Requisitos do Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Os dispositivos que você gerencia dessa maneira são registrados no Intune sem uma conta de usuário e não são associados a nenhum usuário final. Eles não estão destinados a aplicativos de uso pessoal nem a aplicativos que têm um requisito rigoroso em relação a dados de conta específicos do usuário, como o Outlook ou o Gmail.

## <a name="device-requirements"></a>Requisitos do dispositivo

Os dispositivos precisam atender a esses requisitos para serem gerenciados como um dispositivo dedicado com Android Enterprise:

- Sistema operacional Android versão 5.1 e posterior.
- Os dispositivos precisam executar uma distribuição do Android que tem conectividade com GMS (Google Mobile Services). Os dispositivos precisam ter o GMS disponível e conseguir se conectar a ele.

## <a name="set-up-android-enterprise-dedicated-device-management"></a>Configurar o gerenciamento de dispositivo dedicado com Android Enterprise

Para configurar o gerenciamento de um dispositivo dedicado com Android Enterprise, execute estas etapas:

1. Para preparar-se para gerenciar dispositivos móveis, você precisa [definir a autoridade de MDM (gerenciamento de dispositivo móvel) para o **Microsoft Intune**](../fundamentals/mdm-authority-set.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configura o Intune para o gerenciamento de dispositivo móvel.
2. [Conecte sua conta de locatário do Intune à sua conta do Google Play Gerenciado](connect-intune-android-enterprise.md).
3. [Crie um perfil de registro.](#create-an-enrollment-profile)
4. [Crie um grupo de dispositivos](#create-a-device-group).
5. [Registre os dispositivos dedicados](#enroll-the-dedicated-devices).

### <a name="create-an-enrollment-profile"></a>Criar um perfil de registro

> [!NOTE]
> Quando um token expira, o perfil associado a ele deixa de ser exibido em **Registro de dispositivo** > **Registro do Android** > **Dispositivos dedicados de propriedade corporativa**. Para ver todos os perfis associados aos tokens ativos e inativos, clique em **Filtro** e marque as caixas dos estados de política "Ativo" e "Inativo". 

Você precisa criar um perfil de registro para que seja possível registrar os dispositivos dedicados. Quando o perfil é criado, ele fornece um token de registro (uma cadeia de caracteres aleatória) e um código QR. Dependendo do sistema operacional Android e da versão do dispositivo, é possível usar o token ou o código QR para [registrar o dispositivo dedicado](#enroll-the-dedicated-devices).

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) e escolha **Registro de dispositivos** > **Registro do Android** > **Dispositivos dedicados de propriedade corporativa**.
2. Escolha **Criar** e preencha os campos obrigatórios.
    - **Nome**: digite um nome que você usará ao atribuir o perfil ao grupo de dispositivos dinâmicos.
    - **Data de vencimento do token**: a data em que o token expira. O Google impõe o máximo de 90 dias.
3. Escolha **Criar** para salvar o perfil.

### <a name="create-a-device-group"></a>Criar um grupo de dispositivos

Você pode direcionar aplicativos e políticas a grupos de dispositivos atribuídos ou dinâmicos. Você pode configurar grupos de dispositivos dinâmicos do AAD para popular automaticamente os dispositivos registrados com um perfil de registro específico, seguindo estas etapas:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) e selecione **Grupos** > **Todos os grupos** > **Novo grupo**.
2. Na folha **Grupo**, preencha os campos obrigatórios da seguinte forma:
    - **Tipo de grupo**: Segurança
    - **Nome do grupo**: digite um nome intuitivo (como, dispositivos Fábrica 1)
    - **Tipo de associação**: dispositivo dinâmico
3. Escolha **Adicionar consulta dinâmica**.
4. Na folha **Regras de associação dinâmica**, preencha os campos da seguinte maneira:
    - **Adicionar regra de associação dinâmica**: regra simples
    - **Adicionar dispositivos em que**: enrollmentProfileName
    - Na caixa do meio, escolha **É igual a**.
    - No último campo, insira o nome do perfil de registro que você criou anteriormente.
    Para obter mais informações sobre regras de associação dinâmica, consulte [Regras de associação dinâmica para grupos no AAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership). 
5. Escolha **Adicionar consulta** > **Criar**.

### <a name="replace-or-remove-tokens"></a>Substituir ou remover os tokens

- **Substituir token**: você pode gerar um novo código QR/token quando um deles se aproximar da expiração usando Substituir token.
- **Revogar token**: você pode expirar imediatamente o código QR/token. Desse ponto em diante, o código QR/token não é mais utilizável. Use essa opção quando você:
  - compartilhar acidentalmente o código QR/token com uma entidade não autorizada
  - concluir todos os registros e não precisar mais do token/QR código

A substituição ou a revogação de um código QR/token não terá nenhum efeito em dispositivos que já estejam registrados.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) e escolha **Registro de dispositivos** > **Registro do Android** > **Dispositivos dedicados de propriedade corporativa**.
2. Escolha o perfil com o qual deseja trabalhar.
3. Escolha **Token**.
4. Para substituir o token, escolha **Substituir token**.
5. Para revogar o token, escolha **Revogar token**.

## <a name="enroll-the-dedicated-devices"></a>Registrar o dispositivo dedicado

Agora você pode [registrar seus dispositivos dedicados](android-dedicated-devices-fully-managed-enroll.md).

> [!NOTE]
> O aplicativo **Microsoft Intune** será instalado automaticamente durante o registro de um dispositivo dedicado.  Esse aplicativo é necessário para a inscrição e não pode ser desinstalado. 

## <a name="managing-apps-on-android-enterprise-dedicated-devices"></a>Gerenciamento de aplicativos em dispositivos dedicados com Android Enterprise

Somente os aplicativos que têm o Tipo de atribuição [definido como Obrigatório](../apps/apps-deploy.md#assign-an-app) podem ser instalados em dispositivos dedicados com Android Enterprise. Os aplicativos são instalados da loja do Google Play Gerenciado da mesma maneira que os dispositivos de perfil de trabalho do Android Enterprise.

Os aplicativos são atualizados automaticamente nos dispositivos gerenciados quando o desenvolvedor do aplicativo publica uma atualização no Google Play.

Para remover um aplicativo de dispositivos dedicados com Android Enterprise, você pode fazer o seguinte:
- Excluir a implantação do aplicativo necessário.
- Criar uma implantação de desinstalação para o aplicativo.

## <a name="next-steps"></a>Próximas etapas
- [Implantar aplicativos Android](../apps/apps-deploy.md)
- [Adicionar políticas de configuração do Android](../configuration/device-profiles.md)
