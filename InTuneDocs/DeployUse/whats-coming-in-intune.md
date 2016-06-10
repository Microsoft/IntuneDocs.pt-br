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

## Comunicações do Intune
- **Informações de integridade do serviço do Intune.** para Intune foram movidas para uma localização central com outros serviços da Microsoft. Agora, você encontrará essas informações no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) em Integridade do Serviço. Para obter mais informações, consulte [esta postagem do blog](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

- **Integração da interface do usuário do Centro de Mensagens.** Como parte da migração do Intune para o [Portal de Gerenciamento do Office 365](https://portal.office.com/), começaremos a usufruir do Centro de Mensagens que ele tem para comunicar novos recursos e outras notificações. Além disso, ao instalar o aplicativo móvel de administração do Office 365 complementar, você pode receber notificações no telefone celular e encaminhar facilmente todas as mensagens para usuários ou para um alias de distribuição.
Começaremos a usar o Centro de Mensagens na versão de maio para notificá-lo quando as atualizações forem concluídas e passarem a incluir informações sobre os recursos novos e aprimorados do Intune. Confira o Centro de Mensagens hoje mesmo fazendo logon no [Portal de gerenciamento do Office 365](https://portal.office.com/) e escolhendo a opção **Centro de Mensagens** no painel de navegação à esquerda.

## Gerenciamento de aplicativos
- **Novos aplicativos disponíveis para gerenciamento com políticas MAM.** Os aplicativos Microsoft Word, Excel e PowerPoint para Android agora podem ser associados com as políticas MAM em dispositivos que não estão registrados com o Intune. Para ver a lista completa de aplicativos com suporte, vá para a galeria de aplicativos móveis do Microsoft Intune na página [Microsoft Intune application partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) (Parceiros de aplicativos do Microsoft Intune).


- **Acesso condicional para navegador.** Você poderá definir uma política de acesso condicional para o Exchange Online e o SharePoint Online para que eles somente possam ser acessados por dispositivos Android e iOS gerenciados e compatíveis. Os usuários finais que tentarem entrar nos sites OWA (Outlook Web Access) e SharePoint com dispositivos iOS e Android deverão registrar o dispositivo no Intune e corrigir quaisquer problemas de não conformidade para que possam entrar.
<!---TFS 1175844--->

- **SDK do MAM (gerenciamento de aplicativo móvel): Suporte à configuração de tamanho do PIN.** Você poderá especificar o tamanho do PIN para aplicativos de MAM como em um PIN de dispositivo. Isso exigirá que os usuários finais estejam de acordo com as novas restrições que você definir. Eles verão uma tela de PIN um pouco modificada para acomodar uma entrada maior.
<!--- TFS 1104753--->

- **Skype for Business para Android.** Agora, os administradores do Intune podem gerenciar o Skype for Business com MAM sem políticas de registro.  Quando os usuários fizerem logon, as políticas de MAM serão aplicadas.
<!--- TFS item 1248444 --->

- **Skype for Business para iOS.** Agora, os administradores do Intune podem gerenciar o Skype for Business com MAM sem políticas de registro.  Quando os usuários fizerem logon, as políticas de MAM serão aplicadas.
<!--- TFS item 1248443 --->

### Suporte ao Xamarin
Agora, o SDK de aplicativos do Microsoft Intune dá suporte a aplicativos Xamarin nestes cenários:

- Gravando novos aplicativos ou modificando o código de aplicativos de linha de negócios existentes usando o SDK do Intune. Você pode obter o plug-in na página [Github do Microsoft Intune](https://github.com/msintuneappsdk).
- Adicionando suporte de MAM em aplicativos de linha de negócios existentes usando a ferramenta de encapsulamento de aplicativo do Intune

Para obter ajuda para decidir qual método usar, consulte [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) (Decidir como preparar aplicativos para gerenciamento de aplicativo móvel com o Microsoft Intune).
<!--- TFS 1061478 & TFS 1152340--->


## Gerenciamento de dispositivo
- **Sessões de assistência remota para computadores Windows.** A integração do TeamViewer para computadores Windows gerenciados por agentes da área de trabalho permitirá estabelecer sessões de assistência remota com computadores Windows gerenciados por agentes da área de trabalho para oferecer suporte a departamentos de assistência técnica ao usuário final. Compatível com o Windows 7, 8, 8.1 e o Windows 10.
<!--- TFS 1284856--->



## Portal da Empresa

- **Notificações do sistema do usuário final.** Os usuários finais agora verão notificações do sistema do aplicativo do Portal da Empresa do Android quando registrarem ou removerem seus dispositivos do Portal da Empresa.
- **A faixa de identificação de dispositivo fornecerá mais informações aos usuários finais.** Os usuários finais poderão identificar facilmente o dispositivo que selecionaram ao usarem o site Portal da Empresa. Se um dispositivo errado for selecionado, eles poderão selecionar o dispositivo correto tocando no link "Toque aqui", na faixa de página inicial.
<!--- TFS 1231157--->

- **Muda para as contas de Gerenciadores de Registro do Dispositivo no aplicativo do Portal da Empresa do Android.** Para melhorar o desempenho e a escala, o Intune não mostrará mais todos os dispositivos de DEM (Gerenciadores de Registro do Dispositivo) no painel **Meus Dispositivos** do aplicativo Portal da Empresa do Android. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo do Portal da Empresa. O usuário de DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o console de administração do Intune.

- **Muda para as contas de Gerenciadores de Registro do Dispositivo no aplicativo do Portal da Empresa do iOS.** Para melhorar o desempenho e o dimensionamento, o Intune não mostrará mais todos os dispositivos de DEM (Gerenciadores de Registro do Dispositivo) no painel Meus Dispositivos do aplicativo do Portal da Empresa do iOS. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo Portal da Empresa. O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente pode ser executado usando o Console de Administração do Intune.  Além disso, o Intune substituirá o uso de contas DEM com o Programa de Registro de Dispositivo Apple ou com a ferramenta Apple Configurador. Esses dois métodos de registro já dão suporte ao registro sem usuário para dispositivos iOS compartilhados.  Somente use contas DEM quando o registro sem usuário para dispositivos compartilhados não estiver disponível.



## Serviço preterido
**Remoção de aplicação de regras de notificação em grupo personalizado.**
Regras de notificação do Intune definem para quem um alerta de email será enviado do Intune. No momento, você pode configurar as regras de notificação para enviarem emails para todos os usuários de dispositivos em um grupo de dispositivos do Intune que você criou. A partir de 1º de junho de 2016, direcionar grupos criados pelo usuário não terá mais suporte.

Hoje, para direcionar uma regra de notificação a um grupo criado no console de administração do Microsoft Intune, você realizaria as seguintes etapas:

No espaço de trabalho **Administrador**, clique em **Regras de Notificação** > **Criar Nova Regra**

Na etapa dois do assistente Criar Regra de Notificação, selecione os grupos de dispositivos nos quais a regra será aplicada. Nesta etapa, “selecionar grupos de dispositivos”, está sendo removido do Console do Intune.

A linha do tempo preliminar para essa alteração é a seguinte:
- Em junho de 2016 novos locatários não verão a etapa dois do assistente Criação de Regra de Notificação. Os locatários existentes não são afetados.
- Em torno de agosto de 2016, alguns locatários existentes não verão "selecionar grupos de dispositivo" no assistente.
- Em torno de outubro de 2016, esperamos que todos os locatários não verão "selecionar grupos de dispositivo" no assistente.

<!---   TFS 1278864--->
**Alterações no suporte para o aplicativo do Portal da Empresa do iOS.**
Nos próximos meses, haverá uma atualização para o aplicativo de Portal da Empresa do Microsoft Intune para iOS que dará suporte somente a dispositivos que executam o iOS 8.0 ou posterior. Os usuários não poderão registrar novos dispositivos que executam versões anteriores à iOS 8.0. Dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e, por um período limitado, poderão continuar usando o aplicativo do Portal da Empresa. No entanto, os dispositivos devem estar no iOS 8.0 ou posterior para acessar as versões mais recentes do aplicativo do Portal da Empresa. É recomendável notificar os usuários para atualizar para o iOS 8.0 ou posterior para que eles se beneficiem com os novos recursos do Intune.  

- **Aplicativos do visualizador do Intune.** Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
    - Visualizador de AV do Intune
    - Visualizador de PDF do Intune
    - Visualizador de imagem do Intune para Android no Google Play

  Em vez de usar os aplicativos do visualizador do Intune, é recomendável usar o novo aplicativo do Rights Management (RMS sharing) para o Android, que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança arquivos corporativos em dispositivos Android. Saiba mais sobre o aplicativo RMS sharing (com links para documentação).






### Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.


<!--HONumber=May16_HO5-->


