---
title: Configurar uma página de status de registro
titleSuffix: Microsoft Intune
description: Configure uma página de saudação para usuários que estão registrando dispositivos com Windows 10.
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
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0762c099d30cbeda37ffdaffcb0bed2091f7b9c1
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837077"
---
# <a name="set-up-an-enrollment-status-page"></a>Configurar uma página de status de registro
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Durante a instalação do dispositivo usando o Intune, a Página de Status do Registro exibe informações de instalação no dispositivo. Alguns aplicativos, perfis e certificados podem não estar instalados no momento em que um usuário conclui a entrada de registro inicial pelo usuário para o dispositivo. Uma página de status de registro pode ajudar os usuários a entender o status do dispositivo durante a configuração do dispositivo. Você pode criar perfis de página de status de vários registros e aplicá-los a grupos diferentes. Os perfis podem ser definidos como:
- Mostrar progresso da instalação.
- Bloquear uso até a instalação ser concluída.
- Especificar o que um usuário pode fazer se a configuração do dispositivo falhar.

Você também pode definir a ordem de prioridade para cada perfil para levar em conta atribuições de perfil conflitantes do mesmo usuário ou dispositivo.

 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Ativar a página de status de registro padrão para todos os usuários

Para ativar a página de status de registro, siga as etapas abaixo.
 
1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **página de Status de Registro (Versão Prévia)**.
2. Na folha **Página de Status de Registro**, escolha **Padrão** > **Configurações**.
3. Para **Mostrar o progresso da instalação do aplicativo e do perfil**, escolha **Sim**.
4. Escolha as outras configurações que você deseja ativar e, em seguida, escolha **Salvar**.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Criar perfil da página de status do registro e atribuir a um grupo

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Página de status de registro (Versão prévia)** > **Criar perfil**.
2. Forneça um **Nome** e uma **Descrição**.
3. Escolha **Criar**.
4. Escolha o novo perfil na lista **Página de status de registro**.
5. Escolha **Atribuições** > **Selecionar grupos** > escolha os grupos para os quais você deseja adotar esse perfil > **Selecionar** > **Salvar**.
6. Escolha **Configurações** > escolha as configurações que você deseja aplicar a este perfil > **Salvar**.

## <a name="set-the-enrollment-status-page-priority"></a>Definir a prioridade da página de status do registro

Um dispositivo ou usuário pode estar em vários grupos e ter vários perfis de página de status de registro. Para lidar com esses conflitos, você pode definir as prioridades para cada perfil. Se alguém tiver mais de um perfil de página de status de registro, apenas o perfil com a prioridade mais alta será aplicado.

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **página de Status de Registro (Versão Prévia)**.
2. Focalize o perfil na lista.
3. Usando os três pontos verticais, arraste o perfil para a posição desejada na lista.

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Bloquear o acesso a um dispositivo até que um aplicativo específico seja instalado

Você pode especificar quais aplicativos precisam ser instalados antes de o usuário poder acessar a área de trabalho.

1. No Intune, escolha **Registro de dispositivo** > **Registro do Windows** > **Página de Status de Registro (Versão Prévia)**.
2. Escolha um perfil > **Configurações**.
3. Escolha **Sim** para **Mostrar o andamento da instalação do perfil e de aplicativos**.
4. Escolha **Sim** para **Bloquear o uso do dispositivo até que todos os perfis e aplicativos estejam instalados**.
5. Escolha **Selecionado** para **Bloqueie o uso do dispositivo até que os aplicativos necessários sejam instalados, se eles estiverem atribuídos ao usuário/dispositivo**.
 6. Escolha **Selecionar aplicativos** > escolha os aplicativos > **Selecionar** > **Salvar**.

## <a name="enrollment-status-page-tracking-information"></a>Informações de acompanhamento da página de status do registro

A página de status rastreia informações para preparação do dispositivo, configuração do dispositivo e configuração da conta.

### <a name="device-preparation"></a>Preparação do dispositivo

Para a preparação do dispositivo, a página de status do registro rastreia testados de chave do TPM (Trusted Platform Module) (quando aplicável), o progresso no ingresso no Azure Active Directory e o registro no Intune.

### <a name="device-setup"></a>Configuração do dispositivo

Para a configuração do dispositivo, a página de status de registro controlará os seguintes itens se eles tiverem sido atribuídos a Todos os dispositivos:
- Políticas de segurança
    - Um CSP (provedor de serviço de configuração) para todos os registros.
    - CSPs reais configurados pelo Intune não são rastreados aqui.
- Aplicativos
    - Aplicativos MSI de LoB (linha de negócios) por computador.
    - Aplicativos de repositório de LoB com contexto de instalação = Dispositivo.
    - Aplicativos de repositório de LoB e repositório offline com contexto de instalação = Dispositivo.
- Perfis de conectividade
    - Perfis de Wi-Fi ou VPN atribuídos a **Todos os Dispositivos** ou um grupo de dispositivos do qual o dispositivo de registro é um membro, mas somente para dispositivos do Autopilot
- Perfis de certificado atribuídos a **Todos os Dispositivos** ou a um grupo de dispositivos do qual o dispositivo de registro é um membro, mas somente para dispositivos do Autopilot

### <a name="account-setup"></a>Configuração da conta
Para a configuração de conta, a página de status de registro rastreia os seguintes itens:
- Políticas de segurança
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
