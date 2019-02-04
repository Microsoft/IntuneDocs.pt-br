---
title: Registrar dispositivos usando uma conta do gerenciador de registros de dispositivo
titlesuffix: Microsoft Intune
description: Use a conta do gerenciador de registros de dispositivo para registrar dispositivos no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: be348840df2e1d7864b0c1c57efbb7abcb698392
ms.sourcegitcommit: 6f2f2fa70f4e47fa5ad2f3c536ba7116e1bd1d05
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55199380"
---
# <a name="enroll-devices-in-intune-by-using-a-device-enrollment-manager-account"></a>Registrar dispositivos no Intune por meio do uso de uma conta do gerenciador de registro de dispositivos

Você pode registrar até 1.000 dispositivos móveis com uma única conta do Azure Active Directory usando uma conta do DEM (gerenciador de registros de dispositivo). O DEM é uma permissão do Intune que pode ser aplicada a uma conta de usuário do AAD e permite que o usuário registre até 1.000 dispositivos. Uma conta do DEM é útil para cenários em que os dispositivos são registrados e preparados antes de entregá-los aos usuários dos dispositivos.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitações de dispositivos registrados com uma conta do DEM

Contas de usuário e dispositivos do DEM registrados com uma conta de usuário do DEM têm as seguintes limitações:

  - O apagamento não pode ser feito do Portal da Empresa. O apagamento de um dispositivo registrado por uma conta de usuário do DEM pode ser feito do Intune no portal do Azure.
  - Somente o dispositivo local é exibido no aplicativo Portal da Empresa ou no site.
  - Contas de usuário do DEM não podem usar aplicativos VPP (Apple Volume Purchase Program) com licenças de usuário do Apple VPP devido aos requisitos de ID da Apple para gerenciamento de aplicativo.
  - Os dispositivos poderão instalar aplicativos se tiverem licenças de dispositivo do Apple VPP.
  - Os dispositivos estão bloqueados para Acesso Condicional, com exceção do Windows 10 1803+
  - Cada dispositivo registrado com uma conta do DEM deve ter sua própria licença de dispositivo do Intune.


## <a name="add-a-device-enrollment-manager"></a>Adicionar um gerenciador de registro de dispositivo

1.  No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Gerenciadores de registro de dispositivo**.

2.  Selecione **Adicionar**.

3.  Na folha **Adicionar Usuário**, insira um nome UPN para o usuário DEM e selecione **Adicionar**. O usuário DEM é adicionado à lista de usuários DEM.

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

