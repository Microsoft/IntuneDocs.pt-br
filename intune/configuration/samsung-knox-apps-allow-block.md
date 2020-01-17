---
title: Política do Microsoft Intune para permitir/bloquear aplicativos para o Samsung Knox
titleSuffix: ''
description: Crie um perfil personalizado para permitir e bloquear aplicativos em dispositivos Samsung Knox Standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b83a0339d87375502159467af323fceae5eb6e2
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207070"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Usar políticas personalizadas no Microsoft Intune para permitir e bloquear aplicativos para dispositivos Samsung Knox Standard 

Use o procedimento descrito neste artigo para criar uma política personalizada do Microsoft Intune que cria um dos seguintes:

- Uma lista de aplicativos cuja execução no dispositivo é bloqueada. Aplicativos nesta lista serão impedidos de serem executados, mesmo se já tiverem sido instalados quando a política foi aplicada.
- Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play. Apenas os aplicativos listados podem ser instalados. Nenhum outro aplicativo pode ser instalado por meio da Store.

Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung Knox Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>Criar uma lista de aplicativos permitidos ou bloqueados

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes configurações:

    - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um bom nome de perfil é o **perfil personalizado do Windows Phone**.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e demais detalhes importantes.
    - **Plataforma**: Selecione **Android**.
    - **Tipo de perfil**: selecione **personalizado**.

4. Em **Configurações personalizadas de OMA-URI**, selecione **Adicionar**. Insira as seguintes configurações:

    Para ver uma lista de aplicativos cuja execução no dispositivo é bloqueada:

    - **Nome**: Digite **PreventStartPackages**.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e qualquer outra informação relevante que ajude a localizar o perfil. Por exemplo, insira a **lista de aplicativos que estão impedidos de serem executados**.
    - **OMA-URI** (diferencia maiúsculas de minúsculas): digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**.
    - **Tipo de dados**: selecione **cadeia de caracteres**.
    - **Valor**: Insira uma lista dos nomes de pacotes do aplicativo que deseja permitir. Você pode usar `;`, `:` ou `|` como delimitador. Por exemplo, insira `package1;package2;`.

   Para obter uma lista dos aplicativos que os usuários do dispositivo podem instalar da loja Google Play enquanto todos os outros aplicativos são excluídos:

    - **Nome**: Digite **AllowInstallPackages**.
    - **Descrição**: insira uma descrição que proporciona uma visão geral da configuração e qualquer outra informação relevante que ajude a localizar o perfil. Por exemplo, insira a **lista de aplicativos que os usuários podem instalar de Google Play**.
    - **OMA-URI** (diferencia maiúsculas de minúsculas): digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**.
    - **Tipo de dados**: selecione **cadeia de caracteres**.
    - **Valor**: Insira uma lista dos nomes de pacotes do aplicativo que deseja permitir. Você pode usar `;`, `:` ou `|` como delimitador. Por exemplo, insira `package1;package2;`.

5. Selecione **OK** para salvar suas alterações.
6. Quando terminar, escolha **OK** > **Criar** para criar o perfil do Intune. Após a conclusão, seu perfil será mostrado na lista **Dispositivos – Perfis de configuração**.

>[!TIP]
> Você pode encontrar a ID do pacote de um aplicativo navegando até o aplicativo na loja do Google Play. A ID do pacote está contida na URL da página do aplicativo. Por exemplo, a ID do pacote do aplicativo Microsoft Word é **com.microsoft.office.word**.

Na próxima vez que cada dispositivo de destino fizer check-in, as configurações do aplicativo serão aplicadas.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
