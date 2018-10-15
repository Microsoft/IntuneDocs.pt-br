---
title: Configurar uma página de status de registro
titleSuffix: Microsoft Intune
description: Saúde seus usuários que estão registrando dispositivos Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5460db2d646d8bd417baa50d8188acbf69a251d
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48827982"
---
# <a name="set-up-an-enrollment-status-page"></a>Configurar uma página de status de registro
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Durante a instalação do dispositivo, a página de status do registro exibe informações de instalação no dispositivo. Alguns aplicativos, perfis e certificados podem não estar totalmente instalados no momento em que um usuário é registrado. A página de status pode ajudar os usuários a entender o status do dispositivo durante e após o registro. É possível ativar a página de status para todos os usuários ou criar perfis para direcionar grupos de usuários específicos.  É possível definir os perfis para mostrar o progresso da instalação, bloquear o uso até a conclusão da instalação, permitir redefinições e assim por diante.
 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Ativar a página de status de registro padrão para todos os usuários

Para ativar a página de status de registro para todos os usuários finais, siga as etapas abaixo.
 
1.  No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **página de Status de Registro (Versão Prévia)**.
2.  Na folha **Página de Status de Registro**, escolha **Padrão** > **Configurações**.
3.  Para **Mostrar o progresso da instalação do aplicativo e do perfil**, escolha **Sim**.
4.  Escolha as outras configurações que você deseja ativar e, em seguida, escolha **Salvar**.

## <a name="create-enrollment-status-page-profile-to-target-specific-users"></a>Criar perfil de página de status de registro para direcionar usuários específicos

1.  No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Página de status de registro (Versão prévia)** > **Criar perfil**.
2. Forneça um **Nome** e uma **Descrição**.
3. Escolha **Criar**.
4. Escolha o novo perfil na lista **Página de status de registro**.
5. Escolha **Atribuições** > **Selecionar grupos** > escolha os grupos para os quais você deseja adotar esse perfil > **Selecionar** > **Salvar**.
6. Escolha **Configurações** > escolha as configurações que você deseja aplicar a este perfil > **Salvar**.


## <a name="enrollment-status-page-tracking-information"></a>Informações de acompanhamento da página de status do registro

A página de status rastreia informações para preparação do dispositivo, configuração do dispositivo e configuração da conta.

### <a name="device-preparation"></a>Preparação do dispositivo

Para a preparação do dispositivo, a página de status do registro rastreia testados de chave do TPM (Trusted Platform Module) (quando aplicável), o progresso no ingresso no Azure Active Directory e o registro no Intune.

### <a name="device-setup"></a>Configuração do dispositivo

Para a configuração do dispositivo, a página de status de registro controlará os seguintes itens se eles tiverem sido atribuídos a Todos os dispositivos:
- Diretivas de segurança
    - Um CSP (provedor de serviço de configuração) para todos os registros.
    - CSPs reais configurados pelo Intune não são rastreados aqui.
- Aplicativos
    - Aplicativos MSI de LoB (linha de negócios) por computador.
    - Aplicativos de repositório de LoB com contexto de instalação = Dispositivo.
    - Aplicativos de repositório de LoB e repositório offline com contexto de instalação = Dispositivo.
- Os perfis de conectividade (VPN e Wi-Fi) ainda não são rastreados; portanto, sempre dirão "0 de 0".
- Os certificados ainda não são rastreados; portanto, sempre dirão "0 de 0".

### <a name="account-setup"></a>Configuração da conta
Para a configuração de conta, a página de status de registro rastreia os seguintes itens:
- Diretivas de segurança
    - Um CSP para todos os registros.
    - CSPs reais configurados pelo Intune não são rastreados aqui.
- Aplicativos
    - Aplicativos MSI de LoB por usuário atribuídos a Todos os Dispositivos, Todos os Usuários ou a um grupo de usuário do qual o usuário que está registrando o dispositivo é membro.
    - Aplicativos MSI de LoB por computador atribuídos a Todos os Usuários ou a um grupo de usuários do qual o dispositivo de registro de usuário é membro.
    - Os aplicativos de armazenamento LoB, online e offline estão atribuídos a qualquer um dos seguintes:
        - Todos os Dispositivos
        - Todos os Usuários
        - um grupo de usuários no qual o usuário que está registrando o dispositivo é um membro com contexto de instalação definido como usuário.
- Perfis de conectividade
    - Perfis de Wi-Fi ou VPN atribuídos a Todos os Usuários ou a um grupo de usuários do qual o usuário que está registrando o dispositivo é membro.
- Certificados
    - Perfis de certificado atribuídos a Todos os Usuários ou a um grupo de usuários do qual o usuário que está registrando o dispositivo é membro.

## <a name="next-steps"></a>Próximas etapas
Depois de configurar páginas de registro do Windows, saiba como gerenciar dispositivos do Windows. Para saber mais, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](https://docs.microsoft.com/intune/device-management)