---
title: Configurações do Windows Hello para Empresas no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações de PIN, biométrica e antifalsificação em um perfil de proteção de identidade para usar e configurar o Windows Hello para Empresas em dispositivos Windows 10 no Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: f1727e22f7fdab2ef3971667f9a60c70ee7b3702
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732705"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Configurações do dispositivo Windows 10 para habilitar o Windows Hello para Empresas no Intune

Este artigo lista e descreve as configurações do Windows Hello para Empresas que você pode controlar nos dispositivos Windows 10 no Intune. Como um administrador do Intune, você pode configurar e atribuir essas configurações a dispositivos Windows 10 como parte de sua solução de MDM (gerenciamento de dispositivo móvel). 

Você pode encontrar informações adicionais sobre essas configurações em [Definir configurações de Política do Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings) na documentação do Windows Hello.


Para saber mais sobre os perfis do Windows Hello para Empresas no Intune, confira [configurar a proteção de dados](identity-protection-configure.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello para Empresas
- **Configure o Windows Hello para Empresas**:
  - **Não configurado**: selecione esta configuração se você não quiser usar o Intune para controlar as configurações do Windows Hello para Empresas. As configurações existentes do Windows Hello para Empresas em dispositivos com Windows 10 não são alteradas. Nenhuma outra configuração no painel está disponível.

  - **Desabilitado**: se você não quiser usar o Windows Hello para Empresas, selecione esta configuração. Todas as outras configurações na tela ficam indisponíveis.
  - **Habilitado**: selecione esta configuração se você quiser configurar o Windows Hello para Empresas.  
  
  **Padrão**: não configurado

  Quando definido como *habilitado*, as seguintes configurações estão disponíveis:

  - **Tamanho mínimo do PIN**  
    Especifique um comprimento mínimo de PIN para dispositivos, para ajudar a proteger a entrada. Os padrões de dispositivo do Windows têm seis caracteres, mas essa configuração pode impor um mínimo de quatro a 127 caracteres. 

    **Padrão**: *não configurado*

  - **Tamanho máximo do PIN**  
  Especifique um comprimento máximo de PIN para dispositivos, para ajudar a proteger a entrada. Os padrões de dispositivo do Windows têm seis caracteres, mas essa configuração pode impor um mínimo de quatro a 127 caracteres.  

    **Padrão**: *não configurado*  

  - **Letras minúsculas no PIN**  
    Você pode impor um PIN mais forte exigindo que os usuários finais incluam letras minúsculas. Suas opções:

    - **Não permitido** : impeça que os usuários usem letras minúsculas no PIN. Esse comportamento também ocorre quando a configuração não está definida.
    - **Permitido**: permita que os usuários usem letras minúsculas no PIN, mas isso não é obrigatório.
    - **Obrigatório**: os usuários precisam incluir pelo menos um caractere minúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

  - **Letras maiúsculas no PIN**  
    Você pode impor um PIN mais forte exigindo que os usuários finais incluam letras maiúsculas. Suas opções:

    - **Não permitido**: impeça que os usuários usem letras maiúsculas no PIN. Esse comportamento também ocorre quando a configuração não está definida.
    - **Permitido**: permita que os usuários usem letras maiúsculas no PIN, mas isso não é obrigatório.
    - **Obrigatório**: os usuários precisam incluir pelo menos um caractere maiúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

  - **Caracteres especiais no PIN**  
    Você pode impor um PIN mais forte exigindo que os usuários finais incluam caracteres especiais. Os caracteres especiais incluem: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`  

    Suas opções:
    - **Não permitido**: impeça que os usuários usem caracteres especiais no PIN. Esse comportamento também ocorre quando a configuração não está definida.
    - **Permitido**: permita que os usuários usem letras maiúsculas no PIN, mas isso não é obrigatório.
    - **Obrigatório**: os usuários precisam incluir pelo menos um caractere maiúsculo no PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

    **Padrão**: não permitido

  - **Validade do PIN (dias)**  
    É uma boa prática especificar um período de expiração de um PIN após o qual os usuários devem alterá-lo. Os padrões de dispositivo do Windows são de 41 dias.

    **Padrão**: Não configurado

  - **Lembrar histórico de PINs**  
    Restringe a reutilização de PINs usados anteriormente. Os dispositivos Windows são padrão para impedir a reutilização dos últimos cinco PINs.  

    **Padrão**: Não configurado  

  - **Habilitar a recuperação do PIN**   
    Permite que o usuário use o serviço de recuperação de PIN do Windows Hello para empresas. 
    
    - **Habilitado** -o segredo de recuperação do PIN é armazenado no dispositivo e o usuário pode alterar seu PIN, se necessário.  
    - **Desabilitado** -o segredo de recuperação não é criado ou armazenado.

    **Padrão**: não configurado

  - **Usar um TPM (Trusted Platform Module)**    
    Um chip TPM fornece uma camada adicional de segurança de dados.  

    - **Habilitado**: somente dispositivos com um TPM acessível podem provisionar o Windows Hello para Empresas.
    - **Não configurado**: primeira tentativa dos dispositivos de usar um TPM. Se não estiver disponível, eles podem usar criptografia de software.
    
    **Padrão**: não configurado

  - **Permitir autenticação biométrica**  
     Permite a autenticação biométrica, como reconhecimento facial ou impressão digital, como uma alternativa a um PIN do Windows Hello para Empresas. Os usuários ainda devem configurar um PIN de trabalho no caso de falha de autenticação biométrica. Escolha:

    - **Habilitar**: o Windows Hello para Empresas permite autenticação biométrica.
    - **Não configurado**: o Windows Hello para Empresas impede a autenticação biométrica (para todos os tipos de conta).

    **Padrão**: não configurado

  - **Usar antifalsificação avançada, quando disponível**  
    Define se as funcionalidades antifalsificação do Windows Hello são usadas em dispositivos que dão suporte a ele (por exemplo, detectando uma fotografia de um rosto, em vez do rosto real).  
    - **Habilitar**: o Windows requer que todos os usuários usem a antifalsificação para recursos de rosto quando há suporte.
    - **Não configurado**: o Windows respeita as configurações antifalsificação do dispositivo.

    **Padrão**: não configurado

  - **Certificado para recursos locais**  

    - **Habilitar**: permite que o Windows Hello para Empresas use certificados para autenticar-se em recursos locais.
    - **Não configurado**: impede que o Windows Hello para Empresas use certificados para autenticar-se em recursos locais. Em vez disso, os dispositivos usam o comportamento padrão do *autenticação de chave de confiança local*. Para obter mais informações, veja [Certificado de usuário para autenticação local](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) na documentação do Windows Hello.  

  **Padrão**: não configurado

- **Usar chaves de segurança para entrar**  
  Essa configuração está disponível para dispositivos que executam o Windows 10 versão 1903 ou posterior. Use-o para gerenciar o suporte ao uso de chaves de segurança do Windows Hello para entrada.  

  - **Habilitado** -os usuários podem usar uma chave de segurança do Windows Hello como uma credencial de logon para PCs com essa política. 
  - **Desabilitado** -as chaves de segurança estão desabilitadas e os usuários não podem usá-las para entrar em PCs.   

  **Padrão**: não configurado

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../configuration/device-profile-assign.md) e [monitorar seu status](../configuration/device-profile-monitor.md).
