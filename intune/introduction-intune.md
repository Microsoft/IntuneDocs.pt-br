---
title: O que é o Microsoft Intune
description: Saiba por que o Intune é o componente de MDM (gerenciamento de dispositivo móvel) e de MAM (gerenciamento de aplicativo móvel) da solução Enterprise Mobility + Security e como ele ajuda a proteger os dados da sua empresa.
keywords: o que é o Intune
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/01/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
search.appverid: MET150
ms.custom: get-started
ms.openlocfilehash: d801d824cefb00ff197125588f840246b889844e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187068"
---
# <a name="what-is-intune"></a>O que é o Intune?

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

O Intune é um serviço baseado em nuvem no espaço de EMM (gerenciamento de mobilidade empresarial) que colabora para permitir que sua a força de trabalho fique produtiva e ainda mantém os dados corporativos protegidos. Com o Intune, você pode:
* gerenciar os dispositivos móveis que sua força de trabalho usa para acessar dados da empresa.
* gerenciar os aplicativos móveis que sua força de trabalho usa.
* proteger informações da empresa, ajudando a controlar a forma como sua força de trabalho as acessa e compartilha.
* garantir que dispositivos e aplicativos sejam compatíveis com os requisitos de segurança da empresa.

## <a name="common-business-problems-that-intune-helps-solve"></a>Problemas de negócios comuns que o Intune ajuda a resolver

* [Proteger seus dados e emails locais para que eles possam ser acessados por dispositivos móveis](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Proteger seus dados e emails do Office 365 para que eles possam ser acessados com segurança por dispositivos móveis](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Emitir telefones corporativos para sua força de trabalho](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Oferecer um programa de BYOD (traga seu próprio dispositivo) ou de dispositivos pessoais para todos os funcionários](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Habilitar os funcionários a acessarem o Office 365 de forma segura de um quiosque público não gerenciado](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Emitir tablets compartilhados de uso limitado para seus funcionários](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)


## <a name="how-does-intune-work"></a>Como o Intune funciona?
O Intune é o componente do EMS (Enterprise Mobility + Security) que gerencia aplicativos e dispositivos móveis. Ele se integra intimamente a outros componentes do EMS como o Azure AD (Azure Active Directory) para controle de identidade e acesso e à Proteção de Informações do Azure para proteção de dados. Ao usá-lo com o Office 365, você pode permitir que sua força de trabalho fique produtiva usando todos os dispositivos possíveis e ainda manter as informações da organização protegidas.

![Imagem da arquitetura do Intune](./media/intunearch_sm.png)

Exibir uma [versão maior](./media/intunearchitecture.svg) do diagrama da arquitetura do Intune.

