---
title: Gerenciar aplicativos adquiridos por volume no iOS
titleSuffix: Intune on Azure
description: "Saiba como você pode sincronizar no Intune os aplicativos comprados por volume na loja do iOS e, depois, gerenciar e acompanhar seu uso."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16b7ce81eb63a81534af2911b34904d870ac41ad
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Como gerenciar aplicativos iOS adquiridos por meio de um programa de aquisição com base em volume com o Microsoft Intune
<a id="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Adquirir várias cópias de um aplicativo ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.

O Microsoft Intune ajuda você a gerenciar aplicativos comprados por meio desse programa ao:

- Importar as informações de licença da loja de aplicativos
- Acompanhar quantas licenças você usou
- Impedir a instalação de cópias do aplicativo além do que você possui

Além disso, você pode sincronizar, gerenciar e atribuir livros adquiridos na loja Apple de programas adquiridos por volume com o Intune. Use a carga de trabalho **Books** no portal do Intune para gerenciar livros. Os procedimentos para gerenciar livros são os mesmos utilizados para gerenciar aplicativos.
Você deve ter carregado um token do Apple Volume Purchase Program para fazer isso. No momento, só é possível atribuir livros como uma instalação **Obrigatória**.
Quando você atribui um livro a um dispositivo, esse dispositivo deve ter o aplicativo interno iBooks instalado. Caso contrário, o usuário final deverá reinstalar o aplicativo para ler o livro. No momento, não é possível usar o Intune para restaurar aplicativos internos removidos.


## Gerenciar aplicativos adquiridos por volume para dispositivos iOS
<a id="manage-volume-purchased-apps-for-ios-devices" class="xliff"></a>
Compre várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

## Antes de começar
<a id="before-you-start" class="xliff"></a>
Antes de começar, você precisará obter um token do VPP da Apple e carregá-lo em sua conta do Intune. Além disso, você deve compreender os seguintes critérios:

* Você pode associar vários tokens de programa de compra por volume a sua conta do Intune.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.
* Antes de começar a usar o iOS VPP com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança. O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.
* O Intune dá suporte à adição de até 256 tokens VPP.
* Se você atribuir um aplicativo comprado por volume para um dispositivo registrado por meio de um Perfil de Registro de Dispositivo ou o Apple Configurator, apenas os aplicativos voltados para os dispositivos funcionarão. Não é possível direcionar aplicativos comprados por volume para os usuários de um dispositivo DEP, que não têm nenhuma afinidade de usuário.
* Só há suporte para um token VPP para uso em uma conta do Intune por vez. Não reutilize o mesmo token VPP para vários locatários do Intune.
* Quando você atribui aplicativos VPP usando o modelo de licenciamento de usuário para usuários ou dispositivos (com afinidade de usuário), cada usuário do Intune precisa ser associado com uma ID da Apple exclusiva ou um endereço de email ao aceitar os termos e condições da Apple em seu dispositivo.
Use a ID da Apple exclusiva ou o endereço de email do usuário ao configurar m dispositivo para um novo usuário do Intune. A ID da Apple ou o endereço de email e o usuário do Intune formam um par exclusivo e podem ser usado em até 5 dispositivos.


## Obter e carregar um token de VPP da Apple
<a id="to-get-and-upload-an-apple-vpp-token" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1.  Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Configurar** > **Tokens de VPP do iOS**.
2.  Na folha da lista de tokens do VPP, clique em **Adicionar**.
3.  Na folha **Novo Token VPP**, especifique as seguintes informações:
    - **Arquivo de token do VPP** – Se ainda não tiver feito isso, inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education. Depois de se inscrever, baixe o token do Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.
    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
4. Quando terminar, clique em **Carregar**.

O token é exibido na lista da folha de tokens.


Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

> [!NOTE]
> O Microsoft Intune sincroniza apenas as informações de aplicativos publicamente disponíveis por meio da iTunes Store. Ainda não há suporte para **aplicativos B2B personalizados para iOS**. Se seu cenário for voltado para esses aplicativos, as informações de aplicativo não serão sincronizadas.

## Para atribuir um aplicativo comprado por volume
<a id="to-assign-a-volume-purchased-app" class="xliff"></a>

1. Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos Licenciados**.
2. Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir e selecione “**...**” > **Atribuir Grupos**.
3. Na folha <*nome do aplicativo*> – **Grupos Atribuídos**, escolha **Gerenciar** > **Grupos Atribuídos**.
4. Escolha **Atribuir Grupos** e então, na folha **Selecionar grupos**, escolha o usuário ou os grupos de dispositivos do Azure AD para o(s) qual(is) você deseja atribuir o aplicativo.
Você deve escolher uma ação de atribuição de **Obrigatório**. Além disso, as atribuições a grupos de dispositivos estão disponíveis para novos locatários criados depois de janeiro de 2017. Se seu locatário foi criado antes dessa data e você não tiver a opção de atribuir aplicativos VPP a grupos de dispositivos, entre em contato com o suporte do Intune.
5. Quando terminar, escolha **Salvar**.

>[!NOTE]
>A lista de aplicativos exibida está associada um token. Se você tiver um aplicativo que está associado a vários tokens VPP, verá o mesmo aplicativo exibido várias vezes, uma vez para cada token.

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.

## Informações adicionais
<a id="further-information" class="xliff"></a>

Quando você atribui o aplicativo como uma instalação **Obrigatória**, cada usuário que instala o aplicativo usa uma licença.

Para recuperar uma licença, você deve alterar a ação de atribuição para **Desinstalar**. A licença será recuperada após a desinstalação do aplicativo.

Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. É necessário ingressar para continuar a instalação do aplicativo. O convite para ingressar no Apple Volume Purchase Program exige que o usuário possa usar o aplicativo do iTunes no dispositivo iOS. Se você tiver definido uma política para desabilitar o aplicativo da iTunes Store, o licenciamento baseado em usuário para aplicativos VPP não funcionará. A solução é permitir o aplicativo do iTunes removendo a política ou usar o licenciamento baseado em dispositivo.

Quando você atribui um aplicativo VPP como Disponível, o respectivo conteúdo e a licença são atribuídos diretamente da App Store.
