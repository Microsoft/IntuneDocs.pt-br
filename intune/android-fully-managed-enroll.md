---
title: Configurar registro do Intune para dispositivos Android Enterprise totalmente gerenciados
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos Android Enterprise totalmente gerenciados no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e3615f1f090af3ce589e83f11d12e95a2f07641
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61503807"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices-preview"></a>Configurar registro do Intune dos dispositivos Android Enterprise totalmente gerenciados (versão prévia)

Os dispositivos Android Enterprise totalmente gerenciados são de propriedade corporativa, associados a um único usuário e usados exclusivamente para trabalho, e não para uso pessoal. Os administradores podem gerenciar todo o dispositivo e impor controles de política não disponíveis para perfis de trabalho, como:
- permitir a instalação de aplicativos somente do Google Play Gerenciado
- bloquear a desinstalação de aplicativos gerenciados;
- impedir que os usuários redefinam as configurações de fábrica dos dispositivos, e assim por diante.

O Intune ajuda você a implantar aplicativos e configurações em dispositivos Android Enterprise, incluindo dispositivos Android Enterprise totalmente gerenciados. Para obter detalhes específicos sobre o Android Enterprise, confira [Requisitos do Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Requisitos técnicos

É necessário ter um locatário autônomo do Intune para gerenciar dispositivos Android Enterprise totalmente gerenciados. O gerenciamento de dispositivo totalmente gerenciado não está disponível no modo híbrido (conectado ao Configuration Manager) nem no console de gerenciamento do Silverlight herdado.

Os dispositivos devem atender a esses requisitos para serem gerenciados como um dispositivo Android Enterprise totalmente gerenciado:

- Sistema operacional Android versão 5.1 e posterior.
- Os dispositivos precisam executar um build do Android que tenha conectividade com GMS (Google Mobile Services). Os dispositivos precisam ter o GMS disponível e conseguir se conectar a ele.

Não haverá nenhuma restrição de OEM da fabricante do dispositivo se os requisitos acima forem atendidos.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Configurar o gerenciamento de dispositivo Android Enterprise totalmente gerenciado

Para configurar o gerenciamento de dispositivo Android Enterprise totalmente gerenciado, siga estas etapas:

1. Para se preparar para gerenciar dispositivos móveis, é necessário [definir a autoridade MDM (gerenciamento de dispositivo móvel) como **Microsoft Intune**](mdm-authority-set.md). Você define esse item apenas uma vez, na primeira vez que configura o Intune para o gerenciamento de dispositivo móvel.
2. [Conecte sua conta de locatário do Intune à sua conta do Android Enterprise](connect-intune-android-enterprise.md).
3. [Habilitar dispositivos de usuário de propriedade corporativa](#enable-corporate-owned-user-devices)
4. [Registre os dispositivos totalmente gerenciados](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Habilitar dispositivos corporativos de usuários

1. Vá para o [portal do Intune](https://portal.azure.com) e escolha **Registro de dispositivo** > **Registro do Android** > **Dispositivos de usuário de propriedade corporativa totalmente gerenciados (versão prévia)**.
2. Em **Permitir que os usuários registrem os dispositivos de usuário de propriedade corporativa**, escolha **Sim**.

Quando essa configuração é definida como **Sim**, ela fornece um token de registro (uma cadeia de caracteres aleatória) e um código QR para seu locatário do Intune. Esse token de registro único é válido para todos os usuários e não expirará. Dependendo do sistema operacional Android e da versão do dispositivo, é possível usar o token ou o código QR para registrar o dispositivo de quiosque.

## <a name="enroll-the-fully-managed-devices"></a>Registrar os dispositivos totalmente gerenciados
Agora você pode [registrar seus dispositivos totalmente gerenciados](android-dedicated-devices-fully-managed-enroll.md).

## <a name="considerations-for-this-preview-feature"></a>Considerações para essa versão prévia do recurso
Essa versão prévia pública inclui um conjunto básico de recursos para o conjunto de soluções totalmente gerenciadas do Android Enterprise. Queremos saber sobre sua experiência usando a versão prévia dos recursos por meio de um dos seus canais de comunicação atuais com a equipe (assim como o [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)).

Essa versão prévia dá suporte aos seguintes recursos para dispositivos Android Enterprise totalmente gerenciados:
- Registro de dispositivo usando NFC, entrada de token, código QR e Zero Touch
- Configuração do dispositivo para grupos de usuários
- Distribuição de aplicativos e configuração de grupos de usuários


Ao usar essas versões prévias dos recursos, tenha o seguinte em mente:
- Recursos em versão prévia não são recomendados para implantações críticas ou de produção. 
- As versões prévias dos recursos são implementadas segundo os padrões de produção do Microsoft Intune. No entanto, nem todos os recursos do Intune estão disponíveis para uso com dispositivos Android Enterprise de usuário totalmente gerenciados. As versões prévias dos recursos são claramente rotuladas com "(versão prévia)" no console do Intune. 
- As versões prévias dos recursos são totalmente compatíveis por meio dos canais de suporte usuais do Intune.
- O registro de dispositivos Android Enterprise totalmente gerenciados usando o registro no Samsung Knox Mobile não é compatível com a versão prévia. 
- O uso do aplicativo do Portal da Empresa do Intune não é compatível com dispositivos Android Enterprise totalmente gerenciados. 
- Recursos do Intune como Acesso Condicional, políticas de proteção de aplicativo e implantação de certificado não são compatíveis com a versão prévia. 
- O direcionamento de um perfil ou aplicativo a grupos de dispositivos não é compatível na versão prévia. Apenas o direcionamento a grupos de usuários é compatível. 
- Não há nenhuma interface do usuário de primeira classe para configurar email, Wi-Fi ou VPN. Use políticas de configuração de aplicativo para definir as configurações de aplicativo compatíveis.

## <a name="next-steps"></a>Próximas etapas
- [Adicionar políticas de configuração de dispositivos Android Enterprise totalmente gerenciados](device-restrictions-android-for-work.md#device-owner-only)
- [Definir políticas de configuração de aplicativos para dispositivos Android Enterprise totalmente gerenciados](app-configuration-policies-use-android.md)

