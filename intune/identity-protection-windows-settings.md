---
title: Configurações do Windows Hello para Empresas no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações de PIN, biométrica e antifalsificação em um perfil de proteção de identidade para usar e configurar o Windows Hello para Empresas em dispositivos Windows 10 no Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/14/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 158840a73784516d13defa04785ca5990a9874cf
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041819"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Configurações do dispositivo Windows 10 para habilitar o Windows Hello para Empresas no Intune

Este artigo lista e descreve as configurações do Windows Hello para Empresas que você pode controlar nos dispositivos Windows 10 no Intune. Como um administrador do Intune, você pode configurar e atribuir essas configurações a dispositivos Windows 10 como parte de sua solução de MDM (gerenciamento de dispositivo móvel). 

Você pode encontrar informações adicionais sobre essas configurações em [Definir configurações de Política do Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings) na documentação do Windows Hello.


Para saber mais sobre os perfis do Windows Hello para Empresas no Intune, confira [configurar a proteção de dados](identity-protection-configure.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello para Empresas

- **Configurar Windows Hello para Empresas**: para usar esse recurso e configurar suas configurações, escolha **habilitar**.
- **Tamanho mínimo do PIN**: insira o tamanho mínimo do PIN que você deseja permitir nos dispositivos. O comprimento padrão do PIN é de seis caracteres. O comprimento mínimo do PIN é de quatro (4) caracteres.
- **Tamanho máximo do PIN**: insira o tamanho máximo do PIN que você deseja permitir nos dispositivos. O comprimento padrão do PIN é de seis (6) caracteres. O comprimento máximo do PIN é de 127 caracteres.  
- **Letras minúsculas no PIN**: você pode impor um PIN mais forte exigindo que os usuários finais incluam letras minúsculas. Suas opções:

  - **Não permitido** (padrão): impeça que os usuários usem letras minúsculas no PIN. Esse comportamento também ocorre quando a configuração não está definida.
  - **Permitido**: permita que os usuários usem letras minúsculas no PIN, mas isso não é obrigatório.
  - **Necessário**: os usuários devem incluir pelo menos um caractere minúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

- **Letras maiúsculas no PIN**: você pode impor um PIN mais forte exigindo que os usuários finais incluam letras maiúsculas. Suas opções:

  - **Não permitido** (padrão): impeça que os usuários usem letras maiúsculas no PIN. Esse comportamento também ocorre quando a configuração não está definida.
  - **Permitido**: permita que os usuários usem letras maiúsculas no PIN, mas isso não é obrigatório.
  - **Necessário**: os usuários devem incluir pelo menos um caractere maiúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

- **Caracteres especiais no PIN**: você pode impor um PIN mais forte exigindo que os usuários finais incluam caracteres especiais. Suas opções:

  - **Não permitido** (padrão): impeça que os usuários usem caracteres especiais no PIN. Esse comportamento também ocorre quando a configuração não está definida.
    Os caracteres especiais incluem: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **Permitido**: permita que os usuários usem letras maiúsculas no PIN, mas isso não é obrigatório.
  - **Necessário**: os usuários devem incluir pelo menos um caractere maiúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

- **Expiração do PIN (dias)** : é uma boa prática especificar um período de expiração de um PIN após o qual os usuários finais precisam alterá-lo. O padrão é 41 dias.

- **Lembrar histórico de PINs**: restringe a reutilização de PINs usados anteriormente. Por padrão, os últimos 5 PINs não podem ser reutilizados.  
- **Habilitar recuperação PIN**: permite que o usuário altere o PIN usando o serviço de recuperação de PIN do Windows Hello para Empresas.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Usar um TPM Trusted Platform Module**: um chip TPM fornece uma camada adicional de segurança de dados. Selecione uma das seguintes opções:  
  - **Habilitar**: somente dispositivos com um TPM acessível podem provisionar o Windows Hello para Empresas.
  - **Não configurado**: todos os dispositivos podem provisionar o Windows Hello para Empresas, mesmo quando não há um TPM utilizável. Primeiro os dispositivos tentarão usar um TPM, mas, se não houver nenhum disponível, eles poderão usar a criptografia de software.  

- **Permitir autenticação biométrica**: permite a autenticação biométrica, como reconhecimento facial ou impressão digital, como uma alternativa a um PIN do Windows Hello para Empresas. Os usuários ainda devem configurar um PIN de trabalho no caso de falha de autenticação biométrica. Escolha:

  - **Habilitar**: o Windows Hello para Empresas permite autenticação biométrica.
  - **Não configurado** (padrão): o Windows Hello para Empresas impede a autenticação biométrica (para todos os tipos de conta).

- **Usar antifalsificação avançada, quando disponível**: escolha se os recursos antifalsificação do Windows Hello serão usados em dispositivos compatíveis. Por exemplo, detecte uma fotografia de um rosto, em vez do rosto real.

  - **Habilitar**: o Windows requer que todos os usuários usem a antifalsificação para recursos de rosto quando há suporte.  
  - **Não configurado** (padrão): o Windows respeita as configurações antifalsificação do dispositivo.

- **Certificado para recursos locais**: 

  - **Habilitar**: permite que o Windows Hello para Empresas use certificados para autenticar-se em recursos locais.
  - **Não configurado** (padrão): impede que Windows Hello para Empresas use certificados para autenticar-se em recursos locais. Em vez disso, os dispositivos usam o comportamento padrão do *autenticação de chave de confiança local*. Para obter mais informações, veja [Certificado de usuário para autenticação local](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) na documentação do Windows Hello.  
## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
