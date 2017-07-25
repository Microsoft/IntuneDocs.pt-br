---
title: Gerenciar aplicativos da Windows Store para Empresas
titleSuffix: Intune on Azure
description: "Saiba como você pode sincronizar aplicativos no Intune da Windows Store para Empresas e, em seguida, atribui-los e acompanhá-los."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de6ed7623e33a50bdf8452cbf1bad9c648b13d04
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Como gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune
<a id="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


O [Windows Store para a Empresa](https://www.microsoft.com/business-store) fornece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em um volume. Se conectar a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados com base no volume no portal do Intune. Por exemplo:
* Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.
* Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode atribuí-los da mesma forma que outros aplicativos.
* Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune.
* O Intune bloqueará a atribuição e a instalação de aplicativos caso haja um número insuficiente de licenças disponíveis.

## Antes de começar
<a id="before-you-start" class="xliff"></a>

Examine as seguintes informações antes de iniciar a sincronização e a atribuição de aplicativos da Windows Store for Business:

- Configure o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização.
- Você deve se inscrever para uma conta na Windows Store para Empresas.
- Depois que você tiver associado uma conta da Windows Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.
- Aplicativos adquiridos da loja não poderão ser adicionados ao Intune ou excluídos do Intune manualmente. Eles só poderão ser sincronizados com a Windows Store for Business.
- O Intune sincroniza tanto aplicativos licenciados online quanto offline que você adquiriu na Windows Store para Empresas.
- Somente aplicativos offline gratuitos podem ser sincronizados com o Intune.
- Para usar essa funcionalidade, os dispositivos devem estar ingressados no Active Directory Domain Services ou em um local de trabalho.
- Dispositivos registrados devem estar usando a versão 1511 do Windows 10 ou posterior.

## Associe sua conta da Windows Store for Business ao Intune
<a id="associate-your-windows-store-for-business-account-with-intune" class="xliff"></a>
Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:
1. Certifique-se de entrar no repositório de negócios usando a mesma conta de locatário usada para entrar no Intune.
2. Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.
3. Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha **Microsoft Intune**.

> [!NOTE]
> Anteriormente, era possível associar apenas uma ferramenta de gerenciamento para atribuir a aplicativos com a Windows Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento com a loja, por exemplo, o Intune e o Configuration Manager.

Agora você pode continuar e configurar a sincronização no console do Intune.

## Configurar sincronização
<a id="configure-synchronization" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1. Na folha **Aplicativos Móveis**, escolha **Instalação** > **Windows Store para Empresas**.
2. Clique em **Habilitar**.
3. Se você ainda não tiver feito isso, clique no link para inscrever-se na Windows Store para Empresas e associe sua conta como indicado anteriormente.
5. Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Windows Store para Empresas serão exibidos no Portal do Intune. Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.
6. Clique em **Sincronizar** para obter os aplicativos que você adquiriu da Windows Store no Intune.

## Sincronizar aplicativos
<a id="synchronize-apps" class="xliff"></a>

1. Na carga de trabalho **Aplicativos móveis**, escolha **Instalação** > **Windows Store para Empresas**.
2. Clique em **Sincronizar** para obter os aplicativos que você adquiriu da Windows Store no Intune.

## Atribuir aplicativos
<a id="assign-apps" class="xliff"></a>

Atribua aplicativos da loja da mesma maneira que você atribui qualquer aplicativo do Intune. Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md). No entanto, em vez de atribuir aplicativos da página **Todos os aplicativos**, atribua-os na página **Aplicativos licenciados**.

Aplicativos offline podem ser direcionados para grupos de usuários, grupos de dispositivos ou grupos de usuários e dispositivos.
Aplicativos offline podem ser instalados para um usuário específico em um dispositivo ou para todos os usuários de um dispositivo. 


Quando você atribui um aplicativo da Windows Store para Empresas, uma licença é usada por cada usuário que instala o aplicativo. Se você usar todas as licenças disponíveis para um aplicativo atribuído, não será possível atribuir mais cópias. Efetue uma das seguintes ações:
* Desinstalar o aplicativo de alguns dispositivos.
* Reduza o escopo da atribuição atual para ser voltada apenas para os usuários para os quais você tem licenças suficientes.
* Comprar mais cópias do aplicativo da Windows Store para Empresas.


