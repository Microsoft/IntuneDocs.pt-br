---
title: "Habilitar BYOD (traga seu próprio dispositivo) com o Microsoft Intune"
description: "Um fluxo de trabalho de alto nível para configurar o Intune para habilitar uma solução BYOD (traga seu próprio dispositivo) para sua organização."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: fa70e21b9e9f7adfc508e24bd442a48c834ed7db
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2017
---
# <a name="enable-byod-with-intune"></a>Habilitar BYOD (Traga seu próprio dispositivo) com o Intune

Este tópico fornece um fluxo de trabalho de alto nível para configurar o Intune para habilitar uma solução BYOD (traga seu próprio dispositivo) para sua organização. Ele organiza as tarefas em três processos e vincula-os a tópicos de instruções de suporte.

O fluxo de trabalho é dividido nos três processos a seguir. Você pode personalizar os aspectos de cada processo para atender aos requisitos da sua organização.

-   **[Registrar dispositivos e verificar a conformidade](#enroll-devices-and-check-for-compliance)** descreve como habilitar usuários a registrar os dispositivos pessoais no gerenciamento com o Intune. O Intune gerencia dispositivos macOS, iOS, Android e Windows. Esta seção também descreve como implantar políticas para dispositivos e assegurar que elas atendam aos requisitos básicos de segurança.

- **[Fornecer acesso aos recursos da empresa](#provide-access-to-company-resources)** mostra como você pode permitir que os usuários acessem recursos da empresa, de modo fácil e seguro. Você pode fazer isso implantando os perfis de acesso a dispositivos gerenciados. Esta seção também explica como gerenciar implantações de aplicativo comprado por volume com o Intune.

-   **[Proteger dados da empresa](#protect-company-data)** ajuda você a aprender como fornecer acesso condicional aos recursos da empresa, como evitar a perda de dados e como remover aplicativos e dados empresariais de dispositivos, quando eles não são mais necessários ou forem perdidos ou roubados.

[![Diagrama de fluxo de trabalho de alto nível para habilitar BYOD com o Microsoft Intune](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Antes de começar
Antes que os usuários possam registrar dispositivos, você precisa preparar o serviço do Intune. Para fazer isso, [atribua licenças a usuários](licenses-assign.md) e [defina a autoridade de gerenciamento de dispositivo móvel](mdm-authority-set.md).

Ao fazer isso, você também deve [personalizar o portal da empresa](company-portal-customize.md). Adicione identidade visual da empresa e forneça informações de suporte aos usuários. Isso cria uma experiência de registro e suporte confiável para os usuários. Você também pode criar [termos de uso](terms-and-conditions-create.md) que os usuários devem aceitar antes de registrar ou [restrições de dispositivo](enrollment-restrictions-set.md) para especificar as plataformas para as quais você dá suporte.

## <a name="enroll-devices-and-check-for-compliance"></a>Registrar dispositivos e verifique a conformidade

Depois de preparar o serviço Intune, você precisa atender os vários requisitos de registro para os tipos de dispositivo diferentes que você deseja gerenciar. O processo para registrar dispositivos no gerenciamento é simples, mas ligeiramente diferente com base no tipo de dispositivo.

-   **Dispositivos iOS e Mac** Você precisa [obter um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) para registrar iPads, iPhones ou dispositivos macOS. Depois de carregar o MDM Push Certificate no Intune, os usuários podem [registrar dispositivos iOS](/intune-user-help/enroll-your-device-in-intune-ios) usando o aplicativo Portal da Empresa e usar o site do Portal da Empresa para [registrar dispositivos macOS](/intune-user-help/enroll-your-device-in-intune-macos).

-   **Dispositivos Android** Não há nada que você precise fazer para deixar o serviço do Intune pronto para registrar dispositivos Android. Os usuários podem simplesmente [registrar seus dispositivos Android](/intune-user-help/enroll-your-device-in-intune-android) para gerenciamento usando o aplicativo de Portal da Empresa no Google Play.

-   **Computadores e dispositivos Windows Phone** Os dispositivos Windows podem ser registrados com uma configuração adicional. Você pode habilitar o registro automático para computadores Windows 10 e dispositivos móveis Windows 10 no AD (Azure Active Directory) Premium para simplificar a experiência do usuário final. Se você não tiver o Azure AD Premium ou se precisar dar suporte ao Windows 8.1, você poderá criar [um alias DNS para o servidor de registro](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium) para facilitar o registro.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Verifique se os dispositivos gerenciados satisfazem os requisitos básicos de segurança

Depois que os usuários registrarem os dispositivos no gerenciamento, o departamento de TI deverá verificar se esses dispositivos usados para acessar aplicativos e dados da empresa satisfazem os requisitos básicos de segurança. Essas regras podem incluir o uso de um PIN para acessar os dispositivos e criptografar dados armazenados em dispositivos. Chamamos um conjunto dessas regras de [política de conformidade](device-compliance.md).

Quando você [implanta uma política de conformidade](device-compliance-get-started.md) para um usuário, o Intune verifica todos os dispositivos do usuário que são gerenciados pelo Intune, para confirmar se eles atendem aos requisitos básicos de segurança definidos como parte da sua política de BYOD. Depois de avaliar se um dispositivo está em conformidade com a política, ele relatará o respectivo status de volta ao Intune. Em alguns casos, pode ser solicitado que os usuários corrijam configurações, tais como a criptografia de dispositivo ou PIN. Outras vezes, o aplicativo do portal da empresa simplesmente notifica o usuário sobre as configurações que não satisfazem sua política.

## <a name="provide-access-to-company-resources"></a>Fornecer acesso aos recursos da empresa

A primeira coisa que a maioria dos funcionários deseja em seus dispositivos móveis é o acesso aos documentos e ao email da empresa. Eles esperam configurá-lo sem seguir etapas complexas ou chamar o suporte técnico. O Intune facilita a [criação e implantação de configurações de email](email-settings-configure.md) para aplicativos nativos de email pré-instalados em dispositivos móveis.


> [!NOTE]
> O Intune dá suporte à configuração de perfis de email do Android for Work para os aplicativos do Gmail e do Nine Work encontrados na loja do Google Play.

Intune também ajuda você a controlar e proteger o acesso aos dados da empresa locais quando os usuários trabalham fora da empresa. Os perfis de [Wi-Fi](wi-fi-settings-configure.md), [VPN](vpn-settings-configure.md) e email do Intune funcionam em conjunto para permitir o acesso aos arquivos e recursos de que os usuários precisam para realizar o trabalho deles, independentemente de onde estiverem. Os aplicativos Web e serviços da empresa hospedados localmente também podem ser acessados com segurança e protegidos usando o Proxy de Aplicativo do Azure Active Directory e o acesso condicional.

### <a name="manage-volume-purchased-apps"></a>Gerenciar aplicativos adquiridos por volume
Com o Intune, é fácil:
* Importar as informações de licença de volume de qualquer uma das lojas de aplicativos
* Controlar quantas licenças você usou
* Impedir que os usuários instalem mais cópias do aplicativo do que você possui
* [Entregar aplicativos da loja para dispositivos gerenciados](apps-deploy.md)
* Direcionar aplicativos para dispositivos não gerenciados usando o site do Portal da Empresa

O Intune também permite gerenciar e implantar aplicativos adquiridos com base em volume na loja de aplicativos iOS e na Microsoft Store para Empresas. Isso ajuda a reduzir a sobrecarga administrativa no acompanhamento de aplicativos comprados com base no volume.

> [!TIP]
> Você pode [configurar logon único (SSO) com o Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). O SSO permite que os usuários entrem em aplicativos com o nome de usuário de domínio e a senha que eles usam localmente. Além disso, você pode [fornecer acesso baseado na Internet para aplicativos Web hospedados localmente](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) usando o Proxy de Aplicativo do Azure Active Directory.

-   [Gerenciar aplicativos comprados com base no volume para dispositivos iOS](vpp-apps-ios.md). Você compra várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/). Você precisa configurar uma conta do Apple VPP no site da Apple e carregar o token do Apple VPP no Intune. Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

-   [Gerenciar aplicativos comprados na Microsoft Store para Empresas](windows-store-for-business.md). A [Microsoft Store para Empresas](https://www.microsoft.com/business-store) é um local para encontrar e comprar aplicativos para organizações, uso individual ou com base em volume. Conectando-se à loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados por volume no portal do Intune.

## <a name="protect-company-data"></a>Proteger os dados da empresa

O Intune protege os dados da empresa por meio de várias camadas de tecnologia. Na camada de identidade, o acesso condicional protege o acesso a serviços. O acesso condicional permite que apenas os dispositivos gerenciados e em conformidade acessem os recursos da empresa. Na camada do aplicativo cliente, as políticas de proteção do aplicativo protegem contra perda de dados. Políticas de proteção do aplicativo impedem que os dados sejam movidos para aplicativos ou locais de armazenamento que não estão protegidos. Essas políticas permitem apagar dados da empresa quando um dispositivo é perdido ou roubado.

### <a name="enforce-conditional-access-to-company-resources"></a>Impor acesso condicional aos recursos da empresa

Você pode combinar políticas de conformidade com [políticas de acesso condicional](device-compliance.md) para verificar se os dispositivos satisfazem os requisitos básicos de segurança da sua política de BYOD. Se um dispositivo não atende aos requisitos, as regras são impostas e o acesso é negado até que o dispositivo atenda aos requisitos da política. Isso garante que apenas os dispositivos gerenciados e em conformidade possam acessar dados empresarias em serviços como Exchange ([Exchange Local](exchange-connector-install.md) ou [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, Skype for Business Online e muito mais.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Políticas de acesso condicional não funcionarão se não houver nenhuma política de conformidade em vigor para validar a conformidade.

### <a name="prevent-data-loss-of-company-data-with-app-protection-policies"></a>Evitar a perda de dados da empresa com as políticas de proteção de aplicativos

Com as políticas de proteção de aplicativo do Intune, você pode escolher como os dados são acessados, independentemente do registro de dispositivos. Essa versatilidade permite proteger dados da empresa, de modo que mesmo que um usuário não registre seu dispositivo no Intune, ele ainda poderá acessar dados da empresa com segurança.

Você pode usar as [políticas de proteção de aplicativo do Intune](app-protection-policies.md) para ajudar a proteger os dados da empresa que são acessados por dispositivos Android e iOS. Quando você usa essas políticas em nível de aplicativo, você pode controlar como os funcionários usam e compartilham os dados da empresa, mesmo que os dispositivos em si não sejam gerenciados pelo Intune

Use a [WIP (Proteção de Informações do Windows)](app-protection-policies-configure-windows-10.md) para fazer o mesmo com dispositivos Windows 10 gerenciados. Essas políticas funcionam sem interferir com a experiência do funcionário. Eles não exigem alterações em seu ambiente de rede nem em outros aplicativos.

### <a name="remove-company-data-while-leaving-personal-data-intact"></a>Remover os dados da empresa deixando os dados pessoais intactos

Quando um dispositivo deixa de ser necessário para o trabalho, tem sua função redefinida ou é considerado desaparecido, você pode remover dele os dados e aplicativos da empresa. Para fazer isso, é possível usar os recursos de remoção de dados da empresa e de redefinição de fábrica do Intune. Se os dispositivos de propriedade pessoal dos seus usuários tiverem sido registrados no Intune, esses usuários poderão redefini-los remotamente do Portal da Empresa do Intune.

Uma [redefinição de fábrica](devices-wipe.md) restaura um dispositivo para suas configurações padrão de fábrica e remove o dispositivo do gerenciamento do Intune. A [Remoção dos dados da empresa](devices-wipe.md#remove-company-data) remove apenas os dados da empresa do dispositivo, mas deixa os dados pessoais dos usuários intactos.

Uma vez iniciada, o dispositivo começa imediatamente o processo de redefinição. Quando o processo for concluído, todos os dados da empresa serão excluídos e o nome do dispositivo será removido do Intune. Isso conclui o ciclo de vida de gerenciamento de dispositivo.
