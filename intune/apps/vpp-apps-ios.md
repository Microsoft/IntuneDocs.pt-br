---
title: Gerenciar aplicativos Apple adquiridos por volume
titleSuffix: Microsoft Intune
description: Saiba como é possível sincronizar no Microsoft Intune os aplicativos comprados por volume na App Store para iOS e macOS e, depois, gerenciar e acompanhar seu uso.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ff9a37a1dd815b6ec9d7522604796310e7f0b5ce
ms.sourcegitcommit: a7c35efb31c4efd816bd4aba29240013965aee92
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "73984099"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>Como gerenciar aplicativos iOS e macOS adquiridos por meio do Apple Volume Purchase Program com o Microsoft Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A Apple possibilita que você adquira várias licenças de um aplicativo que deseja executar na empresa em dispositivos iOS e macOS. Comprar várias cópias ajuda você a gerenciar com eficiência os aplicativos em sua empresa.

O Microsoft Intune ajuda você a gerenciar várias cópias de aplicativos comprados por meio desse programa:

- Informações sobre licença de relatórios da app store.
- Acompanhamento de quantas licenças você usou.
- Como ajudar você a não instalar mais cópias do aplicativo além das que já possui.

Há dois métodos que você pode usar para atribuir aplicativos comprados por volume:

## <a name="device-licensing"></a>Licenciamento de dispositivo

Quando você atribui um aplicativo a dispositivos, uma licença do aplicativo é usada e permanece associada ao dispositivo ao qual você a atribuiu.

Quando você atribuir aplicativos adquiridos por volume em um dispositivo, o usuário final do dispositivo não precisa fornecer uma ID Apple para acessar o armazenamento.

## <a name="user-licensing"></a>Licenciamento do usuário

Quando você atribui um aplicativo a um usuário, uma licença de aplicativo é usada e associada ao usuário. O aplicativo pode ser executado em até cinco dispositivos de propriedade do usuário (o limite de dispositivos é controlado pela Apple).

Quando você atribui um aplicativo comprado por volume aos usuários, cada usuário final deve ter uma ID da Apple válida e exclusiva para acessar a loja de aplicativos.

