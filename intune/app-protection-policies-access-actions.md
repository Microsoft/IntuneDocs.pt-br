---
title: Apagar dados seletivamente usando ações de acesso da política de proteção de aplicativo
titleSuffix: Microsoft Intune
description: Saiba como apagar dados seletivamente usando ações de acesso da política de proteção de aplicativo no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2cfd426a0ae7165a7aae60a90d104852fd834db6
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909109"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Apagar dados seletivamente usando ações de acesso da política de proteção de aplicativo no Intune

Usando as políticas de proteção de aplicativo do Intune, você pode definir configurações para impedir que usuários finais acessem uma conta ou um aplicativo corporativo. Essas configurações são direcionadas aos requisitos de realocação de dados e acesso definidos pela sua organização para assuntos como dispositivos com jailbreak e versões mínimas de sistema operacional.
 
Você pode escolher explicitamente apagar os dados corporativos da empresa do dispositivo do usuário final como uma ação a ser executada em caso de não conformidade usando essas configurações. Para algumas configurações, você poderá configurar várias ações, como bloquear o acesso e apagar os dados com base em diferentes valores especificados.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Criar uma política de proteção de aplicativo usando ações de acesso

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**.  
    O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos móveis** > **Políticas de proteção de aplicativo**.
4. Clique em **Adicionar uma política** (você também pode editar uma política existente). 
5. Clique em **Definir as configurações necessárias** para ver a lista de configurações disponíveis a serem configuradas para a política. 
6. Rolando para baixo no painel **Configurações**, você verá uma seção intitulada **Ações de Acesso** com uma tabela editável.

    ![Captura de tela das ações de acesso de proteção de aplicativo do Intune](./media/apps-selective-wipe-access-actions01.png)

7. Selecione uma **Configuração** e insira o **Valor** que os usuários precisam cumprir para entrar no aplicativo da empresa. 
8. Selecione a **Ação** a ser executada se os usuários não atenderem aos seus requisitos. Em alguns casos, várias ações podem ser definidas para uma única configuração. Para obter mais informações, confira [Como criar e atribuir políticas de proteção de aplicativo](app-protection-policies.md).

>[!NOTE]
> Para usar a configuração **Modelos de dispositivo**, insira uma lista separada por ponto e vírgula de identificadores de modelo. 

## <a name="policy-settings"></a>Configurações de política 

A tabela de configurações da política de proteção do aplicativo tem colunas para **Configuração**, **Valor** e **Ação**.

Para iOS, você poderá configurar ações para as seguintes configurações usando a lista suspensa **Configuração**:
-  Máximo de tentativas de PIN
-  Período de cortesia offline
-  Dispositivos com jailbreak ou com root
-  Versão mínima do sistema operacional
-  Versão mínima do aplicativo
-  Versão mínima do SDK
-  Modelos de dispositivo

Para o Android, você poderá configurar ações para as seguintes configurações usando a lista suspensa **Configuração**:
-  Máximo de tentativas de PIN
-  Período de cortesia offline
-  Dispositivos com jailbreak ou com root
-  Versão mínima do sistema operacional
-  Versão mínima do aplicativo
-  Versão mínima de patch
-  Fabricantes de dispositivo

Por padrão, a tabela terá linhas populadas como as configurações definidas para **Período de carência offline** e **Máximo de tentativas de PIN**, se a configuração **Exigir PIN para acesso** estiver definida como **Sim**.
 
Para definir uma configuração, selecione uma configuração na lista suspensa na coluna **Configuração**. Depois que uma configuração for selecionada, a caixa de texto editável será habilitada na coluna **Valor** na mesma linha, se for necessário definir um valor. Além disso, a lista suspensa ficará habilitada na coluna **Ação** com o conjunto de ações de inicialização condicionais aplicáveis à configuração. 

A lista a seguir fornece a lista de ações comuns:
-  **Bloquear acesso** – impedir que o usuário final acesse o aplicativo corporativo.
-  **Apagar dados** – apagar os dados corporativos do dispositivo do usuário final.
-  **Avisar** – fornecer uma caixa de diálogo ao usuário final como uma mensagem de aviso.

### <a name="additional-settings-and-actions"></a>Ações e configurações adicionais 

Em alguns casos, como a configuração **Versão mínima do sistema operacional**, você pode definir a configuração para executar todas as ações aplicáveis, com base em números de versão diferentes. 

![Captura de tela das ações de acesso da proteção de aplicativo do Intune – versão mínima do sistema operacional](./media/apps-selective-wipe-access-actions05.png)

Depois que uma configuração estiver totalmente configurada, a linha aparecerá em uma exibição somente leitura e estará disponível para ser editada a qualquer momento. Além disso, a linha terá uma lista suspensa disponível para seleção na coluna **Configuração**. As configurações que já foram definidas e que não permitem várias ações não estarão disponíveis para seleção na lista suspensa.

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre as políticas de proteção de aplicativo do Intune, confira:
- [Como criar e atribuir as políticas de proteção de aplicativo](app-protection-policies.md)
- [Configurações da política de proteção de aplicativo do iOS](app-protection-policy-settings-ios.md)
- [Configurações da política de proteção de aplicativo do Android no Microsoft Intune](app-protection-policy-settings-android.md) 


