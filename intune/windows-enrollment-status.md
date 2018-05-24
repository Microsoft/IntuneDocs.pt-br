---
title: Configurar uma página de status de registro
titleSuffix: Microsoft Intune
description: Saúde seus usuários que estão registrando dispositivos Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/17/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6604c35cebdad4341f27a51db1a4c735f9a9818
ms.sourcegitcommit: 6bd5867c41fb5288fde114dbfcc127dd206f7148
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="set-up-an-enrollment-status-page"></a>Configurar uma página de status de registro
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Durante a instalação do dispositivo, a página de status do registro exibe informações de status de instalação no dispositivo do usuário final. Alguns aplicativos, perfis e certificados podem não estar totalmente instalados no momento em que um usuário é registrado. A página de status pode ajudar os usuários a entender o status dos dispositivos durante e após o registro. Você pode ativar a página de status para todos os usuários, bem como impedir que os usuários usem o dispositivo até que todos os aplicativos atribuídos e os perfis estejam instalados.
 
Para ativar a página de status de registro para todos os usuários finais, siga as etapas abaixo.
 
1.  No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **página de Status de Registro (Versão Prévia)**.
2.  Na folha **Página de Status de Registro**, escolha **Padrão** > **Configurações**.
3.  Para **Mostrar o progresso da instalação do aplicativo e do perfil**, escolha **Sim**.
4.  Escolha as outras configurações que você deseja ativar e, em seguida, escolha **Salvar**.
 
## <a name="enrollment-status-page-tracking-information"></a>Informações de acompanhamento da página de status do registro

A página de status rastreia informações para preparação do dispositivo, configuração do dispositivo e configuração da conta.

### <a name="device-preparation"></a>Preparação do dispositivo

Para a preparação do dispositivo, a página de status do registro rastreia testados de chave do TPM (Trusted Platform Module) (quando aplicável), o progresso no ingresso no Azure Active Directory e o registro no Intune.

### <a name="device-setup"></a>Configuração do dispositivo

Para a configuração do dispositivo, a página de status do registro rastreará os seguintes itens se eles tiverem sido atribuídos a Todos os Dispositivos:
- Diretivas de segurança
    - Um CSP (provedor de serviço de configuração) para todos os registros.
    - CSPs reais configurados pelo Intune não são rastreados aqui.
- Aplicativos
    - Aplicativos MSI de LoB (linha de negócios) por computador.
    - Aplicativos de repositório de LoB com contexto de instalação = Dispositivo.
    - Aplicativos de repositório de LoB e repositório offline com contexto de instalação = Dispositivo.
- Perfis de conectividade (VPN e Wi-Fi) ainda não são rastreados, assim, eles sempre dirão "0 de 0".
- Certificados ainda não são rastreados, de modo que sempre dirão "0 de 0".

### <a name="account-setup"></a>Configuração da conta
Para a configuração de conta, a página de status de registro rastreia os seguintes itens:
- Diretivas de segurança
    - Um CSP para todos os registros.
    - CSPs reais configurados pelo Intune não são rastreados aqui.
- Aplicativos
    - Aplicativos MSI de LoB por usuário atribuídos a Todos os Dispositivos, Todos os Usuários ou a um grupo de usuário do qual o usuário que está registrando o dispositivo é membro.
    - Aplicativos MSI de LoB por computador atribuídos a Todos os Usuários ou a um grupo de usuários do qual o dispositivo de registro de usuário é membro.
    - Aplicativos de repositório de LoB atribuídos a Todos os Dispositivos, Todos os Usuários ou a um grupo de usuário do qual o usuário que está registrando o dispositivo é membro com o contexto de instalação = Usuário.
    - Aplicativos de repositório online atribuídos a Todos os Dispositivos, Todos os Usuários ou a um grupo de usuário do qual o usuário que está registrando o dispositivo é membro com o contexto de instalação = Usuário.
    - Aplicativos de repositório offline atribuídos a Todos os Dispositivos, Todos os Usuários ou a um grupo de usuário do qual o usuário que está registrando o dispositivo é membro com o contexto de instalação = Usuário.
- Perfis de conectividade
    - Perfis de Wi-Fi ou VPN atribuídos a Todos os Usuários ou a um grupo de usuários do qual o usuário que está registrando o dispositivo é membro.
- Certificados
    - Perfis de certificado atribuídos a Todos os Usuários ou a um grupo de usuários do qual o usuário que está registrando o dispositivo é membro.

## <a name="next-steps"></a>Próximas etapas
Depois de configurar páginas de registro do Windows, saiba como gerenciar dispositivos do Windows. Para saber mais, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](https://docs.microsoft.com/intune/device-management)