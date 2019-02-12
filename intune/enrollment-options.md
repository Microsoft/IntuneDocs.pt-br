---
title: Opções de registro para dispositivos gerenciados pelo Microsoft Intune
titleSuffix: ''
description: Uma lista de opções de registro que os administradores podem definir para dispositivos gerenciados pelo Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: cf3cc41bfb92c6e213121f0ace71eca276d6e8ab
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55840049"
---
# <a name="enrollment-options-for-devices-managed-by-intune"></a>Opções de registro para dispositivos gerenciados pelo Intune

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
## <a name="multi-factor-authentication"></a>Autenticação Multifator

Você pode exigir que os usuários usem um método de verificação adicional, como um telefone, um PIN ou dados biométricos, ao registrar um dispositivo. Saiba mais sobre a [autenticação multifator](multi-factor-authentication.md).

## <a name="device-enrollment-manager"></a>Gerenciador de registro de dispositivos
Você pode transformar usuários em gerenciadores de registros de dispositivos.  Usuários DEM podem registrar um grande número de dispositivos móveis com uma única conta de usuário. A conta do DEM (gerenciador de registros de dispositivos) pode registrar até 1.000 dispositivos. Saiba mais sobre [gerenciadores de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="device-categories"></a>Categorias de dispositivos

Você pode usar as categorias de dispositivo para adicionar automaticamente os dispositivos a grupos com base em categorias definidas por você. Organizar dispositivos em grupos facilita a tarefa de gerenciar esses dispositivos. Saiba mais sobre [categorias de dispositivo](device-group-mapping.md).
