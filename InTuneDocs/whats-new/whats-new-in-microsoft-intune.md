---
title: Novidades | Microsoft Docs
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1d9ebc7fd727b80091625ed5256ae634323a9257
ms.openlocfilehash: f7e71d20923e113b533668a7b5aef688de196182


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Novidades do Microsoft Intune – dezembro de 2016
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

> [!Note]
> Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Visualização pública da nova experiência de administração do Intune no Azure<!--736542-->
No início de 2017, migraremos nossa experiência de administração completa para o Azure, permitindo um gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico. Antes de disponibilizar o portal para todos os locatários do Intune, estamos felizes em anunciar que começaremos a implantar uma visualização dessa nova experiência de administração no final deste mês para locatários selecionados.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, saiba mais sobre o que estamos preparando para o Microsoft Intune no portal do Azure em [nova documentação](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Em caso de dúvidas sobre a linha do tempo para a migração do locatário, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integração de gerenciamento de despesas de telecomunicações na visualização pública do portal do Azure<!--747605-->
Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

## <a name="new-capabilities"></a>Novos recursos

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Autenticação multifator em todas as plataformas <!--747590-->
Agora você pode impor a autenticação multifator (MFA) em um grupo selecionado de usuários quando registram um dispositivo iOS, Android, Windows 8.1 e posterior ou Windows Phone 8.1 e posterior do Portal de Gerenciamento do Azure, configurando o MFA no aplicativo de Registro do Microsoft Intune no Azure Active Directory.

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>Capacidade de restringir o registro de dispositivos móveis<!--747596-->
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.
* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.
* Apenas para iOS, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Avisos

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>A Autenticação Multifator no Registro movida para o portal do Azure <!--VSO 750545-->
Anteriormente, os administradores iriam para o console do Intune ou para o console do Configuration Manager (anterior à versão de outubro de 2016) a fim de definir o MFA para os registros do Intune. Com esse recurso atualizado, você fará o logon no [portal do Microsoft Azure](https://manage.windowsazure.com) usando suas credenciais do Intune e configurará o MFA por meio do Azure AD. Saiba mais sobre isso [aqui](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china--vso-658093--"></a>O aplicativo do Portal da Empresa para Android já disponível na China <!--VSO 658093-->
Estamos publicando o aplicativo do Portal da Empresa para Android para download na China. Devido à ausência da Google Play Store na China, os dispositivos Android devem obter aplicativos dos mercados de aplicativo chineses. O aplicativo do Portal da Empresa para Android estará disponível para download nas seguintes lojas:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

O aplicativo do Portal da Empresa para Android usa o Google Play Services para se comunicar com o serviço do Microsoft Intune. Como o Google Play Services ainda não está disponível na China, a execução de qualquer uma das seguintes tarefas pode levar até 8 horas para ser concluída. 

|Console de Administração do Intune| Aplicativo do Portal da Empresa do Intune para Android |Site do Portal da Empresa do Intune|   
|---|---|---|
|Apagamento completo| Remover um dispositivo remoto| Remover dispositivo (local e remoto)|
|Apagamento seletivo| Redefinir dispositivo| Redefinir dispositivo|
|Implantações de aplicativo novas ou atualizadas| Instalar os aplicativos de linha de negócios disponíveis| Redefinição de senha do dispositivo|
|Bloqueio remoto|||
|Redefinição de senha|||

## <a name="deprecations"></a>Desativações

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>Não há mais suporte para o Silverlight no Firefox<!--VSO TBA-->
O Mozilla não oferecerá suporte para o Silverlight na versão 52 do [navegador Firefox](https://www.mozilla.org/firefox) a partir de março de 2017. Como consequência, não será possível fazer logon no console existente do Intune usando as versões posteriores a 51. É recomendável usar o Internet Explorer 10 ou 11 para acessar o console de administração ou uma [versão do Firefox anterior à versão 52](https://ftp.mozilla.org/pub/firefox/releases/). A transição do Intune para o portal do Azure permitirá oferecer suporte a vários [navegadores modernos](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices), sem depender do Silverlight.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Remoção de políticas de caixa de entrada móvel do Exchange Online <!--770687-->
Começando em dezembro, os administradores não poderão exibir ou configurar as políticas de caixa de correio móvel do Exchange Online (EAS) dentro do console do Intune. Essa alteração será revertida para todos os locatários do Intune em dezembro e janeiro. Todas as políticas existentes permanecerão conforme configurado. Para configurar novas políticas, use o Shell de Gerenciamento do Exchange. Mais informações estão disponíveis [aqui](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Os aplicativos Intune AV Player, o Visualizador de Imagens e Visualizador de PDF não têm mais suporte no Android <!--747553-->
A partir de meados de dezembro de 2016, os usuários não poderão usar os aplicativos Intune AV Player, Visualizador de Imagens e Visualizador de PDF. Esses aplicativos foram substituídos com o aplicativo de Proteção de Informações do Azure. Saiba mais sobre o aplicativo de Proteção de Informações do Azure [aqui](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Arquivo de novidades](whats-new-archive.md)



<!--HONumber=Dec16_HO4-->


