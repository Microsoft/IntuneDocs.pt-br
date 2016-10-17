---
title: Gerenciar aplicativos iOS adquiridos por volume | Microsoft Intune
description: "Use o Intune para gerenciar aplicativos adquiridos por volume na Apple, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 611cfb0176a922234c29642c305dd03699922c5f
ms.openlocfilehash: 5981a2e147c89776d304226250170ec4114e35d8


---

# Gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune
A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Isso ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.

O Microsoft Intune ajuda a gerenciar aplicativos adquiridos por meio desse programa, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.

> [!Important]
> Atualmente, o Intune atribui licenças de aplicativo do iOS VPP (Volume Purchase Program) for Business a usuários, não a dispositivos. Por isso, os usuários devem inserir sua senha de ID da Apple para instalar o aplicativo.
> Não há suporte para o Apple Volume Purchase Program for Education nesta versão.

## Gerenciar aplicativos adquiridos por volume para dispositivos iOS
Você compra várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/). Isso envolve a configuração de uma conta do Apple VPP no site da Apple e upload do token do Apple VPP no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

## Antes de começar
Antes de começar, você precisará obter um token do Apple VPP e carregá-lo em sua conta do Intune. Além disso, você deve compreender o seguinte:

* Cada organização pode ter apenas uma conta VPP e um token.
* Depois de associar uma conta do Apple VPP ao Intune, não é possível associar uma conta diferente mais tarde. Por esse motivo, é muito importante que mais de uma pessoa tenha os detalhes da conta que você usa.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.
* Antes de começar a usar o iOS VPP com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincronizará essas contas de usuário no Intune como medida de segurança. O Intune somente sincronizará os dados do serviço do Apple VPP criados pelo Intune.
* Não é possível implantar aplicativos VPP do iOS em dispositivos que tenham sido registrados usando o DEP (Protocolo de Registro de Dispositivo).

## Obter e carregar um token de VPP da Apple

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador** &gt; **iOS e Mac OS X** &gt;  **Volume Purchase Program**.

2.  Escolha o link **Conta do Apple VPP**. Se você ainda não fez isso, inscreva-se no Volume Purchase Program for Business. Depois de se inscrever, baixe o token do Apple VPP em sua conta.

3.  Na página **Gerenciar VPP (Apple Volume Purchase Program)** do console do Intune, selecione **Carregar o token VPP**.

4.  Na caixa de diálogo **Carregar token do VPP**, insira ou cole o nome do token do VPP e sua ID da Apple e escolha **Carregar**.

5.  Na caixa de diálogo de aviso, marque a caixa para indicar que você entende que não é possível mudar para uma conta do VPP diferente mais tarde e escolha **Sim**.

Na página **Volume Purchase Program**, agora você pode exibir informações sobre o token do Apple VPP, incluindo quando foi sua última atualização, quando ele expirará e quando foi sincronizado pela última vez com o Intune.

Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## Implantar um aplicativo comprado por volume

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Aplicativos** &gt; **Software Gerenciado** &gt; **Aplicativos de Compra de Volume**. Esta lista mostra todos os aplicativos que foram sincronizados do serviço VPP da Apple.

2.  Escolha o aplicativo que você deseja implantar, escolha **Gerenciar Implantação** e use as instruções no tópico [Implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md) para concluir o carregamento, a criação e a implantação do aplicativo.

> [!TIP]
> Você deve escolher uma ação de implantação do tipo **Necessária**. Atualmente, não há suporte para as instalações disponíveis.

Quando você implanta o aplicativo como uma instalação **Obrigatória**, cada usuário que instala o aplicativo usa uma licença.

Para recuperar uma licença, você deve alterar a ação de implantação para **Desinstalar**. A licença será recuperada após a desinstalação do aplicativo.

Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. Eles devem fazer isso antes que a instalação do aplicativo prossiga.

> [!TIP]
> Examine a coluna **Status de Termos do VPP** para ver o status de aceitação para cada usuário ao qual o aplicativo foi implantado.

Se não houver nenhuma outra licença disponível, a implantação falhará.

## Para monitorar aplicativos de VPP da Apple
Você pode monitorar quais aplicativos do VPP foram implantados e a quantidade de licenças utilizadas no espaço de trabalho **Aplicativos**, no nó **Software Gerenciado** &gt; **Aplicativos Adquiridos com Base em Volume**.

> [!TIP]
> Você também pode usar o aplicativo **Filtros** para examinar o status de cada instalação do aplicativo.

### Consulte também
[Implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md)



<!--HONumber=Oct16_HO1-->


