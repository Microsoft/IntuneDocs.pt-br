---
title: Para onde foi o meu recurso Intune no Azure?
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: ajuda a localizar recursos do Intune no console do Azure."
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 9dd6e93108ffc46e9e52b6928cf513161d29f7a4
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Para onde foi o meu recurso Intune no Azure?
Aproveitamos a oportunidade para organizar algumas tarefas mais logicamente à medida que mudamos o Intune para o portal do Azure. Mas cada aperfeiçoamento vem com o custo de aprender a nova organização. Assim, criamos este guia de referência para aqueles que estão totalmente familiarizados com o Intune no console clássico e querem saber como fazer algo no Intune no Azure. Se este artigo não abordar um recurso que você está tentando localizar, deixe um comentário no final do artigo para que possamos atualizá-lo.
## <a name="quick-reference-guide"></a>Guia de referência rápida
| Recurso | Caminho no console clássico | Caminho do Intune no Azure | |------------||---------------|---------------|
| Programa de registro do dispositivo (DEP) | Admin > gerenciamento de dispositivo móvel > iOS e Mac OS X > programa de registro de dispositivo |[Registro de dispositivo > registro Apple > Token do programa de registro](#where-did-apple-dep-go) |
|Programa de registro do dispositivo (DEP) | Admin > gerenciamento de dispositivo móvel > iOS e Mac OS X > programa de registro de dispositivo |[Registro de dispositivo > registro Apple > números de série do programa de registro](#where-did-apple-dep-go) |
|Regras de registro | Admin > gerenciamento de dispositivo móvel > regras de registro |[Registro de dispositivo > restrições de registro](#where-did-enrollment-rules-go) |
| Grupos pelo número de série do iOS | Grupos > todos os dispositivos > dispositivos corporativos pré-registrados > pelo número de série do iOS |[Registro de dispositivo > registro Apple > números de série do programa de registro](#where-did-corporate-pre-enrolled-devices-go) |
|Grupos pelo número de série do iOS | Grupos > todos os dispositivos > dispositivos corporativos pré-registrados > pelo número de série do iOS | [Registro de dispositivo > registro Apple > números de série de CA](#where-did-corporate-pre-enrolled-devices-go)|
|Grupos por IMEI (todas as plataformas) | Grupos > todos os dispositivos > dispositivos corporativos pré-registrados > por IMEI (todas as plataformas) | [Registro de dispositivo > identificadores de dispositivo corporativo](#by-imei-all-platforms)|
| Perfil de registro do dispositivo corporativo | Política > registro de dispositivo corporativo | [Registro de dispositivo > registro Apple > perfis do programa de registro](#where-did-corporate-pre-enrolled-devices-go) |
| Perfil de registro do dispositivo corporativo | Política > registro de dispositivo corporativo | [Registro de dispositivo > registro Apple > perfis de CA](#where-did-corporate-pre-enrolled-devices-go) |
| Android for Work | Admin > Gerenciamento de Dispositivo Móvel > Android for Work | Registro de Dispositivo > Registro do Android for Work | | Termos e Condições | Política > Termos e Condições |Registro de dispositivo > Termos e Condições |


## <a name="where-do-i-manage-groups"></a>Onde gerencio grupos?
Intune no Azure usa o [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) para gerenciar grupos.

## <a name="where-did-enrollment-rules-go"></a>Para onde foram as regras de registro?
No console clássico, você pode definir regras que regem o registro de MDM de dispositivos móveis e modernos com Windows e macOS:

![Imagem de regras de registro de dispositivo móvel clássico](./media/01-classic-rules.png)

Estas regras eram aplicadas a todos os usuários em sua conta do Intune, sem exceção. No portal Azure, estas regras agora são exibidas em dois diferentes tipos de políticas: restrições de tipo de dispositivo e restrições de limite do dispositivo:

![Imagem das restrições de registro de dispositivo móvel do Azure](./media/02-azure-enroll-restrictions.png)

A restrição de limite de dispositivo padrão corresponde ao limite de registro de dispositivo no console clássico:

![Imagem das restrições de limite de dispositivo do Azure](./media/03-azure-device-limit.png)

A restrição de tipo de dispositivo padrão corresponde às restrições de plataforma no console clássico:

![Imagem das restrições de tipo de dispositivo do Azure](./media/04-azure-platform-restrictions.png)

A capacidade de permitir ou bloquear dispositivos de propriedade pessoal agora é gerenciada nas Configurações de plataforma da restrição do tipo de dispositivo:

![Imagem das configurações de bloqueio de dispositivo pessoal do Azure](./media/05-azure-personal-block.png)

Novos recursos de restrição serão adicionados ao Portal do Azure apenas.

## <a name="where-did-apple-dep-go"></a>Para onde foi o Apple DEP?
No console clássico, você podia configurar o Intune para integrar o programa de registro de dispositivo da Apple e solicitar manualmente a sincronização com o serviço da Apple:

![Imagem de token DEP clássico](./media/06-classic-dep-token.png)

No portal do Azure, você configura o programa de registro de dispositivo Apple com as mesmas etapas do Intune clássico:

![Imagem de token de DEP do Azure](./media/07-azure-dep-token.png)

No entanto, a opção de **sincronização** no console clássico foi movida para o fluxo de trabalho de gerenciamento do número de série, pois os resultados de uma sincronização manual aparecerão lá:

![Imagem da sincronização de DEP do Azure](./media/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Para onde foram os dispositivos corporativos pré-registrados?
### <a name="by-ios-serial-number"></a>Por número de série do iOS
No console clássico, você pode registrar dispositivos iOS por meio do programa de registro de dispositivo (DEP) da Apple e da ferramenta Apple Configurator. Ambos os métodos oferecem pré-registro do dispositivo por número de série e envolvem a atribuição de perfis especiais de registro de dispositivo corporativo. Antes do registro, a atribuição de perfil de registro pode ser gerenciada por meio do **Dispositivo corporativo pré-registrado pelo grupo de dispositivos de número de série do iOS**:

![Imagem de números de série da Apple clássicos](./media/09-classic-apple-serials.png)

Lista os números de série para o registro DEP e o Configurator da Apple em uma única lista. Para reduzir a incompatibilidade de atribuição do perfil (perfil DEP para o número de série de CA e vice-versa), dividimos os números de série em duas listas no portal do Azure:

**Números de série DEP**
![Imagem de números de série do Azure DEP](./media/10-azure-dep-serials.png)

**Números de série do Apple Configurator**
![Imagem de números de série do Azure Apple Configurator](./media/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>Por IMEI (todas as plataformas)

No console clássico, você pode listar previamente os números IMEI de dispositivos para marcá-los como corporativos quando eles foram registrados no Intune:

![Imagem da lista clássica de números IMEI](./media/12-classic-corp-imei.png)

No console do Azure, você deve carregar o mesmo IMEI à lista de identificadores de dispositivo corporativo com um arquivo contendo valores separados por vírgulas (CSV). O novo portal não oferecerá suporte à entrada manual de números IMEI:

![Imagem da lista de números IMEI do Azure](./media/13-azure-corp-imei.png)

Intune no portal do Azure está preparado para o futuro para dar suporte a outros tipos de identificadores além de IMEI, mas atualmente só permite números IMEI para pré-listagem.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Para onde foram os perfis de registro de dispositivo corporativo?
Para registrar dispositivos iOS por meio do programa de registro de dispositivo Apple ou com a ferramenta Apple Configurator, você deve fornecer um perfil de registro de dispositivo corporativo para ser atribuído ao dispositivo. No console clássico, a criação e o gerenciamento desses perfis estavam localizados em uma única lista:

![Imagem de perfis de registro de dispositivo clássico](./media/14-classic-corp-profiles.png)

Esta lista mostra perfis habilitados para uso com o programa de registro de dispositivo Apple (**DEP On**) e perfil habilitado somente para uso com a ferramenta Apple Configurator (**DEP Off**).

Para reduzir a confusão entre os dois tipos de perfil e potencias atribuições incorretas de correspondência (perfil DEP para dispositivos Configurator e vice-versa), separamos a criação e o gerenciamento de perfis de programa de registro (para dar suporte ao programa de registro de dispositivo Apple e Apple School Manager) e perfis do Apple Configurator:

**Perfis DEP**
![Imagem de perfis do Azure DEP](./media/15-azure-dep-profiles.png)

**Perfis do Apple Configurator**
![Imagem de perfis do Azure Apple Configurator](./media/16-azure-ac-profiles.png)

