---
title: Novidades | Microsoft Intune
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 500cc93b595e04cea987bda699abf94ae010443a
ms.openlocfilehash: 1f6a4b3988dbebce23a59b4ba14c79cd28cf6882


---

# Novidades do Microsoft Intune
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) (Novidades do Híbrido).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT] 
>Postagem do blog - garantir que dispositivos móveis sejam atualizados usando o Microsoft Intune<br>
>Levando em consideração os ataques de malware "Trident" recentes em dispositivos iOS, publicamos uma nova postagem no blog, [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) (Garantindo que os dispositivos móveis sejam atualizados usando o Microsoft Intune) para ajudar você a saber mais sobre as diferentes maneiras em que o Intune pode ajudar a manter seus dispositivos seguros e atualizados.


## Agosto de 2016
## Gerenciamento de aplicativos
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Aplicativos ocultados e mostrados para iOS 9.3
Para dispositivos supervisionados que executam o iOS 9.3 ou posterior, você pode usar a lista de aplicativos ocultados e exibidos na política de configuração geral do iOS para:
- Especificar uma lista de aplicativos que serão ocultados dos usuários. Os usuários não podem exibir nem iniciar esses aplicativos.
- Especifique uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

Os aplicativos que você pode especificar incluem os dois aplicativos que você implantou e os aplicativos iOS nativos, como Mensagens e Anotações. Para obter detalhes, consulte [iOS policy settings in Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune) (Configurações de política do iOS no Microsoft Intune)
<!---TFS 1279009 checked--->
### Política de aplicativos permitidos e bloqueados para dispositivos Samsung KNOX
Agora você pode configurar uma política personalizada para dispositivos Samsung KNOX que permite que você crie um dos seguintes procedimentos:
- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Mesmo se instalado, um aplicativo definido na lista de bloqueados não pode ser ativado no dispositivo.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play. Nenhum outro aplicativo pode ser instalado da loja.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX.
Para obter detalhes, consulte [Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung KNOX]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
### Novos aplicativos compatíveis com políticas de MAM (Gerenciamento de Aplicativo Móvel)
O aplicativo do Yammer para [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) e [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) é compatível com as [políticas de MAM (gerenciamento de Aplicativo Móvel) do Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), esteja o dispositivo registrado ou não.

Para obter uma lista completa de aplicativos compatíveis com MAM, visite o site [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) (Parceiros de aplicativos do Microsoft Intune).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Aplicativos do Visualizador do Intune
Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
- Visualizador de AV do Intune
- Visualizador de PDF do Intune
- Visualizador de imagem do Intune para Android no Google Play

