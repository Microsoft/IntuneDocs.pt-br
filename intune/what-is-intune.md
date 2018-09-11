---
title: Introdução ao Intune no Portal do Azure
titlesuffix: ''
description: O Microsoft Intune está disponível no portal do Azure. Obtenha as noções básicas sobre o Intune no Portal do Azure.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: get-started
ms.openlocfilehash: 3f8f0dce416c943dbc244d0e2a4366b12b305708
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253775"
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Introdução ao Microsoft Intune no portal do Azure


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Semelhante a outros serviços do Azure, o Microsoft Intune está disponível no Portal do Azure. Ao selecionar **Intune** no Portal do Azure, você pode gerenciar os dispositivos móveis, computadores e aplicativos da sua organização.

> [!NOTE]
> Se você usar uma versão anterior do Microsoft Intune, as informações a seguir poderão ser úteis:
>     * [Para onde foram os meus recursos no Azure? ](ui-changes.md) é uma referência para mostrar as interfaces do usuário e os fluxos de trabalho específicos alterados com a mudança para o Azure.
>     * [Grupos clássicos do Intune no Portal do Azure](groups-get-started.md) explica as implicações da mudança nos grupos de segurança do Azure Active Directory para o gerenciamento de grupos.

Destaques da experiência do Microsoft Intune no Portal do Azure incluem:

- Um console integrado para todos os seus componentes de EMS (Enterprise Mobility + Security)
- Um console baseado em HTML criado nos padrões da Web
- Suporte à API do Microsoft Graph para automatizar diversas ações
- Grupos do Azure Active Directory (AD) para fornecer compatibilidade entre todos os aplicativos do Azure
- Suporte para a maioria dos navegadores da Web modernos

## <a name="before-you-start"></a>Antes de começar

Para usar o Intune no Portal do Azure, você deve ter uma conta de administrador e locatário Intune. [Inscreva-se em uma conta](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) se você ainda não tiver uma.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Navegadores da Web com suporte no Portal do Azure

O Portal do Azure é executado na maioria dos computadores, Macs e tablets. Não há suporte para telefones celulares.
No momento, há suporte para os seguintes navegadores:

- Microsoft Edge (última versão)
- Microsoft Internet Explorer 11
- Safari (última versão, somente Mac)
- Chrome (última versão)
- Firefox (última versão)

Visite o [portal do Azure](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) para obter as informações mais recentes sobre os navegadores com suporte.

## <a name="microsoft-intune-in-the-azure-portal"></a>Microsoft Intune no Portal do Azure

O [Portal do Azure](https://portal.azure.com) é onde você pode encontrar o serviço Microsoft Intune. Há diversos serviços no Azure e muitos deles você não usa regularmente. Para obter um guia rápido para personalizar sua experiência do portal, consulte [Introdução ao Intune no Portal do Azure](get-started-azure.md).

## <a name="the-microsoft-intune-documentation"></a>A documentação do Microsoft Intune

Este tópico, bem como todo o conjunto de documentação do Microsoft Intune, é atualizado continuamente. Caso tenha sugestões que gostaria de ver, deixe seus comentários nos comentários do tópico. Adoraríamos ouvir sua opinião.

A documentação reflete o layout do Microsoft Intune no Portal do Azure (mostrado abaixo) para que seja mais fácil de encontrar as informações necessárias.

![Cargas de trabalho do Portal do Azure](./media/azure-portal-workloads.png)

### <a name="documentation-guide"></a>Guia da documentação

Use a tabela a seguir para localizar rapidamente e compreender as principais áreas do Microsoft Intune.

| Seção                                                      | Descrição                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Introdução](introduction-intune.md)       | Entenda os conceitos básicos do Intune, incluindo:<br /> – Soluções comuns<br /> – A maneira como o Microsoft Intune funciona<br /> – Gerenciamento de dispositivos no Intune<br /> – Gerenciamento de aplicativo no Intune<br /> – EMM (Enterprise Mobility Management) com e sem o registro de dispositivo                                                         |
| [Planejamento e design](planning-guide.md)                         | Diretrizes para ajudá-lo a planejar e projetar seu ambiente do Microsoft Intune com êxito.                                                                                                                                                                                                             |
| [Registro de dispositivo](device-enrollment.md)                    | Entenda como o Microsoft Intune ajuda você a gerenciar dispositivos da sua força de trabalho registrando os dispositivos no serviço Intune. Há vários métodos de registrar os dispositivos da sua força de trabalho.                                                                                                         |
| [Conformidade do dispositivo](device-compliance.md)                    | As políticas de conformidade do dispositivo no Intune definem as regras e as configurações às quais um dispositivo deve satisfazer para ser considerado em conformidade pelo Microsoft Intune. Por exemplo, exigir uma senha para acesso ao dispositivo, criptografar dispositivos e exigir uma versão mínima do sistema operacional são todos os exemplos de conformidade. |
| [Configuração do dispositivo](device-profiles.md)                   | Defina as configurações e os recursos em todos os dispositivos gerenciados usando o Microsoft Intune criando perfis de dispositivo. Por exemplo, você pode configurar esses recursos como notificações, compartilhamento de dados, suporte por email, conectividade de Wi-Fi, certificados e proteção de ponto de extremidade.              |
| [Dispositivos](device-management.md)                              | Garanta que os dispositivos que você gerencia estejam fornecendo os recursos que seus usuários finais precisam para realizar seu trabalho enquanto protege os dados da sua empresa de riscos. Gerencie dispositivos examinando o inventário de dispositivos de força de trabalho e realizando ações de dispositivo remoto.                                                      |
| [Aplicativos móveis](app-management.md)                             | Entenda como adicionar, implantar, monitorar, configurar e proteger aplicativos.                                                                                                                                                                                                                             |
| [Acesso condicional](conditional-access.md)                  | Defina condições baseadas no dispositivo e baseadas no aplicativo que controlam o acesso aos dados corporativos.                                                                                                                                                                                                            |
| [Usuários](users-add.md)                                        | Saiba como adicionar usuários de dispositivos e aplicativos gerenciados por você.                                                                                                                                                                                                                                           |
| [Grupos](groups-get-started.md)                              | Saiba mais sobre como você pode criar e gerenciar grupos com o Intune. Usando grupos, você pode rapidamente atribuir políticas de proteção e configuração de aplicativo e dispositivo.                                                                                                                                             |
| [Funções do Intune](role-based-access-control.md)                 | Saiba como controlar quem pode executar várias ações do Intune e como essas ações são aplicadas. Você pode usar as funções internas que abordam alguns cenários comuns do Intune ou pode criar suas próprias funções.                                                                                 |
| [Atualizações de software](windows-update-for-business-configure.md) | Saiba como configurar atualizações de software para dispositivos Windows 10.                                                                                                                                                                                                                                  |

## <a name="whats-new"></a>Quais são as novidades?

Para saber mais sobre os recursos mais recentes do Microsoft Intune, consulte [Novidades](whats-new.md).
