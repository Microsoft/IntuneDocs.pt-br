---
title: Política do Microsoft Intune para permitir/bloquear aplicativos para o Samsung Knox
titleSuffix: ''
description: Crie um perfil personalizado para permitir e bloquear aplicativos em dispositivos Samsung Knox Standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a8486e121e6497eefdd2d098c2421f2f3b53b8a2
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734343"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Usar políticas personalizadas no Microsoft Intune para permitir e bloquear aplicativos para dispositivos Samsung Knox Standard 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use o procedimento descrito neste artigo para criar uma política personalizada do Microsoft Intune que cria um dos seguintes:

- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Aplicativos nesta lista serão impedidos de serem executados, mesmo se já tiverem sido instalados quando a política foi aplicada.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play. Apenas os aplicativos listados podem ser instalados. Nenhum outro aplicativo pode ser instalado por meio da Store.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung Knox Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>Criar uma lista de aplicativos permitidos ou bloqueados

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, escolha **Gerenciar** > **Perfis**.
2. No painel da lista de perfis, escolha **Criar perfil**.
3. No painel **Criar perfil**, insira um **Nome** e uma **Descrição** opcional para o perfil do dispositivo.
2. Em **Plataforma**, escolha **Android** e em **Tipo de perfil**, escolha **Personalizado**.
3. Clique em **Configurações**.
3. No painel **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.
4. Na caixa de diálogo **Adicionar ou Editar a Configuração de OMA-URI**, especifique as seguintes configurações:

   Para ver uma lista de aplicativos cuja execução no dispositivo é bloqueada:

   - **Nome** – Digite **PreventStartPackages**.
   - **Descrição** – Insira uma descrição opcional, como “Lista de aplicativos impedidos de serem executados”.
   - **Tipo de dados** – Na lista suspensa, escolha **Cadeia de caracteres**.
   - **OMA-URI** – Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**
   - **Valor** – Insira uma lista com os nomes do pacote do aplicativo que você deseja permitir. Você pode usar **; : ,** ou **|** como delimitador. (Exemplo: pacote1; pacote2;)

   Para obter uma lista dos aplicativos que os usuários do dispositivo podem instalar da loja Google Play enquanto todos os outros aplicativos são excluídos:
   - **Nome** – Digite **AllowInstallPackages**.
   - **Descrição** – Insira uma descrição opcional, como “Lista de aplicativos que os usuários podem instalar do Google Play”.
   - **Tipo de dados** – Na lista suspensa, escolha **Cadeia de caracteres**.
   - **OMA-URI** – Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**
   - **Valor** – Insira uma lista com os nomes do pacote do aplicativo que você deseja permitir. Você pode usar **; : ,** ou **|** como delimitador. (Exemplo: pacote1; pacote2;)

4. Clique em **OK** e, em seguida, no painel **Criar Perfil**, escolha **Criar**.

>[!TIP]
> Você pode encontrar a ID do pacote de um aplicativo navegando até o aplicativo na loja do Google Play. A ID do pacote está contida na URL da página do aplicativo. Por exemplo, a ID do pacote do aplicativo Microsoft Word é **com.microsoft.office.word**.

Na próxima vez que cada dispositivo de destino fizer check-in, as configurações do aplicativo serão aplicadas.


<!---## Assign the custom profile--->