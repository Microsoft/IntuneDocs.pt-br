---
# required metadata

title: Quais são as novidades | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Quais são as novidades no Microsoft Intune
Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Confira se há novas atualizações em Quais São as Novidades.

As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos também terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) (Novidades do Híbrido).


## Gerenciamento de aplicativos
- **Alterações na política de dados do Windows 10 Enterprise.** Devido às melhorias da política de aplicativo na política de dados do Windows 10 Enterprise dados, quando você salva uma política que foi configurada com regras de aplicativo (aplicativos anteriormente protegidos), todas as regras existentes configurado serão perdidas. Para continuar, você precisará reconfigurar essas regras de aplicativo.

- **Acesso condicional para navegador.** Você poderá definir uma política de acesso condicional para o Exchange Online e o SharePoint Online para que eles somente possam ser acessados por dispositivos Android e iOS gerenciados e compatíveis. Os usuários finais que tentarem entrar nos sites OWA (Outlook Web Access) e SharePoint com dispositivos iOS e Android deverão registrar o dispositivo no Intune e corrigir quaisquer problemas de não conformidade para que possam entrar.
<!---TFS 1175844--->

- **O Dynamics CRM Online dá suporte ao acesso condicional.** Os clientes poderão definir uma política de acesso condicional para o Dynamics CRM Online para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e compatíveis. Os usuários finais que tentarem entrar no aplicativo móvel Dynamics CRM no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar.
<!---TFS1295358--->

### Suporte ao Xamarin
Agora, o SDK de aplicativos do Microsoft Intune dá suporte a aplicativos Xamarin nestes cenários:

- Gravando novos aplicativos ou modificando o código de aplicativos de linha de negócios existentes usando o SDK do Intune. Você pode obter o plug-in na página [Github do Microsoft Intune](https://github.com/msintuneappsdk).
- Adicionando suporte de MAM em aplicativos de linha de negócios existentes usando a ferramenta de encapsulamento de aplicativo do Intune

Para obter ajuda para decidir qual método usar, consulte [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) (Decidir como preparar aplicativos para gerenciamento de aplicativo móvel com o Microsoft Intune).
<!--- TFS 1061478 & TFS 1152340--->


## Portal da Empresa
**Muda para as contas de Gerenciadores de Registro do Dispositivo no aplicativo do Portal da Empresa do iOS.** Para melhorar o desempenho e o dimensionamento, o Intune não mostrará mais todos os dispositivos de DEM (Gerenciadores de Registro do Dispositivo) no painel Meus Dispositivos do aplicativo do Portal da Empresa do iOS. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa. O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o Console de Administração do Intune.  Além disso, o Intune substituirá o uso de contas DEM com o Programa de Registro de Dispositivo Apple ou com a ferramenta Apple Configurador. Esses dois métodos de registro já dão suporte ao registro sem usuário para dispositivos iOS compartilhados.  Somente use contas DEM quando o registro sem usuário para dispositivos compartilhados não estiver disponível.
<!---TFS 1233681--->

## Serviço preterido
**Aplicativos do Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos a partir de setembro de 2016.** A partir de setembro de 2016, o Microsoft Intune encerrará o suporte para os aplicativos de Portal da Empresa do Microsoft Intune para as plataformas Windows Phone 8 e Windows 8. Atualize os dispositivos para Windows 8.1 e Windows Phone 8.1, e use os aplicativos de Portal da Empresa correspondentes dessas plataformas para continuar a distribuição de aplicativos para esses dispositivos.
<!---TFS 1255391--->

**Remoção de aplicação de regras de notificação em grupo personalizado.**
Regras de notificação do Intune definem para quem um alerta de email será enviado do Intune. No momento, você pode configurar as regras de notificação para enviarem emails para todos os usuários de dispositivos em um grupo de dispositivos do Intune que você criou. A partir de 1º de junho de 2016, direcionar grupos criados pelo usuário não terá mais suporte.

A linha do tempo preliminar para essa alteração é a seguinte:
- Em junho de 2016 novos locatários não verão a etapa dois do assistente Criação de Regra de Notificação. Os locatários existentes não são afetados.
- Em torno de agosto de 2016, alguns locatários existentes não verão "selecionar grupos de dispositivo" no assistente.
- Em torno de outubro de 2016, esperamos que todos os locatários não verão "selecionar grupos de dispositivo" no assistente.

<!---   TFS 1278864--->
**Alterações no suporte para o aplicativo do Portal da Empresa do iOS.**
Os usuários devem atualizar para o aplicativo de Portal da Empresa do iOS mais recente. Nos próximos meses, todos os usuários do aplicativo do Portal da Empresa do Microsoft Intune para iOS deverão usar a versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.  

**Aplicativos do visualizador do Intune.** Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
- Visualizador de AV do Intune
- Visualizador de PDF do Intune
- Visualizador de imagem do Intune para Android no Google Play

Em vez de usar os aplicativos do visualizador do Intune, é recomendável usar o novo aplicativo do Rights Management (RMS sharing) para o Android, que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança arquivos corporativos em dispositivos Android. Saiba mais sobre o aplicativo RMS sharing (com links para documentação).


### Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.


<!--HONumber=Jun16_HO2-->


