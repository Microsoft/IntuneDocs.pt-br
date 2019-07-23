---
title: Adicionar proteção de ponto de extremidade no macOS no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos macOS, use o gatekeeper para determinar quais aplicativos podem ser instalados, incluindo a Mac App Store. Também habilite ou configure um firewall para permitir que aplicativos específicos, aplicativos de especificações de blocos, usem o modo oculto e até mesmo bloqueiem determinados tipos de conexões de entrada usando o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d110013c10f0330c0edbbf230c508009fb47b2a6
ms.sourcegitcommit: 11a31cd39b727f2254e2705b07d18924e103bd2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341319"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Configurações de proteção de ponto de extremidade do macOS no Intune  

Este artigo mostra as configurações de proteção de ponto de extremidade que você pode configurar para dispositivos que executam macOS. Você define essas configurações usando um perfil de configuração de dispositivo macOS para o [Endpoint Protection](endpoint-protection-configure.md) no Intune.  

## <a name="gatekeeper"></a>Gatekeeper  

- **Permitir que os aplicativos sejam baixados destes locais**  
  Limite os aplicativos que um dispositivo pode iniciar, dependendo de onde os aplicativos foram baixados. A intenção é proteger dispositivos contra malware e permitir aplicativos apenas de fontes confiáveis.  

  - **Não configurado**  
  - **Mac App Store**  
  - **Mac App Store e desenvolvedores identificados**  
  - **Qualquer lugar**  

  **Padrão**: não configurado  

- **O usuário pode substituir o gatekeeper**  
  Impede os usuários de ignorar a configuração do Gatekeeper e de clicar em Ctrl para instalar um aplicativo. Quando habilitado, os usuários podem clicar em CTRL em qualquer aplicativo e instalá-lo.  
 
  - **Não configurado** -os usuários podem controlar e clicar para instalar aplicativos.  
  - **Bloquear** – impede que os usuários usem o controle-clique para instalar aplicativos.  

  **Padrão**: não configurado  

## <a name="firewall"></a>Firewall  

Use o firewall para controlar conexões por aplicativo, em vez de por porta. Usar as configurações por aplicativo torna mais fácil aproveitar os benefícios da proteção de firewall. Também ajuda a impedir que aplicativos indesejáveis assumam o controle de portas de rede abertas para aplicativos legítimos.  

**Geral**
- **Firewall**  
  Habilite o Firewall para configurar como as conexões de entrada são tratadas em seu ambiente.  
  - **Não configurado**  
  - **Habilitar**  

  **Padrão**: não configurado  

- **Conexões de entrada**  
  Bloqueie todas as conexões de entrada, exceto as necessárias para serviços básicos da Internet, como DHCP, Bonjour e IPsec. Esse recurso também bloqueia todos os serviços de compartilhamento, como Compartilhamento de Arquivos e Compartilhamento de Tela. Se você estiver usando serviços de compartilhamento, mantenha essa configuração como *Não configurada*.  
  - **Não configurado**  
  - **Bloquear**  

  **Padrão**: não configurado  

**Permitir ou bloquear conexões de entrada para aplicativos específicos.**  

  - **Aplicativos permitidos**  
    Selecione os aplicativos que explicitamente têm permissão para receber conexões de entrada.  

  - **Aplicativos bloqueados**  
    Selecione os aplicativos que devem bloquear conexões de entrada.  

  - **Modo oculto**  
    Para impedir que o computador responda a solicitações de investigação, habilite o modo oculto. O dispositivo continua a responder a solicitações de entrada para aplicativos autorizados. Solicitações inesperadas, como o ICMP (ping), são ignoradas.  
    - **Não configurado**  
    - **Habilitar**  

    **Padrão**: não configurado  

## <a name="filevault"></a>FileVault  
Para obter mais informações sobre as configurações do Apple FileVault, consulte [FDEFileVault](https://developer.apple.com/documentation/devicemanagement/fdefilevault) no conteúdo do desenvolvedor da Apple. 

- **FileVault**  
  Você pode *habilitar* a criptografia de disco completa usando o XTS-AES 128 com o FileVault em dispositivos que executam o MacOS 10,13 e posterior.  
  - **Não configurado**  
  - **Habilitar**  

  **Padrão**: não configurado  

  - **Tipo de chave de recuperação**  
    Chaves de recuperação de *chave pessoal* são criadas para dispositivos. Defina as configurações a seguir para a chave pessoal.  

     - **Local da chave de recuperação pessoal** – especifique uma mensagem curta para o usuário que explica como eles podem recuperar sua chave de recuperação pessoal. Esse texto é inserido na mensagem que o usuário vê ao habilitar o FileVault.  
      
     - **Rotação de chave de recuperação pessoal** – especifique com que frequência a chave de recuperação pessoal de um dispositivo será girada. Você pode selecionar o padrão **não configurado**ou um valor de **1** a **12** meses.  

  - **Adiar FileVault até sair** 
    > [!NOTE]
    > O suporte para FileVault é limitado até que a versão de julho conclua a distribuição em alguns dias. Até que a distribuição seja concluída, se você configurar o FileVault, você deverá definir *Defer FileVault até que a saída* seja **habilitada**.   

    FileVault não será habilitado até que o usuário saia. Um usuário local ou usuário de conta móvel será solicitado a habilitar o FileVault na saída ou na próxima entrada.  
    - **Não configurado**  
    - **Habilitar**  
    
    **Padrão**: não configurado  



    - **Desabilitar aviso ao sair**  
      Impedir o prompt para o usuário que solicita que eles habilitem o FileVault quando eles se desconectarem.  
      - **Não configurado**  
      - **Habilitar**  

      **Padrão**: não configurado  

    - **Número de vezes com permissão para ignorar**  
      Defina o número de vezes que um usuário pode ignorar prompts para habilitar FileVault antes que FileVault seja necessário para que o usuário entre.  

      - **Não configurado** -a criptografia no dispositivo é necessária antes que a próxima entrada seja permitida.  
      -  **1** a **10** -permite que um usuário ignore o prompt de 1 a 10 vezes antes de exigir a criptografia no dispositivo.  
      - **Sem limite, sempre avisar** -o usuário é solicitado a habilitar FileVault, mas a criptografia nunca é necessária.  
 
      **Padrão**: não configurado  


