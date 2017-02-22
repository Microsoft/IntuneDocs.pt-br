---
title: "Gerenciar aplicativos iOS adquiridos por volume | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: aprenda como sincronizar os aplicativos adquiridos por volume da loja do iOS para o Intune, bem como gerenciar e controlar seu uso."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87250baede6c86e7ac5c402e79026908e712f48c
ms.openlocfilehash: 809fe8d8eea7e472d80f6ee22e26c1f376e870eb

---

# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program"></a>Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Isso ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.

O Microsoft Intune ajuda a gerenciar aplicativos adquiridos por meio desse programa, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.

> [!Important]
> Atualmente, o Intune atribui licenças de aplicativo do iOS VPP (Volume Purchase Program) for Business a usuários, não a dispositivos. Por isso, os usuários devem inserir sua senha de ID da Apple para instalar o aplicativo.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Gerenciar aplicativos adquiridos por volume para dispositivos iOS
Você compra várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ou [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Isso envolve a configuração de uma conta do Apple VPP no site da Apple e upload do token do Apple VPP no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

## <a name="before-you-start"></a>Antes de começar
Antes de começar, você precisará obter um token do Apple VPP e carregá-lo em sua conta do Intune. Além disso, você deve compreender o seguinte:

* Você pode associar vários tokens de programa de compra por volume a sua conta do Intune.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.
* Antes de começar a usar o iOS VPP com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincronizará essas contas de usuário no Intune como medida de segurança. O Intune somente sincronizará os dados do serviço do Apple VPP criados pelo Intune.
* Não é possível atribuir aplicativos VPP do iOS em dispositivos que tenham sido registrados usando o DEP (Protocolo de registro do dispositivo).

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Obter e carregar um token de VPP da Apple

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
1.  Na carga de trabalho **Gerenciar Aplicativos**, escolha **Configurar** > **Tokens do VPP iOS**.
2.  Na folha da lista de tokens do VPP, clique em **Adicionar**.
3.  Na folha Novo Token do VPP, especifique as seguintes informações:
    - **Arquivo de token do VPP** – Se ainda não tiver feito isso, inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education. Depois de se inscrever, baixe o token do Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.
    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
4. Quando terminar, clique em **Carregar**.

O token é exibido na lista da folha de tokens.


Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## <a name="to-assign-a-volume-purchased-app"></a>Para atribuir um aplicativo comprado por volume

1. Na carga de trabalho de **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos Licenciados**.
2. Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir e selecione “**...**” > **Atribuir Grupos**.
3. Na folha <*nome do aplicativo*> – **Grupos Atribuídos**, escolha **Gerenciar** > **Grupos Atribuídos**.
4. Escolha **Atribuir Grupos** e, na folha **Selecionar grupos**, escolha os grupos do Azure AD para o qual você deseja atribuir o aplicativo.
Você deve escolher uma ação de atribuição de **Obrigatório**. Atualmente, não há suporte para as instalações disponíveis.
5. Quando terminar, escolha **Salvar**.

Consulte [Como monitorar aplicativos](monitor-apps.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.

## <a name="further-information"></a>Informações adicionais

Quando você atribui o aplicativo como uma instalação **Obrigatória**, cada usuário que instala o aplicativo usa uma licença.

Para recuperar uma licença, você deve alterar a ação de atribuição para **Desinstalar**. A licença será recuperada após a desinstalação do aplicativo.

Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. Eles devem fazer isso antes que a instalação do aplicativo prossiga.



<!--HONumber=Feb17_HO2-->


