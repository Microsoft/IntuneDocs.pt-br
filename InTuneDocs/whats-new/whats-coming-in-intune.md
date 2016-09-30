---
title: "Quais são as novidades | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ecf43b38e9593375981770583220d4ce2dfd709f
ms.openlocfilehash: b5da0aca366a24f2f0ccf62a3661b0b91db9b01a


---

# Quais são as novidades no Microsoft Intune - agosto
Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Confira se há novas atualizações em Quais São as Novidades.

As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) (Novidades do Híbrido).


## Gerenciamento de aplicativos
### Aplicativos ocultados e mostrados para iOS 9.3
Para dispositivos supervisionados que executam o iOS 9.3 ou posterior, você poderá usar a lista de aplicativos ocultos e mostrados na política de configuração geral do iOS para:
- Especificar uma lista de aplicativos que serão ocultados dos usuários. Os usuários não podem exibir nem iniciar esses aplicativos.
- Especifique uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

Os aplicativos que você pode especificar incluem os dois aplicativos que você implantou e os aplicativos iOS nativos, como Mensagens e Anotações.
<!---TFS 1279009--->

### Política de aplicativos permitidos e bloqueados para dispositivos Samsung KNOX

Agora você pode configurar uma política personalizada para dispositivos Samsung KNOX que permite que você crie um dos seguintes procedimentos:
- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Mesmo se instalado, um aplicativo definido na lista de bloqueados não pode ser ativado no dispositivo.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play. Nenhum outro aplicativo pode ser instalado da loja.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX.
<!--- For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md)--->
<!---TFS 1311629 --->

### Novos aplicativos compatíveis com políticas de MAM (Gerenciamento de Aplicativo Móvel)
O aplicativo do Yammer para [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) e [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) será compatível com [políticas de MAM (gerenciamento de Aplicativo Móvel) do Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), esteja o dispositivo registrado ou não.

Para obter uma lista completa de aplicativos compatíveis com MAM, visite o site [Microsoft Intune application partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) (Parceiros de aplicativos do Microsoft Intune).
<!--- TFS 1252335 & 1252336--->

## Gerenciamento de dispositivos
### Suporte do Android 7.0
Em agosto, o Intune oferecerá suporte de "dia 0" para o próximo sistema de operacional Android 7.0 para dispositivos móveis.
<!---TFS 1262053--->
### Remoção pelo Google da funcionalidade de redefinição remota de senha em dispositivos Android 7.0
O Google está removendo a capacidade dos administradores de TI e usuários finais de redefinir remotamente a senha de dispositivos Android 7.0. Anteriormente, os administradores de TI podiam redefinir remotamente a senha de um usuário, e os usuários finais podiam redefinir suas senhas do site do Portal da Empresa.

## Gerenciamento de grupos
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

## Serviço preterido
### Aplicativos Portal da Empresa para Windows 8 e Windows Phone 8 serão preteridos a partir de setembro de 2016
A partir de outubro de 2016, o Microsoft Intune preterirá o suporte para aplicativos do Portal da Empresa do Windows 8 e Windows Phone 8. O Microsoft Intune também preterirá o suporte para a plataforma Windows Phone 8. Em consequência disso, você não poderá registrar nem atualizar dispositivos Windows Phone 8. Você pode continuar a gerenciar dispositivos Windows Phone 8 e Windows 8 já registrados. Atualize os dispositivos Windows Phone 8 e Windows 8 para Windows 8.1 e Windows Phone 8.1 e use os aplicativos do Portal da Empresa correspondentes do Windows 8.1 e do Windows Phone 8.1 para continuar a distribuir aplicativos para esses dispositivos sem interrupções.
<!---TFS 1255391--->

### Remoção de direcionamento em grupo personalizado de regras de notificação
Regras de notificação do Intune definem para quem um alerta de email será enviado do Intune. No momento, você pode configurar as regras de notificação para enviarem emails para todos os usuários de dispositivos em um grupo de dispositivos do Intune que você criou. A partir de junho de 2016, não haverá mais suporte ao direcionamento para grupos criados pelo usuário.

A linha do tempo preliminar para essa alteração é a seguinte:
- Em setembro de 2016, novos locatários não verão a etapa dois do Assistente de Criação de Regra de Notificação. Os locatários existentes não são afetados.
- Em torno de outubro de 2016, alguns locatários existentes não verão "selecione grupos de dispositivos" no assistente.
- Em uma data posterior, esperamos que nenhum locatário veja "selecionar grupos de dispositivo" no assistente.

<!---   TFS 1278864--->
### Alterações no suporte para o aplicativo Portal da Empresa do iOS
Em setembro, todos os usuários do aplicativo do Portal da Empresa Microsoft Intune para iOS deverão usar sua versão mais recente. Novos usuários só poderão baixar a versão mais recente e os usuários atuais precisarão atualizar para ela. A versão mais recente requer iOS 8.0 ou posterior, por isso dispositivos que executam versões anteriores do iOS não conseguirão usar o Portal da Empresa ou registrar-se até atualizar seu dispositivo para o iOS 8.0 ou posterior, para então atualizar o aplicativo de Portal da Empresa para a versão mais recente. Os dispositivos que executam versões abaixo do iOS 8.0 continuarão a ser gerenciados e listados no Console de Administração do Intune.

<!---TFS 1283165--->


### Aplicativos do Visualizador do Intune
Com o lançamento do novo aplicativo RMS sharing, removeremos os seguintes aplicativos do visualizador do Intune a partir de agosto de 2016:
- Visualizador de AV do Intune
- Visualizador de PDF do Intune
- Visualizador de imagem do Intune para Android no Google Play

Em vez de usar os aplicativos do visualizador do Intune, é recomendável usar o novo aplicativo do Rights Management (RMS sharing) para o Android, que permite implantar um aplicativo em vez de três aplicativos separados para exibir com segurança arquivos corporativos em dispositivos Android. Saiba mais sobre o [aplicativo RMS sharing](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app).
<!--- goes in 1608 What's New--->


### Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.



<!--HONumber=Sep16_HO5-->


