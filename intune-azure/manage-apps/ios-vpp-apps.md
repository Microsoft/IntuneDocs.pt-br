---
title: Gerenciar aplicativos adquiridos por volume para iOS | Microsoft Docs
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda como sincronizar os aplicativos adquiridos por volume da loja do iOS para o Intune, bem como gerenciar e controlar seu uso."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: f9e8a5deb17ebb77d480213567e5ccf6550e3493
ms.openlocfilehash: 1909549b321f51069bb6ad83f2f245afbf60b7dd
ms.contentlocale: pt-br
ms.lasthandoff: 05/03/2017

---

# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Como gerenciar aplicativos iOS adquiridos por meio de um programa de aquisição com base em volume com o Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Isso ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.

O Microsoft Intune ajuda a gerenciar aplicativos adquiridos por meio desse programa, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.

Além disso, você pode sincronizar, gerenciar e atribuir livros que adquiriu da loja Apple de programas de aquisição com base em volume com o Intune e atribuí-los aos usuários. Use a carga de trabalho **Books** no portal do Intune para gerenciar livros. Os procedimentos para gerenciar livros são os mesmos utilizados para gerenciar aplicativos.
Você deve ter carregado um token do Apple Volume Purchase Program para fazer isso. No momento, só é possível atribuir livros como uma instalação **Obrigatória**.
Quando você atribui um livro a um dispositivo, esse dispositivo deve ter o aplicativo interno iBooks instalado. Se não estiver, o usuário final deverá instalá-lo novamente para ler o livro. No momento, não é possível usar o Intune para restaurar aplicativos internos removidos.


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

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Obter e carregar um token de VPP da Apple

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1.  Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Configurar** > **Tokens de VPP do iOS**.
2.  Na folha da lista de tokens do VPP, clique em **Adicionar**.
3.  Na folha Novo Token do VPP, especifique as seguintes informações:
    - **Arquivo de token do VPP** – Se ainda não tiver feito isso, inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education. Depois de se inscrever, baixe o token do Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.
    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
4. Quando terminar, clique em **Carregar**.

O token é exibido na lista da folha de tokens.


Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## <a name="to-assign-a-volume-purchased-app"></a>Para atribuir um aplicativo comprado por volume

1. Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos Licenciados**.
2. Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir e selecione “**...**” > **Atribuir Grupos**.
3. Na folha <*nome do aplicativo*> – **Grupos Atribuídos**, escolha **Gerenciar** > **Grupos Atribuídos**.
4. Escolha **Atribuir Grupos** e então, na folha **Selecionar grupos**, escolha o usuário ou os grupos de dispositivos do Azure AD para o(s) qual(is) você deseja atribuir o aplicativo.
Você deve escolher uma ação de atribuição de **Obrigatório**. Além disso, as atribuições a grupos de dispositivos estão disponíveis para novos locatários criados depois de janeiro de 2017. Se seu locatário foi criado antes e você não tiver a opção de atribuir aplicativos VPP a grupos de dispositivos, entre em contato com o suporte do Intune.
5. Quando terminar, escolha **Salvar**.

Consulte [Como monitorar aplicativos](monitor-apps.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.

## <a name="further-information"></a>Informações adicionais

Quando você atribui o aplicativo como uma instalação **Obrigatória**, cada usuário que instala o aplicativo usa uma licença.

Para recuperar uma licença, você deve alterar a ação de atribuição para **Desinstalar**. A licença será recuperada após a desinstalação do aplicativo.

Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. Eles devem fazer isso antes que a instalação do aplicativo prossiga.

Quando você atribui um aplicativo VPP como Disponível, o respectivo conteúdo e a licença são atribuídos diretamente da App Store.

