---
title: Para onde foi o meu recurso Intune no Azure?
titleSuffix: Microsoft Intune
description: Ajuda a encontrar recursos do Microsoft Intune no Portal do Azure.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 1/4/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f74ed8586bcfca21ea7434ec1c6ad045c8bc1bbd
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71735552"
---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Para onde foi o meu recurso Intune no Azure?
Aproveitamos a oportunidade para organizar algumas tarefas mais logicamente à medida que mudamos o Intune para o portal do Azure. Mas cada aperfeiçoamento vem com o custo de aprender a nova organização. Este guia de referência destina-se àqueles que estão totalmente familiarizados com o Intune no portal clássico e querem saber como fazer algo no Intune por meio do portal do Azure. Se este artigo não abordar um recurso que você está tentando localizar, deixe um comentário no final do artigo para que possamos atualizá-lo.
## <a name="quick-reference-guide"></a>Guia de referência rápida

|Recurso |Caminho no Portal Clássico|Caminho no Intune no Portal do Azure|
|------------|---------------|---------------|
|DEP (Programa de registro de dispositivos) [somente iOS]|Administração > Gerenciamento de Dispositivo Móvel > iOS > Programa de Registro de Dispositivos|[Registro de dispositivo > Registro da Apple > Token do Programa de Registro](#where-did-apple-dep-go) |
|DEP (Programa de registro de dispositivos) [somente iOS]| Administração > Gerenciamento de dispositivo móvel > iOS e Mac OS X > Programa de registro de dispositivos |[Registro de dispositivo > Registro da Apple > Números de Série do Programa de Registro](#where-did-apple-dep-go) |
|Regras de Registro |Administração > Gerenciamento de dispositivo móvel > Regras de Registro|[Registro de dispositivo > Restrições de Registro](#where-did-enrollment-rules-go) |
|Grupos pelo número de série do iOS |Grupos > Todos os Dispositivos > Dispositivos corporativos pré-registrados > Por Número de Série do iOS|[Registro de dispositivo > Registro da Apple > Números de Série do Programa de Registro](#where-did-corporate-pre-enrolled-devices-go) |
|Grupos pelo número de série do iOS |Grupos > Todos os Dispositivos > Dispositivos corporativos pré-registrados > Por Número de Série do iOS| [Registro de dispositivo > Registro da Apple > Números de série de CA](#where-did-corporate-pre-enrolled-devices-go)|
|Grupos por IMEI (todas as plataformas)| Grupos > Todos os Dispositivos > Dispositivos corporativos pré-registrados > Por IMEI (Todas as Plataformas) | [Registro de dispositivo > Identificadores de Dispositivos Corporativos](#by-imei-all-platforms)|
| Perfil de Registro de Dispositivo Corporativo| Política> Registro de Dispositivo Corporativo | [Registro de dispositivo > Registro da Apple > Perfis do Programa de Registro](#where-did-corporate-pre-enrolled-devices-go) |
| Perfil de Registro de Dispositivo Corporativo | Política> Registro de Dispositivo Corporativo | [Registro de dispositivo > Registro da Apple > Perfis de CA](#where-did-corporate-pre-enrolled-devices-go) |
| Android for Work | Administração > Gerenciamento de Dispositivo Móvel > Android for Work | Registro de dispositivo > Registro do Android |
| Termos e condições | Política > Termos e Condições | Registro de dispositivo > Termos e Condições |
Configurações do Portal da Empresa|Administrador > Portal da Empresa|**Gerenciar** > Aplicativos móveis<br> **Configurar** > Identidade visual do Portal da Empresa


## <a name="where-do-i-manage-groups"></a>Onde gerencio grupos?
Intune no Portal do Azure usa o [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) para gerenciar grupos.

## <a name="where-did-enrollment-rules-go"></a>Para onde foram as regras de registro?
No portal clássico, você pode definir as regras que regem o registro de MDM de dispositivos Windows e macOS modernos e móveis.

![Imagem de regras de registro de dispositivo móvel clássico](./media/ui-changes/01-classic-rules.png)

Estas regras eram aplicadas a todos os usuários em sua conta do Intune, sem exceção. No portal do Azure, estas regras agora são exibidas em dois tipos de políticas distintos: Restrições de Tipo de Dispositivo e Restrições de Limite de Dispositivos.

![Imagem das restrições de registro de dispositivo móvel do Azure](./media/ui-changes/02-azure-enroll-restrictions.png)

A Restrição de Limite de Dispositivos padrão corresponde ao Limite de Registro de Dispositivos no portal clássico.

![Imagem das restrições de limite de dispositivo do Azure](./media/ui-changes/03-azure-device-limit.png)

A Restrição de Tipo de Dispositivo padrão corresponde às Restrições de Plataforma no portal clássico.

![Imagem das restrições de tipo de dispositivo do Azure](./media/ui-changes/04-azure-platform-restrictions.png)

A capacidade de permitir ou bloquear dispositivos de propriedade pessoal agora é gerenciada nas Configurações de Plataforma da Restrição de Tipo de Dispositivo.

![Imagem das configurações de bloqueio de dispositivo pessoal do Azure](./media/ui-changes/05-azure-personal-block.png)

Novos recursos de restrição são adicionados ao Portal do Azure apenas.

## <a name="where-did-my-conditional-access-policies-go"></a>Para que local foram minhas políticas de Acesso Condicional?
Depois que o locatário é migrado para o portal do Azure, as políticas de Acesso Condicional do locatário continuam sendo impostas. No entanto, não é possível exibir nem modificá-las por meio do Intune no portal do Azure.

Se você desejar exibir e fazer alterações nas políticas de Acesso Condicional por meio do portal do Azure, precisará remover as políticas antigas do portal clássico. Em seguida, recrie-as no portal do Azure. Para obter mais informações sobre como migrar as políticas de Acesso Condicional, confira [Migrar as políticas clássicas no portal do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration). 

## <a name="where-did-my-compliance-policies-go"></a>Para que local foram minhas políticas de conformidade?
Depois que o locatário é migrado para o portal do Azure, as políticas de conformidade do locatário continuam sendo impostas. No entanto, não é possível exibir nem modificá-las por meio do Intune no portal do Azure.

Se você desejar exibir e fazer alterações nas políticas de conformidade por meio do portal do Azure, precisará remover as políticas antigas do portal clássico. Em seguida, recrie-as no portal do Azure. Para obter mais informações sobre as políticas de conformidade do dispositivo, confira [Introdução às políticas de conformidade do dispositivo no Intune](../protect/device-compliance-get-started.md). 

## <a name="where-did-apple-dep-go"></a>Para onde foi o Apple DEP?
No Portal Clássico, você podia configurar o Intune para integrar o Programa de registro de dispositivos da Apple e solicitar manualmente a sincronização com o serviço da Apple:

![Imagem de token DEP clássico](./media/ui-changes/06-classic-dep-token.png)

No portal do Azure, você configura o programa de registro de dispositivo Apple com as mesmas etapas do Intune clássico:

![Imagem de token de DEP do Azure](./media/ui-changes/07-azure-dep-token.png)

No entanto, a opção de **sincronização** no Portal Clássico foi movida para o fluxo de trabalho de gerenciamento do número de série, pois os resultados de uma sincronização manual aparecem lá:

![Imagem da sincronização de DEP do Azure](./media/ui-changes/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Para onde foram os dispositivos corporativos pré-registrados?
### <a name="by-ios-serial-number"></a>Por número de série do iOS
No Portal Clássico, você pode registrar dispositivos iOS por meio do Programa de registro de dispositivos (DEP) da Apple e da ferramenta Apple Configurator. Ambos os métodos oferecem pré-registro do dispositivo por número de série e envolvem a atribuição de perfis especiais de registro de dispositivo corporativo. Antes do registro, a atribuição de perfil de registro pode ser gerenciada por meio do **Dispositivo corporativo pré-registrado pelo grupo de dispositivos de número de série do iOS**:

![Imagem de números de série da Apple clássicos](./media/ui-changes/09-classic-apple-serials.png)

Lista os números de série para o registro DEP e o Configurator da Apple em uma única lista. Para reduzir a incompatibilidade de atribuição do perfil (perfil DEP para o número de série de CA e vice-versa), dividimos os números de série em duas listas no portal do Azure:

**Números de série DEP**
![Imagem de números de série do Azure DEP](./media/ui-changes/10-azure-dep-serials.png)

**Números de série do Apple Configurator**
![Imagem de números de série do Azure Apple Configurator](./media/ui-changes/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>Por IMEI (todas as plataformas)

No Portal Clássico, você pode listar previamente os números IMEI de dispositivos para marcá-los como corporativos quando eles foram registrados no Intune:

![Imagem da lista clássica de números IMEI](./media/ui-changes/12-classic-corp-imei.png)

No Portal do Azure, você deve carregar o mesmo IMEI à lista de identificadores de dispositivo corporativo com um arquivo contendo valores separados por vírgulas (CSV). O novo portal não oferece suporte à entrada manual de números IMEI:

![Imagem da lista de números IMEI do Azure](./media/ui-changes/13-azure-corp-imei.png)

Intune no portal do Azure está preparado para o futuro para dar suporte a outros tipos de identificadores além de IMEI, mas atualmente só permite números IMEI para pré-listagem.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Para onde foram os perfis de registro de dispositivo corporativo?
Para registrar dispositivos iOS por meio do programa de registro de dispositivo Apple ou com a ferramenta Apple Configurator, você deve fornecer um perfil de registro de dispositivo corporativo para ser atribuído ao dispositivo. No Portal Clássico, a criação e o gerenciamento desses perfis estavam localizados em uma única lista:

![Imagem de perfis de registro de dispositivo clássico](./media/ui-changes/14-classic-corp-profiles.png)

Esta lista mostra perfis habilitados para uso com o programa de registro de dispositivo Apple (**DEP On**) e perfil habilitado somente para uso com a ferramenta Apple Configurator (**DEP Off**).

Para reduzir a confusão entre os dois tipos de perfil e potencias atribuições incorretas de correspondência (perfil DEP para dispositivos Configurator e vice-versa), separamos a criação e o gerenciamento de perfis de programa de registro (para dar suporte ao programa de registro de dispositivo Apple e Apple School Manager) e perfis do Apple Configurator:

**Perfis DEP**
![Imagem de perfis do Azure DEP](./media/ui-changes/15-azure-dep-profiles.png)

**Perfis do Apple Configurator**
![Imagem de perfis do Azure Apple Configurator](./media/ui-changes/16-azure-ac-profiles.png)
