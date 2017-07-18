---
title: "Opções de registro para o Intune"
description: 
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
ms.openlocfilehash: dcc97e5bcffb35752b65e8ce275d38b9578da6fa
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2017
---
# <a name="enrollment-options-for-intune"></a>Opções de registro para o Intune

Como um administrador do Intune, você pode configurar o registro de dispositivo para ajudar os usuários e habilitar funcionalidades do Intune.  O Intune inclui as seguintes opções de registro:

## <a name="terms-and-conditions"></a>Termos e condições

Você pode exigir que os usuários aceitem os termos e condições de sua empresa antes de poderem usar o Portal da Empresa para registrar seus dispositivos e acessar recursos como aplicativos e email da empresa. A configuração dos termos e condições é opcional. Aprenda mais sobre os [termos e condições](terms-and-conditions-create.md).

## <a name="enrollment-restrictions"></a>Restrições de registro

Você pode optar por restringir o registro de dispositivo por:
- Plataforma do dispositivo
- Número de dispositivos por usuário
- Bloquear dispositivos pessoais

Saiba mais sobre [restrições de registro](enrollment-restrictions-set.md).

## <a name="enable-apple-device-enrollment"></a>Habilitar registro de dispositivo da Apple

Um certificado de Push MDM é necessário para registrar dispositivos iOS e macOS. Saiba mais sobre [MDM push certificates](apple-mdm-push-certificate-get.md).

## <a name="corporate-identifiers"></a>Identificadores corporativos

Você pode listar os números de IMEI (identificador de equipamento móvel internacional) e números de série para identificar dispositivos corporativos. Saiba mais sobre [identificadores corporativos](corporate-identifiers-add.md).

## <a name="device-enrollment-manager"></a>Gerenciador de registro de dispositivos
Você pode transformar usuários em gerenciadores de registros de dispositivos.  Usuários DEM podem registrar um grande número de dispositivos móveis com uma única conta de usuário. A conta do DEM (gerenciador de registros de dispositivos) pode registrar até 1.000 dispositivos. Saiba mais sobre [gerenciadores de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="device-categories"></a>Categorias de dispositivos

Você pode usar as categorias de dispositivo para adicionar automaticamente os dispositivos a grupos com base em categorias definidas por você. Organizar dispositivos em grupos facilita a tarefa de gerenciar esses dispositivos. Saiba mais sobre [categorias de dispositivo](device-group-mapping.md).
