---
title: "Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados"
titlesuffix: Microsoft Intune
description: "Use as políticas de configuração do aplicativo no Microsoft Intune para fornecer as configurações quando os usuários executam um aplicativo Android for Work."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 206e229e95633ce553637bcedef708ee5630864c
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use as políticas de configuração do aplicativo no Microsoft Intune para fornecer as configurações quando os usuários executam um aplicativo Android for Work. Você não atribui essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo. As configurações de política são usadas quando o aplicativo as verifica, normalmente, na primeira vez em que ele é executado.

> [!Note]  
> Nem todo aplicativo dá suporte à configuração de aplicativo. Verifique com o desenvolvedor do aplicativo se ele criou o aplicativo para dar suporte a políticas de configuração de aplicativo.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione a carga de trabalho de **Aplicativos móveis**.
4. Escolha **Políticas de configuração do aplicativo** no grupo **Gerenciar** e escolha **Adicionar**.
5. Defina os seguintes detalhes:
    - **Nome**  
      O nome do perfil que será exibido no Portal do Azure.
    - **Descrição**  
      A descrição do perfil que será exibida no Portal do Azure.
    - **Tipo de registro de dispositivo**  
      Selecione **Dispositivos gerenciados**.
6. Selecione **Android for Work** em **Plataforma**.
7. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração de aplicativo. Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune.
8. Selecione **Definições de configuração**. É possível definir configurações usando:
    - [Designer de configuração](#Use-the-configuration-designer)
    - [Editor de JSON](#Enter-the-JSON-editor)
9. Escolha **OK** e, em seguida, **Adicionar**.

## <a name="use-the-configuration-designer"></a>Usar o designer de configuração

Você pode usar o designer de configuração para aplicativos em dispositivos que são registrados ou não registrados no Intune. O designer permite que você configure chaves e valores de configuração específicos. Você também deve especificar o tipo de dados para cada valor.

Para cada chave e valor na configuração, defina:

  - **Chave de configuração**  
     A chave que identifica exclusivamente a configuração específica.
  - **Tipo de valor**  
    O tipo de dados do valor de configuração. Os tipos incluem Inteiro, Real, Cadeia de caracteres ou Booliano.
  - **Valor da configuração**  
    O valor para a configuração. 

## <a name="enter-the-json-editor"></a>Inserir o editor de JSON

Algumas definições de configuração em aplicativos (como aquelas com os tipos Pacote) não podem ser configuradas com o designer de configuração. É necessário usar o editor de JSON para esses valores. As configurações são fornecidas para os aplicativos automaticamente quando o aplicativo é instalado.

1. Em **Formato de definições de configuração**, selecione **Inserir editor de JSON**.
2. No editor, é possível definir os valores JSON para as definições de configuração. Escolha **Baixar modelo de JSON** para baixar um arquivo de exemplo que, em seguida, pode ser configurado.
3. Escolha **OK** e, em seguida, **Adicionar**.

A política será criada e exibida na folha da lista de políticas.

Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração de aplicativo.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Pré-configurar o estado de concessão de permissões para aplicativos

Você também pode pré-configurar a permissão para que os aplicativos acessem os recursos do dispositivo Android. Por padrão, os aplicativos Android que exigem permissões de dispositivo – como o acesso à localização ou à câmera do dispositivo – solicitam que os usuários aceitem ou neguem as permissões. Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final deverá conceder ao aplicativo permissão para usar o microfone.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Escolha **Aplicativos móveis**.
3. Em **Gerenciar**, escolha **Políticas de configuração do aplicativo** e, em seguida, clique em **Adicionar**.
4. Defina os seguintes detalhes:
    - **Nome**. O nome do perfil que será exibido no Portal do Azure.
    - **Descrição**. A descrição do perfil que será exibida no Portal do Azure.
    - **Tipo de registro de dispositivo**. Selecione **Dispositivos gerenciados**.
    - **Plataforma**. Selecione **Android for Work**.
5. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração. Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune.
6. Selecione **Permissões** e, em seguida, escolha **Adicionar**.
7. Selecione na lista de permissões de aplicativo disponíveis e, em seguida, escolha **OK**.
8. Selecione uma opção para cada permissão a ser concedida com esta política:
    - **Aviso**. Avise o usuário para aceitar ou recusar.
    - **Concessão automática**. Aprovar automaticamente sem notificar o usuário.
    - **Negação automática**. Negar automaticamente sem notificar o usuário.
9. Para atribuir a política de configuração de aplicativo, selecione a política de configuração de aplicativo, selecione **Atribuição** e, em seguida, selecione **Selecionar grupos**.
10. Selecione os grupos de usuários a serem atribuídos e, em seguida, escolha **Selecionar**.
11. Escolha **Salvar** para atribuir a política.

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo.

