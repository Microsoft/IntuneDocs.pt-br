---
# required metadata

title: Arquivo de novidades | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


## Setembro de 2015
### Atualizações de gerenciamento de aplicativo e dispositivo móvel
**Todos os recursos de gerenciamento de iOS do Intune agora dão suporte ao iOS 9**
Para saber detalhes sobre as funcionalidades de gerenciamento do iOS 9, consulte [esta postagem de blog](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx).

**Nova política de configuração do aplicativo móvel para iOS**
Use a nova política de configuração de aplicativo móvel para fornecer automaticamente configurações de que um aplicativo iOS pode precisar quando é executado. Por exemplo, você poderia fornecer uma porta de rede ou um nome de usuário. Para saber detalhes, consulte [Configure apps with mobile app configuration policies in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx) (Configurar aplicativos com políticas de configuração de aplicativo móvel no Microsoft Intune).

**Gerenciamento de aplicativo mais fácil para usuários do iOS 9**
 Nesta versão, você pode colocar aplicativos já implantados sob gerenciamento do Intune para usuários do iOS 9. Para versões anteriores do iOS, quando você implantar um aplicativo e uma versão não gerenciada dele já estiver instalada em um dispositivo, você ainda precisará pedir ao usuário para desinstalar o aplicativo manualmente antes que o Intune possa instalar o aplicativo gerenciado.

 Mas, ao começar com esta versão do Intune, você agora pode solicitar que os usuários de dispositivos iOS 9 permitam que o Intune assuma o gerenciamento do aplicativo e aplique as políticas de gerenciamento de aplicativo móvel relevantes.

 **Gerenciamento do Windows 10** Use a nova [Política de configuração geral do Windows 10](https://technet.microsoft.com/library/mt404697.aspx) para configurar a senha, o dispositivo, o navegador e outras configurações para dispositivos que executam o Windows 10 e Windows 10 Mobile.

 **Criar e implantar aplicativos em dispositivos Windows 10 registrados** Um novo tipo de instalador de software, o Windows Installer, por meio do MDM (&#42;.msi) permite criar e implantar aplicativos do Windows Installer em dispositivos registrados que executam o Windows 10. Para saber detalhes, consulte [Get started with app deployment in Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx) (Introdução à implantação de aplicativo no Microsoft Intune).

### Alterações e atualizações nos aplicativos do portal Microsoft Company
As seguintes alterações foram feitas nos aplicativos de portal da empresa nesta versão:

**iOS**
* A Microsoft coleta automaticamente dados anônimos sobre o desempenho e o uso do portal da empresa para aprimorar os produtos e serviços Microsoft. Os usuários finais podem desativar a coleta de dados usando a configuração de Dados de Uso em seu dispositivo, mas os administradores não têm controle sobre a coleta de dados e não podem alterar a seleção do usuário final para essa configuração.
* Suporte de resolução de tela completo no iPhone 6 e iPhone 6 Plus
* Correções de bugs para aumentar a segurança

### Novidades na documentação do Intune – setembro de 2015
**Novos tópicos**

|Nome|Detalhes|
|----|--------|
|[Definições de política de configuração do Windows 10 no Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Esta é uma nova política de configuração que permite que você gerencie as configurações e recursos em dispositivos que executam o Windows 10 e Windows 10 Mobile.
| [Configurar aplicativos com as políticas de configuração de aplicativo móvel no Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Este é um novo tipo de política que permite que você forneça automaticamente as configurações que podem ser necessárias quando o usuário executa um aplicativo iOS. |

**Tópicos atualizados**

|Nome|Detalhes|
|----|-------|
|[Usar políticas para gerenciar computadores e dispositivos móveis com o Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Atualizado para incluir as informações mais recentes para ajudá-lo a entender e criar políticas.|

## Agosto de 2015
### Atualizações de gerenciamento de aplicativo e dispositivo móvel
* Os**Termos e condições** para registro no Intune e acesso da empresa agora [são gerenciados usando políticas](https://technet.microsoft.com/library/mt405893.aspx). Você pode direcionar conjuntos diferentes de termos e condições para atender a requisitos específicos de grupo de usuários. Por exemplo, você pode implantar termos e condições em idiomas diferentes para grupos de usuários definidos geograficamente. Você também pode [editar seus termos e condições](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) e especificar se deseja incrementar números de versão, exigindo que os usuários concordem com os novos termos e condições para poderem usar o portal da empresa.
* **Diversas políticas do Intune foram renomeadas** para torná-los mais consistente em todo o produto e para facilitar a localização. Para obter uma lista de todas as políticas do Intune disponíveis, consulte [Use policies to manage computers and mobile devices with Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx) (Usar políticas para gerenciar computadores e dispositivos móveis com o Microsoft Intune).
* **Perfis de Certificado PKCS #12 (.PFX)** estão disponíveis para Android 4.0 ou posterior e Windows 10 (Desktop e Mobile) e posterior. Usar o .PFX não requer um servidor NDES. Saiba como usar os perfis de certificado .PFX em [Habilitar o acesso aos recursos da empresa usando perfis de certificado com o Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx)
* **As configurações de limites corporativos para Windows 10 Desktop e Mobile** habilitam configurações de VPN granulares, conforme descrito em [Ajudar os usuários a se conectarem ao seu trabalho usando perfis de VPN com o Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx)
* **O aplicativo OneDrive para Android agora dá suporte a várias identidades**. Esta e outras atualizações às políticas de gerenciamento de aplicativos móveis são descritas na [lista de aplicativos da Microsoft que você pode gerenciar](https://technet.microsoft.com/library/dn708489.aspx).
* **Ignorar Bloqueio de Ativação do iOS**. Se dispositivos iOS da empresa estiverem protegidos pelo Bloqueio de Ativação, você deverá inserir a ID Apple e a senha do usuário antes de apagar ou reativar o dispositivo. Isso pode representar um desafio quando os usuários deixam a empresa e retornam um dispositivo da empresa sem desativar o Bloqueio de Ativação. Para ajudar a resolver esse problema, você pode usar o [Bypass de Bloqueio de Ativação do Intune](https://technet.microsoft.com/library/mt414176.aspx)

### Acesso condicional para PCs
Agora você pode configurar políticas de acesso condicional para PCs. Isto permite que aplicativos da área de trabalho do Office acessem os serviços do Exchange Online e do SharePoint Online.
Para habilitar a política de acesso condicional para PCs, o PC deve ser ingressado no domínio ou ser compatível.
* A seção **Introdução** em [Gerenciar acesso ao email e SharePoint com o Microsoft Intune](http://technet.microsoft.com/library/dn818907) (.aspx) lista o conjunto completo de requisitos para habilitar o acesso condicional para PCs.
* Consulte [Gerenciar acesso ao email com o Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) para obter as opções que você pode definir para habilitar o acesso condicional para acesso de email.
* Consulte [Gerenciar acesso ao SharePoint Online com o Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) para obter as opções que você pode definir para habilitar o acesso condicional para acesso ao SharePoint Online.

### Alterações e atualizações nos aplicativos do portal Microsoft Company
As seguintes alterações foram feitas nos aplicativos de portal da empresa nesta versão:

**Android**

Os usuários agora encontrarão instruções de registro de dispositivo depois de entrar se não tiverem registrado seus dispositivos para gerenciamento.

### Novidades na documentação do Intune – Agosto de 2015
**Novos tópicos**

|Título|Detalhes|
|-----|-------|
|[Ajude a proteger dispositivos iOS com bypass de Bloqueio de Ativação para o Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Saiba mais sobre como você pode usar o Intune para ignorar o bloqueio de Ativação do iOS quando um usuário sair da empresa e devolver um dispositivo bloqueado.|

**Tópicos atualizados**

|Título|Detalhes|
|-----|-------|
|[Aplicativos da Microsoft podem ser usados com políticas de gerenciamento de aplicativos móveis Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx)|Atualizado com as informações mais recentes sobre aplicativos que você pode gerenciar com políticas de gerenciamento de aplicativos móveis.
|[Usar políticas para gerenciar computadores e dispositivos móveis com o Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Atualizado com as políticas mais recentes adicionadas ao Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->


<!--HONumber=May16_HO1-->


