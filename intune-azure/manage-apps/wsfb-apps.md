---
title: Gerenciar aplicativos da Windows Store para Empresas
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como você pode sincronizar aplicativos no Intune da Windows Store para Empresas e, em seguida, atribuir e controlá-los."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d02d7c3367e18c96cc1d72de3a3a0ef581ef63ff
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>Como gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


O [Windows Store para a Empresa](https://www.microsoft.com/business-store) fornece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em um volume. Se conectar a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados com base no volume no portal do Intune. Por exemplo:
* Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.
* Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode atribuí-los como quaisquer outros aplicativos.
* Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune.
* O Intune bloqueará a implantação e a instalação de aplicativos caso haja um número insuficiente de licenças disponíveis.

## <a name="before-you-start"></a>Antes de começar
Examine as seguintes informações antes de iniciar a sincronização e a implantação de aplicativos da Windows Store for Business:
* Você deve configurar o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização.
* Você deve se inscrever para uma conta na Windows Store para Empresas.
* Depois que você tiver associado uma conta da Windows Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.
* Aplicativos adquiridos da loja não poderão ser adicionados ao Intune ou excluídos do Intune manualmente. Eles só poderão ser sincronizados com a Windows Store for Business.
* O Intune sincroniza apenas aplicativos online licenciados que você adquiriu da Windows Store for Business.
* Para usar essa funcionalidade, os dispositivos devem estar ingressados no Active Directory Domain Services ou em um local de trabalho.
* Dispositivos registrados devem estar usando a versão 1511 do Windows 10 ou posterior.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Associe sua conta da Windows Store for Business ao Intune
Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:
1. Certifique-se de entrar no repositório de negócios usando a mesma conta de locatário usada para entrar no Intune.
2. Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.
3. Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha **Microsoft Intune**.

> [!NOTE]
> Se você está usando mais de uma ferramenta de gerenciamento para implantar aplicativos da Windows Store para Empresas, anteriormente, você podia associar apenas um deles à Windows Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento com a loja, por exemplo, o Intune e o Configuration Manager.

Agora você pode continuar e configurar a sincronização no console do Intune.

## <a name="configure-synchronization"></a>Configurar sincronização

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
1. Na folha **Aplicativos Móveis**, escolha **Instalação** > **Windows Store para Empresas**.
2. Clique em **Habilitar**.
3. Se você ainda não tiver feito isso, clique no link para inscrever-se para a Windows Store para Empresas e associe sua conta como indicado anteriormente.
5. Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Windows Store para Empresas serão exibidos no portal do Intune. Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.
6. Clique em **Sincronizar** para obter os aplicativos que você adquiriu da Windows Store no Intune.

## <a name="synchronize-apps"></a>Sincronizar aplicativos

1. Na carga de trabalho **Gerenciar aplicativos**, escolha **Instalação** > **Windows Store para Empresas**.
2. Clique em **Sincronizar** para obter os aplicativos que você adquiriu da Windows Store no Intune.

## <a name="assign-apps"></a>Atribuir aplicativos

Atribua aplicativos da loja da mesma maneira que você implanta qualquer aplicativo do Intune. Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](deploy-apps.md). No entanto, em vez de atribuir aplicativos da página **Todos os aplicativos**, atribua-os na página **Aplicativos licenciados**.

Quando você atribui um aplicativo da Windows Store para Empresas, uma licença é usada por cada usuário que instala o aplicativo. Se você usar todas as licenças disponíveis para um aplicativo implantado, você não poderá implantar mais cópias. Você deve executar uma das seguintes ações:
* Desinstalar o aplicativo de alguns dispositivos.
* Reduzir o escopo da implantação atual para o destino apenas os usuários para os quais você tiver licenças suficientes.
* Comprar mais cópias do aplicativo da Windows Store para Empresas.

> [!Important]
> Aplicativos implantados só estão disponíveis para o usuário que originalmente registrou o dispositivo. Nenhum outro usuário pode acessar o aplicativo.

