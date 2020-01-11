---
title: Como remover seu dispositivo Android no Intune | Microsoft Docs
description: Remover seu dispositivo Android do Portal da Empresa do Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: be980a8cd2eb7f0cbe40002f73f9bc36a36d1193
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75859059"
---
# <a name="unenroll-your-android-device-from-management"></a>Cancelar o registro do dispositivo Android do gerenciamento  

Remova um dispositivo Android registrado para que ele não seja gerenciado pela sua organização. Este artigo descreve como remover o dispositivo do aplicativo Portal da Empresa. Depois de remover o dispositivo:  

* O dispositivo perde o acesso aos recursos e dados protegidos da sua organização.
* O dispositivo não aparecerá mais no Portal da Empresa.
* Você não poderá instalar aplicativos do Portal da Empresa.
* Qualquer configuração que tiver sido alterada em seu dispositivo quando você o adicionou (por exemplo, desabilitar a câmera ou exigir uma senha com determinado tamanho) não se aplicará mais.  

> [!NOTE]
> Você não pode cancelar o registro ou remover seu dispositivo de propriedade corporativa do aplicativo Microsoft Intune. O dispositivo foi registrado durante a instalação inicial do dispositivo e deve ser registrado para acessar os recursos da sua organização.  

1. No Portal da Empresa, vá para o canto superior direito e toque nos três pontos verticais. Abre o menu de ação é aberto.

   ![Uma captura de tela do aplicativo do Portal da Empresa do Android, com o menu de ação aberto no canto superior direito. A nova opção “Remover o Portal da Empresa” está disponível como a terceira opção, sob “Meu perfil” e “Configurações” e acima de “Termos e condições”, “Ajuda e comentários” e “Sobre”.](./media/android_remove_cp_menu_action_after_1705.png)

2. Toque em **Remover o Portal da Empresa**.  

3. Será exibida uma mensagem com informações sobre o que acontece depois que você cancela o registro do seu dispositivo. Toque em **OK** para confirmar que você deseja remover o dispositivo do Portal da Empresa.

   ![Uma captura de tela de confirmação, que está disponível após a seleção da nova opção “Remover o Portal da Empresa” no menu de ação.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="remove-data-collected-by-the-company-portal-app"></a>Remover os dados coletados pelo aplicativo Portal da Empresa  

Para remover todos os dados que o aplicativo Portal da Empresa para Android armazena no seu dispositivo:

- Limpar dados de aplicativo tocando **Aplicativos** > **[*nome do aplicativo*]**  > **Limpar dados**.
- Exclua a seguinte pasta: \storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal.

## <a name="uninstall-the-company-portal-app"></a>Desinstalar o aplicativo Portal da Empresa

O Portal da Empresa é um aplicativo de gerenciamento de dispositivo. Ele não poderá ser desinstalado enquanto você não cancelar o registro de seu dispositivo do gerenciamento. Depois que for concluído, toque e segure o ícone do aplicativo Portal da Empresa até ver **Desinstalar**. Toque em **Desinstalar** para remover o aplicativo do dispositivo.  

Como alternativa, toque em **Configurações** > **Aplicativos** > **Portal da Empresa** > **Desinstalar**.  

### <a name="remove-the-company-portal-app-as-a-device-administrator"></a>Remover o aplicativo Portal da Empresa como administrador do dispositivo

Como último recurso, você poderá desinstalar o aplicativo do dispositivo como administrador do dispositivo.  

Caso você tenha um dispositivo de propriedade da empresa, sua organização poderá exigir que o Portal da Empresa esteja em seu dispositivo em todos os momentos. Se você desinstalá-lo, poderá perder o acesso aos recursos protegidos da empresa, como email, aplicativos, Wi-Fi ou VPN, até que o aplicativo seja reinstalado. Para obter mais informações sobre como instalar, atualizar ou remover aplicativos obrigatórios, confira [Adicionar aplicativos ao Microsoft Intune](/intune/apps/apps-add#apps-that-are-added-automatically-by-intune).

Veja como desabilitar o Portal da Empresa como administrador do dispositivo. Os nomes reais de cada configuração podem variar no dispositivo Android.  

**Opção 1**:  

1. Selecione **Configurações** > **Segurança** > **Configurações de Segurança Adicionais** > **Administradores do Dispositivo**.  
2. Desmarque a seleção **Portal da Empresa**.  

**Opção 2**:

1. Selecione **Configurações** > **Tela de bloqueio e segurança** > **Outras configurações de segurança** > **Aplicativos administrador do dispositivo**.
2. Desmarque a seleção **Portal da Empresa**.

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://go.microsoft.com/fwlink/?linkid=2010980).
