---
title: Gerenciar aplicativos adquiridos por volume para iOS | Microsoft Docs
titlesuffix: Azure portal
description: "Saiba como você pode sincronizar no Intune os aplicativos comprados por volume na loja do iOS e, depois, gerenciar e acompanhar seu uso."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f820be41c532384f9f2db57e0e0e497a05307d73
ms.sourcegitcommit: 06abc5ccc8b868c9ff3ad3f8f62473a87b2da481
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Como gerenciar aplicativos iOS adquiridos por meio de um programa de aquisição com base em volume com o Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Comprar várias cópias ajuda você a gerenciar com eficiência os aplicativos em sua empresa.

O Microsoft Intune ajuda você a gerenciar várias cópias de aplicativos comprados por meio desse programa:

- Informações sobre licença de relatórios da app store.
- Acompanhamento de quantas licenças você usou.
- Como ajudar você a não instalar mais cópias do aplicativo além das que já possui.

Há dois métodos que você pode usar para atribuir aplicativos comprados por volume:

### <a name="device-licensing"></a>Licenciamento de dispositivo

Quando você atribui um aplicativo a dispositivos, uma licença do aplicativo é usada e permanece associada ao dispositivo ao qual você a atribuiu.

Quando você atribuir aplicativos adquiridos por volume em um dispositivo, o usuário final do dispositivo não precisa fornecer uma ID Apple para acessar o armazenamento.

### <a name="user-licensing"></a>Licenciamento do usuário

Quando você atribui um aplicativo a um usuário, uma licença de aplicativo é usada e associada ao usuário. O aplicativo pode ser executado em vários dispositivos de propriedade do usuário (com um limite controlado pela Apple).

Quando você atribui um aplicativo comprado por volume aos usuários, cada usuário final deve ter uma ID da Apple válida e exclusiva para acessar a loja de aplicativos.

