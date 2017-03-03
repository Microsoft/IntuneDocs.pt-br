---
title: "Edição antecipada | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/13/2017
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
ms.sourcegitcommit: d0b3a883bb307fb06cb8d16500798086f328314a
ms.openlocfilehash: eeebf8b6b3bc5c7c35386eb20c96097af1f6769c
ms.lasthandoff: 02/14/2017


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>A edição antecipada do Microsoft Intune – Fevereiro de 2017

A **Edição antecipada** fornece uma lista de recursos que estarão disponíveis em versões futuras do Microsoft Intune. Estas informações são fornecidas sob NDA (acordo de confidencialidade) de forma extremamente limitada e estão sujeitas a alterações. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Entre em contato com seu colega do Intune/PM caso tenha perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

> [!Note]
> As seguintes alterações estão em desenvolvimento para o Intune. Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernizando o site Portal da Empresa <!--753980-->
A partir de fevereiro, o design do site do Portal da Empresa será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu de hambúrguer", ![pequena imagem do menu de hambúrguer que foi adicionada na parte superior esquerda do site do Portal da Empresa](./media/CP_hamburger_menu.png) que contém detalhes de contato do suporte técnico e informações sobre dispositivos gerenciados existentes. A página de aterrissagem será reorganizada para enfatizar os aplicativos que estão disponíveis aos usuários, com carrosséis para aplicativos em destaque e atualizados recentemente. Você pode localizar imagens de antes e depois disponíveis na [página de atualizações da interface do usuário](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nova experiência orientada para o Portal da Empresa do Windows 10 <!--713927-->
A partir de março, o Portal da Empresa para o Windows 10 incluirá uma experiência passo a passo interativa do Intune para dispositivos que não foram identificados ou registrados. A nova experiência fornece instruções passo a passo personalizadas para o build do Windows 10 do usuário, que guia os usuários pela execução do registro AAD (necessário para a identificação de recursos de Acesso Condicional) e o registro de MDM (necessário para recursos de gerenciamento de dispositivo). A experiência interativa poderá ser acessada na home page do Portal da Empresa e é opcional. Os usuários poderão continuar a usar o aplicativo mesmo se não concluírem o registro, porém podem ter funcionalidades limitadas.

###

## <a name="notices"></a>Avisos

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>A migração de grupo não exigirá nenhuma atualização para grupos ou políticas para dispositivos iOS <!--898837-->
Durante a migração para grupos de dispositivos do Azure Active Directory, para cada grupo de dispositivos do Intune previamente atribuído por um perfil de Registro de Dispositivo Corporativo, um grupo de dispositivos dinâmico correspondente será criado no AAD com base no nome desse perfil. Isso garantirá que, conforme ocorrer o registro dos dispositivos, eles serão automaticamente agrupados e receberão as mesmas políticas e aplicativos que o grupo do Intune original.

Depois que um locatário entrar no processo de migração para agrupamento e direcionamento, o Intune criará automaticamente um grupo dinâmico do AAD para corresponder a um grupo do Intune direcionado por um perfil de Registro de Dispositivo Corporativo. Se o administrador do Intune excluir o grupo do Intune direcionado, o grupo AAD dinâmico correspondente não será excluído. Os membros do grupo e a consulta dinâmica serão apagados, mas o grupo permanecerá até que o administrador de TI remova-o por meio do portal do AAD.

