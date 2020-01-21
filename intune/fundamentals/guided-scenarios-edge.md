---
title: Cenário guiado – Implantar o Microsoft Edge para dispositivos móveis
titleSuffix: Microsoft Intune
description: Saiba mais sobre o cenário guiado para implantar o Microsoft Edge para Dispositivos Móveis do portal de Gerenciamento de Dispositivo do Microsoft 365.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 88beb8f4791c127b0a225878f5bc43b6dd9b4025
ms.sourcegitcommit: 637375a390b6e34f9c4415c77b99fe2980bbf554
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75839369"
---
# <a name="guided-scenario---deploy-microsoft-edge-for-mobile"></a>Cenário guiado – Implantar o Microsoft Edge para dispositivos móveis 

Seguindo este [cenário guiado](~/fundamentals/guided-scenarios-overview.md), você pode atribuir o aplicativo Microsoft Edge aos seus usuários em dispositivos iOS ou Android em sua organização. A atribuição desse aplicativo permitirá que os usuários procurem conteúdo diretamente usando seus dispositivos corporativos. 

O Microsoft Edge permite que os usuários acabem com a desordem da Web com recursos internos que os ajudem a consolidar, organizar e gerenciar conteúdo de trabalho. Os usuários de dispositivos iOS e Android que entrarem com suas contas corporativas do Azure AD no aplicativo Microsoft Edge encontrarão seu navegador pré-carregado com os **Favoritos** do local de trabalho e filtros de site que você definir.

> [!NOTE]
> Se você tiver impedido os usuários de registrarem dispositivos iOS ou Android, esse cenário não permitirá o registro e os usuários precisarão instalar o Microsoft Edge por conta própria.
Os seguintes recursos corporativos do Microsoft Edge habilitados pelas políticas do Microsoft Intune incluem: 

- **Identidade Dupla**: os usuários podem adicionar uma conta corporativa e uma conta pessoal para navegação. Há uma separação completa entre as duas identidades, o que é semelhante à arquitetura e a experiência no Office 365 e no Outlook. Administradores do Intune poderão definir as políticas desejadas para uma experiência de navegação protegida dentro da conta de trabalho. 
- **Integração de política de proteção de aplicativo do Intune**: agora, os administradores podem direcionar políticas de proteção de aplicativo ao Microsoft Edge, inclusive o controle de ações de recortar, copiar e colar, impedir capturas de tela e garantir que links selecionados pelo usuário abram somente em outros aplicativos gerenciados.
- **Integração de Proxy de Aplicativo Azure**: os administradores podem controlar o acesso a aplicativos SaaS e aplicativos Web, ajudando a garantir que somente aplicativos baseados em navegador sejam executados no navegador seguro Microsoft Edge, mesmo se os usuários finais se conectarem da rede corporativa ou da Internet. 
- **Favoritos Gerenciados e atalhos da Home Page**: para facilitar o acesso, os administradores podem definir que as URLs apareçam sob os favoritos quando os usuários finais estiverem em seu contexto corporativo. Os administradores podem definir um atalho da home page, que aparecerá como o atalho primário quando o usuário corporativo abrir uma nova página ou uma nova guia no Microsoft Edge.

## <a name="prerequisites"></a>Pré-requisitos

