---
title: Como remover seu dispositivo Android no Intune | Microsoft Docs
description: Descreve como cancelar o registro de um dispositivo Android do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d932005c955afed7f16e9766b559b77b2cd43182
ms.sourcegitcommit: 604b29c480b24270b5debc3e5f3141c8149ee6ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49959478"
---
# <a name="unenroll-your-android-device-from-management"></a>Cancelar o registro do dispositivo Android do gerenciamento  

Remova um dispositivo Android registrado para que ele não seja gerenciado pela sua organização. Este artigo descreve como remover o dispositivo do aplicativo Portal da Empresa. Depois de remover o dispositivo:  

* O dispositivo perde o acesso aos recursos e dados protegidos da sua organização.
* O dispositivo não aparecerá mais no Portal da Empresa.
* Você não poderá instalar aplicativos do Portal da Empresa.
* Qualquer configuração que tiver sido alterada em seu dispositivo quando você o adicionou (por exemplo, desabilitar a câmera ou exigir uma senha com determinado tamanho) não se aplicará mais.  

1. No Portal da Empresa, vá para o canto superior direito e toque nos três pontos verticais. Abre o menu de ação é aberto.

   ![Uma imagem do aplicativo do Portal da Empresa do Android, com o menu de ação aberto no canto superior direito. A nova opção “Remover o Portal da Empresa” está disponível como a terceira opção, sob “Meu perfil” e “Configurações” e acima de “Termos e condições”, “Ajuda e comentários” e “Sobre”.](./media/android_remove_cp_menu_action_after_1705.png)

2. Toque em **Remover o Portal da Empresa**.  

3. Será exibida uma mensagem com informações sobre o que acontece depois que você cancela o registro do seu dispositivo. Toque em **OK** para confirmar que você deseja remover o dispositivo do Portal da Empresa.

   ![Uma imagem da caixa de diálogo de confirmação, que está disponível após a seleção da nova opção “Remover o Portal da Empresa” no menu de ação. A caixa de diálogo informa o usuário do seguinte: “Ao remover o Portal da Empresa, seu dispositivo não será mais gerenciado pelo suporte de sua empresa e isso poderá remover o acesso a dados, aplicativos e email da empresa”. Em seguida, ela solicita ao usuário que confirme se deseja remover o aplicativo do Portal da Empresa com a seleção de “Sim”.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Removendo os dados coletados pelo aplicativo Portal da Empresa  

Para remover todos os dados que o aplicativo Portal da Empresa para Android armazena no seu dispositivo:

-   Limpe os dados do aplicativo em Aplicativos -> Clique no aplicativo -> botão "Limpar dados"
-   Exclua a pasta '\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal'

## <a name="uninstall-the-company-portal-app"></a>Desinstalar o aplicativo Portal da Empresa  
O Portal da Empresa é um aplicativo de gerenciamento de dispositivo, portanto, não pode ser desinstalada até você [cancelar o registro do seu dispositivo do seu gerenciamento](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management). Depois que for concluído, toque e segure o ícone do aplicativo Portal da Empresa até ver **Desinstalar**. Toque em **Desinstalar** para remover o aplicativo do dispositivo.  

Como alternativa, toque em **Configurações** > **Aplicativos** > **Portal da Empresa** > **Desinstalar**.  

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter informações de contato, confira o [site Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980)
