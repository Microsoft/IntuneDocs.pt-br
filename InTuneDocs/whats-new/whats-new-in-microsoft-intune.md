---
title: Novidades | Microsoft Docs
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a9336e3d230de962d2623dd627e45c6e9262a822
ms.openlocfilehash: cfe4a0bb802956278387ac2a39d5316482e09332
ms.lasthandoff: 03/02/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Novidades do Microsoft Intune – fevereiro de 2017
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

> [!Note]
> Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizando o site Portal da Empresa <!--753980-->
O site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados. O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu de hambúrguer", ![Pequena imagem do menu de hambúrguer que é agora adicionada ao canto superior esquerdo do site Portal da Empresa](./media/CP_hamburger_menu.png) e que conterá detalhes de contato de suporte técnico e informações sobre os dispositivos gerenciados existentes. A página de aterrissagem será reorganizada para enfatizar os aplicativos que estão disponíveis aos usuários, com carrosséis para aplicativos em destaque e atualizados recentemente. Você pode localizar imagens de antes e depois disponíveis na [página de atualizações da interface do usuário](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nova experiência orientada para o Portal da Empresa do Windows 10 <!--713927-->
A partir de março, o Portal da Empresa para o Windows 10 incluirá uma experiência passo a passo interativa do Intune para dispositivos que não foram identificados ou registrados. A nova experiência fornece instruções passo a passo personalizadas para o build do Windows 10 do usuário, que guia os usuários pela execução do registro AAD (necessário para a identificação de recursos de Acesso Condicional) e o registro de MDM (necessário para recursos de gerenciamento de dispositivo). A experiência interativa poderá ser acessada na home page do Portal da Empresa e é opcional. Os usuários poderão continuar a usar o aplicativo mesmo se não concluírem o registro, porém podem ter funcionalidades limitadas.

## <a name="notices"></a>Avisos

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>A migração de grupo não exigirá nenhuma atualização para grupos ou políticas para dispositivos iOS <!--898837-->
Durante a migração para grupos de dispositivos do Azure Active Directory, para cada grupo de dispositivos do Intune previamente atribuído por um perfil de Registro de Dispositivo Corporativo, um grupo de dispositivos dinâmico correspondente será criado no AAD com base no nome desse perfil. Isso garantirá que, conforme ocorrer o registro dos dispositivos, eles serão automaticamente agrupados e receberão as mesmas políticas e aplicativos que o grupo do Intune original.

Depois que um locatário entrar no processo de migração para agrupamento e direcionamento, o Intune criará automaticamente um grupo dinâmico do AAD para corresponder a um grupo do Intune direcionado por um perfil de Registro de Dispositivo Corporativo. Se o administrador do Intune excluir o grupo do Intune direcionado, o grupo AAD dinâmico correspondente não será excluído. Os membros do grupo e a consulta dinâmica serão apagados, mas o grupo permanecerá até que o administrador de TI remova-o por meio do portal do AAD.

Da mesma forma, se o administrador de TI alterar qual grupo Intune é afetado por um perfil de Registro de Dispositivo Corporativo, o Intune criará um novo grupo dinâmico refletindo a nova atribuição de perfil, mas não removerá o grupo dinâmico criado para a atribuição antiga.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Usar como padrão o gerenciamento de dispositivos da área de trabalho do Windows por meio das configurações do Windows <!--663050-->
O comportamento padrão para o registro de áreas de trabalho do Windows 10 está mudando. Os novos registros seguirão o fluxo típico de registro do agente de MDM em vez de ocorrer por meio do agente do computador. O site do Portal da Empresa fornecerá aos usuários da área de trabalho do Windows 10 instruções de registro que vão orientá-los pelo processo de adição de computadores desktop do Windows 10 como dispositivos móveis. Isso não afetará os computadores atualmente registrados e sua organização ainda poderá gerenciar áreas de trabalho do Windows 10 usando o agente do computador [se você preferir](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Melhorando o suporte de gerenciamento de aplicativo móvel para o apagamento seletivo <!--581242-->
Os usuários finais receberão outras diretrizes sobre como recuperar o acesso a dados corporativos ou de estudante se esses dados forem removidos automaticamente devido à política “Intervalo offline antes do apagamento dos dados de aplicativo”.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Portal da Empresa para links do iOS abertos no aplicativo <!--665954-->
Os links dentro do aplicativo Portal da Empresa para iOS, incluindo os links para a documentação e os aplicativos, serão abertos diretamente no aplicativo Portal da Empresa usando uma exibição no aplicativo do Safari. Essa atualização será fornecida separadamente da atualização de serviço em janeiro.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Novo endereço de servidor MDM para dispositivos Windows <!--893007-->
Uma tentativa registrar um dispositivo por usuários do Windows e Windows Phone falhará se eles inserirem __manage.microsoft.com__ como o endereço do servidor MDM (se solicitado). O endereço do servidor MDM está mudando de __manage.microsoft.com__ para __enrollment.manage.microsoft.com__. Notifique seu usuário para usar __enrollment.manage.microsoft.com__ como o endereço do servidor MDM se solicitado durante o registro de um dispositivo Windows ou Windows Phone. Não é necessária nenhuma alteração em sua configuração CNAME. Para obter informações adicionais sobre essa alteração, visite [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622-->
A partir de março, o aplicativo de Portal da empresa para Android seguirá [as diretrizes de design de material](https://material.io/guidelines/material-design/introduction.html) para criar uma aparência mais moderna. Essa experiência do usuário aprimorada inclui:

* __Cores__: cabeçalhos de guia podem ser coloridos de acordo com sua paleta de cores personalizada.
* __Interface__: os botões Aplicativos em Destaque e Todos os Aplicativos foram atualizados na guia Aplicativos. O botão Pesquisa agora é um botão de ação flutuante.
* __Navegação__: Todos os Aplicativos mostra uma exibição com guias de Em Destaque, Todos e Categorias para facilitar a navegação.
* __Serviço__: as guias Meus Dispositivos e Contatar TI têm legibilidade aprimorada.

Você pode localizar imagens de antes e depois na [página de atualizações da interface do usuário](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Associar várias ferramentas de gerenciamento da Windows Store para Empresas <!--926135-->
Se você está usando mais de uma ferramenta de gerenciamento para implantar aplicativos da Windows Store para Empresas, anteriormente, você podia associar apenas um deles à Windows Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento com a loja, por exemplo, o Intune e o Configuration Manager. Para ver mais detalhes, consulte [Gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Novidades na visualização pública da experiência de administração do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](https://docs.microsoft.com/intune-azure/introduction/whats-new).

Em caso de dúvidas sobre a linha do tempo para a migração do locatário, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Você pode encontrar as novidades na visualização do Intune no Azure [aqui](https://docs.microsoft.com/intune-azure/introduction/whats-new).

## <a name="whats-coming"></a>O que está por vir

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->

A partir do primeiro semestre de 2017, a Apple anunciou que imporá requisitos específicos para Segurança de Transporte de Aplicativo (ATS). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes. 

### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na visualização do Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Novidades na interface do usuário do Portal da Empresa](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Arquivo de novidades](whats-new-archive.md)

