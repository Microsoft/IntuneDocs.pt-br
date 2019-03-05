---
title: Como integrar o Windows Hello para Empresas ao Microsoft Intune | Microsoft Intune
description: Saiba como criar uma política para controlar o uso do Windows Hello para Empresas em dispositivos gerenciados.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 7192c7fa5865a9b9928370d6348218ce0258b659
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237394"
---
# <a name="integrate-windows-hello-for-business-with-microsoft-intune"></a>Integrar o Windows Hello para Empresas com o Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Você pode integrar o Windows Hello para Empresas (anteriormente Microsoft Passport for Work) com o Microsoft Intune.

 O Hello for Business é um método de conexão alternativo que usa o Active Directory ou uma conta do Azure Active Directory, para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual. Ele permite que você use um *gesto do usuário* para entrar, em vez de uma senha. Um gesto do usuário pode ser um PIN simples, uma autenticação biométrica, como o Windows Hello, ou um dispositivo externo, como um leitor de impressão digital.

O Intune é integrado ao Hello para Empresas de duas maneiras:

-   Uma política do Intune pode ser criada em **Registro do dispositivo**. Essa política se destina a toda a organização (abrange todo o locatário). Ela dá suporte à OOBE (tela de apresentação) do Windows AutoPilot e é aplicada quando um dispositivo é registrado. 
-  Um perfil de proteção de identidade pode ser criado em **Configuração do dispositivo**. Esse perfil destina-se a usuários e dispositivos atribuídos e é aplicado durante o check-in. 

Use este artigo para criar uma política padrão do Windows Hello para Empresas direcionada à organização inteira. Para criar um perfil de proteção de identidade a ser aplicado a grupos de dispositivos e de usuários selecionados, confira [Configurar um perfil de proteção de identidade](identity-protection-configure.md).  

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> Nas versões do Windows 10 Desktop e Mobile anteriores à Atualização de Aniversário, você podia configurar dois PINs diferentes que poderiam ser usados para se autenticar nos recursos:
> - O **PIN do dispositivo** poderia ser usado para desbloquear o dispositivo e conectar-se aos recursos de nuvem.
> - O **PIN de trabalho** foi usado para acessar recursos do Azure AD em dispositivos pessoais do usuário (BYOD).
> 
> Na Atualização de Aniversário, esses dois PINs foram mesclados em um único PIN do dispositivo.
> Qualquer política de configuração do Intune definida para controlar o PIN do dispositivo e, além disso, qualquer política do Windows Hello para Empresas configurada; agora ambas definem esse novo valor do PIN.
> Se você definiu os dois tipos de política para controlar o PIN, a política do Windows Hello para Empresas será aplicada nos dispositivos de área de trabalho e dispositivos móveis do Windows 10.
> Para garantir que os conflitos de política sejam resolvidos e que a política de PIN seja aplicada corretamente, atualize sua Política do Windows Hello para Empresas para que corresponda às configurações em sua política de configuração e solicite aos usuários que sincronizem seus dispositivos no aplicativo Portal da Empresa.



## <a name="create-a-windows-hello-for-business-policy"></a>Criar uma política do Windows Hello para Empresas

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. No painel do Intune, escolha **Registro de dispositivo** e, em seguida, escolha **Registro do Windows** > **Windows Hello para Empresas**.

3. No painel que é aberto, escolha as configurações **Padrão**.

4. No painel **Todos os Usuários**, clique em **Propriedades** e, em seguida, insira um **Nome** e uma **Descrição** opcional para as configurações do Windows Hello para Empresas.

5. No painel **Todos os Usuários**, clique em **Configurações** e, em seguida, escolha entre as seguintes opções de **Configurar o Windows Hello para Empresas**:

    - **Desabilitada**. Se você não quiser usar o Windows Hello para Empresas, selecione esta configuração. Todas as outras configurações na tela ficam indisponíveis.
    - **Habilitada**. Selecione essa configuração se você quiser configurar o Windows Hello para Empresas.
    - **Não configurado**. Selecione essa configuração se você não quiser usar o Intune para controlar as configurações do Windows Hello para Empresas. As configurações existentes do Windows Hello para Empresas em dispositivos com Windows 10 não são alteradas. Nenhuma outra configuração no painel está disponível.

