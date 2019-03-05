---
title: Gerenciamento de dispositivos no Microsoft 365
description: O Microsoft 365 Enterprise inclui o Microsoft Intune. Veja como o Intune fornece gerenciamento de dispositivo móvel e gerenciamento de aplicativo móvel para sua organização, incluindo cenários comuns e usando o Intune para implantar o Microsoft 365 no seu ambiente.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93e34c3de77dde59b87829617b8cbbd2614f7081
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57231240"
---
# <a name="what-is-device-management"></a>O que é o gerenciamento de dispositivo? 

Uma tarefa essencial de qualquer Administrador é proteger os recursos e os dados de uma organização. Essa tarefa é o gerenciamento de dispositivo. Os usuários têm muitos dispositivos nos quais eles abrem e compartilham arquivos pessoais, visitam sites e instalam aplicativos e jogos. Esses mesmos usuários também são funcionários e alunos, e querem usar seus dispositivos para acessar os recursos do trabalho e da escola, como o email e o OneNote. O *Gerenciamento de dispositivo* permite às organizações proteger os recursos e os dados. 

Usando um provedor de gerenciamento de dispositivo, as organizações podem garantir que somente indivíduos e dispositivos autorizados tenham acesso às informações proprietárias. Da mesma forma, os usuários de dispositivos podem se sentir à vontade para acessar dados de trabalho de seu próprio smartphone, pois sabem que seus dispositivos atendem aos requisitos de segurança da organização. Como uma organização, você pode perguntar – **O que podemos usar para proteger nossos recursos?**

É aí que o [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) entra. O Intune oferece MDM (gerenciamento de dispositivo móvel) e MAM (gerenciamento de aplicativo móvel). Algumas das tarefas principais de qualquer solução de MDM ou MAM são:

- Compatibilidade com um ambiente móvel diversificado&mdash;gerenciar dispositivos iOS, Android, Windows e macOS com segurança
- Garantir que dispositivos e aplicativos estejam em conformidade com os requisitos de segurança da sua organização
- Criar políticas que ajudam a proteger os dados da empresa em dispositivos pessoais e de propriedade da empresa
- Usar uma solução móvel unificada para impor essas políticas e ajudar a gerenciar dispositivos, aplicativos, usuários e grupos.

O Intune está incluído no Microsoft 365, e se integra ao Microsoft Azure AD (Azure Active Directory). O Microsoft Azure AD ajuda a controlar quem tem acesso e o que pode ser acessado.

## <a name="hello-intune"></a>Olá, Intune!
Muitas organizações, como a Microsoft, usam o Intune para proteger os dados proprietários que os usuários acessam em seus dispositivos móveis pessoais e de propriedade da empresa. O Intune inclui recursos como políticas de configuração de dispositivos e aplicativos, políticas de atualização de software e status de instalação (bem como gráficos, tabelas e relatórios) para ajudar você a proteger e monitorar o acesso a dados.

É comum que as pessoas tenham vários dispositivos que usam plataformas diferentes. Por exemplo, um funcionário pode usar o Surface Pro para o trabalho e um dispositivo móvel Android em sua vida pessoal. E é comum acessar recursos organizacionais, como o Microsoft Outlook e o SharePoint, desses vários dispositivos.

Com o Intune, é possível gerenciar vários dispositivos por pessoa e as diferentes plataformas que são executadas em cada um deles, incluindo iOS, macOS, Android e Windows. O Intune separa as políticas e as configurações por plataforma de dispositivo, portanto, é muito fácil gerenciar e exibir os dispositivos de uma plataforma específica.

