---
title: Gerenciar aplicativos da Microsoft Store para Empresas
titlesuffix: Azure portal
description: "Saiba como sincronizar aplicativos no Intune da Microsoft Store para Empresas e, em seguida, atribui-los e acompanhá-los."
keywords: 
author: mattbriggs
ms.author: mabrigg
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
ms.openlocfilehash: cf0fc665ef70950b292241751d56122ebc9b0912
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Como gerenciar aplicativos adquiridos na Microsoft Store para Empresas com o Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


O [Microsoft Store para Empresas](https://www.microsoft.com/business-store) é um local para encontrar e comprar aplicativos para organizações, uso individual ou com base em volume. Conectando a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados por volume no Portal do Azure. Por exemplo:
* Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.
* Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode atribuí-los da mesma forma que outros aplicativos.
* Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune.
* O Intune bloqueará a atribuição e a instalação de aplicativos caso haja um número insuficiente de licenças disponíveis.

## <a name="before-you-start"></a>Antes de começar

Examine as seguintes informações antes de iniciar a sincronização e a atribiuição de aplicativos da Microsoft Store para Empresas:

- Configure o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização.
- É necessário inscrever-se em uma conta na Microsoft Store para Empresas.
- Depois que você tiver associado uma conta da Windows Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.
- Aplicativos adquiridos da loja não poderão ser adicionados ao Intune ou excluídos do Intune manualmente. Eles só poderão ser sincronizados com a Microsoft Store para Empresas.
- O Intune sincroniza tanto os aplicativos licenciados online quanto offline adquiridos na Microsoft Store para Empresas.
- Somente aplicativos offline gratuitos podem ser sincronizados com o Intune.
- Para usar essa funcionalidade, os dispositivos devem estar ingressados no Active Directory Domain Services ou em um local de trabalho.
- Dispositivos registrados devem estar usando a versão 1511 do Windows 10 ou posterior.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Associe sua conta da Microsoft Store para Empresas ao Intune
Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:
1. Certifique-se de entrar no repositório de negócios usando a mesma conta de locatário usada para entrar no Intune.
2. Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.
3. Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha **Microsoft Intune**.

> [!NOTE]
> Anteriormente, era possível associar apenas uma ferramenta de gerenciamento para atribuir a aplicativos com a Microsoft Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento ao armazenamento, por exemplo, o Intune e o Configuration Manager.

Agora você pode continuar e configurar a sincronização no console do Intune.

## <a name="configure-synchronization"></a>Configurar sincronização

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1. Na folha **Aplicativos Móveis**, escolha **Instalação** > **Microsoft Store para Empresas**.
2. Clique em **Habilitar**.
3. Se você ainda não tiver feito isso, clique no link para inscrever-se na Microsoft Store para Empresas e associe sua conta como indicado anteriormente.
5. Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Microsoft Store para Empresas serão exibidos no Portal do Azure. Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.
6. Clique em **Sincronizar** para obter os aplicativos que adquiridos na Microsoft Store no Intune.

## <a name="synchronize-apps"></a>Sincronizar aplicativos

1. Na carga de trabalho **Aplicativos móveis**, escolha **Instalação** > **Microsoft Store para Empresas**.
2. Clique em **Sincronizar** para obter os aplicativos que adquiridos na Microsoft Store no Intune.

## <a name="assign-apps"></a>Atribuir aplicativos

Atribua aplicativos da loja da mesma maneira que você atribui qualquer aplicativo do Intune. Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md). No entanto, em vez de atribuir aplicativos da página **Todos os aplicativos**, atribua-os na página **Aplicativos licenciados**.

Aplicativos offline podem ser direcionados para grupos de usuários, grupos de dispositivos ou grupos de usuários e dispositivos.
Aplicativos offline podem ser instalados para um usuário específico em um dispositivo ou para todos os usuários de um dispositivo. 


Ao atribuir um aplicativo da Microsoft Store para Empresas, uma licença é usada por cada usuário que instala o aplicativo. Se você usar todas as licenças disponíveis para um aplicativo atribuído, não será possível atribuir mais cópias. Efetue uma das seguintes ações:
* Desinstalar o aplicativo de alguns dispositivos.
* Reduza o escopo da atribuição atual para ser voltada apenas para os usuários para os quais você tem licenças suficientes.
* Comprar mais cópias do aplicativo da Microsoft Store para Empresas.


