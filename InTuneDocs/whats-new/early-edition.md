---
title: "A Edição Antecipada | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6dd584397451d38be86fa0780efff435ffb9b2af
ms.openlocfilehash: d70ebf87bc930f853741ddc0d572d2174c636dac


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>A Edição Antecipada do Microsoft Intune – Dezembro

A **Edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) (Novidades do Híbrido).

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Visualização pública da nova experiência de administração do Intune no Azure

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se você quiser testar ou examinar qualquer uma das novas funcionalidades até que seu locatário seja migrado, inscreva-se para uma nova conta de avaliação do Intune ou dê uma olhada na nova documentação.

Em caso de dúvidas sobre a linha do tempo para a migração do locatário, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integração de gerenciamento de despesas de telecomunicações na visualização pública do portal do Azure<!--747605-->
Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Novos recursos

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Autenticação multifator em todas as plataformas <!--747590-->
Agora você pode impor a autenticação multifator (MFA) em um grupo selecionado de usuários quando registram um dispositivo iOS, Android, Windows 8.1 e posterior ou Windows Phone 8.1 e posterior do Portal de Gerenciamento do Azure, configurando o MFA no aplicativo de Registro do Microsoft Intune no Azure Active Directory.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>Configurar o acesso condicional para o MAM com o SharePoint Online <!--VSO 679339-->
Você pode impedir que os aplicativos sem suporte das políticas de gerenciamento do aplicativo móvel do Intune (MAM) acessem o SharePoint Online.  Você pode começar usando o gerenciamento de aplicativo móvel do Intune no portal do Azure. Procure a seção __Acesso Condicional__ na folha __Configurações__ que inclui a opção para o SharePoint Online. Este recurso será enviado separadamente do restante da versão de serviço.

### <a name="ability-to-restrict-intune-mobile-device-enrollment"></a>Capacidade de restringir o registro de dispositivos móveis do Intune
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile. 
* O macOS e o Windows 8.1 ou superior podem ter os registros impedidos como plataformas de dispositivos móveis. 
* Restringir o registro do dispositivo móvel não restringe o registro de agente do computador. 
* Apenas para iOS, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal. O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Avisos

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>A Autenticação Multifator no Registro movida para o portal do Azure <!--VSO 750545-->
Anteriormente, os administradores iriam para o console do Intune ou para o console do Configuration Manager (anterior à versão 1610) para definir o MFA para os registros do Intune. Com esse recurso atualizado, você fará o logon no [portal do Microsoft Azure](https://manage.windowsazure.com) usando suas credenciais do Intune e configurará o MFA por meio do Azure AD. Saiba mais sobre isso [aqui](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>O aplicativo do Portal da Empresa para Android já disponível na China <!--VSO 658093-->
Estamos publicando o aplicativo do Portal da Empresa para Android para download na China. Devido à ausência da Google Play Store na China, os dispositivos Android devem obter aplicativos dos mercados de aplicativo chineses. O aplicativo do Portal da Empresa para Android estará disponível para download em 360, Tencent, Xiaomi, Wandoujia e Huawei. 

O aplicativo do Portal da Empresa para Android usa o Google Play Services para se comunicar com o serviço do Microsoft Intune. Como o Google Play Services ainda não está disponível na China, a execução de qualquer uma das seguintes tarefas pode levar até 8 horas para ser concluída. 

|Console de Administração do Intune| Aplicativo do Portal da Empresa do Intune para Android |Site do Portal da Empresa do Intune|   
|---|---|---|
|Apagamento completo| Remover um dispositivo remoto| Remover dispositivo (local e remoto)|
|Apagamento seletivo| Redefinir dispositivo| Redefinir dispositivo|
|Implantações de aplicativo novas ou atualizadas| Instalar os aplicativos de linha de negócios disponíveis| Redefinição de senha do dispositivo|
|Bloqueio remoto|||
|Redefinição de senha|||

## <a name="deprecations"></a>Desativações

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Remoção de políticas de caixa de entrada móvel do Exchange Online <!--770687-->
Começando em dezembro, os administradores não poderão exibir ou configurar as políticas de caixa de correio móvel do Exchange Online (EAS) dentro do console do Intune. Essa alteração será revertida para todos os locatários do Intune em dezembro e janeiro. Todas as políticas existentes permanecerão conforme configurado. Para configurar novas políticas, use o Shell de Gerenciamento do Exchange. Mais informações estão disponíveis [aqui](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Os aplicativos Intune AV Player, o Visualizador de Imagens e Visualizador de PDF não têm mais suporte no Android <!--747553-->
A partir de meados de dezembro de 2016, os usuários não poderão usar os aplicativos Intune AV Player, Visualizador de Imagens e Visualizador de PDF. Esses aplicativos foram substituídos com o aplicativo de Proteção de Informações do Azure. Saiba mais sobre o aplicativo de Proteção de Informações do Azure [aqui](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.



<!--HONumber=Nov16_HO5-->