**[Cenários comuns](https://docs.microsoft.com/intune/common-scenarios)** é um excelente recurso para ver como o Intune responde a perguntas comuns ao trabalhar com dispositivos móveis. Você encontrará cenários sobre:  
- Proteger o email com o Exchange no Local
- Acessar o Office 365 de forma segura
- Usar dispositivos pessoais para acessar recursos organizacionais

## <a name="integration-with-secure-and-protect-services"></a>Integração com serviços de segurança e proteção
Uma tarefa essencial de qualquer solução de gerenciamento de dispositivo é fornecer segurança e proteção. O Intune realiza um excelente trabalho de integração com outros serviços para realizar essa tarefa. Por exemplo:

- O **Microsoft 365** é um componente fundamental para simplificar tarefas comuns de TI. Usando o Centro de Administração do Microsoft 365, você pode criar usuários, gerenciar grupos e obter acesso a outros serviços, como o Intune, o Azure Active Directory e muito mais. Por exemplo, você pode criar um grupo de dispositivos iOS no Microsoft 365. Em seguida, pode usar o Intune para efetuar push das políticas para o grupo de dispositivos iOS com foco nos recursos iOS, como o acesso à App Store, o uso do AirDrop, o backup para o iCloud, o uso do filtro de Web da Apple e muito mais.

- O **Windows Defender** inclui muitos recursos de segurança para ajudar a proteger dispositivos Windows 10. Por exemplo, usando o Intune e o Windows Defender juntos, você pode: 

    - Habilite o [Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10) para procurar atividades suspeitas nos arquivos e aplicativos nos dispositivos móveis. 
    - Use a [ATP (Proteção Avançada contra Ameaças) do Windows Defender](https://docs.microsoft.com/intune/advanced-threat-protection) para ajudar a evitar violações de segurança em dispositivos móveis e ajudar a limitar o impacto de uma violação de segurança ao bloquear um usuário de recursos corporativos.

- O **acesso condicional** é um recurso do Azure Active Directory e se integra perfeitamente com o Intune. Usando o [acesso condicional](https://docs.microsoft.com/intune/conditional-access), você pode garantir que somente dispositivos em conformidade tenham permissão para acessar o email, o SharePoint e outros aplicativos. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Escolha a solução de gerenciamento de dispositivo ideal para você

Há duas maneiras de abordar o gerenciamento de dispositivo. A primeira é gerenciar todos os aspectos de dispositivos usando todos os recursos internos do Intune. Isso é chamado de **MDM (gerenciamento de dispositivo móvel)**. Nessa abordagem, os usuários “registram” seus dispositivos e usam certificados para se comunicar com o Intune. Como um administrador de TI, você pode efetuar push de aplicativos para dispositivos, restringir os dispositivos a um sistema operacional específico, bloquear dispositivos pessoais e muito mais. Se um dispositivo for perdido ou roubado, você também poderá remover todos os dados do dispositivo. 

Na segunda abordagem, é possível gerenciar os aplicativos nos dispositivos. Isso é chamado de **MAM (gerenciamento de aplicativos móveis)**. Nessa abordagem, os usuários podem usar seus dispositivos pessoais para acessar recursos organizacionais. Ao abrir um aplicativo, como o email ou o SharePoint, é solicitado que os usuários realizem autenticação adicional. Se um dispositivo for perdido ou roubado, você poderá remover todos os dados da organização do dispositivo. 

Você também pode usar uma combinação de [MDM e MAM](https://docs.microsoft.com/intune/byod-technology-decisions) juntos.

Ao configurar o Intune, você também pode optar por trabalhar exclusivamente no portal do Azure para gerenciar dispositivos ou usar o Intune e o Microsoft 365 juntos para gerenciar dispositivos. Veja como o departamento de TI da Microsoft escolheu uma abordagem de gerenciamento de dispositivo moderno e as lições aprendidas no estudo de caso da IT da Microsoft [Migração do gerenciamento de dispositivo móvel para o Intune no portal do Azure](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal). 

## <a name="simplify-it-tasks-using-the-device-management-dashboard"></a>O departamento de TI simplifica as tarefas de usar o painel do Gerenciamento de Dispositivo

O [painel de Gerenciamento de Dispositivo](https://devicemanagement.portal.azure.com/) é um ponto único centralizado para gerenciar e concluir as tarefas em seus dispositivos móveis. Este painel inclui os serviços usados para gerenciamento de dispositivos, incluindo o Intune e o Azure Active Directory, e também para gerenciar aplicativos de cliente. 

No painel de Gerenciamento de Dispositivo, é possível:

- [Registrar dispositivos](https://docs.microsoft.com/intune/device-enrollment)
- [Configurar a conformidade do dispositivo](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Gerenciar dispositivos](https://docs.microsoft.com/intune/device-management)
- [Gerenciar aplicativos](https://docs.microsoft.com/intune/app-management)  
- [Livros eletrônicos do iOS](https://docs.microsoft.com/intune/vpp-ebooks-ios)  
- [Instalar o conector local do Exchange](https://docs.microsoft.com/intune/exchange-connector-install)  
- [Gerenciar funções](https://docs.microsoft.com/intune/role-based-access-control)  
- Gerenciar atualizações de software
  - [Gerenciar as atualizações do Windows 10](https://docs.microsoft.com/intune/windows-update-for-business-configure)  
  - [Gerenciar as atualizações do iOS](https://docs.microsoft.com/intune/software-updates-ios)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Gerenciar usuários](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Gerenciar grupos e membros](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Solucionar problemas](https://docs.microsoft.com/intune/help-desk-operators)

## <a name="next-step"></a>Próxima etapa
Quando estiver pronto para começar a usar uma solução de MDM ou MAM, percorra as diferentes etapas para configurar o Intune, registrar dispositivos e iniciar a criação de políticas, consulte [Gerenciamento de dispositivo móvel para o Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure). 
