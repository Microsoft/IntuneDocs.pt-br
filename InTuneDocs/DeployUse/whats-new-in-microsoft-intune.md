---
title: Novidades | Microsoft Intune
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68af4d7f0b082f14e6f9c06f8739805f9590384e
ms.openlocfilehash: 64bd2e3c8e8da3949634a544eb2c582e889c8209


---

# Novidades do Microsoft Intune
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) (Novidades do Híbrido).

## Agosto de 2016
## Atualizações do Portal da Empresa

### Android
- **Aplicativo Android do Portal da Empresa**<br/>
O aplicativo do Portal da empresa Intune para Android oferece suporte de "dia 0" para o próximo sistema de operacional Android 7.0 para dispositivos móveis.  

- **Remoção pelo Google da funcionalidade de redefinição remota de senha em dispositivos Android 7.0**<br/>
Em dispositivos Android 7.0, os administradores de TI do Intune e os usuários finais não serão capazes de redefinir remotamente a senha do dispositivo, porque o Google removeu essa funcionalidade para dispositivos Android 7.0. Para versões anteriores ao Android 7.0, os administradores de TI ainda poderão redefinir remotamente a senha do usuário e os usuários finais ainda poderão redefinir suas senhas do site do Portal da Empresa.

## Julho de 2016
## Gerenciamento de aplicativos
### Melhorar a experiência de atualização de perfil de provisionamento de aplicativo
Os aplicativos móveis de linha de negócios de iOS da Apple são criados com um perfil de provisionamento incluído e com assinatura por código com um certificado. Quando o aplicativo é executado em um dispositivo iOS, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento.

