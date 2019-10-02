---
title: Registrar dispositivos usando uma conta do gerenciador de registros de dispositivo
titleSuffix: Microsoft Intune
description: Use a conta do gerenciador de registros de dispositivo para registrar dispositivos no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cbfe0e30794ddfe5b2f089d50456f9cbdd031e6d
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723314"
---
# <a name="enroll-devices-in-intune-by-using-a-device-enrollment-manager-account"></a>Registrar dispositivos no Intune por meio do uso de uma conta do gerenciador de registro de dispositivos

Você pode registrar até 1.000 dispositivos móveis com uma única conta do Azure Active Directory usando uma conta do DEM (gerenciador de registros de dispositivo). O DEM é uma permissão do Intune que pode ser aplicada a uma conta de usuário do AAD e permite que o usuário registre até 1.000 dispositivos. Uma conta do DEM é útil para cenários em que os dispositivos são registrados e preparados antes de entregá-los aos usuários dos dispositivos. Por design, há um limite de 25 contas do DEM (Gerenciador de Registros de Dispositivo) no Microsoft Intune.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitações de dispositivos registrados com uma conta do DEM

Contas de usuário e dispositivos do DEM registrados com uma conta de usuário do DEM têm as seguintes limitações:

- um usuário de conta do DEM deve receber uma licença do Intune.
- O apagamento não pode ser feito do Portal da Empresa. O apagamento de um dispositivo registrado por uma conta de usuário do DEM pode ser feito do Intune no portal do Azure.
- Somente o dispositivo local é exibido no aplicativo Portal da Empresa ou no site.
- Contas de usuário do DEM não podem usar aplicativos VPP (Apple Volume Purchase Program) com licenças de usuário do Apple VPP devido aos requisitos de ID da Apple para gerenciamento de aplicativo.
- Os dispositivos poderão instalar aplicativos se tiverem licenças de dispositivo do Apple VPP.
- Os dispositivos estão bloqueados para Acesso Condicional, com exceção do Windows 10 1803+
- Cada dispositivo registrado em contas do DEM precisa ser corretamente licenciado para ser gerenciado pelo Intune. A licença poderia ser uma licença de usuário ou de dispositivo do Intune.
- Se você fizer o [registro de dispositivos de perfil de trabalho do Android Enterprise](android-work-profile-enroll.md) usando uma conta de DEM, haverá um limite de 10 dispositivos que podem ser registrados por conta.


## <a name="add-a-device-enrollment-manager"></a>Adicionar um gerenciador de registro de dispositivo

1. No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Gerenciadores de registro de dispositivo**.

2. Selecione **Adicionar**.

3. Na folha **Adicionar Usuário**, insira um nome UPN para o usuário DEM e selecione **Adicionar**. O usuário DEM é adicionado à lista de usuários DEM.

## <a name="permissions-for-dem"></a>Permissões para o DEM

As funções do Azure AD de Administrador Global ou Administrador de Serviços do Intune são necessárias para
- atribuir permissão de DEM a uma conta de usuário do Azure AD
- ver todos os usuários do DEM

Se um usuário não tiver a função Administrador Global ou Administrador de Serviços do Intune atribuída, mas tiver permissões de leitura habilitadas para a função Gerentes de Registro de Dispositivo atribuída a ele, poderá ver apenas os usuários do DEM que ele criou.


## <a name="remove-device-enrollment-manager-permissions"></a>Remover permissões do gerenciador de registros de dispositivo

Remover um gerenciador de registros de dispositivos não afeta os dispositivos registrados.

**Para remover um gerenciador de registro de dispositivo**

1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** e, em seguida, selecione **Gerentes de registro de dispositivo**.
2. Na folha **Gerenciadores de registro de dispositivo**, selecione o usuário DEM e selecione **Excluir**.