Em vez de usar os aplicativos do Visualizador do Intune, é recomendável usar o novo [aplicativo do Rights Management (RMS sharing) para o Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança os arquivos corporativos em dispositivos Android. Quando o aplicativo do Visualizador do Intune não tiver mais suporte, ele será removido da Google Store e não estará disponível para uso futuro.

## Gerenciamento de dispositivos
### Suporte do Android 7.0
O Intune oferece suporte de "dia 0" para o próximo sistema de operacional Android 7.0 para dispositivos móveis.
<!---TFS 1262053--->
### Remoção pelo Google da funcionalidade de redefinição remota de senha em dispositivos Android 7.0
O Google está removendo a capacidade dos administradores de TI e usuários finais de redefinir remotamente a senha de dispositivos Android 7.0. Anteriormente, os administradores de TI podiam redefinir remotamente a senha de um usuário, e os usuários finais podiam redefinir suas senhas do site do Portal da Empresa.



## Atualizações do Portal da Empresa
### Site do Portal da Empresa
- **Link de comentários do Portal da Empresa para a Microsoft** <br/>
O site de Portal da empresa permite que os usuários finais toquem em um novo link "Comentários" na parte inferior da página para enviar comentários à Microsoft sobre sua experiência com o site. Os comentários anônimos coletados ajudarão a Microsoft a aprimorar a experiência do site do Portal da Empresa para os usuários.
<!--- TFS 1313657 checked--->

### iOS
- **Versão mínima do Managed Browser do iOS atualizada para 8.0**<br/>
O aplicativo Microsoft Intune Managed Browser para iOS foi atualizado para dar suporte a dispositivos que executam o iOS 8.0 ou posterior. Embora dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
<!---TFS 1313253 checked--->

## O que está por vir
### Transição de grupos do Intune para os grupos do Azure Active Directory a partir de setembro de 2016
O Intune está criando uma nova experiência de gerenciamento de grupos que usa os grupos de segurança do AAD (Azure Active Directory) como grupos de usuários e de dispositivos no Intune. Esses grupos serão usados para todo o gerenciamento de grupo, implantação de política e implantação de perfil **quando lançarmos o novo portal de administração do Intune baseado no Azure**.

Essa nova experiência evitará que você precise duplicar grupos entre serviços, **concederá acesso a alguns recursos de grupo novos do AADP (Azure Active Directory Premium)** e fornecerá extensibilidade usando o PowerShell e o Graph. Ela também unificará a experiência de gerenciamento de grupo no gerenciamento de mobilidade empresarial.

Para habilitar a mudança para grupos de segurança, a experiência no **console do administrador** atual passará por algumas modificações. **Essas alterações e o uso de grupos de segurança do AAD serão registrados na documentação do Intune**.

Os cientes que forem novos no Intune verão **algumas das alterações de grupos de segurança antes dos locatários atuais**.

Além das alterações no gerenciamento de grupo, **as seguintes funcionalidades serão preteridas**:
- Exclusão de membros ou grupos ao criar um novo grupo
- Grupos de **Usuários Desagrupados** e **Dispositivos Desagrupados**
- **Gerenciar Grupos** na função Administrador do Serviço
- Alertas personalizados com base em grupo para Regras de Notificação
- Dinamização com grupos em relatórios
<!--- TFS 1295329--->

### Adição de 'Notificações' ao Portal da Empresa para Android
Lançaremos uma atualização para o Portal da Empresa para Android em setembro que apresentará um novo ícone **Notificações** na home page. Tocar nesse ícone acessará a pagina **Notificações** que lhe mostrará ao seu usuário final todos os itens que exigem atenção no aplicativo Portal da Empresa, como a não conformidade de dispositivo, atualização de registro e ativação de registro. Se você também usar o aplicativo de Portal da Empresa do iOS, já verá a experiência de notificações. Com a introdução da página **Notificações**, você não verá a página **Configuração de Acesso da Empresa** sempre que iniciar ou retomar o Portal da Empresa para Android contanto que o dispositivo já esteja registrado. Ouvimos que muitos de vocês criaram diretrizes para usuário final e apreciariam um aviso antecipado quando for possível que suas diretrizes/capturas precisem ser atualizadas. Atualize sua documentação para refletir a alteração futura na experiência. Encontre capturas de tela atualizadas aqui: https://aka.ms/androidcpupdate.  

### Melhorias na maneira como os usuários finais do iOS obtêm seus aplicativos
As alterações a seguir estão sendo feitas em setembro nos blocos de aplicativos no aplicativo Portal da Empresa para iOS para encaminhar os usuários a diferentes modos de exibição em um único local, o site Portal da Empresa, para todos os seus aplicativos. Atualmente, as restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da app store sejam listados no aplicativo Portal da Empresa e exigem que os usuários acessem diferentes modos de exibição para localizar todos os seus aplicativos.

- Atualmente, o bloco **Aplicativos da Empresa** aponta para uma lista de todos os aplicativos na guia TODOS do site Portal da Empresa e continuará a funcionar da mesma maneira. O nome do bloco será alterado para **Todos os Aplicativos**.
- O bloco **Outros Aplicativos** aponta para um modo de exibição no aplicativo Portal da Empresa que lista todos os aplicativos que Apple permite que o aplicativo Portal da Empresa mostre. O nome do bloco será alterado para **Aplicativos em Destaque** e, ao tocar no bloco, os usuários são levados para a guia EM DESTAQUE do site Portal da Empresa.
-  O bloco **Categorias** aponta atualmente para um modo de exibição no aplicativo Portal da Empresa que lista categorias de aplicativos. O nome do bloco não será alterado, mas agora apontará para a guia CATEGORIAS do site Portal da Empresa. Você pode encontrar capturas de tela atualizadas [aqui](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Roteiro de nuvem
Mantenha-se informado sobre futuros desenvolvimentos do Intune com a [Estratégia de plataforma em nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviço preterido
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Alterações no suporte para o aplicativo Portal da Empresa do iOS**<br/>
Em setembro, todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS deverão usar sua versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.  

- **Versão mínima do Managed Browser do iOS atualizada para 8.0**<br/>
Em agosto, o Intune lançará um aplicativo Microsoft Intune Managed Browser atualizado para iOS que dará suporte apenas a dispositivos executando o iOS 8.0 ou posterior. Embora os dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
<!---TFS 1313253--->

- **Aplicativos Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos** <br/>
A partir de outubro de 2016, o Microsoft Intune preterirá o suporte para aplicativos do Portal da Empresa do Windows 8 e Windows Phone 8. O Microsoft Intune também preterirá o suporte para a plataforma Windows Phone 8. Em consequência disso, você não poderá registrar nem atualizar dispositivos Windows Phone 8. Você pode continuar a gerenciar dispositivos Windows Phone 8 e Windows 8 já registrados. Atualize os dispositivos Windows Phone 8 e Windows 8 para Windows 8.1 e Windows Phone 8.1 e use os aplicativos do Portal da Empresa correspondentes do Windows 8.1 e do Windows Phone 8.1 para continuar a distribuir aplicativos para esses dispositivos sem interrupções.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->



## Versões anteriores do Intune
Se você quiser ver o que foi lançado no Intune durante os últimos seis meses, consulte a lista no artigo [Previous Intune releases](previous-intune-releases.md) (Versões anteriores do Intune).

### Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roteiro da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Aug16_HO5-->


