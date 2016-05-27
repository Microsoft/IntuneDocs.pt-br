---
# required metadata

title: Quais são as novidades | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
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

As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos também terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página O que há de novo em híbrido](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Integração do Centro de Mensagens
Como parte da migração do Intune para o [Portal de Gerenciamento do Office 365](https://portal.office.com/), começaremos a usufruir do Centro de Mensagens que ele tem para comunicar novos recursos e outras notificações.  Além disso, ao instalar o aplicativo móvel de administração do Office 365 complementar, você pode receber notificações no telefone celular e encaminhar facilmente todas as mensagens para usuários ou para um alias de distribuição.<br>  
Começaremos a usar o Centro de Mensagens na versão de maio para notificá-lo quando as atualizações forem concluídas e passarem a incluir informações sobre os recursos novos e aprimorados do Intune.  Confira o Centro de Mensagens hoje mesmo fazendo logon no [Portal de gerenciamento do Office 365](https://portal.office.com/) e escolhendo a opção **CENTRO DE MENSAGENS** no painel de navegação à esquerda.
<!---TFS 1242782--->


## Gerenciamento de aplicativos
- **Acesso condicional para navegador.** Você poderá definir uma política de acesso condicional para o Exchange Online e o SharePoint Online para que eles somente possam ser acessados por dispositivos Android e iOS gerenciados e compatíveis. Os usuários finais que tentarem entrar nos sites OWA (Outlook Web Access) e SharePoint com dispositivos iOS e Android deverão registrar o dispositivo no Intune e corrigir quaisquer problemas de não conformidade para que possam entrar.
<!---TFS 1175844--->

- **SDK do MAM (gerenciamento de aplicativo móvel): Suporte à configuração de tamanho do PIN.** Você poderá especificar o tamanho do PIN para aplicativos de MAM como em um PIN de dispositivo. Isso exigirá que os usuários finais estejam de acordo com as novas restrições que você definir. Eles verão uma tela de PIN um pouco modificada para acomodar uma entrada maior.
<!--- TFS 1104753--->

- **Controles de MAM para impedir a sincronização de contatos do Outlook (iOS).** Uma nova configuração está disponível para o gerenciamento de aplicativo móvel sem registro de dispositivo. Essa configuração permite que o administrador do Intune impeça que um aplicativo sincronize contatos para o catálogo de endereços nativo em dispositivos iOS. Quando essa configuração for habilitada, o aplicativo não poderá mais salvar contatos no catálogo de endereços nativo. Quando essa configuração for desabilitada, o aplicativo poderá salvar contatos no catálogo de endereços nativo. Quando um administrador do Intune apagar um dispositivo seletivamente, todos os contatos que já tiverem sido salvos no catálogo de endereços nativo serão removidos. Agora, essa nova configuração tem suporte no aplicativo Outlook em dispositivos iOS.
<!---TFS item 1276166--->

- **Skype for Business para Android.** Agora, os administradores do Intune podem gerenciar o Skype for Business com MAM sem políticas de registro.  Quando os usuários fizerem logon, as políticas de MAM serão aplicadas.
<!--- TFS item 1248444 --->

- **Skype for Business para iOS.** Agora, os administradores do Intune podem gerenciar o Skype for Business com MAM sem políticas de registro.  Quando os usuários fizerem logon, as políticas de MAM serão aplicadas.
<!--- TFS item 1248443 --->

### Suporte ao Xamarin
Agora, o SDK de aplicativos do Microsoft Intune dá suporte a aplicativos Xamarin nestes cenários:

- Gravando novos aplicativos ou modificando o código de aplicativos de linha de negócios existentes usando o SDK do Intune. Você pode obter o plug-in na página [Github do Microsoft Intune](https://github.com/msintuneappsdk).
- Adicionando suporte de MAM em aplicativos de linha de negócios existentes usando a ferramenta de encapsulamento de aplicativo do Intune

Para obter ajuda para decidir qual método usar, consulte [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) (Decida como preparar aplicativos para gerenciamento de aplicativo móvel com o Microsoft Intune).
<!--- TFS 1061478 & TFS 1152340--->


## Gerenciamento de dispositivos
- **Sessões de assistência remota para computadores Windows.** A integração do TeamViewer para computadores Windows gerenciados por agentes da área de trabalho permitirá estabelecer sessões de assistência remota com computadores Windows gerenciados por agentes da área de trabalho para oferecer suporte a departamentos de assistência técnica ao usuário final. Compatível com o Windows 7, 8, 8.1 e o Windows 10.
<!--- TFS 1284856--->


<!--- TFS item 1274326 --->

## Controle de acesso
* **O Skype for Business Online dá suporte ao acesso condicional.** Os administradores do Intune poderão definir uma política de acesso condicional para o Skype for Business Online para que ele somente possa ser acessado por dispositivos iOS e Android gerenciados e compatíveis. Os usuários finais que tentarem entrar no aplicativo móvel Skype for Business no iOS e no Android deverão se registrar no Intune e corrigir quaisquer problemas de não conformidade para poder entrar.
<!---TFS item 1254499--->

## Portal da Empresa
* **A faixa de identificação de dispositivo fornecerá mais informações aos usuários finais.** Os usuários finais poderão identificar facilmente o dispositivo que selecionaram ao usarem o site Portal da Empresa. Se um dispositivo errado for selecionado, eles poderão selecionar o dispositivo correto tocando no link "Toque aqui", na faixa de página inicial.
<!--- TFS 1231157--->

* **Pacotes de aplicativos do Windows disponíveis diretamente no Portal da Empresa**: os usuários de computadores Windows 8, Windows 8.1 e Windows RT agora podem instalar pacotes de aplicativos do Windows (com a extensão .appx) diretamente do site Portal da Empresa. Anteriormente, os administradores do Intune tinham que implantar, ou os usuários tinham que instalar o aplicativo Portal da Empresa em seus dispositivos para instalar aplicativos.
<!--- TFS item 1082481 --->

* **Os usuários podem bloquear o dispositivo remotamente usando o Portal da Empresa** Uma nova opção de bloqueio remoto foi adicionada no site Portal da Empresa para permitir que os usuários finais bloqueiem seus dispositivos remotamente usando o portal, no caso de perda ou roubo do dispositivo. A tabela a seguir lista o suporte às plataformas para bloqueio remoto do Intune e do Intune com o Configuration Manager.
<!--- TFS item 1195661 --->

|Plataforma  |Detalhes do suporte|
|---------|---------|
|iOS | Com suporte|
|Android | Com suporte|
|Windows Phone 8.1 | Com suporte|
|Windows 10 Mobile | Com suporte apenas se o telefone tiver uma senha definida|
|Computador (Windows 8.0 e anterior) | Sem suporte|
|Computador (Windows 8.1) | Sem suporte|
|Windows Phone 8.0 | Sem suporte|
|Windows 10 Desktop | Sem suporte|

## Serviço preterido
* **Remoção de aplicação de regras de notificação em grupo personalizado.** A partir do início de junho de 2016, não será mais possível usar o Assistente para Criar Regra de Notificação para aplicar regras de notificação nos grupos criados pelo usuário.

    Atualmente, para aplicar em um grupo criado pelo usuário usando o Console de Administração do Microsoft Intune, você escolhe **Administração** > **Regras de Notificação** > **Criar Nova Regra**. Na etapa dois do Assistente para Criar Regra de Notificação, você deve selecionar os grupos de dispositivos aos quais a regra será aplicada. Nesta etapa, **Selecionar grupos de dispositivos**, está sendo preterido Console do Intune.

    **Selecionar grupos de dispositivos** não terá mais suporte após o lançamento do Intune de junho de 2016. No entanto, você continuará a ter esta opção até agosto de 2016. Depois de agosto, começaremos a transferir os locatários para a nova experiência durante um período de dois meses. Até outubro de 2016, todos os clientes existentes já deverão ter sido transferidos para a nova experiência. Após a migração para a nova experiência, você não terá mais a opção de aplicar regras de notificação em um grupo específico.
<!---   TFS 1278864--->







### Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.


<!--HONumber=May16_HO1-->


