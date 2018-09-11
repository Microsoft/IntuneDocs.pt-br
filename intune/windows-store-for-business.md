---
title: Gerenciar aplicativos da Microsoft Store para Empresas
titlesuffix: Microsoft Intune
description: Saiba como é possível sincronizar os aplicativos da Microsoft Store para Empresas com o Intune e, em seguida, atribuir e controlar esses aplicativos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 143b4f3390d3058177f4bfde4cbfe0d210f57e86
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347909"
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Como gerenciar aplicativos adquiridos na Microsoft Store para Empresas com o Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O [Microsoft Store para Empresas](https://www.microsoft.com/business-store) é um local para encontrar e comprar aplicativos para organizações, uso individual ou com base em volume. Conectando a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados por volume no Portal do Azure. Por exemplo:
* Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.
* Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode atribuí-los da mesma forma que outros aplicativos.
* Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune.
* O Intune bloqueará a atribuição e a instalação de aplicativos caso haja um número insuficiente de licenças disponíveis.
* Os aplicativos gerenciados pela Microsoft Store para Empresas revogarão automaticamente as licenças quando um usuário sair da empresa ou quando o administrador remover o usuário e os dispositivos do usuário.

## <a name="before-you-start"></a>Antes de começar

Examine as seguintes informações antes de iniciar a sincronização e a atribiuição de aplicativos da Microsoft Store para Empresas:

- Configure o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização.
- É necessário inscrever-se em uma conta na Microsoft Store para Empresas.
- Depois que você tiver associado uma conta da Microsoft Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.
- Aplicativos adquiridos da loja não poderão ser adicionados ao Intune ou excluídos do Intune manualmente. Eles só poderão ser sincronizados com a Microsoft Store para Empresas.
- Os aplicativos licenciados online e offline adquiridos na Microsoft Store para Empresas são sincronizados no portal do Intune. Você poderá implantar esses aplicativos em grupos de dispositivos ou de usuários. 
- As instalações de aplicativos online são gerenciadas pela loja.
- Os aplicativos offline gratuitos também podem ser sincronizados com o Intune. Esses aplicativos são instalados pelo Intune e não pela loja.
- Para usar essa funcionalidade, os dispositivos devem estar ingressados no Active Directory Domain Services ou em um local de trabalho.
- Dispositivos registrados devem estar usando a versão 1511 do Windows 10 ou posterior.

Além disso, os conjuntos relacionados e aplicativos licenciados offline sincronizados por meio da Microsoft Store para Empresas agora serão ser consolidados em um única entrada de aplicativo na interface do usuário. Todos os detalhes de implantação dos pacotes individuais serão migrados para a única entrada. Para exibir conjuntos relacionados no portal do Azure, selecione **Licenças de aplicativo** na folha **Aplicativos clientes**.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Associe sua conta da Microsoft Store para Empresas ao Intune
Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:
1. Certifique-se de entrar no repositório de negócios usando a mesma conta de locatário usada para entrar no Intune.
2. Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.
3. Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha **Microsoft Intune**.

> [!NOTE]
> Anteriormente, era possível associar apenas uma ferramenta de gerenciamento para atribuir a aplicativos com a Microsoft Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento ao armazenamento, por exemplo, o Intune e o Configuration Manager.

Agora você pode continuar e configurar a sincronização no console do Intune.

## <a name="configure-synchronization"></a>Configurar sincronização

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Aplicativos clientes**.
1. No painel **Aplicativos clientes**, escolha **Instalação** > **Microsoft Store para Empresas**.
2. Clique em **Habilitar**.
3. Se você ainda não tiver feito isso, clique no link para inscrever-se na Microsoft Store para Empresas e associe sua conta como indicado anteriormente.
5. Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Microsoft Store para Empresas serão exibidos no Portal do Azure. Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.
6. Clique em **Sincronizar** para obter os aplicativos que adquiridos na Microsoft Store no Intune.

## <a name="synchronize-apps"></a>Sincronizar aplicativos

1. Na carga de trabalho **Aplicativos clientes**, escolha **Instalação** > **Microsoft Store para Empresas**.
2. Clique em **Sincronizar** para obter os aplicativos que adquiridos na Microsoft Store no Intune.

## <a name="assign-apps"></a>Atribuir aplicativos

Atribua aplicativos da loja da mesma maneira que você atribui qualquer aplicativo do Intune. Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md). No entanto, em vez de atribuir aplicativos da página **Todos os aplicativos**, atribua-os na página **Aplicativos licenciados**.

Aplicativos offline podem ser direcionados para grupos de usuários, grupos de dispositivos ou grupos de usuários e dispositivos.
Aplicativos offline podem ser instalados para um usuário específico em um dispositivo ou para todos os usuários de um dispositivo. 


Ao atribuir um aplicativo da Microsoft Store para Empresas, uma licença é usada por cada usuário que instala o aplicativo. Se você usar todas as licenças disponíveis para um aplicativo atribuído, não será possível atribuir mais cópias. Efetue uma das seguintes ações:
* Desinstalar o aplicativo de alguns dispositivos.
* Reduza o escopo da atribuição atual para ser voltada apenas para os usuários para os quais você tem licenças suficientes.
* Comprar mais cópias do aplicativo da Microsoft Store para Empresas.


