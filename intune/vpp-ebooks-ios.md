---
title: "Gerenciar livros eletrônicos do iOS comprados por volume"
titlesuffix: Azure portal
description: "Saiba como você pode sincronizar no Intune os livros comprados por volume na loja do iOS e, depois, gerenciar e acompanhar seu uso."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16f1e720e94ac8c6b35158477b41bfaeac9dc0a8
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Como gerenciar livros eletrônicos do iOS comprados por meio de um programa de compra por volume com o Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Apple VPP (Volume Purchase Program) permite que você compre várias licenças de um livro que você deseja distribuir aos usuários em sua empresa. Distribua livros das lojas de Negócios ou Educação.

O Microsoft Intune ajuda você a sincronizar, gerenciar e atribuir livros comprados por meio desse programa. Importe informações de licença da loja e acompanhe quantas licenças você utilizou.

Os procedimentos para gerenciar livros são semelhantes aos usados para [gerenciar aplicativos VPP](vpp-apps-ios.md).

## <a name="manage-volume-purchased-books-for-ios-devices"></a>Gerenciar aplicativos comprados por volume em dispositivos iOS
Você compra várias licenças para livros do iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.  Depois, você pode sincronizar suas informações de compra por volume com o Intune e acompanhar o uso de livros comprados por volume.

## <a name="before-you-start"></a>Antes de começar
Antes de começar, obtenha um token VPP da Apple e carregue-o em sua conta do Intune. Além disso:

* Você pode associar até 256 tokens VPP à sua conta do Intune.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.
* Antes de começar a usar os livros do iOS com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança. O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.
* Quando você atribui um livro a um dispositivo, esse dispositivo deve ter o aplicativo interno iBooks instalado. Caso contrário, o usuário final deverá reinstalar o aplicativo antes de poder ler o livro. No momento, não é possível usar o Intune para restaurar aplicativos internos removidos.
* Você pode atribuir somente livros do site do Apple Volume Purchase Program. Não é possível carregar nem, em seguida, atribuir livros que você criou internamente.
* Atualmente, não é possível atribuir livros a categorias de usuário final da mesma maneira que os aplicativos.
* Não é possível recuperar uma licença depois que o livro é atribuído.
* Quando um usuário com um dispositivo qualificado tenta instalar um livro do VPP pela primeira vez, ele deve ingressar no Apple Volume Purchase Program antes de instalar um livro. Atribua também licenças a grupos de segurança com as IDs da Apple gerenciadas. Se você fizer isso, os usuários não precisarão fornecer suas IDs da Apple quando um livro for instalado.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Obter e carregar um token de VPP da Apple

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1.  Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Configurar** > **Tokens de VPP do iOS**.
2.  Na folha da lista de tokens do VPP, clique em **Adicionar**.
3.  Na folha **Novo Token VPP**, especifique as seguintes informações:
    - **Arquivo de token VPP** – inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education. Depois, baixe o token Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.
    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
4. Quando terminar, clique em **Carregar**.

O token é exibido na lista da folha de tokens.


Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## <a name="to-assign-a-volume-purchased-app"></a>Para atribuir um aplicativo comprado por volume

1. Na carga de trabalho **Livros Eletrônicos**, escolha **Gerenciar** > **Todos os Livros Eletrônicos**.
2. Na folha de lista de livros, escolha o catálogo que deseja atribuir e, em seguida, escolha '**... **' > **Atribuir Grupos**.
3. Na folha <*nome do livro*> – **Grupos Atribuídos**, escolha **Gerenciar** > **Grupos Atribuídos**.
4. Escolha **Atribuir Grupos** e, na folha **Selecionar grupos**, escolha os grupos de usuários do Azure AD aos quais você deseja atribuir o livro. No momento, não há suporte para grupos de dispositivos.
Escolha uma ação de atribuição **Disponível** ou **Obrigatória**. 
5. Quando terminar, escolha **Salvar**.

## <a name="next-steps"></a>Próximas etapas

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de livro.






