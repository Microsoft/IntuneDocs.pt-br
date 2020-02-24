---
title: Gerenciar livros eletrônicos do iOS/iPadOS comprados por volume
titleSuffix: Microsoft Intune
description: Saiba como é possível sincronizar no Intune os livros comprados por volume na loja do iOS e, depois, gerenciar e acompanhar seu uso.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f7c2bd0603961b9d618b3f743ecb323fb7fc9823
ms.sourcegitcommit: ecaff388038fb800f2e646f8efcf8f3b1e2fd1b1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2020
ms.locfileid: "77437861"
---
# <a name="how-to-manage-iosipados-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Como gerenciar livros eletrônicos do iOS/iPadOS comprados por meio de um programa de compra por volume com o Microsoft Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Apple VPP (Volume Purchase Program) permite que você compre várias licenças de um livro que você deseja distribuir aos usuários em sua empresa. Distribua livros das lojas de Negócios ou Educação.

O Microsoft Intune ajuda você a sincronizar, gerenciar e atribuir livros comprados por meio desse programa. Importe informações de licença da loja e acompanhe quantas licenças você utilizou.

Os procedimentos para gerenciar livros são semelhantes aos usados para [gerenciar aplicativos VPP](../vpp-apps-ios.md).

## <a name="manage-volume-purchased-books-for-ios-devices"></a>Gerenciar aplicativos comprados por volume em dispositivos iOS
Você compra várias licenças para livros do iOS/iPadOS por meio do [Apple Volume Purchase Program for Business](https://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](https://volume.itunes.apple.com/us/store). Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.  Depois, você pode sincronizar suas informações de compra por volume com o Intune e acompanhar o uso de livros comprados por volume.

## <a name="before-you-start"></a>Antes de começar
Antes de começar, obtenha um token VPP da Apple e carregue-o em sua conta do Intune. Além disso:

* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.
* Antes de começar a usar os livros do iOS/iPadOS com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança. O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.
* Quando você atribui um livro a um dispositivo, esse dispositivo deve ter o aplicativo interno iBooks instalado. Caso contrário, o usuário final deverá reinstalar o aplicativo antes de poder ler o livro. No momento, não é possível usar o Intune para restaurar aplicativos internos removidos.
* Você pode atribuir somente livros do site do Apple Volume Purchase Program. Não é possível carregar nem, em seguida, atribuir livros que você criou internamente.
* Atualmente, não é possível atribuir livros a categorias de usuário final da mesma maneira que os aplicativos.
* Não é possível recuperar uma licença depois que o livro é atribuído.
* Quando um usuário com um dispositivo qualificado tenta instalar um livro do VPP pela primeira vez, ele deve ingressar no Apple Volume Purchase Program antes de instalar um livro. Atribua também licenças a grupos de segurança com as IDs da Apple gerenciadas. Se você fizer isso, os usuários não precisarão fornecer suas IDs da Apple quando um livro for instalado.
* Os dispositivos devem ser registrados com afinidade de usuário, pois os livros eletrônicos só podem ser atribuídos a grupos de usuários.   


## <a name="to-get-and-upload-an-apple-vpp-token"></a>Obter e carregar um token de VPP da Apple

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Administração de locatários** > **Conectores e tokens** > **Tokens VPP da Apple**.
3. No painel da lista de tokens VPP, clique em **Criar**.
5. No painel **Novo Token VPP**, especifique as seguintes informações:
    - **Arquivo de token VPP** – inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education. Depois, baixe o token Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.
    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
5. Quando terminar, clique em **Criar**.

O token será exibido na lista do painel de tokens.


Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## <a name="to-assign-a-volume-purchased-app"></a>Para atribuir um aplicativo comprado por volume

1. Selecione **Aplicativos** > **Livros eletrônicos** > **Todos os livros eletrônicos**.
2. No painel da lista de livros, escolha o livro que você deseja atribuir e, em seguida, ' **...** ' > **Atribuir Grupos**.
3. No painel <*nome do livro*> – **Grupos Atribuídos**, escolha **Gerenciar** > **Grupos Atribuídos**.
4. Escolha **Atribuir Grupos** e, no painel **Selecionar grupos**, escolha os grupos de usuários do Microsoft Azure AD aos quais você deseja atribuir o livro. No momento, não há suporte para grupos de dispositivos.
Escolha uma ação de atribuição **Disponível** ou **Obrigatória**. 
5. Quando terminar, escolha **Salvar**.

## <a name="next-steps"></a>Próximas etapas

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de livro.






