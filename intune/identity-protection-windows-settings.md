---
title: Configurações do Windows Hello para Empresas no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações de PIN, biométrica e antifalsificação em um perfil de proteção de identidade para usar e configurar o Windows Hello para Empresas em dispositivos Windows 10 no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5eb4097ab2bedf032270b1d4230d81f7b326fbf1
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57228571"
---
# <a name="windows-10-and-newer-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Configurações do dispositivo Windows 10 (e mais recente) para habilitar o Windows Hello para Empresas no Intune

Este artigo lista e descreve as configurações do Windows Hello para Empresas que você pode controlar nos dispositivos Windows 10 no Intune. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use essas configurações para usar um PIN ou impressão digital para entrar e muito mais.

Como administrador do Intune, você pode criar e atribuir essas configurações aos dispositivos Windows 10 ou posteriores.

Para saber mais sobre os perfis do Windows Hello para Empresas no Intune, confira [configurar a proteção de dados](identity-protection-configure.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello para Empresas

- **Configure o Windows Hello para Empresas**: Para usar esse recurso e definir suas configurações, escolha **Habilitar**.
- **Tamanho mínimo do PIN**: Insira o tamanho mínimo do PIN que você deseja permitir nos dispositivos. O comprimento padrão do PIN é de seis caracteres. O comprimento mínimo do PIN é de quatro (4) caracteres.
- **Tamanho máximo do PIN**: Insira o tamanho máximo do PIN que você deseja permitir nos dispositivos. O comprimento padrão do PIN é de seis (6) caracteres. O comprimento máximo do PIN é de 127 caracteres.  
- **Letras minúsculas no PIN**: Você pode impor um PIN mais forte exigindo que os usuários finais incluam letras minúsculas. Suas opções:

  - **Não permitido** (padrão): Impeça que os usuários usem letras minúsculas no PIN. Esse comportamento também ocorre quando a configuração não está definida.
  - **Permitido**: Permita que os usuários usem letras minúsculas no PIN, mas isso não é obrigatório.
  - **Obrigatório**: Os usuários devem incluir pelo menos um caractere minúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

- **Letras maiúsculas no PIN**: Você pode impor um PIN mais forte exigindo que os usuários finais incluam letras maiúsculas. Suas opções:

  - **Não permitido** (padrão): Impeça que os usuários usem letras maiúsculas no PIN. Esse comportamento também ocorre quando a configuração não está definida.
  - **Permitido**: Permita que os usuários usem letras maiúsculas no PIN, mas isso não é obrigatório.
  - **Obrigatório**: Os usuários devem incluir pelo menos um caractere maiúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

- **Caracteres especiais no PIN**: Você pode impor um PIN mais forte exigindo que os usuários finais incluam caracteres especiais. Suas opções:

  - **Não permitido** (padrão): Impeça que os usuários usem caracteres especiais no PIN. Esse comportamento também ocorre quando a configuração não está definida.
    Os caracteres especiais incluem: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **Permitido**: Permita que os usuários usem letras maiúsculas no PIN, mas isso não é obrigatório.
  - **Obrigatório**: Os usuários devem incluir pelo menos um caractere maiúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

- **Expiração do PIN (dias)**: É uma boa prática especificar um período de expiração de um PIN após o qual os usuários devem alterá-lo. O padrão é 41 dias.

- **Lembrar histórico de PINs**: Restringe a reutilização de PINs usados anteriormente. Por padrão, os últimos 5 PINs não podem ser reutilizados.  
- **Habilitar a recuperação do PIN**: Permite que o usuário altere o PIN usando o serviço de recuperação de PIN do Windows Hello para Empresas.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Usar um TPM (Trusted Platform Module)**: Um chip TPM fornece uma camada adicional de segurança de dados. Selecione uma das seguintes opções:  
  - **Habilitar**: Somente dispositivos com um TPM acessível podem provisionar o Windows Hello para Empresas.
  - **Não configurado**: Todos os dispositivos podem provisionar o Windows Hello para Empresas, mesmo quando não há um TPM utilizável. Primeiro os dispositivos tentarão usar um TPM, mas, se não houver nenhum disponível, eles poderão usar a criptografia de software.  

- **Permitir autenticação biométrica**: Permite a autenticação biométrica, como reconhecimento facial ou impressão digital, como uma alternativa a um PIN do Windows Hello para Empresas. Os usuários ainda devem configurar um PIN de trabalho no caso de falha de autenticação biométrica. Escolha:

  - **Habilitar**: O Windows Hello para Empresas permite autenticação biométrica.
  - **Não configurado** (padrão): O Windows Hello para Empresas impede a autenticação biométrica (para todos os tipos de conta).

- **Usar antifalsificação avançada, quando disponível**: Escolha se as funcionalidades antifalsificação do Windows Hello são usadas em dispositivos que dão suporte a ele. Por exemplo, detecte uma fotografia de um rosto, em vez do rosto real.

  - **Habilitar**: O Windows requer que todos os usuários usem a antifalsificação para recursos de rosto quando há suporte.  
  - **Não configurado** (padrão): O Windows respeita as configurações antifalsificação do dispositivo.

- **Certificado para recursos locais**: 

  - **Habilitar**: Permite que o Windows Hello para Empresas use certificados para autenticar-se em recursos locais.
  - **Não configurado** (padrão): Impede que Windows Hello para Empresas use certificados para autenticar-se em recursos locais.  

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
