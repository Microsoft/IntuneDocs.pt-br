---
title: Habilitar a conformidade do Google Play Protect com o Intune
titleSuffix: Azure portal
description: "Saiba como criar uma política de conformidade para criar uma política de conformidade para dispositivos Android para habilitar o Google Play Protect."
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3d9e687ff31d50e30ea4d15a4eb751c0e78dc24e
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2018
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Como criar uma política de conformidade do dispositivo para habilitar o Google Play Protect

Você pode criar uma nova política de conformidade para a plataforma Android para verificar a conformidade do Google Play Protect (GPP).

A política de conformidade que requer essas configurações pode, então, ser direcionada a um grupo de dispositivos ou usuários Android. Se um dispositivo não tiver essas configurações habilitadas, ele fica fora da conformidade.

## <a name="create-a-compliance-policy"></a>Criar uma política de conformidade

1. Entre no Portal do Azure. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** + **Intune**.
2. Escolha **Conformidade do dispositivo** no grupo **Gerenciar**. 
3. Escolha **Políticas** e escolha **Criar Política**.
4. Digite o **Nome** e a **Descrição** da política.
5. Selecione **Android** para Plataforma.
6. Escolha **Configurações** > **Integridade do Dispositivo**.
7. Defina as configurações do **Google Play Protect**.
8. Quando você tiver definido as configurações do Google Play Protect, especifique as configurações **Segurança** e **Propriedade do dispositivo**. Quando terminar, escolha **OK**.

## <a name="configure-the-google-play-protect-settings"></a>Definir as configurações do Google Play Protect

 - **O Google Play Services está configurado**  
   Exige que o aplicativo de serviços do Google Play esteja instalado e habilitado. Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google.
 - **Provedor de segurança atualizada**  
   Exige que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas.
 - **Verificação de ameaças em aplicativos**  
   Exige que o recurso **Verificar Aplicativos** do Android esteja ativado.
    > [!Note]  
    > Na plataforma Android herdada, esse recurso é uma configuração de conformidade. O Intune só pode verificar se essa configuração está habilitada no nível do dispositivo. Em dispositivos com perfis de trabalho, anteriormente Android for Work, essa configuração pode ser encontrada como uma definição de política de configuração. Isso permite que os administradores habilitem a configuração para um dispositivo.

    Se sua empresa usa perfis de trabalho do Android, você pode habilitar a **Verificação de ameaças em aplicativos** para seus dispositivos registrados. Estabeleça um perfil de dispositivo e exija a configuração de segurança do sistema. Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

 - **Atestado de dispositivo SafetyNet**  
   Defina o nível de integridade do atestado do dispositivo SafetyNet que deve ser atendido. Os níveis incluem **Não configurado**, **Verificação de integridade básica** e **Verificação de integridade básica e dispositivos certificados**.




## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre como trabalhar com as políticas de conformidade do dispositivo no Intune, confira a [Introdução às políticas de conformidade do dispositivo do Intune](device-compliance-get-started.md).