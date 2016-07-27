---
title: "Quais são as novidades | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 35ee5d0c8898c95898c0527a623cf13c454387f2
ms.openlocfilehash: 831cec6cd0e02a94c1a3f67d4adf5a5dcbb01449


---

# Quais são as novidades no Microsoft Intune – julho
Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Confira se há novas atualizações em Quais São as Novidades.

As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) (Novidades do Híbrido).


## Gerenciamento de aplicativos
### Melhorar a experiência de atualização de perfil de provisionamento de aplicativo
Os aplicativos móveis de linha de negócios de iOS da Apple são criados com um perfil de provisionamento incluído e com assinatura por código com um certificado. Quando o aplicativo é executado em um dispositivo iOS, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento.

A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos. No entanto, o perfil de provisionamento expira após um ano. Com essa atualização, o Intune fornecerá as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos se aproximando da expiração enquanto o certificado ainda for válido.
<!--- TFS 1280247--->

### Suporte ao Xamarin
O SDK de aplicativos do Microsoft Intune dará suporte a aplicativos Xamarin nestes cenários:

- Gravando novos aplicativos ou modificando o código de aplicativos de linha de negócios existentes usando o SDK do Intune. Você pode obter o plug-in na página [GitHub do Microsoft Intune](https://github.com/msintuneappsdk).
- Adicionando suporte de MAM em aplicativos de linha de negócios existentes usando a ferramenta de encapsulamento de aplicativo do Intune

Para obter ajuda para decidir qual método usar, consulte [Decide how to prepare apps for mobile application management with Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) (Decidir como preparar aplicativos para gerenciamento de aplicativo móvel com o Microsoft Intune).

<!--- TFS 1061478 & TFS 1152340--->

## Gerenciamento de dispositivos
### Limites de registro de dispositivo maior
O Intune aumentará o limite máximo de registro de dispositivo configurável de 5 para 15 dispositivos por usuário.
<!---TFS 1289896 --->

## Gerenciamento de grupos
### Transição de grupos do Intune para os grupos do Azure Active Directory a partir de agosto de 2016
O Intune está criando uma nova experiência de gerenciamento de grupos que usa os grupos de segurança do AAD (Azure Active Directory) como grupos de usuários e de dispositivos no Intune. Esses grupos serão usados para todo o gerenciamento de grupo, implantação de política e implantação de perfil **quando lançarmos o novo portal de administração do Intune baseado no Azure**.

Essa nova experiência evitará que você precise duplicar grupos entre serviços, **concederá acesso a alguns recursos de grupo novos do AADP (Azure Active Directory Premium)** e fornecerá extensibilidade usando o PowerShell e o Graph. Ela também unificará a experiência de gerenciamento de grupo no gerenciamento de mobilidade empresarial.

Para habilitar a mudança para grupos de segurança, a experiência no **console do administrador** atual passará por algumas modificações. **Essas alterações e o uso de grupos de segurança do AAD serão registrados na documentação do Intune**.

Os cientes que forem novos no Intune verão **algumas das alterações de grupos de segurança antes dos locatários atuais**.

Além das alterações no gerenciamento de grupo, **as seguintes funcionalidades serão preteridas**:
- Exclusão de membros ou grupos ao criar um novo grupo
- ‘Gerenciar Grupos' na função Administrador do Serviço
- Alertas personalizados com base em grupo para Regras de Notificação
- Dinamização com grupos em relatórios


## Portal da Empresa

### Adição de 'Notificações' ao Portal da Empresa para Android
Lançaremos uma atualização para o Portal da Empresa para Android em agosto que apresentará um novo ícone **Notificações** na home page. Tocar nesse ícone acessará a pagina **Notificações** que lhe mostrará ao seu usuário final todos os itens que exigem atenção no aplicativo Portal da Empresa, como a não conformidade de dispositivo, atualização de registro e ativação de registro. Se você também usar o aplicativo de Portal da Empresa do iOS, já verá a experiência de notificações. Com a introdução da página **Notificações**, você não verá a página **Configuração de Acesso da Empresa** sempre que iniciar ou retomar o Portal da Empresa para Android contanto que o dispositivo já esteja registrado. Ouvimos que muitos de vocês criaram diretrizes para usuário final e apreciariam um aviso antecipado quando for possível que suas diretrizes/capturas precisem ser atualizadas. Atualize sua documentação para refletir a alteração futura na experiência. Para encontrar as capturas de tela atualizadas, acesse aqui: https://aka.ms/androidcpupdate  

### Ajudar os usuários a resolver problemas de registro quando o Ingresso no Local de Trabalho falhar
Quando você estiver usando o acesso condicional, as etapas de registro para o Windows 8.1, Windows 10 Desktop e Windows 10 Mobile serão simplificadas no site do Portal da empresa para usuários finais que enfrentarem uma falha de WPJ (Ingresso no Local de Trabalho). Anteriormente, quando os usuários finais tentavam se registrar e realizar um WPJ e seu registro era bem-sucedido, mas o WPJ falhava, o dispositivo registrado não aparecia na lista de dispositivos para a identificação dos usuários, causando confusão para os usuários. Agora os usuários verão as etapas “Registro do dispositivo” e “Ingresso no local de trabalho”, tornando mais fácil que eles vejam o status de seu dispositivo e concluam o processo após a falha de WPJ. É esperado que as etapas separadas também simplifiquem o processo de solução de problemas para os administradores de TI.

### Muda para as contas de Gerenciadores de Registro de Dispositivos no aplicativo Portal da Empresa do iOS
Para melhorar o desempenho e o dimensionamento, o Intune não mostrará mais todos os dispositivos DEM (Gerenciadores de Registro do Dispositivo) no painel Meus Dispositivos do aplicativo Portal da Empresa do iOS. Somente o dispositivo local que estiver executando o aplicativo será exibido e somente se ele tiver sido registrado por meio do aplicativo do Portal da Empresa. O usuário DEM pode realizar ações no dispositivo local, mas o gerenciamento remoto de outros dispositivos registrados somente poderá ser executado usando o Console de Administração do Intune.  Além disso, o Intune substituirá o uso de contas DEM com o Programa de Registro de Dispositivo Apple ou com a ferramenta Apple Configurador. Esses dois métodos de registro já dão suporte ao registro sem usuário para dispositivos iOS compartilhados. Somente use contas DEM quando o registro sem usuário para dispositivos compartilhados não estiver disponível.
<!---TFS 1233681--->
### Restringir a instalação de aplicativos carregados por sideload aos dispositivos Android
Os dispositivos Android não podem mais instalar aplicativos por meio do site do Portal da Empresa a menos que os dispositivos tenham sido registrados no Intune usando o aplicativo Portal da Empresa do Intune para Android. 
<!---TFS 1299082--->

## Serviço preterido
**Aplicativos do Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos a partir de setembro de 2016.** A partir de setembro de 2016, o Microsoft Intune encerrará o suporte para os aplicativos de Portal da Empresa do Microsoft Intune para as plataformas Windows Phone 8 e Windows 8. Atualize os dispositivos para Windows 8.1 e Windows Phone 8.1, e use os aplicativos de Portal da Empresa correspondentes dessas plataformas para continuar a distribuição de aplicativos para esses dispositivos.
<!---TFS 1255391--->

**Remoção de aplicação de regras de notificação em grupo personalizado.**
Regras de notificação do Intune definem para quem um alerta de email será enviado do Intune. No momento, você pode configurar as regras de notificação para enviarem emails para todos os usuários de dispositivos em um grupo de dispositivos do Intune que você criou. A partir de 1º de junho de 2016, direcionar grupos criados pelo usuário não terá mais suporte.

A linha do tempo preliminar para essa alteração é a seguinte:
- Em agosto de 2016, novos locatários não verão a etapa dois do Assistente para Criar Regra de Notificação. Os locatários existentes não são afetados.
- Em torno de setembro de 2016, alguns locatários existentes não verão "selecione grupos de dispositivos" no assistente.
- Em torno de novembro de 2016, esperamos que todos os locatários não vejam "selecione grupos de dispositivos" no assistente.

<!---   TFS 1278864--->

**Alterações no suporte para o aplicativo do Portal da Empresa do iOS.**
Em julho, todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS deverão usar a versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.  

**Aplicativos do visualizador do Intune.** Com o lançamento do novo aplicativo RMS sharing, estamos removendo os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
- Visualizador de AV do Intune
- Visualizador de PDF do Intune
- Visualizador de imagem do Intune para Android no Google Play

Em vez de usar os aplicativos do visualizador do Intune, é recomendável usar o novo aplicativo do Rights Management (RMS sharing) para o Android, que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança arquivos corporativos em dispositivos Android. Saiba mais sobre o aplicativo RMS sharing (com links para documentação).



### Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.



<!--HONumber=Jul16_HO3-->


