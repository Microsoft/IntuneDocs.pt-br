---
title: Como remover seu dispositivo Android no Intune | Microsoft Docs
description: Descreve como cancelar o registro de um dispositivo Android do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
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
ms.openlocfilehash: ec3c0a1c8ce4e04f4d23fb01e7c2525d8f2eed5b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31018355"
---
# <a name="how-to-remove-your-android-device-from-intune"></a>Como remover seu dispositivo Android do Intune

Ao remover seu dispositivo Android do Intune, você não poderá mais acessar os recursos da empresa.  Para obter mais informações sobre o que acontece quando você remove um dispositivo do gerenciamento, veja [O que acontece se você cancela o registro do seu dispositivo do Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

## <a name="removing-the-device-from-the-company-portal-app"></a>Removendo o dispositivo do aplicativo Portal da Empresa

Para remover seu dispositivo do Intune e o aplicativo do Portal da Empresa, siga estas etapas:

1. Abra o **menu de ação** tocando nos três pontos verticais no canto superior direito do aplicativo do Portal da Empresa.

   ![Uma imagem do aplicativo do Portal da Empresa do Android, com o menu de ação aberto no canto superior direito. A nova opção “Remover o Portal da Empresa” está disponível como a terceira opção, sob “Meu perfil” e “Configurações” e acima de “Termos e condições”, “Ajuda e comentários” e “Sobre”.](./media/android_remove_cp_menu_action_after_1705.png)

2. Toque em **Remover o Portal da Empresa**.

3. Uma confirmação será exibida, perguntando se você tem certeza de que deseja remover o Portal da Empresa. Ela fornecerá algumas informações sobre o que acontece quando você cancela o registro de seu dispositivo. Depois de ler essa mensagem, toque em **OK** para remover o aplicativo.

   ![Uma imagem da caixa de diálogo de confirmação, que está disponível após a seleção da nova opção “Remover o Portal da Empresa” no menu de ação. A caixa de diálogo informa o usuário do seguinte: “Ao remover o Portal da Empresa, seu dispositivo não será mais gerenciado pelo suporte de sua empresa e isso poderá remover o acesso a dados, aplicativos e email da empresa”. Em seguida, ela solicita ao usuário que confirme se deseja remover o aplicativo do Portal da Empresa com a seleção de “Sim”.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Removendo os dados coletados pelo aplicativo Portal da Empresa

Para remover todos os dados que o aplicativo Portal da Empresa para Android armazena no seu dispositivo:

-   Limpe os dados do aplicativo em Aplicativos -> Clique no aplicativo -> botão "Limpar dados"
-   Exclua a pasta '\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal'

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