- [Definir a autoridade MDM como Intune](mdm-authority-set.md#set-mdm-authority-to-intune) – A configuração de autoridade MDM (gerenciamento de dispositivo móvel) determina como você gerencia seus dispositivos. Como administrador de TI, você deverá definir uma autoridade MDM antes que os usuários possam registrar dispositivos para gerenciamento.
- Permissões de Administrador do Intune necessárias:
    - Permissões de leitura, criação, exclusão e atribuição de aplicativos gerenciados
    - Permissões de leitura, criação e atribuição de aplicativos móveis
    - Permissões de leitura, criação e atribuição de política
    - Permissão de leitura e atualização da organização

## <a name="step-1---introduction"></a>Etapa 1 – Introdução

Seguindo o cenário guiado **Implantar Microsoft Edge para Dispositivos Móveis**, você configurará uma implantação básica do Microsoft Edge para um grupo selecionado de usuários do iOS e Android. Essa implantação implementará **Identidade Dupla** e os **atalhos Favoritos Gerenciados e Página Inicial**. Além disso, os dispositivos registrados pelos usuários selecionados terão automaticamente o aplicativo Microsoft Edge instalado pelo Intune. Essa instalação automática ocorrerá em todos os tipos de registro controlados pelo usuário, que incluem: 
- Registro de iOS por meio do aplicativo do Portal da Empresa 
- Registro de afinidade de usuário do iOS por meio do Apple Business Manager 
- Registro de Android herdado por meio do Aplicativo do Portal da Empresa 

Este cenário guiado permitirá automaticamente que **MyApps** seja exibido nos favoritos do Microsoft Edge e configurará o navegador com a mesma identidade visual que você definiu para o aplicativo Portal da Empresa do Intune. 

### <a name="what-you-will-need-to-continue"></a>Do que você precisará para continuar
Perguntaremos a você sobre os favoritos do local de trabalho de que seus usuários precisam e os filtros necessários para a navegação na Web. Conclua as seguintes tarefas antes de continuar:

- Adicionar usuários a grupos do Azure AD. Para obter mais informações, confira [Criar um grupo básico e adicionar membros usando Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=2102458).
- Registrar dispositivos iOS ou Android no Intune. Para obter mais informações, confira [Registro de dispositivos](https://go.microsoft.com/fwlink/?linkid=2102547).
- Reunir uma lista de favoritos de local de trabalho a serem adicionados no Microsoft Edge.
- Reunir uma lista de filtros de site a ser imposta no Microsoft Edge.

## <a name="step-2---basics"></a>Etapa 2 – Conceitos básicos

Nesta etapa, você deverá inserir um nome e uma descrição para suas novas políticas do Microsoft Edge. Essas políticas poderão ser consultadas posteriormente se você precisar alterar as atribuições e configurações. O cenário guiado adicionará e atribuirá um aplicativo iOS do Microsoft Edge para seus dispositivos iOS e um aplicativo Android do Microsoft Edge para seus dispositivos Android. Além disso, esta etapa criará políticas de configuração para esses aplicativos.

## <a name="step-3---configuration"></a>Etapa 3 – Configuração

Nesta etapa, o cenário guiada configurará o Microsoft Edge para mostrar todos os outros aplicativos atribuídos a usuários por meio do Intune e compartilhar a mesma identidade visual que o aplicativo do Portal da Empresa do Microsoft Intune. Você pode configurar mais o Microsoft Edge com uma **URL de atalho da Página Inicial**, uma lista de **Indicadores Gerenciados** e uma lista de **URLs Bloqueadas**. A **URL de atalho da Página Inicial** será exibida para usuários como o primeiro ícone embaixo da barra de pesquisa quando eles abrirem uma nova guia no Microsoft Edge em seu dispositivo. Os **Indicadores Gerenciados** são uma lista de URLs favoritas que estão disponíveis para seus usuários quando eles usam o Microsoft Edge em seu contexto de trabalho. As **URLs Bloqueadas** especificam os sites bloqueados para seus usuários enquanto estão em seu contexto de trabalho. Todos os outros sites serão permitidos. 

## <a name="step-4---assignments"></a>Etapa 4 – Atribuições

Nesta etapa, você poderá escolher os grupos de usuários que deseja incluir para que o Microsoft Edge móvel esteja configurado para trabalho. O Microsoft Edge também será instalado em todos os dispositivos iOS e Android registrados por esses usuários.

## <a name="step-5---review--create"></a>Etapa 5 – Examinar + criar

A etapa final permite que você examine um resumo das configurações que você definiu. Após examinar suas escolhas, clique em **Criar** para concluir o cenário guiado. 

> [!NOTE]
> O Microsoft Edge pode levar até 12 horas para receber a configuração. Para saber mais, confira [Políticas de configuração de aplicativos do Microsoft Intune](~/apps/app-configuration-policies-overview.md).

> [!IMPORTANT]
> Depois que o cenário guiado estiver concluído, ele exibirá um resumo. Você pode modificar os recursos listados no resumo posteriormente. No entanto, a tabela que exibe esses recursos não será salva.

## <a name="next-steps"></a>Próximas etapas

- Aprimore a segurança do uso do Microsoft Edge configurando a integração da política de proteção de aplicativo do Intune. Para obter mais informações, confira [Políticas de proteção de aplicativo para o Microsoft Edge](~/apps/manage-microsoft-edge.md#application-protection-policies-for-microsoft-edge).
- Se você tiver sites de intranet a serem incluídos, explore a proteção de acesso com a integração de Proxy do Aplicativo Azure. Para obter mais informações, confira [Definir as configurações de Proxy de Aplicativo para o Microsoft Edge](~/apps/manage-microsoft-edge.md#configure-application-proxy-settings-for-microsoft-edge).

