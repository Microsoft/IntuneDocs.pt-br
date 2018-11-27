---
title: Definir configurações de proteção de identidade no Microsoft Intune – Azure | Microsoft Docs
description: Adicionar um perfil de dispositivo para definir as configurações do Windows Hello para Empresas em dispositivos Windows 10 no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f9d0db8e15e6de1241984f98bf651fcff1578033
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188615"
---
# <a name="configure-identity-protection-settings-in-microsoft-intune"></a>Definir configurações de proteção de identidade no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Os perfis de proteção de identidade controlam como o Windows Hello para Empresas é provisionado e configurado em dispositivos Windows 10 gerenciados. Crie esse perfil para configurar:  
* A disponibilidade do Windows Hello para Empresas para dispositivos e usuários.
* Os requisitos de PIN do dispositivo.
* Os gestos que os usuários podem e não podem usar para entrar em seus dispositivos.  

 Você pode atribuir esse perfil para selecionar grupos de usuários e de dispositivos, ou para todos os usuários e todos os dispositivos. Os grupos recebem o perfil de proteção de identidade quando fazem check-in no Intune.    

Use as informações neste artigo para criar um perfil de proteção de identidade. Em seguida, [atribua o perfil](device-profile-assign.md) a grupos de usuários e de dispositivos.

Esse recurso aplica-se a dispositivos que executam:  
- Windows 10 e posterior
- Windows Holographic for Business  

## <a name="create-a-device-profile-with-identity-protection-settings"></a>Criar um perfil de dispositivo com configurações de proteção de identidade

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
4. Insira um **Nome** e uma **Descrição** para o perfil de proteção de identidade.
5. Na lista suspensa **Plataforma**, escolha **Windows 10 e posterior**. O Windows Hello para Empresas apenas é compatível com dispositivos que executam o Windows 10 e posteriores.
6. Na lista suspensa **Tipo de perfil**, escolha **Proteção de identidade**.
7. No painel do Windows Hello para Empresas, escolha entre as seguintes opções para configurar o Windows Hello para Empresas:
    * Desabilitado. Se você não quiser usar o Windows Hello para Empresas, selecione esta configuração. Todas as outras configurações na tela ficam indisponíveis.
    * Habilitado. Selecione essa configuração se você quiser configurar o Windows Hello para Empresas.  

8. Se você selecionou **Habilitado** na etapa anterior, defina as configurações necessárias que serão aplicadas aos usuários e dispositivos Windows 10 e Windows 10 Mobile registrados.

> [!NOTE]
> Durante a atribuição de perfis de proteção de identidade somente a usuários, o contexto do dispositivo padrão é **Não configurado**.  

   - **Tamanho mínimo do PIN**/**Tamanho máximo do PIN**. Configura os dispositivos para usar os tamanhos mínimo e máximo do PIN especificados para ajudar a garantir a entrada segura. O comprimento padrão do PIN é de seis caracteres, mas você pode impor um comprimento mínimo de quatro caracteres. O comprimento máximo do PIN é de 127 caracteres.  

   - **Letras minúsculas no PIN**/**Letras maiúsculas no PIN**/**Caracteres especiais no PIN**. Você pode impor um PIN mais forte exigindo o uso de letras maiúsculas, letras minúsculas e caracteres especiais no PIN. Escolha:

     - **Permitido**. Os usuários podem usar o tipo de caractere no seu PIN, mas não é obrigatório.

     - **Obrigatório**. Os usuários devem incluir pelo menos um dos tipos de caracteres em seu PIN. Por exemplo, é uma prática comum exigir pelo menos uma letra maiúscula e um caractere especial.

     - **Não permitido** (padrão). Os usuários não devem usar esses tipos de caractere no seu PIN. (Esse comportamento também ocorre quando a configuração não está definida.)<br>Os caracteres especiais incluem: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **Validade do PIN (dias)**. É uma boa prática especificar um período de expiração de um PIN após o qual os usuários devem alterá-lo. O padrão é 41 dias.

   - **Lembrar histórico do PIN**. Restringe a reutilização de PINs usados anteriormente. Por padrão, os últimos 5 PINs não podem ser reutilizados.  
   - **Habilitar recuperação PIN**: permite que o usuário altere o PIN usando o serviço de recuperação de PIN do Windows Hello para Empresas. 
       - **Habilitar**. O serviço de nuvem criptografa um segredo de recuperação de PIN a ser armazenado no dispositivo. O usuário pode alterar o PIN, se necessário.  
       - **Não configurado** (padrão). Não é criado nem armazenado um segredo de recuperação de PIN. Se o PIN do usuário for esquecido, a única maneira de obter um novo PIN será excluindo o PIN existente e criando um novo. O usuário precisará registrar-se novamente em algum serviço para o qual o PIN antigo fornece acesso.  
   
   - **Usar o TPM (Trusted Platform Module)**. Um chip TPM fornece uma camada adicional de segurança de dados. Selecione uma das seguintes opções:  
     - **Habilitar**. Somente dispositivos com um TPM acessível podem provisionar o Windows Hello para Empresas.
     - **Não configurado**. Todos os dispositivos podem provisionar o Windows Hello para Empresas, mesmo quando não há um TPM utilizável. Primeiro os dispositivos tentarão usar um TPM, mas, se não houver nenhum disponível, eles poderão usar a criptografia de software.  

   - **Permitir autenticação biométrica**. Permite a autenticação biométrica, como reconhecimento facial ou impressão digital, como uma alternativa a um PIN do Windows Hello para Empresas. Os usuários ainda devem configurar um PIN de trabalho no caso de falha de autenticação biométrica. Escolha:

     - **Habilitar**. O Windows Hello para Empresas permite autenticação biométrica.
     - **Não configurado** (padrão). O Windows Hello para Empresas impede a autenticação biométrica (para todos os tipos de conta).

   - **Usar a antifalsificação avançada, quando disponível**. Define se as funcionalidades antifalsificação do Windows Hello são usadas em dispositivos que dão suporte a ele (por exemplo, detectando uma fotografia de um rosto, em vez do rosto real).
       - **Habilitar**. O Windows requer que todos os usuários usem a antifalsificação para recursos de rosto quando há suporte.  
       - **Não configurado** (padrão). O Windows respeita as configurações antifalsificação do dispositivo.

   - **Certificado para recursos locais**. 
       - **Habilitar**. Permite que o Windows Hello para Empresas use certificados para autenticar-se em recursos locais.
       - **Não configurado** (padrão). Impede que Windows Hello para Empresas use certificados para autenticar-se em recursos locais.  
9. Clique em **OK** para salvar o perfil.  

O perfil é criado e aparece na lista **Configuração do dispositivo – perfis**. Para continuar e atribuir esse perfil a grupos, confira [Como atribuir perfis de dispositivo](device-profile-assign.md).  

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
