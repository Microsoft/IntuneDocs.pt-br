---
title: "Novidades na versão prévia do Microsoft Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Descubra as novidades da visualização do Intune Azure"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9852fdb9d1bfeede4931f0ead2fa0898dfcacb0b
ms.openlocfilehash: a05c7464b3f2fbca467d44218904671529320dda
ms.lasthandoff: 02/15/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Novidades da versão prévia do Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Conforme o andamento da versão prévia pública e à medida que mais recursos forem adicionados, nós os apresentaremos aqui.

## <a name="february-2017"></a>Fevereiro de 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782-->
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.

* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.  
* Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Exibir todas as ações em dispositivos gerenciados <!--677150-->
Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações. Consulte [O que é o gerenciamento de dispositivos?](https://docs.microsoft.com/intune-azure/manage-devices/what-is).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->
Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Exibir categorias de dispositivos <!--814654-->
Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos. Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo. Consulte [como adicionar um aplicativo ao Intune](/intune-azure/manage-apps/add-apps). 

## <a name="january-2017"></a>Janeiro de 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Atribuir aplicativos de linha de negócios independentemente de os dispositivos estarem registrados ou não <!--748823-->
Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo dos usuários não estiver registrado no Intune, eles deverão acessar o site do Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa. Consulte [O que é o gerenciamento de aplicativo](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Resolva o problema em que os dispositivos iOS estão inativos ou o console de administração não pode se comunicar com eles
Quando os dispositivos dos usuários perdem contato com o Intune, você pode fornecer novas etapas de solução de problemas para ajudá-los a recuperar o acesso aos recursos da empresa. Consulte [Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Dezembro de 2016 (versão inicial)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integração de gerenciamento de despesas de telecomunicações na visualização pública do portal do Azure<!--747605-->
Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Implantar e gerenciar aplicativos de um repositório para dispositivos iOS, Android e Windows
- Implantar e gerenciar aplicativos LOB (linha de negócios) para dispositivos iOS, Android e Windows
- Implantar e gerenciar aplicativos adquiridos de volume para dispositivos iOS e Windows
- Implantar e gerenciar aplicativos Web para dispositivos Android, iOS e Windows
- Perfis de configuração do aplicativo gerenciado por iOS
- Configurar políticas de proteção de aplicativo e implantar aplicativos de linha de negócios em dispositivos que não são registrados com o Intune
- Perfis VPN, VPN por aplicativo, Wi-Fi, email e perfis de certificado
- Políticas de conformidade
- Acesso condicional para Azure AD
- Acesso condicional para Exchange Local
- Registro de dispositivo
- Controle de acesso baseado em função

## <a name="deprecated-features-in-the-azure-portal"></a>Recursos preteridos no Portal do Azure

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Suporte para examinar de linha por linha dos identificadores de hardware
O Portal do Azure não dá suporte à analise de linha por linha de identificadores de hardware para números IMEI e números de série da Apple. No console do Intune clássico, você pode importar detalhes de um arquivo valores separados por vírgulas (.csv) e substituir os detalhes existentes pelos identificadores de hardware individuais. O Portal do Azure apresenta uma única opção simplificada que automaticamente substitui detalhes para todos os identificadores de hardware ou ignora detalhes novos para identificadores existentes.

#### <a name="how-this-affects-you"></a>Como isso afeta você
No Portal do Azure, você não poderá decidir, linha por linha, os dispositivos de identidade de equipamentos de móveis internacional (IMEI) para atualizar. O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.

#### <a name="how-to-get-ready-for-this-change"></a>Como se preparar para essa alteração
Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração. Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Suporte para o padrão perfis de registro de dispositivo corporativo em Apple DEP
O Portal do Azure não dá suporte para o perfil de registro de dispositivo corporativo "padrão" para números de série do dispositivo do DEP (Programa de registro de dispositivos) da Apple. Essa funcionalidade, disponível no console do Intune clássico, está sendo descontinuada para impedir que os perfis atribuídos acidentalmente. No Portal do Azure, os números de série sincronizados com base em uma conta de DEP da Apple inicialmente não terá nenhum perfil de registro de dispositivo corporativo atribuído.

#### <a name="how-this-affects-you"></a>Como isso afeta você
No Portal do Azure, você não poderá definir uma política de perfil padrão em todos os dispositivos da Apple. O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.

#### <a name="how-to-get-ready-for-this-change"></a>Como se preparar para essa alteração
Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração. Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.

