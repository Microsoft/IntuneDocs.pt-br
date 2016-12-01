---
title: "O que é o Microsoft Intune | Microsoft Docs"
description: "Saiba como o Intune é o componente de gerenciamento de dispositivo móvel da solução Enterprise Mobility + Security e como ele ajuda você a proteger dados da empresa."
keywords: "o que é o Intune"
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6932a0d81654edc4c2e3108ca11df892e9ec5bf4
ms.openlocfilehash: 50a9b89140a0fff9994b267f10fa7912af89f116


---

# <a name="what-is-intune"></a>O que é o Intune?
O Intune é um serviço de EMM (gerenciamento de mobilidade empresarial) baseado em nuvem que ajuda a habilitar sua força de trabalho a ser produtiva enquanto mantém dados corporativos protegidos. Com o Intune, você pode:
* gerenciar os dispositivos móveis que sua força de trabalho usa para acessar dados da empresa.
* gerenciar os aplicativos móveis que sua força de trabalho usa.
* proteger informações da empresa, ajudando a controlar a forma como sua força de trabalho as acessa e compartilha.
* garantir que dispositivos e aplicativos sejam compatíveis com os requisitos de segurança da empresa.

O Intune se integra estreitamente ao Azure AD (Azure Active Directory) para o controle de acesso e identidade e ao Azure RMS (Azure Rights Management) para proteção de dados. Ele é o *braço de gerenciamento* do Microsoft EMS (Enterprise Mobility + Security), enquanto o Office 365 é o *braço de produtividade* da solução de mobilidade da Microsoft.  

Juntos, o Office 365 e o EMS possibilitam que sua força de trabalho seja produtiva usando todos os seus dispositivos, ao mesmo tempo em que mantêm protegidas as informações da organização. O Office 365 com o EMS é um pacote integrado completo para mobilidade corporativa, que inclui produtividade, identidade, controle de acesso, gerenciamento e proteção de dados. Ele fornece a uma maneira eficiente para implantar e operar uma solução de mobilidade em sua organização.

## <a name="how-does-intune-work"></a>Como o Intune funciona?
O Intune fornece MDM (gerenciamento de dispositivo móvel) e MAM (gerenciamento de aplicativo móvel). Os recursos de MDM e MAM do Intune, por sua vez, contribuem para os cenários de conformidade e proteção de dados do pacote EMS.  