A maneira de usar os recursos de gerenciamento de dispositivo e aplicativo do Intune e a proteção de dados do EMS dependerá do [problema de negócios que você estiver tentando resolver](#common-business-problems-that-intune-helps-solve). Por exemplo:
* Você usará o gerenciamento de dispositivo intensamente se estiver criando um pool de dispositivos de uso único para serem compartilhados por funcionários em turnos diferentes em uma loja de varejo.
* Você poderá contar com o gerenciamento de aplicativo e a proteção de dados se permitir que sua força de trabalho use seus dispositivos pessoais para acessar dados corporativos (BYOD).  
* Se pretender emitir telefones corporativos para funcionários que trabalham com informações, você usará intensamente todas essas tecnologias.

## <a name="intune-device-management-explained"></a>Explicação sobre o gerenciamento de dispositivo do Intune
O gerenciamento de dispositivo do Intune funciona usando os protocolos ou as APIs que estão disponíveis nos sistemas operacionais móveis. Ele inclui tarefas como:
* Registrar dispositivos no gerenciamento para que o setor de TI tenha um inventário dos dispositivos que estão acessando serviços corporativos
* configurar dispositivos para garantir que eles atendam aos padrões de integridade e segurança da empresa
* Fornecer certificados e perfis de Wi-Fi/VPN para acessar serviços corporativos
* emitir relatórios e avaliar a conformidade do dispositivo com os padrões corporativos
* remover dados corporativos de dispositivos gerenciados  

Algumas pessoas podem pensar que o **controle de acesso a dados corporativos** é um recurso de gerenciamento do dispositivo. Nós não pensamos dessa forma porque não é algo que o sistema operacional móvel fornece. Em vez disso, é algo que o provedor de identidade fornece. Em nosso caso, o provedor de identidade é o Azure AD (Azure Active Directory), o sistema de gerenciamento de acesso e identidade da Microsoft.  

O Intune se integra ao Azure AD para habilitar um amplo conjunto de cenários de controle de acesso. Por exemplo, você pode exigir que um dispositivo móvel esteja em conformidade com os padrões corporativos que você define no Intune, para que ele possa acessar um serviço corporativo como o Exchange. Da mesma forma, você pode bloquear o serviço corporativo para um conjunto específico de aplicativos móveis. Por exemplo, você pode bloquear o Exchange Online para ser acessado apenas pelo Outlook ou pelo Outlook Mobile.

## <a name="intune-app-management-explained"></a>Explicação sobre o gerenciamento de aplicativo do Intune
Quando falamos sobre gerenciamento de aplicativo, estamos falando de:
* Atribuir aplicativos móveis para funcionários
* Definir os aplicativos com configurações padrão a serem usadas quando o aplicativo for executado
* controlar a forma como os dados corporativos são usados e compartilhados em aplicativos móveis
* remover dados corporativos de aplicativos móveis   
* Atualizar aplicativos
* emitir relatórios sobre o inventário de aplicativos móveis
* Acompanhar o uso de aplicativos móveis

Nós vimos que o termo MAM (gerenciamento de aplicativo móvel) é usado para indicar uma dessas coisas individualmente ou para indicar combinações específicas. Especificamente, é comum que as pessoas associem o conceito de configuração de aplicativo ao conceito de proteger dados corporativos de dentro dos aplicativos móveis. Isso ocorre porque alguns aplicativos móveis expõem definições que permitem que seus recursos de segurança de dados sejam configurados.

Quando falamos sobre configuração de aplicativo e sobre o Intune, estamos nos referimos especificamente a tecnologias como [configuração de aplicativo gerenciado no iOS](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html).

Quando usa o Intune com outros serviços no EMS, você pode fornecer à sua organização segurança de aplicativo móvel muito além da que é fornecida pelo sistema operacional móvel e pelo próprio aplicativo por meio da configuração do aplicativo. Um aplicativo gerenciado com o EMS tem acesso a um conjunto mais amplo de proteções de dados e aplicativos móveis que inclui:

* [Logon único](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Autenticação multifator](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication)
* [Acesso condicional do aplicativo – permitir acesso se o aplicativo móvel contiver dados corporativos](app-based-conditional-access-intune.md)
* [Isolar dados corporativos de dados pessoais dentro do mesmo aplicativo](app-protection-policy.md)
* [Política de proteção de aplicativo (PIN, criptografia, salvar como, área de transferência etc.)](app-protection-policies.md)
* [Apagamento de dados corporativos de um aplicativo móvel](apps-selective-wipe.md)
* [Suporte do Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Imagem que mostra os níveis de segurança de dados do gerenciamento de aplicativo](./media/managing-mobile-apps.png)

### <a name="intune-app-security"></a>Segurança de aplicativo do Intune
Fornecer segurança de aplicativo faz parte do gerenciamento de aplicativo e, no Intune, quando falamos em segurança de aplicativo móvel, queremos dizer:
* manter informações pessoais isoladas do reconhecimento de TI corporativo
* restringir as ações que os usuários podem executar com informações corporativas, como copiar, recortar/colar, salvar e exibir
* remover dados corporativos de aplicativos móveis, também conhecido como apagamento seletivo ou apagamento corporativo

Uma maneira do Intune fornecer segurança de aplicativo móvel é por meio de seu recurso de **política de proteção de aplicativo**. A política de proteção de aplicativo usa a identidade do Azure AD para isolar dados corporativos de dados pessoais. Os dados acessados usando uma credencial corporativa terão proteções corporativas adicionais.

Por exemplo, quando um usuário faz logon em seu dispositivo usando credenciais corporativas, sua identidade corporativa permite acessar dados que são negados à sua identidade pessoal. Quando esses dados corporativos são usados, as políticas de proteção de aplicativo controlam como eles são salvos e compartilhados. Essas mesmas proteções não são aplicadas a dados acessados quando o usuário faz logon no dispositivo usando sua identidade pessoal. Dessa forma, o setor de TI tem controle dos dados corporativos enquanto o usuário final mantém o controle e a privacidade dos dados pessoais.

## <a name="emm-with-and-without-device-enrollment"></a>EMM com e sem registro de dispositivo
A maioria das soluções de gerenciamento de mobilidade empresarial dá suporte a tecnologias básicas de dispositivos móveis e aplicativos móveis. Normalmente, elas estão ligadas ao dispositivo que está sendo registrado na solução de MDM (gerenciamento de dispositivo móvel) da organização. O Intune dá suporte a esses cenários e, além disso, dá suporte a vários cenários "sem registro".  

As organizações variam em termos do quanto adotam cenários "sem registro". Algumas organizações os padronizam. Alguns os permitem para dispositivos complementares, como um tablet particular. Outras não dão suporte algum. Mesmo nesse último caso, em que a organização exige que todos os dispositivos de funcionários estejam registrados no MDM, normalmente a organização dá suporte a cenários "sem registro" para prestadores de serviços, fornecedores e outros dispositivos com alguma isenção específica.

Você pode até mesmo usar a tecnologia "sem registro" do Intune em dispositivos registrados. Por exemplo, um dispositivo registrado no MDM pode ter proteções do tipo "abrir em" fornecidas pelo sistema operacional móvel. A proteção “abrir em” é um recurso do iOS que impede que um documento de um aplicativo, como o Outlook, seja aberto em outro aplicativo, como o Word, a menos que ambos os aplicativos sejam gerenciados pelo provedor de MDM. Além disso, o setor de TI pode aplicar a política de proteção de aplicativo a aplicativos móveis gerenciados pelo EMS para controlar as opções de "salvar como" ou fornecer autenticação multifator.

Qualquer que seja o posicionamento da sua organização com relação a aplicativos e dispositivos móveis não registrados, o Intune, como parte do EMS, tem ferramentas que ajudarão a aumentar a produtividade da sua força de trabalho enquanto protege os dados corporativos.



### <a name="next-steps"></a>Próximas etapas
* Leia sobre algumas das [formas comuns para usar o Intune](common-scenarios.md).
* Familiarize-se com o produto [com uma avaliação de 30 dias do Intune](free-trial-sign-up.md).
* Aprofunde-se nas [funcionalidades e requisitos técnicos](supported-devices-browsers.md) do Intune.
