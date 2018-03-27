---
title: Gerenciar aplicativos iOS adquiridos por volume
description: Use o Intune para gerenciar aplicativos adquiridos por volume na Apple, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 10/11/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b05007a7c2d6fa1719b0f298f0e7981e735042e
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Isso ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.

O Microsoft Intune ajuda a gerenciar aplicativos adquiridos por meio desse programa, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.

> [!Important]
> Atualmente, o Intune atribui licenças de aplicativo do iOS VPP (Volume Purchase Program) for Business a usuários e dispositivos. Por isso, os usuários podem ter que inserir sua senha de ID da Apple para instalar o aplicativo.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Gerenciar aplicativos adquiridos por volume para dispositivos iOS
Você compra várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/). Isso envolve a configuração de uma conta do Apple VPP no site da Apple e upload do token do Apple VPP no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

## <a name="before-you-start"></a>Antes de começar
Antes de começar, você precisará obter um token do Apple VPP e carregá-lo em sua conta do Intune. Além disso, você deve compreender o seguinte:

* O Intune dá suporte à adição de até 256 tokens VPP.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.
* Antes de começar a usar o iOS VPP com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincronizará essas contas de usuário no Intune como medida de segurança. O Intune somente sincronizará os dados do serviço do Apple VPP criados pelo Intune.
* Somente será possível implantar aplicativos VPP do iOS em dispositivos do usuário que foram registrados usando o DEP (Protocolo de Registro de Dispositivo) se a afinidade do usuário para o dispositivo estiver configurada.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Obter e carregar um token de VPP da Apple

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador** &gt; **iOS e Mac OS X** &gt;  **Volume Purchase Program**.

2.  Escolha o link **Conta do Apple VPP**. Se você ainda não fez isso, inscreva-se no Volume Purchase Program for Business. Depois de se inscrever, baixe o token do Apple VPP em sua conta.

3.  Na página **Gerenciar VPP (Apple Volume Purchase Program)** do console do Intune, selecione **Carregar o token VPP**.

4.  Na caixa de diálogo **Carregar token do VPP**, insira ou cole o nome do token do VPP e sua ID da Apple e escolha **Carregar**.

5.  Na caixa de diálogo de aviso, marque a caixa para indicar que você entende que não é possível mudar para uma conta do VPP diferente mais tarde e escolha **Sim**.

Na página **Volume Purchase Program**, agora você pode exibir informações sobre o token do Apple VPP, incluindo quando foi sua última atualização, quando ele expirará e quando foi sincronizado pela última vez com o Intune.

Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## <a name="to-deploy-a-volume-purchased-app"></a>Implantar um aplicativo comprado por volume

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Aplicativos** &gt; **Aplicativos** &gt; **Aplicativos de Compra por Volume**. Esta lista mostra todos os aplicativos que foram sincronizados do serviço VPP da Apple.

2.  Escolha o aplicativo que você deseja implantar, escolha **Gerenciar Implantação** e use as instruções no tópico [Implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md) para concluir o carregamento, a criação e a implantação do aplicativo.

> [!TIP]
> Você deve escolher uma ação de implantação do tipo **Necessária**. Atualmente, não há suporte para as instalações disponíveis. Além disso, é possível implantar o aplicativo somente em grupos de usuários.

Quando você implanta o aplicativo como uma instalação **Obrigatória**, cada usuário que instala o aplicativo usa uma licença.

Para recuperar uma licença, você deve alterar a ação de implantação para **Desinstalar**. A licença será recuperada após a desinstalação do aplicativo.

Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. Eles devem fazer isso antes que a instalação do aplicativo prossiga.

Se não houver nenhuma outra licença disponível, a implantação falhará.

## <a name="to-monitor-apple-vpp-apps"></a>Para monitorar aplicativos de VPP da Apple
Você pode monitorar quais aplicativos do VPP foram implantados e a quantidade de licenças utilizadas no espaço de trabalho **Aplicativos**, no nó **Aplicativos Adquiridos com Base em Volume**.

> [!TIP]
> Você também pode usar o aplicativo **Filtros** para examinar o status de cada instalação do aplicativo.

### <a name="see-also"></a>Consulte também
[Implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md)