6. Se você selecionou **Habilitado** na etapa anterior, defina as configurações necessárias que serão aplicadas a todos os dispositivos Windows 10 e Windows 10 Mobile registrados.

   - **Usar o TPM (Trusted Platform Module)**. Um chip TPM fornece uma camada adicional de segurança de dados.<br>Selecione uma das seguintes opções:

     - **Obrigatório** (padrão). Somente dispositivos com um TPM acessível podem provisionar o Windows Hello para Empresas.
     - **Preferencial**. Primeira tentativa dos dispositivos para usar um TPM. Se não estiver disponível, eles podem usar criptografia de software.

   - **Tamanho mínimo do PIN**/**Tamanho máximo do PIN**. Configura os dispositivos para usar os tamanhos mínimo e máximo do PIN especificados para ajudar a garantir a entrada segura. O comprimento padrão do PIN é de seis caracteres, mas você pode impor um comprimento mínimo de quatro caracteres. O comprimento máximo do PIN é de 127 caracteres.

   - **Letras minúsculas no PIN**/**Letras maiúsculas no PIN**/**Caracteres especiais no PIN**. Você pode impor um PIN mais forte exigindo o uso de letras maiúsculas, letras minúsculas e caracteres especiais no PIN. Escolha:

     - **Permitido**. Os usuários podem usar o tipo de caractere no seu PIN, mas não é obrigatório.

     - **Obrigatório**. Os usuários devem incluir pelo menos um dos tipos de caracteres em seu PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

     - **Não permitido** (padrão). Os usuários não devem usar esses tipos de caractere no seu PIN. (Esse também é o comportamento se a configuração não estiver configurada.)<br>Os caracteres especiais incluem: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **Validade do PIN (dias)**. É uma boa prática especificar um período de expiração de um PIN após o qual os usuários devem alterá-lo. O padrão é 41 dias.

   - **Lembrar histórico do PIN**. Restringe a reutilização de PINs usados anteriormente. Por padrão, os últimos 5 PINs não podem ser reutilizados.

   - **Permitir autenticação biométrica**. Permite a autenticação biométrica, como reconhecimento facial ou impressão digital, como uma alternativa a um PIN do Windows Hello para Empresas. Os usuários ainda devem configurar um PIN de trabalho no caso de falha de autenticação biométrica. Escolha:

     - **Sim**. O Windows Hello para Empresas permite autenticação biométrica.
     - **Não**. O Windows Hello para Empresas impede a autenticação biométrica (para todos os tipos de conta).

   - **Usar a antifalsificação avançada, quando disponível**. Define se as funcionalidades antifalsificação do Windows Hello são usadas em dispositivos que dão suporte a ele (por exemplo, detectando uma fotografia de um rosto, em vez do rosto real).<br>Se isso for definido como **Sim**, o Windows exige que todos os usuários usem a antifalsificação para recursos faciais quando houver suporte.

   - **Permitir entrada de telefone**. Se essa opção for definida como **Sim**, os usuários poderão usar um passaporte remoto para servir como um dispositivo portátil complementar para autenticação de computador desktop. O computador desktop deve ter ingressado no Azure Active Directory e o dispositivo complementar deve ser configurado com um PIN do Windows Hello para Empresas.

## <a name="windows-holographic-for-business-support"></a>Compatibilidade do Windows Holographic for Business

O Windows Holographic for Business é compatível com as seguintes configurações do Windows Hello para Empresas:

- Usar o Trusted Platform Module (TPM)
- Tamanho mínimo do PIN
- Tamanho máximo do PIN
- Letras minúsculas no PIN
- Letras maiúsculas no PIN
- Caracteres especiais no PIN
- Término do PIN (dias)
- Lembrar do histórico do PIN

## <a name="further-information"></a>Informações adicionais
Para obter mais informações sobre o Microsoft Passport, consulte [o guia](https://technet.microsoft.com/library/mt589441.aspx) na documentação do Windows 10.
