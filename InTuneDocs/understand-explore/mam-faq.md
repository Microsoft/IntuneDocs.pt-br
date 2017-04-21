---
title: "Perguntas frequentes sobre o MAM e a proteção do aplicativo"
description: "Este artigo fornece respostas para algumas perguntas frequentes sobre o Intune MAM (gerenciamento de aplicativo móvel) e a proteção do aplicativo do Intune."
keywords: 
author: oydang
ms.author: oydang
manager: mtillman
ms.date: 01/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: aea41c86e1fe784d6234f4ff90e299632b2a6d5f
ms.lasthandoff: 04/14/2017


---

# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Perguntas frequentes sobre o MAM e a proteção do aplicativo

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este artigo fornece respostas para algumas perguntas frequentes sobre o Intune MAM (gerenciamento de aplicativo móvel) e a proteção do aplicativo do Intune.

## <a name="mam-basics"></a>Noções básicas sobre o MAM


**O que é o MAM?** [Gerenciamento de aplicativo móvel do Intune](../deploy-use/overview-of-app-lifecycle-in-microsoft-intune.md) refere-se ao pacote de recursos de gerenciamento do Intune que permite publicar, enviar por push, configurar, proteger, monitorar e atualizar aplicativos móveis para os usuários.

**Quais são os benefícios da proteção do aplicativo do MAM?** O MAM protege os dados de uma organização em um aplicativo. Com o MAM-WE, um aplicativo relacionado ao trabalho ou à escola que contém dados confidenciais pode ser gerenciado em quase todos os dispositivos, incluindo dispositivos pessoais em cenários de BYOD (traga seu próprio dispositivo). Vários aplicativos de produtividade, como os aplicativos do Microsoft Office, podem ser gerenciados pelo Intune MAM. Consulte a lista oficial de [aplicativos habilitados pelo Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) disponíveis para uso público.

**Quais configurações de dispositivo têm suporte no MAM?** O Intune MAM dá suporte a duas configurações:
  1. **Intune MDM + MAM**: essa foi a primeira configuração com suporte no MAM quando ele foi lançado pela primeira vez. Os administradores de TI apenas podem gerenciar aplicativos usando o MAM e políticas de proteção do aplicativo em dispositivos registrados no Intune MDM (gerenciamento de dispositivo móvel). Para gerenciar aplicativos usando o MDM + MAM, os clientes devem usar o console independente do Intune em http://manage.microsoft.com.

  2. **MAM sem registro de dispositivo**: o MAM sem registro de dispositivo, ou MAM-WE, permite que os administradores de TI gerenciem aplicativos usando o MAM e políticas de proteção do aplicativo em dispositivos não registrados no Intune MDM. Isso significa que os aplicativos podem ser gerenciados pelo Intune em dispositivos registrados em provedores de EMM de terceiros. Para gerenciar aplicativos usando o MAM-WE, os clientes devem usar o console do Intune no portal do Azure em http://portal.azure.com.


## <a name="app-protection-policies"></a>Políticas de proteção do aplicativo

**O que são políticas de proteção do aplicativo**? Políticas de proteção do aplicativo são regras que garantem que os dados de uma organização permanecem seguros ou contidos em um aplicativo gerenciado. Uma política pode ser uma regra imposta quando o usuário tenta acessar ou mover dados “corporativos” ou um conjunto de ações proibidas ou monitoradas quando o usuário está no aplicativo.

**Quais são exemplos de políticas de proteção do aplicativo?** Consulte [Android app protection policy settings](../deploy-use/android-mam-policy-settings.md) (Configurações da política de proteção de aplicativo Android) e [iOS app protection policy settings](../deploy-use/ios-mam-policy-settings.md) (Configurações da política de proteção de aplicativo iOS) para obter informações detalhadas sobre cada configuração da política de proteção do aplicativo.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplicativos que podem ser gerenciados com políticas de proteção do aplicativo

**Quais aplicativos podem ser gerenciados por políticas de proteção do aplicativo?** Qualquer aplicativo que tenha sido habilitado pelo [SDK do Aplicativo do Intune](../develop/intune-app-sdk.md) ou encapsulado pela [Ferramenta de Disposição do Aplicativo do Intune](../deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) pode ser gerenciado por políticas de proteção do aplicativo do Intune. Consulte a lista oficial de [aplicativos habilitados pelo Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) disponíveis para uso público.

