---
title: Gerenciar aplicativos da Microsoft Store para Empresas
description: "Conecte o Microsoft Intune à Microsoft Store para Empresas para gerenciar e implantar aplicativos adquiridos com base em volume no console do Intune"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2de00bab670cd414d10750bb6f7f05283ea8bff3
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Gerenciar aplicativos adquiridos na Microsoft Store para Empresas com o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O [Microsoft Store para Empresas](https://www.microsoft.com/business-store) é um local para encontrar e comprar aplicativos para organizações, uso individual ou com base em volume. Ao conectar o repositório no Microsoft Intune, você pode gerenciar os aplicativos adquiridos por volume no console do Intune. Por exemplo:
* Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.
* Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode implantá-los como quaisquer outros aplicativos.
* Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune.
* O Intune bloqueará a implantação e a instalação de aplicativos caso haja um número insuficiente de licenças disponíveis.

## <a name="before-you-start"></a>Antes de começar
Examine as seguintes informações antes de iniciar a sincronização e a implantação de aplicativos da Microsoft Store para Empresas:
* Você deve configurar o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização. Para obter mais informações, consulte [Pre-requisitos para registrar dispositivos no Microsoft Intune](prerequisites-for-enrollment.md).
* É necessário inscrever-se em uma conta na Microsoft Store para Empresas.
* Depois que você tiver associado uma conta da Windows Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.
* Aplicativos adquiridos da loja não poderão ser adicionados ao Intune ou excluídos do Intune manualmente. Eles só poderão ser sincronizados com a Microsoft Store para Empresas.
* O Intune sincroniza apenas aplicativos licenciados online adquiridos da Microsoft Store para Empresas.
* Os dispositivos devem ser ingressados nos Serviços de Domínio do Active Directory ou ingressados no local de trabalho para que seja possível usar essa funcionalidade.
* Dispositivos registrados devem estar usando a versão 1511 do Windows 10.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Associe sua conta da Microsoft Store para Empresas ao Intune
Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:
1. Certifique-se de entrar no repositório de negócios usando a mesma conta de locatário usada para entrar no Intune.
2. Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.
3. Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha **Microsoft Intune**.

> [!NOTE]
> Se você está usando mais de uma ferramenta de gerenciamento para implantar aplicativos da Microsoft Store para Empresas, anteriormente, era possível associar apenas um deles à Microsoft Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento ao armazenamento, por exemplo, o Intune e o Configuration Manager.

Agora você pode continuar e configurar a sincronização no console do Intune.

## <a name="configure-synchronization"></a>Configurar sincronização

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.
2. No espaço de trabalho **Administração**, expanda **Gerenciamento de Dispositivo Móvel** > **Windows** e escolha **Store para Empresas**.
3. Na página **Microsoft Store para Empresas**, faça o seguinte:
 * Se você ainda não tiver feito isso, clique no link para inscrever-se na Microsoft Store para Empresas.
 * Quando você estiver se inscrito, clique em **Configurar Sincronização**.
4. Na caixa de diálogo **Configurar sincronização do aplicativo da Microsoft Store para Empresas**, selecione **Habilitar sincronização da Microsoft Store para Empresas**.
5. Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Microsoft Store para Empresas serão exibidos no console do Intune. Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.
6. Clique em **OK**.

## <a name="synchronize-apps"></a>Sincronizar aplicativos

1. Na página **Microsoft Store para Empresas**, escolha **Sincronizar agora** para sincronizar os aplicativos comprados na loja com o Intune.
2. No espaço de trabalho **Aplicativos**, escolha **Aplicativos** > **Aplicativos Adquiridos com Base em Volume** para exibir os aplicativos que você pode implantar e verificar se os aplicativos comprados foram importados corretamente. Os aplicativos nesse nó são exibidos com o número total de licenças que você tem e o número de licenças disponíveis que você tem.
Por exemplo, é possível adquirir o aplicativo de Portal da Empresa (licenciado online) da Microsoft Store para Empresas, sincronizá-lo com o console do Intune e, em seguida, implantá-lo como um aplicativo necessário nos dispositivos Windows 10 em questão. 


## <a name="deploy-apps"></a>Implantar aplicativos

Implante aplicativos da loja da mesma maneira que você implanta qualquer aplicativo do Intune. Para obter mais informações, consulte [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Implantar aplicativos no Microsoft Intune).
Ao implantar um aplicativo da Microsoft Store para Empresas, uma licença é usada por cada usuário que instala o aplicativo. Se você usar todas as licenças disponíveis para um aplicativo implantado, você não poderá implantar mais cópias. Você deve executar uma das seguintes ações:
* Desinstalar o aplicativo de alguns dispositivos.
* Reduzir o escopo da implantação atual para o destino apenas os usuários para os quais você tiver licenças suficientes.
* Comprar mais cópias do aplicativo da Microsoft Store para Empresas.

> [!Important]
> Aplicativos implantados só estão disponíveis para o usuário que originalmente registrou o dispositivo. Nenhum outro usuário pode acessar o aplicativo.


### <a name="see-also"></a>Consulte também
[Adicionar aplicativos a dispositivos móveis no Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)