A forma como você usará os recursos de MDM/MAM do Intune e a proteção de dados do EMS depende do [problema de negócios que está tentando resolver](#common-business-problems-that-intune-helps-solve). Por exemplo:
* Você usará o MDM intensamente se estiver criando um pool de dispositivos de uso único para serem compartilhados por funcionários em turnos em uma loja de varejo.
* Você aproveitará o MAM e a proteção de dados se permitir que sua força de trabalho use seus dispositivos pessoais para acessar dados corporativos (BYOD).  
* Se for emitir telefones corporativos para funcionários que trabalham com informações, você usará intensamente todas as tecnologias.

## <a name="intune-mobile-device-management-mdm-explained"></a>O MDM (gerenciamento de dispositivo móvel) explicado
O MDM funciona usando os protocolos ou APIs que estão disponíveis nos sistemas operacionais móveis. Ele inclui tarefas como:
* registrar dispositivos para gerenciamento para que o setor de TI tenha um inventário dos dispositivos que estão acessando serviços corporativos
* configurar dispositivos para garantir que eles atendam aos padrões de integridade e segurança da empresa
* Fornecer certificados e perfis de Wi-Fi/VPN para acessar serviços corporativos
* emitir relatórios e avaliar a conformidade do dispositivo com os padrões corporativos
* remover dados corporativos de dispositivos gerenciados  

Às vezes, as pessoas acreditam que o **controle de acesso a dados corporativos** é um recurso do MDM. Nós não pensamos dessa forma porque não é algo que o sistema operacional móvel fornece. Em vez disso, é algo que o provedor de identidade fornece. Em nosso caso, o provedor de identidade é o Azure AD (Azure Active Directory), o sistema de gerenciamento de acesso e identidade da Microsoft.  

O Intune se integra ao Azure AD para habilitar um amplo conjunto de cenários de controle de acesso. Por exemplo, você pode exigir que um dispositivo móvel seja compatível com padrões corporativos, conforme definido no Intune, antes que o dispositivo possa acessar um serviço corporativo como o Exchange. Da mesma forma, você pode bloquear o serviço corporativo para um conjunto específico de aplicativos móveis. Por exemplo, você pode bloquear o Exchange Online para ser acessado apenas pelo Outlook ou pelo Outlook Mobile.

## <a name="intune-mobile-app-management-mam-explained"></a>O MAM (gerenciamento de aplicativo móvel) do Intune explicado
Quando falamos em MAM, estamos falando sobre o conjunto de coisas que nossas soluções permitem que os profissionais de TI façam com aplicativos móveis, como:
* publicar aplicativos móveis para funcionários
* configurar aplicativos
* controlar a forma como os dados corporativos são usados e compartilhados em aplicativos móveis
* remover dados corporativos de aplicativos móveis   
* atualizar aplicativos móveis
* emitir relatórios sobre o inventário de aplicativos móveis
* Acompanhar o uso de aplicativos móveis

Nós vimos que o termo MAM é usado para indicar qualquer uma dessas coisas individualmente ou para indicar combinações específicas. Em particular, é comum que as pessoas combinem o conceito de configuração de aplicativo (ou seja, usar tecnologias como a [configuração de aplicativo gerenciado no iOS](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html)) com o conceito de proteger dados corporativos de dentro de aplicativos móveis. Isso ocorre porque alguns aplicativos móveis expõem definições que permitem que seus recursos de segurança de dados sejam configurados.

Isso, em conjunto com recursos do sistema operacional para proteger dados (por exemplo, recursos de MDM, como a Proteção de Informações do Windows no Windows 10), oferece muita proteção a dados em dispositivos móveis.

Quando usa o Intune com outros serviços no EMS, você pode fornecer à sua organização segurança de aplicativo móvel muito além da que é fornecida pelo sistema operacional móvel e pelo próprio aplicativo por meio da configuração do aplicativo. Um aplicativo gerenciado com o EMS tem acesso a um conjunto mais amplo de proteções de dados e aplicativos móveis que inclui:

* [Logon único](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Autenticação multifator](https://docs.microsoft.com/en-us/multi-factor-authentication/multi-factor-authentication)
* [Acesso condicional do aplicativo (permitir acesso se o aplicativo móvel contiver dados corporativos)](https://docs.microsoft.com/en-us/intune/deploy-use/allow-policy-managed-apps-access-to-o365)
* [Isolar dados corporativos de dados pessoais dentro do mesmo aplicativo](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Política de proteção de aplicativo (PIN, criptografia, salvar como, área de transferência etc.)](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Apagamento de dados corporativos de um aplicativo móvel](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Suporte do Rights Management](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-azure-rms)

![Imagem que mostra os níveis de segurança de dados do gerenciamento de aplicativo](./media/managing-mobile-apps.png)

### <a name="intune-mobile-app-security"></a>Segurança de aplicativo móvel do Intune
Fornecer segurança de aplicativo é uma parte do MAM e, no Intune, quando falamos em segurança de aplicativo móvel, queremos dizer:
* manter informações pessoais isoladas do reconhecimento de TI corporativo
* restringir as ações que os usuários podem executar com informações corporativas, como copiar, recortar/colar, salvar e exibir
* remover dados corporativos de aplicativos móveis, também conhecido como apagamento seletivo ou apagamento corporativo

Uma maneira do Intune fornecer segurança de aplicativo móvel é por meio de seu recurso de **política de proteção de aplicativo**. A política de proteção de aplicativo usa a identidade do Azure AD para isolar dados corporativos de dados pessoais. Os dados acessados usando uma credencial corporativa terão proteções corporativas adicionais.

Quando um usuário faz logon em seu dispositivo usando credenciais corporativas, sua identidade corporativa permite acessar dados que são negados à sua identidade pessoal. Quando esses dados corporativos são usados, o Intune, em conjunto com outras tecnologias do EMS, controla como eles são salvos e compartilhados. Essas mesmas proteções não são aplicadas a dados acessados quando o usuário faz logon no dispositivo usando sua identidade pessoal. Dessa forma, o setor de TI tem controle dos dados corporativos enquanto o usuário final mantém o controle e a privacidade dos dados pessoais.

## <a name="emm-with-and-without-device-enrollment"></a>EMM com e sem registro de dispositivo
A maioria das soluções de gerenciamento de mobilidade empresarial dá suporte a tecnologias básicas de dispositivos móveis e aplicativos móveis. Normalmente, elas estão ligadas ao dispositivo que está sendo registrado na solução de MDM da organização. O Intune dá suporte a esses cenários e, além disso, dá suporte a vários cenários "sem registro".  

As organizações variam em termos do quanto adotam cenários "sem registro". Algumas organizações os padronizam. Alguns os permitem para dispositivos complementares, como um tablet particular. Outras não dão suporte algum. Mesmo nesse último caso, em que a organização exige que todos os dispositivos de funcionários estejam registrados no MDM, essas organizações normalmente dão suporte a cenários "sem registro" para prestadores de serviços, fornecedores e outros dispositivos que têm uma isenção específica.

Você pode até mesmo usar a tecnologia "sem registro" do Intune em dispositivos registrados. Por exemplo, um dispositivo registrado no MDM pode ter proteções do tipo "abrir em" fornecidas pelo sistema operacional móvel. Além disso, o setor de TI pode aplicar a política de proteção de aplicativo a aplicativos móveis gerenciados pelo EMS para controlar as opções de "salvar como" ou fornecer autenticação multifator.

Qualquer que seja o posicionamento da sua organização com relação a aplicativos e dispositivos móveis não registrados, o Intune, como parte do EMS, tem ferramentas que ajudarão a aumentar a produtividade da sua força de trabalho enquanto protege os dados corporativos.

## <a name="common-business-problems-that-intune-helps-solve"></a>Problemas de negócios comuns que o Intune ajuda a resolver
A lista a seguir de problemas de negócios leva a informações mais detalhadas sobre as soluções que podemos fornecer. Apenas o último item requer o registro no MDM como parte da solução:

* [Proteger seus dados e emails locais para que eles possam ser acessados por dispositivos móveis](common-ways-to-use-intune.md#Protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Proteger seus dados e emails do Office 365 para que eles possam ser acessados com segurança por dispositivos móveis](common-ways-to-use-intune.md#Protecting-your-Office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Emitir telefones corporativos para sua força de trabalho](common-ways-to-use-intune.md#Issue-corporate-owned-phones-to-your-information-workers)
* [Oferecer um programa de BYOD (traga seu próprio dispositivo) ou de dispositivos pessoais para todos os funcionários](common-ways-to-use-intune.md#Offer-a-bring-your-own-device-program-to-all-employees)
* [Habilitar os funcionários a acessarem o Office 365 de forma segura de um quiosque público não gerenciado](common-ways-to-use-intune.md#Enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Emitir tablets compartilhados de uso limitado para seus funcionários](common-ways-to-use-intune.md#Issue-limited-use-shared-tablets-to-your-task-workers)

### <a name="next-steps"></a>Próximas etapas
* Leia sobre algumas das [formas comuns para usar o Intune](common-ways-to-use-intune.md).
* Familiarize-se com o produto [com uma avaliação de 30 dias do Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md).
* Aprofunde-se nas [funcionalidades e requisitos técnicos](/intune/get-started/what-to-know-before-you-start-microsoft-intune) do Intune.



<!--HONumber=Nov16_HO3-->


