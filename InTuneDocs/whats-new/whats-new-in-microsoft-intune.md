---
title: Novidades | Microsoft Docs
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: 2a602b351cf7f345bd56f20394943ea25f2d2060
ms.lasthandoff: 03/15/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>O que há de novo no Microsoft Intune - março de 2017
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

> [!Note]
> Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622-->

O aplicativo Portal da Empresa para Android atualizará sua interface do usuário para uma aparência mais moderna e melhor experiência do usuário. As atualizações importantes são:

- Cores: os cabeçalhos de guia do Portal da Empresa são coloridos com a identidade visual definida para TI.
- Aplicativos: na guia **Apps**, os botões **Aplicativos em Destaque** e **Todos os Aplicativos** foram atualizados.
- Pesquisa: na guia **Apps**, o botão **Pesquisar** é um botão de ação flutuante.
- Aplicativos de navegação: a exibição **Todos os Aplicativos** mostra uma exibição com guias de **Em Destaque**, **Todos** e **Categorias** para facilitar a navegação.
- Suporte: as guias **Meus Dispositivos** e **Contato de TI** foram atualizadas para melhorar a legibilidade.

Para obter mais detalhes sobre essas alterações, consulte [Atualizações da IU para aplicativos do usuário final do Intune](whats-new-in-intune-app-ui.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->

Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Assinatura do Script para o Portal da Empresa do Windows 10<!--941642-->

Se você precisar baixar e carregar o aplicativo Portal da Empresa do Windows 10, agora poderá usar um script para simplificar e facilitar o processo de autenticação do aplicativo para sua organização.   Para baixar o script e as instruções de uso, confira [Script de assinatura do Microsoft Intune](https://aka.ms/win10cpscript) do Portal da Empresa do Windows 10 na Galeria do TechNet. Para obter mais detalhes sobre este lançamento, confira [Atualizar seu aplicativo do Portal da Empresa do Windows 10](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) no Blog da Equipe de Suporte do Intune.


## <a name="notices"></a>Avisos

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Suporte aprimorado para os usuários do Android com base na China <!--720444-->

Devido à ausência da Google Play Store na China, os dispositivos Android devem obter aplicativos dos mercados chineses. O Portal da Empresa oferecerá suporte a este fluxo de trabalho redirecionando os usuários do Android na China para baixarem os aplicativos Portal da Empresa e Outlook das lojas de aplicativos locais. Isso melhora a experiência do usuário quando as políticas de acesso condicional estão habilitadas para Gerenciamento do Dispositivo Móvel e Gerenciamento de Aplicativos Móveis. Os aplicativos Portal da Empresa e Outlook para Android estão disponíveis nas seguintes lojas de aplicativos chinesas:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Prática recomendada: verificar se seus aplicativos Portal da Empresa estão atualizados<!--879465-->

Em dezembro de 2016, lançamos uma atualização que habilitou a imposição da autenticação multifator (MFA) em um grupo de usuários quando eles registram um dispositivo iOS, Android, Windows 8.1+ ou Windows Phone 8.1+. Este recurso não pode funcionar sem determinadas versões da linha de base do aplicativo Portal da Empresa para o Android (v5.0.3419.0+) e o iOS (v2.1.17+).

A Microsoft está aperfeiçoando continuamente o Intune adicionando novas funções ao console e aos aplicativos Portal da Empresa em todas as plataformas com suporte. Como resultado, a Microsoft lança apenas correções para os problemas encontrados na versão atual do aplicativo Portal da Empresa. Portanto, recomendamos usar as versões mais recentes dos aplicativos Portal da Empresa para ter a melhor experiência de usuário.

>[!Tip]
> Faça com que os usuários definam seus dispositivos para atualizarem automaticamente os aplicativos na loja de aplicativos apropriada. Se você disponibilizou o aplicativo Portal da Empresa Android em um compartilhamento de rede, poderá baixar a versão mais recente no [Centro de Download da Microsoft](https://www.microsoft.com/download/details.aspx?id=49140).

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Agora, o Microsoft Teams está habilitado para o MAM no iOS e Android

A Microsoft anunciou a disponibilidade geral do Microsoft Teams. Os aplicativos Microsoft Teams atualizados para o iOS e Android agora são habilitados com os recursos MAM (gerenciamento do aplicativo móvel) do Intune, portanto, você pode capacitar as equipes a trabalharem livremente entre os dispositivos, garantindo que as conversas e os dados corporativos estejam protegidos o tempo todo. Para obter mais detalhes, consulte [o lançamento do Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) no blog de Mobilidade e Segurança da Empresa.


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Novidades na visualização pública da experiência de administração do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](https://docs.microsoft.com/intune-azure/introduction/whats-new).

> [!Note]
> Para a visualização do portal do Azure, estamos implantando atualizações este mês. No entanto, as alterações podem não estar disponíveis imediatamente devido a como o serviço do Intune é distribuído.  Vários componentes do serviço devem ser atualizados em sequência antes dos novos recursos do portal ficarem disponíveis. Procure alterações na visualização do portal do Azure na distribuição posterior deste mês. Para obter uma lista completa de alterações, consulte [O que há de novo na visualização do Microsoft Intune](/intune-azure/introduction/whats-new).

## <a name="whats-coming"></a>O que está por vir

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->

A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na visualização do Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Novidades na interface do usuário do Portal da Empresa](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Arquivo de novidades](whats-new-archive.md)