Além disso, você pode sincronizar, gerenciar e atribuir livros adquiridos na loja do VPP (Apple Volume Purchase Program) com o Intune. Para obter mais informações, consulte [Como gerenciar livros eletrônicos do iOS comprados por meio de um programa de compra por volume](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Gerenciar aplicativos adquiridos por volume para dispositivos iOS

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps-for-ios-devices"></a>Dá suporte a aplicativos adquiridos por volume do Apple Volume Purchase Program para dispositivos iOS

Compre várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

### <a name="supports-business-to-business-volume-purchased-apps-for-ios-devices"></a>Dá suporte a aplicativos adquiridos por volume entre empresas para dispositivos iOS

Além disso, os desenvolvedores de terceiros também podem distribuir de maneira privativa aplicativos a membros autorizados do Volume Purchase Program for Business especificados no iTunes Connect. Esses membros do VPP for Business podem entrar na App Store do Volume Purchase Programa e adquirir seus aplicativos. Aplicativos do VPP for Business adquiridos pelo usuário final serão sincronizado com seus locatários do Intune.

## <a name="before-you-start"></a>Antes de começar
Antes de começar, você precisará obter um token do VPP da Apple e carregá-lo em sua conta do Intune. Além disso, você deve compreender os seguintes critérios:

* Você pode associar vários tokens do VPP à sua conta do Intune.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Antes de começar a usar o Apple VPP com o Intune, remova todas as contas de usuários do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança. O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.
* O Intune dá suporte à adição de até 256 tokens VPP.
* O programa de Perfil de registro do dispositivo (DEP) Apple automatiza o registro de MDM (gerenciamento do dispositivo móvel). Ao usar o DEP, você pode configurar dispositivos da empresa sem tocá-los. Você pode se registrar no programa de DEP usando a mesma conta de agente do programa que usou no VPP da Apple. A ID do Programa de implantação da Apple é exclusiva para programas listados no site dos [Programas de implantação da Apple](https://deploy.apple.com) e não pode ser usada para fazer logon em serviços Apple, como na loja iTunes.
* Quando você atribui aplicativos VPP usando o modelo de licenciamento de usuário para usuários ou dispositivos (com afinidade de usuário), cada usuário do Intune precisa ser associado com uma ID da Apple exclusiva ou um endereço de email ao aceitar os termos e condições da Apple em seu dispositivo. Use a ID da Apple exclusiva ou o endereço de email do usuário ao configurar um dispositivo para um novo usuário do Intune. A ID da Apple ou o endereço de email e o usuário do Intune formam um par exclusivo e podem ser usados em até cinco dispositivos.
* Só há suporte para um token VPP para uso em uma conta do Intune por vez. Não reutilize o mesmo token VPP para vários locatários do Intune.
* Quando você atribui aplicativos VPP usando o modelo de licenciamento de usuário para usuários ou dispositivos (com afinidade de usuário), cada usuário do Intune precisa ser associado com uma ID da Apple exclusiva ou um endereço de email ao aceitar os termos e condições da Apple em seu dispositivo.
Use a ID da Apple exclusiva ou o endereço de email do usuário ao configurar m dispositivo para um novo usuário do Intune. A ID da Apple ou o endereço de email e o usuário do Intune formam um par exclusivo e podem ser usados em até cinco dispositivos.

>[!IMPORTANT]
>Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Obter e carregar um token de VPP da Apple

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
1.  Na folha **Intune**, escolha **Aplicativos móveis** > **Tokens do VPP do iOS** em **Instalação**.
2.  Na folha com a lista de tokens VPP, selecione **Criar**.
4. Na folha **Criar token VPP**, especifique as seguintes informações:
    - **Arquivo de token do VPP** – Se ainda não tiver feito isso, inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education. Depois de se inscrever, baixe o token do Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.
    - **País/região** – selecione a loja do país do VPP.  O Intune sincroniza aplicativos VPP para todas as localidades da loja VPP especificada de um país.
        > [!WARNING]  
        > Alterar o país atualizará os metadados de aplicativos e a URL da loja na próxima sincronização com o serviço da Apple para aplicativos criados com esse token. O aplicativo não será atualizado se ele não existir na loja do novo país.

    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
    - **Atualizações automáticas do aplicativo** -Alterne de **Ligado** para **Desligado** para habilitar as atualizações automáticas. Quando habilitado, o Intune atualiza todos os aplicativos adquiridos para o token especificado por meio do serviço Intune quando o dispositivo fizer check-in.
detecta as atualizações do aplicativo VPP dentro da loja de aplicativos e as enviará por push automaticamente ao dispositivo quando o dispositivo fizer check-in.
4. Quando terminar, selecione **Carregar**.

O token é exibido na lista da folha de tokens.

Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## <a name="to-assign-a-volume-purchased-app"></a>Para atribuir um aplicativo comprado por volume

1.  Na folha **Intune**, escolha **Aplicativos móveis** > **Aplicativos** em **Gerenciar**.
2.  Na folha de lista de aplicativos, escolha o aplicativo que deseja atribuir e, em seguida, escolha **Atribuições**.
3.  Na folha ***Nome do aplicativo*** - **Atribuições**, escolha **Selecionar Grupos** e, na folha **Selecionar grupos**, escolha o usuário ou os grupos de dispositivos do Azure AD para os quais você deseja atribuir o aplicativo.
5.  Para cada grupo selecionado, escolha as configurações a seguir:
    - **Tipo** – escolha se o aplicativo será **Disponível** (os usuários finais poderão instalar o aplicativo por meio do Portal da Empresa) ou **Necessário** (o aplicativo será instalado automaticamente nos dispositivos dos usuários finais).
    - **Tipo de licença** -Selecione **Licenciamento de usuário**, ou **Licenciamento de dispositivo**.
6.  Quando terminar, escolha **Salvar**.


>[!NOTE]
>A lista de aplicativos exibida está associada um token. Se você tiver um aplicativo que está associado a vários tokens VPP, verá o mesmo aplicativo exibido várias vezes, uma vez para cada token.

## <a name="end-user-prompts-for-vpp"></a>Avisos do VPP para o usuário final

O usuário final receberá avisos durante a instalação do aplicativo do VPP em vários cenários. A tabela a seguir explica cada condição:

| # | Cenário                                | Convidar para o programa Apple VPP                              | Aviso de instalação de aplicativo | Solicitar ID da Apple |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | BYOD – usuário licenciado                             | Y                                                                                               | Y                                           | Y                                 |
| 2 | Corp – usuário licenciado (dispositivo não supervisionado)     | Y                                                                                               | Y                                           | Y                                 |
| 3 | Corp – usuário licenciado (dispositivo supervisionado)         | Y                                                                                               | N                                           | Y                                 |
| 4 | BYOD – dispositivo licenciado                           | N                                                                                               | Y                                           | N                                 |
| 5 | CORP – dispositivo licenciado (dispositivo não supervisionado)                           | N                                                                                               | Y                                           | N                                 |
| 6 | CORP – dispositivo licenciado (dispositivo supervisionado)                           | N                                                                                               | N                                           | N                                 |
| 7 | Modo de quiosque (dispositivo supervisionado) – dispositivo licenciado | N                                                                                               | N                                           | N                                 |
| 8 | Modo de quiosque (dispositivo supervisionado) – usuário licenciado   | --- | ---                                          | ---                                |

> [!Note]  
> Não é recomendável atribuir aplicativos do VPP a dispositivos de modo de quiosque usando o licenciamento de usuário do VPP.

## <a name="further-information"></a>Informações adicionais

Para recuperar uma licença, você deve alterar a ação de atribuição para **Desinstalar**. A licença será recuperada após a desinstalação do aplicativo. Se você remover um aplicativo que foi atribuído a um usuário, o Intune tentará recuperar todas as licenças de aplicativo associadas a esse usuário.

<!-- 820879 -->You can delete a iOS Volume Purchasing Program (VPP) token using the console. This may be necessary when you have duplicate instances of a VPP token. Deleting a token will also delete any associated apps and assignment. However, deleting a token does not revoke app licenses. Intune cannot revoke app licenses after a token has been deleted. 

Quando um usuário com um dispositivo qualificado tentar instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. É necessário ingressar para continuar a instalação do aplicativo. O convite para ingressar no Apple Volume Purchase Program exige que o usuário possa usar o aplicativo do iTunes no dispositivo iOS. Se você tiver definido uma política para desabilitar o aplicativo da iTunes Store, o licenciamento baseado em usuário para aplicativos VPP não funcionará. A solução é permitir o aplicativo do iTunes removendo a política ou usar o licenciamento baseado em dispositivo.

## <a name="next-steps"></a>Próximas etapas

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.
