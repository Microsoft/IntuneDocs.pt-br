---
title: "Edição antecipada | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: 3b355d43d4be05535f256d88a8648c2e67035882
ms.lasthandoff: 03/13/2017


---


# <a name="the-early-edition-for-microsoft-intune---march-2017"></a>A Edição Antecipada do Microsoft Intune – março de 2017

A **Edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
> As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622-->

O aplicativo Portal da Empresa para Android atualizará sua interface do usuário para uma aparência mais moderna e melhor experiência do usuário. As atualizações importantes são:

- Cores: os cabeçalhos de guia do Portal da Empresa são coloridos com a identidade visual definida para TI.
- Aplicativos: na guia **Apps**, os botões **Aplicativos em Destaque** e **Todos os Aplicativos** foram atualizados.
- Pesquisa: na guia **Apps**, o botão **Pesquisar** é um botão de ação flutuante.
- Aplicativos de navegação: a exibição **Todos os Aplicativos** mostra uma exibição com guias de **Em Destaque**, **Todos** e **Categorias** para facilitar a navegação.
- Suporte: as guias **Meus Dispositivos** e **Contato de TI** foram atualizadas para melhorar a legibilidade.

Mais detalhes sobre essas alterações podem ser encontrados na [página de atualizações do aplicativo da interface do usuário](whats-new-in-intune-app-ui.md].

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Assinatura do Script para o Portal da Empresa do Windows 10<!--941642-->

Para clientes que precisam baixar e carregar o aplicativo de Portal da Empresa do Windows 10, agora você pode usar um script para simplificar e facilitar o processo de autenticação de aplicativo para sua organização.   Para baixar o script e as instruções de uso, confira [Script de assinatura do Microsoft Intune](https://aka.ms/win10cpscript) do Portal da Empresa do Windows 10 na Galeria do TechNet. Para obter mais detalhes sobre este lançamento, confira [Atualizar seu aplicativo do Portal da Empresa do Windows 10](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) no Blog da Equipe de Suporte do Intune. 

## <a name="notices"></a>Avisos

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Suporte aprimorado para os usuários do Android com base na China <!--720444-->

Devido à ausência da Google Play Store na China, os dispositivos Android devem obter aplicativos dos mercados chineses. O Portal da Empresa oferecerá suporte a este fluxo de trabalho redirecionando os usuários do Android na China para baixarem os aplicativos Portal da Empresa e Outlook das lojas de aplicativos locais. Isso melhora a experiência do usuário quando as políticas de acesso condicional estão habilitadas para Gerenciamento do Dispositivo Móvel e Gerenciamento de Aplicativos Móveis. Os aplicativos Portal da Empresa e Outlook para Android estão disponíveis nas seguintes lojas de aplicativos chinesas:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->

A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Visualização pública da nova experiência do administrador do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->

Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### <a name="improvements-to-device-actions-report---677150--"></a>Aprimoramentos para o relatório de Ações de Dispositivo <!--677150-->

Fizemos aprimoramentos no relatório de Ações de Dispositivo para melhorar o desempenho. Além disso, agora você pode filtrar o relatório por estado. Por exemplo, você pode filtrar o relatório para mostrar somente as ações do dispositivo que foram concluídas.

### <a name="actions-for-non-compliance---730266--"></a>Medidas para não conformidade <!--730266-->

**Ações de não conformidade** é um novo recurso das políticas de conformidade que permite tomar medidas em relação a dispositivos que estão fora de conformidade. É possível especificar uma ou várias ações e especificar o período em que essas ações devem ocorrer. Por exemplo, é possível notificar por email os usuários de dispositivos que não estão em conformidade imediatamente depois que os dispositivos passarem para esse estado ou impedir que os dispositivos que não estão em conformidade acessem recursos corporativos após um período de cortesia de três dias por meio do Acesso Condicional.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->

Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Atribuir aplicativos LOB para usuários com dispositivos não registrados <!--748823-->

Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo do usuário não estiver registrado no Intune, ele deverá ir para o site Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### <a name="new-compliance-reports---846671--"></a>Novos relatórios de conformidade <!--846671-->

Agora você tem relatórios de conformidade que dão a postura de conformidade de dispositivos na sua empresa e permitem que você solucione rapidamente problemas relacionados à conformidade encontrados pelos usuários. Você pode exibir informações sobre

- Estado de conformidade geral de dispositivos
- Estado de conformidade para uma configuração individual
- Estado de conformidade para uma política individual

Você também pode usar esses relatórios para uma busca detalhada em um dispositivo individual para exibir as configurações específicas e as diretivas que afetam esse dispositivo.

### <a name="additional-windows-10-upgrade-paths---903672--"></a>Caminhos de atualização adicionais do Windows 10 <!--903672-->

Agora você pode criar uma política de atualização de edição para atualizar os dispositivos para as seguintes edições adicionais do Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->

Para contas do Intune criadas depois de janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho de registrar dispositivos na Versão Prévia do Portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.

