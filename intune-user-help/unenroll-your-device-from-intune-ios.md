---
title: Remover o registro do dispositivo iOS no Intune | Microsoft Docs
description: Descreve como remover um dispositivo iOS do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 28914db1-3e62-45f5-9632-b0d2a808a44d
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 0a90cace32edb33293ba0b0b89d272465ea32418
ms.sourcegitcommit: 07528df71460589522a2e1b3e5f9ed63eb773eea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34547481"
---
# <a name="remove-your-ios-device-from-intune"></a>Remover seu dispositivo iOS do Intune

Quando você remover o dispositivo iOS do Intune, o dispositivo não poderá mais acessar recursos da empresa e não será mais gerenciado pelo Intune.


## <a name="removing-the-device-from-my-devices"></a>Remover o dispositivo do Meus Dispositivos

Para remover seu dispositivo do Intune, use estas etapas ou assista a este vídeo:


1.  No aplicativo de Portal da Empresa, toque em **Dispositivos.** e selecione o dispositivo cujo registro você deseja cancelar. Se você tiver somente um dispositivo, ao tocar em **Dispositivos**, você irá diretamente para a tela de detalhes do dispositivo.

2.  Ao lado de **RENOMEAR**, toque no botão de reticências > **Remover Dispositivo** > **Remover**.  

    |![Captura de tela da tela de Dispositivos do aplicativo Portal da Empresa, mostrando opções depois de o usuário clicar em Remover. Mostra os botões "Remover Dispositivo", "Redefinição de Fábrica" e "Cancelar".](/intune-user-help/media/cp_ios_unenroll_after_1804_001.png)|

    |![Captura de tela da tela de Dispositivos do aplicativo Portal da Empresa, mostrando opções depois de o usuário clicar no botão Remover Dispositivo. Mostra o botão "Remover" destacado em vermelho, o botão "Saiba Mais" destacado em azul e o botão "Cancelar".](/intune-user-help/media/cp_ios_unenroll_after_1804_002.png)|


  Quando você cancela o registro de dispositivo do Intune, o seguinte acontece:

  -   Seu dispositivo não aparecerá mais no portal da empresa.

  -   Você não poderá mais instalar aplicativos do portal da empresa.

  -   Quaisquer configurações alteradas no seu dispositivo quando ele foi adicionado, por exemplo a desabilitação da câmera ou a solicitação de uma senha de determinado tamanho, não se aplicarão mais.

  -   Talvez você não tenha mais acesso a alguns recursos da empresa, como compartilhamentos de arquivos ou sites internos, no seu dispositivo.

  -   Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.

  -   Talvez você não consiga mais se conectar à rede da empresa usando o Wi-Fi ou uma rede virtual privada (VPN).

  -   Perfis de email da empresa são removidos do dispositivo.

  -   Dispositivos que são configurados somente para email não aparecerão mais no site ou no aplicativo do portal da empresa.
  
  -   Aplicativos são desinstalados. Dados de aplicativo da empresa são removidos.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Removendo os dados coletados pelo aplicativo Portal da Empresa

Há três locais em que o Portal da Empresa armazena dados locais no seu dispositivo.

-   **Logs de informações**: dados de atividade de aplicativo padrão que a Microsoft coleta, como há quanto tempo o aplicativo foi aberto ou se está em estado de falha, são automaticamente apagados quando você remove o dispositivo do Portal da Empresa.

-   **Análise da Apple**: dados de atividade de falha de aplicativo padrão que a Apple coleta. Essas informações podem ser removidas apenas redefinindo o dispositivo de volta às configurações de fábrica. Isso apagará todas as informações pessoais em seu dispositivo. Para fazer isso, abra **Configurações** > **Geral** > **Redefinir** > **Apagar todo o conteúdo e as configurações de**.

-   **Conjunto de chaves**: o dispositivo armazena suas senhas e outras informações utilizadas para entrada no seu Conjunto de chaves. Os aplicativos da Microsoft compartilham as informações de conexão com todos os aplicativos desenvolvidos pela Microsoft que você tem em seu dispositivo, incluindo o Microsoft Outlook e o Microsoft Authenticator. Como a análise da Apple, essas informações podem ser removidas apenas redefinindo o dispositivo de volta às configurações de fábrica. Isso apagará todas as informações pessoais em seu dispositivo. Para fazer isso, abra **Configurações** > **Geral** > **Redefinir** > **Apagar todo o conteúdo e as configurações de**.


Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
