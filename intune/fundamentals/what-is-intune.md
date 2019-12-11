---
title: O que é o Microsoft Intune – Azure | Microsoft Docs
description: Saiba por que o Microsoft Intune é o componente de MDM (gerenciamento de dispositivo móvel) e de MAM (gerenciamento de aplicativo móvel) da solução Enterprise Mobility + Security e como ele ajuda a proteger os dados da sua empresa.
keywords: o que é o Intune
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/14/2019
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: c3c03c67a99b78804c999250f8d1148a4b3d1d97
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504757"
---
# <a name="microsoft-intune-is-an-mdm-and-mam-provider-for-your-devices"></a>O Microsoft Intune é um provedor de MDM e de MAM para seus dispositivos

O Microsoft Intune é um serviço baseado em nuvem que se concentra no MDM (gerenciamento de dispositivo móvel) e no MAM (gerenciamento de aplicativo móvel). O Intune está incluído no [pacote de EMS (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) e permite que os usuários sejam produtivos, garantindo a proteção dos dados da organização. Ele se integra a outros serviços, inclusive ao Microsoft 365 e ao Azure Active Directory (Azure AD), para controlar quem tem acesso e a que conteúdo o acesso é permitido, e à Proteção de Informações do Azure, para garantir a proteção dos dados. Ao usá-lo com o Microsoft 365, você pode permitir que sua força de trabalho se mantenha produtiva em todos os dispositivos, ao mesmo tempo que protege as informações da organização.

![Imagem da arquitetura do Intune](./media/what-is-intune/intunearch_sm.png)

Exibir uma [versão maior](./media/what-is-intune/intunearchitecture.svg) do diagrama da arquitetura do Intune.

Com o Intune, você pode:

- Escolha estar 100% na nuvem com o Intune ou ser [cogerenciado](https://docs.microsoft.com/sccm/comanage/overview) com o Configuration Manager e o Intune.
- Defina regras e configurações em dispositivos pessoais e de propriedade da organização para acessar dados e redes.
- Implante e autentique aplicativos em dispositivos locais e móveis.
- Proteja as informações da empresa controlando a maneira como os usuários acessam e compartilham informações.
- Os dispositivos e aplicativos devem atender aos requisitos de segurança.

## <a name="manage-devices"></a>Gerenciar dispositivos

No Intune, você gerencia os dispositivos usando uma abordagem adequada para você. Para dispositivos de propriedade da organização, convém ter controle total sobre os dispositivos, incluindo configurações, recursos e segurança. Nessa abordagem, os dispositivos e os usuários desses dispositivos "inscrevem-se" no Intune. Depois de inscritos, eles recebem suas regras e configurações por meio de políticas configuradas no Intune. Por exemplo, você pode definir os requisitos de senha e PIN, criar uma conexão VPN, configurar a proteção contra ameaças e muito mais.

Para dispositivos pessoais ou BYOD (traga seu próprio dispositivo), os usuários podem não querer que os administradores da organização tenham controle total. Nessa abordagem, dê opções aos usuários. Por exemplo, os usuários [registrarão](../enrollment/device-enrollment.md) os dispositivos se desejarem ter acesso total aos recursos da organização. Ou, se esses usuários só quiserem acessar o email ou o Microsoft Teams, use as políticas de proteção de aplicativo que exigem a MFA (autenticação multifator) para usar esses aplicativos.

Quando os dispositivos são registrados e gerenciados no Intune, os administradores podem:

- Ver os dispositivos registrados e obter um inventário dos dispositivos que acessam os recursos da organização.
- Configurar os dispositivos para que eles atendam aos padrões de segurança e integridade. Por exemplo, você provavelmente desejará bloquear dispositivos com jailbreak.
- Envie certificados por push para os dispositivos para que os usuários possam facilmente acessar sua rede Wi-Fi ou usar uma VPN para se conectar à sua rede.
- Confirar relatórios sobre usuários e dispositivos que estão em conformidade ou não.
- Remover os dados da organização de um dispositivos caso ele seja perdido, roubado ou não seja mais usado.

**Recursos online**:

- [Qual é o registro de dispositivos?](../enrollment/device-enrollment.md)

- [Aplicar recursos e configurações aos seus dispositivos usando perfis de dispositivo](../configuration/device-profiles.md)

- [Proteger dispositivos com o Microsoft Intune](../protect/device-protect.md)

## <a name="manage-apps"></a>Gerenciar aplicativos

O MAM (gerenciamento de aplicativo móvel) no Intune foi projetado para proteger os dados da organização no nível do aplicativo, inclusive aplicativos personalizados e aplicativos da loja. O gerenciamento de aplicativos pode ser usado em dispositivos pessoais e de propriedade da organização.

Quando os aplicativos são gerenciados no Intune, os administradores podem:

- Adicionar e atribuir aplicativos móveis a grupos de usuários, inclusive usuários em grupos específicos, dispositivos em grupos específicos e muito mais.
- Configurar aplicativos para iniciar ou executar com configurações específicas habilitadas e atualizar os aplicativos existentes que já estão no dispositivo.
- Conferir relatórios sobre quais aplicativos são usados e acompanhar o uso deles.
- Fazer um apagamento seletivo removendo somente os dados da organização dos aplicativos.

Uma maneira do Intune fornecer segurança de aplicativo móvel é por meio das **[políticas de proteção de aplicativo](../apps/app-protection-policy.md)** . Políticas de proteção de aplicativo:

- Usam a identidade do Azure AD para isolar dados da organização de dados pessoais. Portanto, as informações pessoais são isoladas do reconhecimento de TI organizacional. Os dados acessados usando as credenciais da organização recebem proteção de segurança adicional.
- Ajudam a proteger o acesso em dispositivos pessoais restringindo ações que os usuários podem executar, como copiar e colar, salvar e exibir.
- Podem ser criadas e implantadas em dispositivos registrados no Intune, registrados em outro serviço de MDM ou não registrados em nenhum serviço de MDM. Em dispositivos registrados, as políticas de proteção de aplicativo podem adicionar uma camada extra de proteção.

Por exemplo, um usuário entra em um dispositivo com suas respectivas credenciais da organização. A identidade da organização permite acessar os dados que são negados à identidade pessoal. À medida que os dados da organização são usados, as políticas de proteção de aplicativo controlam como os dados são salvos e compartilhados. Quando os usuários entram usando a identidade pessoal, essas mesmas proteções não são aplicadas. Dessa forma, o setor de TI tem controle dos dados da organização, enquanto os usuários finais mantêm o controle e a privacidade dos dados pessoais.

E você pode usar o Intune com outros serviços no EMS. Esse recurso fornece ao aplicativo móvel da sua organização segurança além da que está incluída no sistema operacional e em qualquer aplicativo. Aplicativos gerenciados com o EMS têm acesso a um conjunto mais amplo de recursos de proteção de dados e de aplicativos móveis.

![Imagem que mostra os níveis de segurança de dados do gerenciamento de aplicativo](./media/what-is-intune/managing-mobile-apps.png)

## <a name="compliance-and-conditional-access"></a>Conformidade e acesso condicional

O Intune se integra ao Azure AD para habilitar um amplo conjunto de cenários de controle de acesso. Por exemplo, exigir que os dispositivos móveis estejam em conformidade com os padrões da organização definidos no Intune antes de acessar recursos de rede, como email ou SharePoint. Da mesma forma, você pode bloquear os serviços para que eles só sejam disponibilizados para um conjunto específico de aplicativos móveis. Por exemplo, você pode bloquear o Exchange Online para que ele só seja acessado pelo Outlook ou pelo Outlook Mobile.

**Recursos online**:

- [Definir regras em dispositivos para permitir o acesso aos recursos da sua organização](../protect/device-compliance-get-started.md)

- [Maneiras comuns de usar o Acesso Condicional com o Intune](../protect/conditional-access-intune-common-ways-use.md)

## <a name="how-to-get-intune"></a>Como obter o Intune

O Intune está disponível:

- Como um [serviço Azure](https://go.microsoft.com/fwlink/?linkid=2090973) autônomo
- Incluído com o [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune) e o [Microsoft 365 Governamental](https://www.microsoft.com/microsoft-365/government)
- Como o [Gerenciamento de Dispositivo Móvel no Office 365](https://support.office.com/article/choose-between-mdm-for-office-365-and-microsoft-intune-c93d9ab9-efb2-4349-9b93-30c30562ee22), que consiste em alguns recursos limitados do Intune

O Intune é usado por muitos setores, inclusive por [governos](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description), [instituições de ensino](https://www.microsoft.com/en-us/education/intune), [dispositivos de quiosque ou dedicados](../configuration/kiosk-settings.md) para manufatura e varejo e muito mais.

## <a name="next-steps"></a>Próximas etapas

- Leia alguns dos [problemas comuns de negócios que o Intune ajuda a resolver](https://docs.microsoft.com/intune/common-scenarios).
- Comece com uma [avaliação gratuita de 30 dias do Intune](free-trial-sign-up.md).
- Planeje sua [migração para o Intune](migration-guide.md).
- Com sua assinatura ou avaliação gratuita, percorra o [Início Rápido: Criar um perfil de dispositivo de email para iOS](../configuration/quickstart-email-profile.md).
