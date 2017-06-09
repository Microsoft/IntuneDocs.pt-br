---
title: "Política do Intune para permitir/bloquear aplicativos para o Samsung KNOX"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: criar um perfil personalizado para permitir e bloquear aplicativos para dispositivos Samsung KNOX Standard."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: dea090e108d5ea023dc64d8d168b25d30b688cb2
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017



---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung KNOX Standard no Microsoft Intune
[!INCLUDE[azure_preview](./includes/azure_preview.md)]Use os procedimentos neste tópico para criar uma política personalizada do Microsoft Intune que cria um dos seguintes:

- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Aplicativos nesta lista serão impedidos de serem executados, mesmo se já tiverem sido instalados quando a política foi aplicada.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play. Apenas os aplicativos listados podem ser instalados. Nenhum outro aplicativo pode ser instalado da loja.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>Criar uma lista de aplicativos permitidos ou bloqueados

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
2. Na folha da lista de perfis, escolha **Criar Perfil**.
3. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** opcional para o perfil do dispositivo.
2. Escolha um **Tipo de plataforma** **Android** e um Tipo de perfil **Personalizado**.
3. Clique em **Configurações**.
3. Na folha **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
4. Na caixa de diálogo **Adicionar ou Editar Configuração de OMA-URI**, especifique o seguinte:

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>Para ver uma lista de aplicativos cuja execução no dispositivo é bloqueada:

- **Nome** – Digite **PreventStartPackages**.
- **Descrição** – Insira uma descrição opcional, como “Lista de aplicativos impedidos de serem executados”.
-     **Tipo de dados** – Na lista suspensa, escolha **Cadeia de caracteres**.
-     **OMA-URI** – Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
-     **Valor** – Insira uma lista com os nomes do pacote do aplicativo que você deseja permitir. Você pode usar **; : ,** ou **|** como delimitador. (Exemplo: pacote1; pacote2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>Para obter uma lista dos aplicativos que os usuários do dispositivo podem instalar da loja Google Play enquanto todos os outros aplicativos são excluídos:
- **Nome** – Digite **AllowInstallPackages**.
- **Descrição** – Insira uma descrição opcional, como “Lista de aplicativos que os usuários podem instalar do Google Play”.
- **Tipo de dados** – Na lista suspensa, escolha **Cadeia de caracteres**.
- **OMA-URI** – Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
- **Valor** – Insira uma lista com os nomes do pacote do aplicativo que você deseja permitir. Você pode usar **; : ,** ou **|** como delimitador. (Exemplo: pacote1; pacote2;)

4. Clique em **OK** e, em seguida, na folha **Criar Perfil**, escolha **Criar**.

>[!TIP]
> Você pode encontrar a ID do pacote de um aplicativo navegando até o aplicativo na loja do Google Play. A ID do pacote está contida na URL da página do aplicativo. Por exemplo, a ID do pacote do aplicativo Microsoft Word é **com.microsoft.office.word**.

Na próxima vez que cada dispositivo de destino fizer check-in, as configurações do aplicativo serão aplicadas.


<!---## Assign the custom profile--->