**Quais são os requisitos de linha de base para usar as políticas de proteção do aplicativo em um aplicativo habilitado pelo Intune?**
  1. O usuário final deve ter uma conta do AAD (Azure Active Directory). Consulte [Adicionar usuários e conceder permissão administrativa para o Intune](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3.md) para saber como criar usuários do Intune no Azure Active Directory.

  2. O usuário final deve ter uma licença do Microsoft Intune atribuída à sua conta do Azure Active Directory. Consulte [Gerenciar licenças do Intune](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4.md) para saber como atribuir licenças do Intune aos usuários finais.

  3. O usuário final deve pertencer a um grupo de segurança destinado a uma política de proteção do aplicativo. A mesma política de proteção do aplicativo deve ter como destino o aplicativo específico utilizado. Políticas de proteção do aplicativo podem ser criadas e implantadas no console do Intune no [portal do Azure](http://portal.azure.com). No momento, grupos de segurança podem ser criados no [portal do Office](http://portal.office.com).

  4. O usuário final deve se conectar ao aplicativo usando sua conta do AAD.

**Quais são os requisitos adicionais para usar o [aplicativo móvel do Outlook](https://www.microsoft.com/outlook-com/mobile/)?**

  1. O usuário final deve ter o aplicativo móvel do Outlook instalado em seu dispositivo.

  2. O usuário final deve ter uma caixa de correio do [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) e uma licença vinculada à sua conta do Azure Active Directory.

  >[!NOTE]
  > No momento, o aplicativo móvel do Outlook dá suporte apenas ao Microsoft Exchange Online e não dá suporte ao Exchange no Local nem ao Exchange no Office 365 Dedicated.

**Quais são os requisitos adicionais para usar os [aplicativos Word, Excel e PowerPoint](https://products.office.com/business/office)?**

  1. O usuário final deve ter uma licença do [Office 365 Business ou Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) vinculada à sua conta do Azure Active Directory. A assinatura deve incluir os aplicativos do Office em dispositivos móveis e uma conta de armazenamento em nuvem com o [OneDrive para Empresas](https://onedrive.live.com/about/business/). As licenças do Office 365 podem ser atribuídas no [portal do Office](http://portal.office.com) seguindo estas [instruções](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

  2. O usuário final deve ter o aplicativo [OneDrive](https://onedrive.live.com/about/) instalado em seu dispositivo e entrar com sua conta do AAD.

  3. O aplicativo OneDrive deve ser destinado à política de proteção do aplicativo implantada no usuário final.

  >[!NOTE]
  > No momento, os aplicativos móveis do Office dão suporte apenas ao SharePoint Online e não ao SharePoint local.

**Por que o OneDrive é necessário para o Office?** O Intune marca todos os dados no aplicativo como “corporativos” ou “pessoais”. Os dados são considerados “corporativos” quando tem como origem um local da empresa. Para os aplicativos do Office, o Intune considera o seguinte como locais da empresa: email (Exchange) ou armazenamento em nuvem (aplicativo OneDrive com uma conta do OneDrive para Empresas).

**Quais são os requisitos adicionais para usar o Skype for Business?** Consulte os requisitos de licença do [Skype for Business](https://products.office.com/skype-for-business/it-pros).
  >[!NOTE]
  > No momento, o aplicativo móvel Skype for Business dá suporte apenas ao Skype for Business Online.

## <a name="app-protection-features"></a>Recursos de proteção do aplicativo

**O que é o suporte a várias identidades?** Suporte a várias identidades é a capacidade do SDK do Aplicativo do Intune de aplicar políticas de proteção do aplicativo apenas à conta corporativa ou de estudante conectada ao aplicativo. Se uma conta pessoal estiver conectada ao aplicativo, os dados permanecerão inalterados.

**Qual é a finalidade do suporte a várias identidades?** O suporte a várias identidades permite que aplicativos com público “corporativo” e de consumidor (ou seja, os aplicativos do Office) sejam liberados publicamente com as funcionalidades de proteção do aplicativo do Intune para as contas “corporativas”.

**Quando a tela do PIN será exibida?** A tela do PIN do Intune é exibida somente quando o usuário tenta acessar dados “corporativos” no aplicativo. Por exemplo, em aplicativos Word/Excel/PowerPoint, ela é exibida quando o usuário final tenta abrir um documento do OneDrive para Empresas (supondo que você implantou com êxito uma política de proteção do aplicativo que impõe um PIN).

**E o Outlook e as várias identidades?** Como o Outlook tem uma exibição de email combinada de emails pessoal e “corporativo”, o aplicativo Outlook solicita o PIN do Intune na inicialização.

**O que é o PIN do aplicativo do Intune?** O PIN (Número de Identificação Pessoal) é uma senha usada para verificar se o usuário correto está acessando os dados da organização em um aplicativo.

  1. **Quando o usuário deverá inserir seu PIN?** O Intune solicitará o PIN do aplicativo do usuário apenas quando o usuário estiver prestes a acessar dados “corporativos”. Em aplicativos de várias identidades, como o Word/Excel/PowerPoint, o usuário é solicitado a inserir seu PIN ao tentar abrir um arquivo ou documento “corporativo”. Em aplicativos de identidade única, como aplicativos de linha de negócios habilitados com a Ferramenta de Disposição do Aplicativo do Intune, o PIN é solicitado na inicialização, pois o SDK do Aplicativo do Intune sabe que a experiência do usuário no aplicativo é sempre “corporativa”.

  2. **O PIN é seguro?** O PIN serve para permitir que somente o usuário correto acesse os dados de sua organização no aplicativo. Portanto, um usuário final deve entrar com sua conta corporativa ou de estudante antes de definir ou redefinir o PIN do aplicativo do Intune. Essa autenticação é manipulada pelo Azure Active Directory por meio da troca de tokens seguros e não é transparente para o SDK do Aplicativo do Intune. Sob a perspectiva de segurança, a melhor maneira de proteger dados corporativos ou de estudante é criptografá-los. A criptografia não está relacionada ao PIN do aplicativo, mas é sua própria política de proteção do aplicativo.

  3. **Como o Intune protege o PIN contra ataques de força bruta?** Como parte da política de PIN do aplicativo, o administrador de TI pode definir o número máximo de vezes que um usuário pode tentar autenticar seu PIN antes do bloqueio do aplicativo. Depois que o número de tentativas for atingido, o SDK do Aplicativo do Intune poderá apagar os dados “corporativos” no aplicativo.

**E a criptografia?** Os administradores de TI podem implantar uma política de proteção do aplicativo que exige a criptografia dos dados do aplicativo. Como parte da política, o administrador de TI também pode especificar quando o conteúdo é criptografado.

  1. **Como o Intune criptografa os dados?** Consulte [Android app protection policy settings (Configurações da política de proteção do aplicativo Android)](../deploy-use/android-mam-policy-settings.md) e [iOS app protection policy settings (Configurações da política de proteção do aplicativo iOS)](../deploy-use/ios-mam-policy-settings.md) para obter informações detalhadas sobre a configuração da política de proteção do aplicativo para criptografia.

  2. **O que é criptografado?** Somente os dados marcados como “corporativos” são criptografados, de acordo com a política de proteção do aplicativo do administrador de TI. Os dados são considerados “corporativos” quando tem como origem um local da empresa. Para os aplicativos do Office, o Intune considera o seguinte como locais da empresa: email (Exchange) ou armazenamento em nuvem (aplicativo OneDrive com uma conta do OneDrive para Empresas). Para aplicativos de linha de negócios habilitados pela Ferramenta de Disposição do Aplicativo do Intune, todos os dados do aplicativo são considerados “corporativos”.

**Como o Intune apaga os dados remotamente?** O Intune pode apagar os dados do aplicativo de três maneiras diferentes: apagamento completo do dispositivo, apagamento seletivo para MDM e apagamento seletivo de MAM. Para saber mais sobre o apagamento remoto para MDM, confira [Ajudar a proteger os dados com apagamento completo ou seletivo usando o Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). Para saber mais sobre o apagamento seletivo usando MAM, confira [Apagar dados gerenciados de aplicativo de empresa com o Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md)

  1. **O que é o apagamento completo?** O [apagamento completo](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) remove todos os dados e configurações do usuário **do dispositivo** restaurando o dispositivo para as configurações padrão de fábrica. O dispositivo é removido do Intune.
  >[!NOTE]
  > O apagamento completo pode ser realizado apenas em dispositivos registrados no Intune MDM (gerenciamento de dispositivo móvel).

  2. **O que é o apagamento seletivo para MDM?** Consulte [Ajudar a proteger os dados com apagamento completo ou seletivo usando o Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) para ler sobre o apagamento seletivo.

  3. **O que é o apagamento seletivo para MAM?** O apagamento seletivo para MAM simplesmente remove dados de aplicativo da empresa de um aplicativo. A solicitação é iniciada usando o portal do Azure no Intune. Para saber como iniciar uma solicitação de apagamento, confira [Apagar dados gerenciados de aplicativo da empresa com o Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md)

  4. **Com que rapidez o apagamento seletivo para MAM ocorre?** Se o usuário estiver usando o aplicativo quando o apagamento seletivo for iniciado, o SDK do Aplicativo do Intune verificará a cada 30 minutos uma solicitação de apagamento seletivo do serviço Intune MAM. Ele também verifica o apagamento seletivo quando o usuário inicia o aplicativo pela primeira vez e se conecta com sua conta corporativa ou de estudante.

**Por que os serviços Locais não funcionam com os aplicativos protegidos do Intune?** A proteção do aplicativo do Intune depende da consistência da identidade do usuário entre o aplicativo e o SDK do Aplicativo do Intune. A única maneira de assegurar isso é por meio da autenticação moderna. Existem cenários nos quais os aplicativos podem funcionar com uma configuração local, mas eles não são consistentes nem têm garantia.

**Existe uma maneira segura de abrir links da Web em aplicativos gerenciados?** Sim. O administrador de TI pode implantar e definir uma política de proteção do aplicativo para o [aplicativo Intune Managed Browser](../deploy-use/manage-internet-access-using-managed-browser-policies.md), um navegador da Web desenvolvido pelo Microsoft Intune que pode ser gerenciado facilmente com o Intune. O administrador de TI pode exigir que todos os links da Web em aplicativos habilitados pelo Intune sejam abertos com o aplicativo Managed Browser.


## <a name="app-experience-on-android"></a>Experiência do aplicativo no Android

**Por que o aplicativo Portal da Empresa é necessário para o funcionamento da proteção do aplicativo do Intune em dispositivos Android?** Grande parte da funcionalidade de proteção do aplicativo é interna ao aplicativo Portal da Empresa. O registro de dispositivo _não é necessário_, embora o aplicativo Portal da Empresa seja sempre obrigatório. Para o MAM-WE, o usuário final precisa apenas ter o aplicativo Portal da Empresa instalado no dispositivo.

## <a name="app-experience-on-ios"></a>Experiência do aplicativo no iOS

**Consigo usar a extensão de compartilhamento do iOS para abrir dados corporativos ou de estudante em aplicativos não gerenciados, mesmo com a política de transferência de dados definida como “apenas aplicativos gerenciados” ou “nenhum aplicativo”. Isso não causa a perda de dados?** A política de proteção do aplicativo do Intune não pode controlar a extensão de compartilhamento do iOS sem gerenciar o dispositivo. Portanto, o _**Intune criptografa os dados “corporativos” antes que eles sejam compartilhados fora do aplicativo**_. É possível validar isso ao tentar abrir o arquivo “corporativo” fora do aplicativo gerenciado. O arquivo deve ser criptografado e não pode ser aberto fora do aplicativo gerenciado.

### <a name="see-also"></a>Consulte também
- [Configurações de política de gerenciamento de aplicativo móvel do Android no Microsoft Intune](../deploy-use/android-mam-policy-settings.md)
- [Configurações de política de gerenciamento de aplicativo móvel iOS](../deploy-use/ios-mam-policy-settings.md)
- [Validar a configuração do gerenciamento de aplicativo móvel](../deploy-use/validate-mobile-application-management.md)
- [Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Como obter suporte para o Microsoft Intune](../troubleshoot/how-to-get-support-for-microsoft-intune.md)

