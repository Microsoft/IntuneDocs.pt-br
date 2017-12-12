---
title: "Controlar as configurações do Windows Hello para Empresas em dispositivos"
description: "Saiba como o Intune é integrado ao Windows Hello para Empresas, um método de entrada alternativo que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, cartão inteligente ou cartão inteligente virtual."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b7b3ab8b266ed4699b6982c26aca173244dc19d0
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="control-windows-hello-for-business-settings-on-devices-with-microsoft-intune"></a>Controlar as configurações do Windows Hello para Empresas em dispositivos com o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune se integra com o Windows Hello para Empresas (antigo Microsoft Passport for Work), um método de entrada alternativo que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, cartão inteligente ou cartão inteligente virtual.

O Hello para Empresas permite que você use um *gesto de usuário* para entrar, em vez de uma senha. Um gesto do usuário pode ser um PIN simples, uma autenticação biométrica, como o Windows Hello, ou um dispositivo externo, como um leitor de impressão digital.

O Intune é integrado ao Hello para Empresas de duas maneiras:

-   Você pode usar uma política do Intune para controlar quais gestos os usuários podem e não podem usar para entrar.

-   Você pode armazenar certificados de autenticação no Windows Hello para Empresas para o KSP (provedor de armazenamento de chaves). Para obter mais informações, consulte [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado no Microsoft Intune).

> [!IMPORTANT]
> Nas versões do Windows 10 Desktop e Mobile anteriores à Atualização de Aniversário, você podia configurar dois PINs diferentes que poderiam ser usados para se autenticar nos recursos:
- O **PIN do dispositivo** poderia ser usado para desbloquear o dispositivo e conectar-se aos recursos de nuvem.
- O **PIN de trabalho** foi usado para acessar recursos do Azure AD em dispositivos pessoais do usuário (BYOD).

>Na Atualização de Aniversário, esses dois PINs foram mesclados em um único PIN do dispositivo.
Qualquer política de configuração do Intune definida para controlar o PIN do dispositivo e, além disso, qualquer política do Windows Hello para Empresas configurada; agora ambas definem esse novo valor do PIN.
Se você tiver definido os dois tipos de política para controlar o PIN, a política do Windows Hello para Empresas será aplicada nos dispositivos Windows 10 Desktop e Mobile.
Para garantir que os conflitos de política sejam resolvidos e que a política de PIN seja aplicada corretamente, atualize sua Política do Windows Hello para Empresas para que corresponda às configurações em sua política de configuração e solicite aos usuários que sincronizem seus dispositivos no aplicativo Portal da Empresa.



## <a name="create-a-windows-hello-for-business-policy"></a>Criar uma política do Windows Hello para Empresas

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows** &gt; **Windows Hello para Empresas** para abrir a página do Windows Hello para Empresas.

    ![Página do Windows Hello para Empresas](../media/passport.png)

2.  Escolha uma das seguintes configurações:
    - **Desabilitar o Windows Hello para Empresas em dispositivos registrados**. Se você não quiser usar o Windows Hello para Empresas, selecione esta configuração. Todas as outras configurações na tela ficam indisponíveis.
    - **Habilitar o Windows Hello para Empresas em dispositivos registrados**. Selecione essa configuração se você quiser configurar o Windows Hello para Empresas.
    - **Não configurado**. Selecione essa configuração se você não quiser usar o Intune para controlar as configurações do Windows Hello para Empresas. Qualquer configuração existente do Windows Hello para Empresas em dispositivos com Windows 10 não será alterada. Todas as outras configurações na tela ficam indisponíveis.
3.  Se você selecionou **Habilitar o Windows Hello para Empresas em dispositivos registrados**, defina as configurações necessárias que serão aplicadas a todos os dispositivos Windows 10 e Windows 10 Mobile registrados.
4.  Quando você terminar, escolha **Salvar**.


## <a name="settings-for-the-windows-hello-for-business-policy"></a>Configurações para a política do Windows Hello para Empresas

- **Usar o TPM (Trusted Platform Module)**. Um chip TPM fornece uma camada adicional de segurança de dados.<br>Selecione uma das seguintes opções:
    - **Obrigatório** (padrão). Somente dispositivos com um TPM acessível podem provisionar o Windows Hello para Empresas.
    - **Preferencial**. Primeira tentativa dos dispositivos para usar um TPM. Se não estiver disponível, eles podem usar criptografia de software.
- **Exigir tamanho mínimo do PIN**/**Exigir tamanho máximo do PIN**. Configura os dispositivos para usar os tamanhos mínimo e máximo do PIN especificados para ajudar a garantir a entrada segura. O comprimento padrão do PIN é de seis caracteres, mas você pode impor um comprimento mínimo de quatro caracteres. O comprimento máximo do PIN é de 127 caracteres.
- **Exigir letras minúsculas no PIN**/**Exigir letras maiúsculas no PIN**/**Exigir caracteres especiais no PIN**. Você pode impor um PIN mais forte exigindo o uso de letras maiúsculas, letras minúsculas e caracteres especiais no PIN. Escolha:
    - **Permitido**. Os usuários podem usar o tipo de caractere no seu PIN, mas não é obrigatório.
    - **Obrigatório**. Os usuários devem incluir pelo menos um dos tipos de caracteres em seu PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.
    - **Não permitido** (padrão). Os usuários não devem usar esses tipos de caractere no seu PIN. (Esse também é o comportamento se a configuração não estiver configurada.)<br>Os caracteres especiais incluem: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **Validade do PIN (dias)**. É uma boa prática especificar um período de expiração de um PIN após o qual os usuários devem alterá-lo. O padrão é 41 dias.
- **Lembrar histórico do PIN**. Restringe a reutilização de PINs usados anteriormente. Por padrão, os últimos 5 PINs não podem ser reutilizados.
- **Permitir autenticação biométrica**. Permite a autenticação biométrica, como reconhecimento facial ou impressão digital, como uma alternativa a um PIN do Windows Hello para Empresas. Os usuários ainda devem configurar um PIN de trabalho no caso de falha de autenticação biométrica. Escolha:
    - **Sim**. O Windows Hello para Empresas permite autenticação biométrica.
    - **Não**. O Windows Hello para Empresas impede a autenticação biométrica (para todos os tipos de conta).
- **Usar a antifalsificação avançada, quando disponível**. Define se as funcionalidades antifalsificação do Windows Hello são usadas em dispositivos que dão suporte a ele (por exemplo, detectando uma fotografia de um rosto, em vez do rosto real).<br>Se isso for definido como **Sim**, o Windows exige que todos os usuários usem a antifalsificação para recursos faciais quando houver suporte.
- **Usar a função entrar com o telefone**. Se essa opção for definida como **Sim**, os usuários poderão usar um passaporte remoto para servir como um dispositivo portátil complementar para autenticação de computador desktop. O computador desktop deve ter ingressado no Azure Active Directory e o dispositivo complementar deve ser configurado com um PIN do Windows Hello para Empresas.

## <a name="further-information"></a>Informações adicionais
Para obter mais informações sobre o Microsoft Passport, consulte [o guia](https://technet.microsoft.com/library/mt589441.aspx) na documentação do Windows 10.