Da mesma forma, se o administrador de TI alterar qual grupo Intune é afetado por um perfil de Registro de Dispositivo Corporativo, o Intune criará um novo grupo dinâmico refletindo a nova atribuição de perfil, mas não removerá o grupo dinâmico criado para a atribuição antiga.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Novo endereço de servidor MDM para dispositivos Windows <!--893007-->
Uma tentativa registrar um dispositivo por usuários do Windows e Windows Phone falhará se eles inserirem __manage.microsoft.com__ como o endereço do servidor MDM (se solicitado). O endereço do servidor MDM está mudando de __manage.microsoft.com__ para __enrollment.manage.microsoft.com__. Notifique seu usuário para usar __enrollment.manage.microsoft.com__ como o endereço do servidor MDM se solicitado durante o registro de um dispositivo Windows ou Windows Phone. Essa atualização exigirá que qualquer CNAME no DNS que redirecione o __EnterpriseEnrollment.contoso.com__ para __manage.microsoft.com__ seja substituído por um CNAME no DNS que redirecione __EnterpriseEnrollment.contoso.com__ para __EnterpriseEnrollment-s.manage.microsoft.com__. Para obter informações adicionais sobre essa alteração, visite [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622-->
A partir de março, o aplicativo de Portal da empresa para Android seguirá [as diretrizes de design de material](https://material.io/guidelines/material-design/introduction.html) para criar uma aparência mais moderna. Essa experiência do usuário aprimorada inclui:

* __Cores__: cabeçalhos de guia podem ser coloridos de acordo com sua paleta de cores personalizada.
* __Interface__: os botões Aplicativos em Destaque e Todos os Aplicativos foram atualizados na guia Aplicativos. O botão Pesquisa agora é um botão de ação flutuante.
* __Navegação__: Todos os Aplicativos mostra uma exibição com guias de Em Destaque, Todos e Categorias para facilitar a navegação.
* __Serviço__: as guias Meus Dispositivos e Contatar TI têm legibilidade aprimorada.

Você pode localizar imagens de antes e depois na [página de atualizações da interface do usuário](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Associar várias ferramentas de gerenciamento da Windows Store para Empresas <!--926135-->
Se você está usando mais de uma ferramenta de gerenciamento para implantar aplicativos da Windows Store para Empresas, anteriormente, você podia associar apenas um deles à Windows Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento com a loja, por exemplo, o Intune e o Configuration Manager. Para ver mais detalhes, consulte [Gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Visualização pública da nova experiência do administrador do Intune no Azure <!--736542-->

No início de 2017, vamos migrar nossa experiência de administração completa para o Azure, permitindo gerenciamento poderoso e integrado dos principais fluxos de trabalho do EMS em uma plataforma de serviços moderna que é extensível ao usar APIs de Gráfico.

Novos locatários de avaliação começarão a ver a visualização pública da nova experiência de administração no portal do Azure neste mês. Enquanto estiver no estado de visualização, os recursos e o paritário com o console do Intune existente serão entregues interativamente.

A experiência de administração no portal do Azure usará o novo agrupamento já anunciado e a funcionalidade de destino. Quando seu locatário existente for migrado para a nova experiência de agrupamento, você também será migrado para visualizar a nova experiência de administração no seu locatário. Enquanto isso, se desejar testar ou examinar uma das novas funcionalidades até a migração do locatário, inscreva-se para uma nova conta de avaliação do Intune ou confira a [nova documentação](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Em caso de dúvidas sobre a linha do tempo para a migração do locatário, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="february-2017"></a>Fevereiro de 2017

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782-->
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.

* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.  
* Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

#### <a name="view-all-actions-on-managed-devices---677150--"></a>Exibir todas as ações em dispositivos gerenciados <!--677150-->
Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->
Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

#### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](/intune-azure/manage-apps/add-apps).

#### <a name="display-device-categories---814654--"></a>Exibir categorias de dispositivos <!--814654-->
Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos. Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo.

### <a name="january-2017"></a>Janeiro de 2017

#### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Atribuir aplicativos de linha de negócios independentemente de os dispositivos estarem registrados ou não <!--748803-->
Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo dos usuários não estiver registrado no Intune, eles deverão acessar o site do Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### <a name="december-2016"></a>Dezembro de 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integração de gerenciamento de despesas de telecomunicações na visualização pública do portal do Azure<!--747605-->
Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new-in-microsoft-intune.md) para saber detalhes sobre os desenvolvimentos mais recentes.