Além disso, você pode sincronizar, gerenciar e atribuir livros adquiridos na loja do VPP (Volume Purchase Program) da Apple para dispositivos iOS com o Intune. Para obter mais informações, consulte [Como gerenciar livros eletrônicos do iOS comprados por meio de um programa de compra por volume](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-and-macos-devices"></a>Gerenciar aplicativos comprados por volume para dispositivos iOS e macOS

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps"></a>Dá suporte a aplicativos adquiridos por volume pelo Apple Volume Purchase Program

Compre várias licenças para aplicativos iOS e macOS por meio do [Apple Volume Purchase Program for Business](https://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](https://volume.itunes.apple.com/us/store). Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

### <a name="supports-business-to-business-volume-purchased-apps"></a>Dá suporte a aplicativos adquiridos por volume entre empresas

Além disso, os desenvolvedores terceirizados também podem distribuir de maneira privativa aplicativos a membros autorizados do Volume Purchase Program for Business especificados no App Store Connect. Esses membros do VPP for Business podem entrar na App Store do Volume Purchase Programa e adquirir seus aplicativos. Aplicativos do VPP for Business adquiridos pelo usuário final serão sincronizado com seus locatários do Intune.

## <a name="before-you-start"></a>Antes de começar
Antes de começar, você precisará obter um token do VPP da Apple e carregá-lo em sua conta do Intune. Além disso, você deve compreender os seguintes critérios:

* Você pode associar vários tokens do VPP à sua conta do Intune.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Antes de começar a usar o Apple VPP com o Intune, remova todas as contas de usuários do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança. O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.
* O programa de Perfil de registro do dispositivo (DEP) Apple automatiza o registro de MDM (gerenciamento do dispositivo móvel). Ao usar o DEP, você pode configurar dispositivos da empresa sem tocá-los. Você pode se registrar no programa de DEP usando a mesma conta de agente do programa que usou no VPP da Apple. A ID do Programa de implantação da Apple é exclusiva para programas listados no site dos [Programas de implantação da Apple](https://deploy.apple.com) e não pode ser usada para fazer logon em serviços Apple, como na loja iTunes.
* Quando você atribui aplicativos VPP usando o modelo de licenciamento de usuário para usuários ou dispositivos (com afinidade de usuário), cada usuário do Intune precisa ser associado com uma ID da Apple exclusiva ou um endereço de email ao aceitar os termos e condições da Apple em seu dispositivo.
* Use a ID da Apple exclusiva ou o endereço de email do usuário ao configurar um dispositivo para um novo usuário do Intune. A ID da Apple ou o endereço de email e o usuário do Intune formam um par exclusivo e podem ser usados em até cinco dispositivos.
* Só há suporte para um token VPP para uso em uma conta do Intune por vez. Não reutilize o mesmo token VPP para vários locatários do Intune.

>[!IMPORTANT]
>Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Obter e carregar um token de VPP da Apple

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, escolha **Aplicativos clientes** > **Tokens de VPP da Apple** em **Instalação**.
4. Na lista do painel de tokens do VPP, selecione **Criar**.
5. No painel **Criar token do VPP**, especifique as seguintes informações:
    - **Arquivo de token do VPP** – Se ainda não tiver feito isso, inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education. Depois de se inscrever, baixe o token do Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.
    - **Assumir o controle do token de outro MDM** – Definir essa opção como **Sim** permite que o token seja reatribuído ao Intune de outro MDM.
    - **Nome do token** – um campo administrativo para definir o nome do token.    
    - **País/região**: escolha a loja do país/região do VPP.  O Intune sincroniza aplicativos do VPP para todas as localidades da loja VPP especificada de um país/região.
        > [!WARNING]  
        > Alterar o país/região atualizará os metadados de aplicativos e a URL da loja na próxima sincronização com o serviço da Apple para aplicativos criados com esse token. O aplicativo não será atualizado se não existir na loja do novo país/região.

    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
    - **Atualizações automáticas do aplicativo** – escolha ente **Ligado** ou **Desligado** para habilitar as atualizações automáticas. Quando habilitada, o Intune detecta as atualizações do aplicativo do VPP dentro da App Store e as envia por push automaticamente ao dispositivo durante seu check-in. Atualizações automáticas do aplicativo para aplicativos do Apple VPP serão atualizadas automaticamente somente os aplicativos implantados com a intenção de instalação **Obrigatória**. Para aplicativos implantados com a intenção de instalação **Disponível**, a atualização automática gera uma mensagem de status para o administrador informando que uma nova versão do aplicativo está disponível. Essa mensagem de status pode ser exibida selecionando o aplicativo, selecionando Status de instalação do dispositivo e verificando os Detalhes do Status. Além disso, o usuário verá o aplicativo como não instalado no Portal da Empresa, mesmo que uma versão anterior do aplicativo esteja instalada. Nesse caso, o usuário pode reinstalar o aplicativo clicando em **Instalar** na tela de detalhes do aplicativo no aplicativo Portal da Empresa para instalar a versão mais recente.

        > [!NOTE]
        > As atualizações automáticas do aplicativo funcionam para aplicativos licenciados para o dispositivo e para o usuário no iOS versão 11.0 e posteriores ou no macOS versão 10.12 e posteriores.

    - **Eu concedo à Microsoft a permissão para enviar informações sobre o usuário e o dispositivo para a Apple.** – Você deve selecionar **Eu concordo** para continuar. Para examinar quais dados a Microsoft envia para a Apple, confira [Dados que o Intune envia para a Apple](~/protect/data-intune-sends-to-apple.md).

6. Quando terminar, selecione **Criar**.

O token será exibido na lista do painel de tokens.

Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.

## <a name="to-assign-a-volume-purchased-app"></a>Para atribuir um aplicativo comprado por volume

1. No painel **Intune**, escolha **Aplicativos clientes** > **Aplicativos** em **Gerenciar**.
2. Na lista do painel de aplicativos, escolha o aplicativo que deseja atribuir e, em seguida, selecione **Atribuições**.
3. No painel ***Nome do aplicativo*** - **Atribuições**, escolha **Adicionar grupo** e, em seguida, no painel **Adicionar grupo**, escolha um **Tipo de atribuição** e selecione os grupos de usuários ou de dispositivos do Azure AD para os quais você deseja atribuir o aplicativo.
5. Para cada grupo selecionado, escolha as configurações a seguir:
    - **Tipo** – escolha se o aplicativo será **Disponível** (os usuários finais poderão instalar o aplicativo por meio do Portal da Empresa) ou **Necessário** (o aplicativo será instalado automaticamente nos dispositivos dos usuários finais).
    - **Tipo de licença** -Selecione **Licenciamento de usuário**, ou **Licenciamento de dispositivo**.
6. Quando terminar, escolha **Salvar**.


>[!NOTE]
>Não há suporte para a intenção de implantação disponível para grupos de dispositivos, há suporte apenas para os grupos de usuários. A lista de aplicativos exibida está associada um token. Se você tiver um aplicativo que está associado a vários tokens VPP, verá o mesmo aplicativo exibido várias vezes, uma vez para cada token.

## <a name="end-user-prompts-for-vpp"></a>Avisos do VPP para o usuário final

O usuário final receberá avisos durante a instalação do aplicativo do VPP em vários cenários. A tabela a seguir explica cada condição:

| # | Cenário                                | Convidar para o programa Apple VPP                              | Aviso de instalação de aplicativo | Solicitar ID da Apple |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | BYOD – usuário licenciado                             | S                                                                                               | S                                           | S                                 |
| 2 | Corp – usuário licenciado (dispositivo não supervisionado)     | S                                                                                               | S                                           | S                                 |
| 3 | Corp – usuário licenciado (dispositivo supervisionado)         | S                                                                                               | N                                           | S                                 |
| 4 | BYOD – dispositivo licenciado                           | N                                                                                               | S                                           | N                                 |
| 5 | CORP – dispositivo licenciado (dispositivo não supervisionado)                           | N                                                                                               | S                                           | N                                 |
| 6 | CORP – dispositivo licenciado (dispositivo supervisionado)                           | N                                                                                               | N                                           | N                                 |
| 7 | Modo de quiosque (dispositivo supervisionado) – dispositivo licenciado | N                                                                                               | N                                           | N                                 |
| 8 | Modo de quiosque (dispositivo supervisionado) – usuário licenciado   | --- | ---                                          | ---                                |

> [!Note]  
> Não é recomendável atribuir aplicativos do VPP a dispositivos de modo de quiosque usando o licenciamento de usuário do VPP.

## <a name="revoking-app-licenses"></a>Revogação de licenças de aplicativos

Você pode revogar todas as licenças associadas de aplicativo do VPP (Volume Purchase Program) do iOS ou macOS com base em um determinado dispositivo, usuário ou aplicativo.  Porém, existem algumas diferenças entre as plataformas iOS e macOS. 

### <a name="revoking-app-licenses-on-ios"></a>Revogação de licenças de aplicativos no iOS
Você poderá notificar os usuários quando um aplicativo não estiver mais atribuído a eles. No entanto, a revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo do VPP e recuperar uma licença do aplicativo atribuída a um usuário ou dispositivo, você precisa alterar a ação de atribuição para **Desinstalar**. Quando você remove um aplicativo que foi atribuído a um usuário, o Intune recupera a licença do usuário ou do dispositivo e desinstala o aplicativo do dispositivo. A contagem de licenças recuperadas será refletida no nó **Aplicativos Licenciados** na carga de trabalho de **Aplicativo** do Intune. Após desinstalar um aplicativo VPP e recuperar a licença do aplicativo, é possível optar por atribuir a licença do aplicativo a outro usuário ou dispositivo.


### <a name="revoking-app-licenses-on-macos"></a>Revogação de licenças de aplicativos no macOS
A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Ao revogar uma licença de aplicativo que foi atribuída a um usuário, o Intune recupera a licença do usuário ou do dispositivo. O aplicativo macOS com licença revogada permanece utilizável no dispositivo, mas não pode ser atualizado até que uma licença seja reatribuída ao usuário ou dispositivo. De acordo com a Apple, esses aplicativos são removidos após um período de carência de 30 dias. No entanto, a Apple não fornece um meio para o Intune remover o aplicativo usando a ação de atribuição **Desinstalar**. Porém, você pode optar por atribuir a licença recuperada do aplicativo a outro usuário ou dispositivo.

>[!NOTE]
>O Intune recuperará as licenças de aplicativos VPP do iOS licenciadas para usuários do iOS e macOS quando um funcionário sair da empresa e não fizer mais parte dos grupos do AAD.

## <a name="deleting-vpp-tokens"></a>Como excluir tokens do VPP
<!-- 820879 -->  
É possível excluir um token do VPP (Volume Purchasing Program) da Apple usando o console. Isso pode ser necessário quando houver instâncias duplicadas de um token VPP. Excluir um token também excluirá os aplicativos e a atribuição associados. No entanto, a exclusão de um token não revoga as licenças de aplicativo ou desinstala aplicativos. 

>[!NOTE]
>O Intune não pode revogar licenças de aplicativo após a exclusão de um token. 

<!-- 820870 -->  
Para revogar a licença de todos os aplicativos VPP de um token VPP determinado, primeiro você deve revogar todas as licenças de aplicativo associadas ao token e, em seguida, excluir o token.

## <a name="renewing-app-licenses"></a>Renovação de licenças de aplicativos

Você pode renovar um token VPP da Apple baixando um novo token do portal do Apple Volume Purchase Program e atualizando o token existente no Intune.

## <a name="deleting-a-vpp-app"></a>Como excluir um aplicativo VPP

No momento, não é possível excluir do Microsoft Intune um aplicativo iOS do VPP.

## <a name="assigning-custom-role-permissions-for-vpp"></a>Atribuir permissões de função personalizadas ao VPP

O acesso aos tokens do VPP da Apple e aos aplicativos VPP pode ser controlado de forma independente com as permissões atribuídas às funções personalizadas de administrador no Intune.

* Para permitir que uma função personalizada do Intune gerencie tokens do VPP da Apple, em **Aplicativos cliente** > **Tokens do VPP da Apple**, atribua permissões para **Aplicativos gerenciados**.
* Para permitir que uma função personalizada do Intune gerencie tokens do VPP do iOS, em **Aplicativos cliente** > **Aplicativos**, atribua permissões para **Aplicativos móveis**. 

## <a name="additional-information"></a>Informações adicionais

Quando um usuário com um dispositivo qualificado tentar instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. É necessário ingressar para continuar a instalação do aplicativo. O convite para ingressar no programa Apple Volume Purchase exige que o usuário possa usar o aplicativo da App Store no dispositivo iOS ou macOS. Se você definiu uma política para desabilitar o aplicativo da App Store, o licenciamento baseado em usuário para aplicativos VPP não funciona. A solução é permitir o aplicativo da App Store removendo a política ou usar o licenciamento baseado em dispositivo.

A Apple oferece assistência direta para criar e renovar tokens do VPP. Para obter mais informações, veja [Distribuir conteúdo para usuários com o Programa de compra por volume (VPP)](https://go.microsoft.com/fwlink/?linkid=2014661) na documentação da Apple. 

Se **Atribuído a MDM externo** estiver indicado no portal do Intune, você (o administrador) precisará remover o token do VPP do MDM de terceiros antes de usá-lo no Intune.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Quanto tempo o portal leva para atualizar a contagem de licenças depois que um aplicativo estiver instalado ou tiver sido removido do dispositivo?
A licença deve ser atualizada em algumas horas depois de instalar ou desinstalar um aplicativo. Observe que, se o usuário final remover o aplicativo do dispositivo, a licença ainda será atribuída a esse usuário ou dispositivo.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>É possível substituir um aplicativo e, em caso afirmativo, em que circunstância?
Sim. O administrador do Intune pode substituir um aplicativo. Por exemplo, se o administrador comprar 100 licenças para o aplicativo XYZ e, em seguida, direcionar o aplicativo a um grupo com 500 membros. Os 100 primeiros membros (usuários ou dispositivos) obterão a licença atribuída a eles; o restante dos membros falharão na atribuição de licença.

### <a name="how-frequently-does-intune-sync-vpp-tokens-with-apple"></a>Com que frequência o Intune sincroniza tokens do VPP com a Apple?
O Intune sincroniza as licenças e tokens do VPP duas vezes por dia com a Apple. O administrador do Intune pode iniciar uma sincronização manual em **Aplicativos cliente** > **Tokens do VPP da Apple**.

## <a name="next-steps"></a>Próximas etapas

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.