A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos. No entanto, o perfil de provisionamento expira após um ano. Com essa atualização, o Intune fornece as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos se aproximando da expiração enquanto o certificado ainda for válido. Para obter mais informações, consulte [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Usar políticas de perfil de provisionamento para manter seus aplicativos de linha de negócios atualizados).
<!--- TFS 1280247--->
### O SDK do Xamarin para aplicativos do Intune está disponível
O componente Xamarin do SDK do aplicativo do Intune permite que você habilite os recursos de gerenciamento do aplicativo móvel do Intune em seus aplicativos móveis iOS e Android criados com o Xamarin. Você pode encontrar o componente na [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) ou na [página do GitHub do Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

## Gerenciamento de dispositivos
### Limites de registro de dispositivo maior
O Intune aumentou o limite máximo de registro de dispositivo configurável de 5 para 15 dispositivos por usuário.
<!---TFS 1289896 --->

### Integração do TeamViewer para computadores Windows que executam o software cliente do Intune
A integração do [TeamViewer](https://www.teamviewer.com) para computadores Windows que executam o cliente do Intune permite que você estabeleça sessões de assistência remota com computadores Windows para ajudar a dar suporte a departamentos de suporte técnico para o usuário final. Compatível com o Windows 7, 8, 8.1 e o Windows 10. Para obter detalhes, consulte [Common Windows PC management tasks with the Microsoft Intune computer client](intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client) (Tarefas comuns de gerenciamento de computadores Windows com o cliente de computador do Microsoft Intune).
<!---TFS 1284856--->

## Atualizações do Portal da Empresa
### Site do Portal da Empresa
- **Experiência do usuário final melhorada ao registrar dispositivos Windows**<br/>
Quando você estiver usando o acesso condicional, as etapas de registro para o Windows 8.1, Windows 10 Desktop e Windows 10 Mobile serão esclarecidas no site do Portal da Empresa. Agora os usuários verão as etapas “Registro do dispositivo” e “Ingresso no local de trabalho”, tornando mais fácil que eles vejam o status de seu dispositivo e concluam o processo se enfrentarem uma falha de WPJ (Ingresso no local de trabalho). Também é esperado que as etapas separadas simplifiquem o processo de solução de problemas para os administradores de TI. Anteriormente, quando os usuários finais tentavam se registrar e todas as etapas de registro eram bem-sucedidas exceto pelo WPJ, o dispositivo registrado não aparecia na lista de dispositivos para a identificação dos usuários, causando confusão para os usuários.

### Android
- **Aplicativo Android do Portal da Empresa**<br/>
Se os usuários finais do Android virem uma mensagem de erro indicando que o dispositivo não tem um certificado necessário, eles poderão tocar no botão “Como resolver isso” para obter as [etapas](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) para instalar o certificado que está faltando. Se os usuários concluírem as etapas, mas virem uma mensagem de erro adicional de “certificado faltando”, será solicitado que eles entrem em contato com o administrador de TI e forneçam este [link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), que contém as etapas que os administradores de TI podem usar para corrigir o problema do certificado.

- **Restringir instalações de aplicativo carregado por sideload a dispositivos registrados**<br/>
Os dispositivos Android não podem mais instalar aplicativos por meio do site do Portal da Empresa a menos que os dispositivos tenham sido registrados no Intune usando o aplicativo Portal da Empresa do Intune para Android.
<!---TFS 1299082--->

### iOS
- **Muda para as contas de Gerenciadores de Registro de Dispositivos no aplicativo Portal da Empresa do iOS**<br/>
Para melhorar o desempenho e o dimensionamento, o Intune não mostra mais todos os dispositivos de DEM (Gerenciadores de Registro de Dispositivos) no painel **Meus Dispositivos** do aplicativo Portal da Empresa do iOS. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa.

    O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o Console de Administração do Intune. Além disso, o Intune substituirá o uso de contas DEM com o Programa de Registro de Dispositivo Apple ou com a ferramenta Apple Configurador. Esses dois métodos de registro já dão suporte ao registro sem usuário para dispositivos iOS compartilhados.

    Somente use contas DEM quando o registro sem usuário para dispositivos compartilhados não estiver disponível. Para obter mais informações, consulte [Registrar dispositivos corporativos com o Gerenciador de Registro de Dispositivos no Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Alteração dos nomes dos recursos do Windows
- O [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) agora é conhecido como o **Windows Hello para Empresas**.
- [Proteção de dados empresariais](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) agora é conhecido como **Windows Information Protection**.

## O que está por vir
### Transição de grupos do Intune para os grupos do Azure Active Directory a partir de agosto de 2016
O Intune está criando uma nova experiência de gerenciamento de grupos que usa os grupos de segurança do AAD (Azure Active Directory). Esses grupos de segurança baseados no Azure AD podem conter usuários e dispositivos e serão usados para todo o gerenciamento de grupo, implantação de política e implantação de perfil quando lançarmos o novo portal de administração do Intune baseado no Azure.

Esta nova experiência vai:
- Liberá-lo da necessidade de duplicar grupos entre serviços.
- Permitir o acesso a alguns recursos novos do grupo do AADP (Azure Active Directory Premium).
- Fornecer extensibilidade usando o PowerShell e o Graph.
- Unificar a experiência de gerenciamento de grupo no gerenciamento de mobilidade empresarial.

Para habilitar a mudança para grupos de segurança, a experiência no console do administrador atual passará por algumas modificações. Essas alterações e o uso de grupos de segurança do Azure AD serão registrados na documentação do Intune.

Os cientes que forem novos no Intune verão algumas das alterações de grupos de segurança antes dos locatários atuais.

Além das alterações no gerenciamento de grupo, as seguintes funcionalidades serão preteridas:
- Exclusão de membros ou grupos ao criar um novo grupo
- Grupos de **Usuários Desagrupados** e **Dispositivos Desagrupados**
- **Gerenciar Grupos** na função Administrador do Serviço
- Alertas personalizados com base em grupo para Regras de Notificação
- Dinamização com grupos em relatórios

Para obter mais informações sobre como essas substituições podem ser mitigadas serão liberadas em agosto.

### Adição de 'Notificações' ao Portal da Empresa para Android
Lançaremos uma atualização para o Portal da Empresa para Android em setembro que apresentará um novo ícone **Notificações** na home page. Tocar nesse ícone acessará a pagina **Notificações** que lhe mostrará ao seu usuário final todos os itens que exigem atenção no aplicativo Portal da Empresa, como a não conformidade de dispositivo, atualização de registro e ativação de registro. Se você também usar o aplicativo de Portal da Empresa do iOS, já verá a experiência de notificações. Com a introdução da página **Notificações**, você não verá a página **Configuração de Acesso da Empresa** sempre que iniciar ou retomar o Portal da Empresa para Android contanto que o dispositivo já esteja registrado. Ouvimos que muitos de vocês criaram diretrizes para usuário final e apreciariam um aviso antecipado quando for possível que suas diretrizes/capturas precisem ser atualizadas. Atualize sua documentação para refletir a alteração futura na experiência. Encontre capturas de tela atualizadas aqui: https://aka.ms/androidcpupdate.  



### Roteiro de nuvem
Mantenha-se informado sobre futuros desenvolvimentos do Intune com a [Estratégia de plataforma em nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviço preterido
- **Alterações no suporte para o aplicativo Portal da Empresa do iOS**<br/>
Em setembro, todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS deverão usar sua versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.  

- **Versão mínima do Managed Browser do iOS atualizada para 8.0**<br/>
Em agosto, o Intune lançará um aplicativo Microsoft Intune Managed Browser atualizado para iOS que dará suporte apenas a dispositivos executando o iOS 8.0 ou posterior. Embora os dispositivos iOS 7.1 ainda possam usar o aplicativo Managed Browser existente, incentive seus usuários a atualizar para o iOS 8.0 ou posterior para acessar e aproveitar por completo os recursos do Managed Browser.  
<!---TFS 1313253--->

- **Aplicativos Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos a partir de setembro de 2016** <br/>
A partir de setembro de 2016, o Microsoft Intune encerrará o suporte para os aplicativos de Portal da Empresa do Microsoft Intune para as plataformas Windows Phone 8 e Windows 8. Atualize os dispositivos para Windows 8.1 e Windows Phone 8.1, e use os aplicativos de Portal da Empresa correspondentes dessas plataformas para continuar a distribuição de aplicativos para esses dispositivos.
<!---TFS 1255391--->

- **Aplicativos do Visualizador do Intune** <br/>
Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
    - Visualizador de AV do Intune
    - Visualizador de PDF do Intune
    - Visualizador de imagem do Intune para Android no Google Play

  Em vez de usar os aplicativos do Visualizador do Intune, é recomendável usar o novo [aplicativo do Rights Management (RMS sharing) para o Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança os arquivos corporativos em dispositivos Android. Quando o aplicativo do Visualizador do Intune não tiver mais suporte, ele será removido da Google Store e não estará disponível para uso futuro.

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



<!--HONumber=Aug16_HO2-->


