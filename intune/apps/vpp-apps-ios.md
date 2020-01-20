---
title: Gerenciar aplicativos Apple adquiridos por volume
titleSuffix: Microsoft Intune
description: Saiba como é possível sincronizar no Microsoft Intune os aplicativos comprados por volume na App Store para iOS e macOS e, depois, gerenciar e acompanhar seu uso.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/17/2019
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
ms.openlocfilehash: 0bc511669ec8a88523581b3afbcca161d5208934
ms.sourcegitcommit: de663ef5f3e82e0d983899082a7f5b62c63f24ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75956219"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>Como gerenciar aplicativos iOS e macOS adquiridos por meio do Apple Volume Purchase Program com o Microsoft Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A Apple permite que você compre várias licenças para um aplicativo que você deseja usar em sua organização em dispositivos iOS e macOS usando o [Apple Business Manager](https://business.apple.com/) ou o [Apple School Manager](https://school.apple.com/). Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume. A compra de licenças de aplicativos ajuda você a gerenciar aplicativos com eficiência em sua empresa e a manter a propriedade e o controle dos aplicativos comprados. 

O Microsoft Intune ajuda você a gerenciar os aplicativos comprados por meio desse programa:

- Sincronizando os tokens de localização baixados no Apple Business Manager.
- Acompanhando quantas licenças estão disponíveis e quantas foram usadas para os aplicativos comprados.
- Ajudando você a instalar aplicativos até o número de licenças existentes.

Além disso, você pode sincronizar, gerenciar e atribuir livros comprados no Apple Business Manager com o Intune aos dispositivos iOS. Para obter mais informações, consulte [Como gerenciar livros eletrônicos do iOS comprados por meio de um programa de compra por volume](vpp-ebooks-ios.md).

## <a name="what-are-location-tokens"></a>O que são tokens de localização?
Os tokens de localização também são conhecidos como tokens VPP (Volume Purchase Program). Esses tokens são usados para atribuir e gerenciar licenças compradas com o Apple Business Manager. Os Gerenciadores de Conteúdo podem comprar e associar licenças com tokens de localização aos quais têm permissões no Apple Business Manager. Esses tokens de localização são então baixados no Apple Business Manager e carregados no Microsoft Intune. O Microsoft Intune dá suporte ao upload de vários tokens de localização por locatário. Cada token é válido por um ano.

## <a name="how-are-purchased-apps-licensed"></a>Como os aplicativos comprados são licenciados?
Os aplicativos comprados podem ser atribuídos a grupos usando dois tipos de licenças oferecidos pela Apple para dispositivos iOS e macOS.

|   | Licenciamento do Dispositivo | Licenciamento do Usuário |
|-----|------------------|----------------|
| **Conexão à App Store** | Não necessário. | É necessário que cada usuário final use uma ID da Apple exclusiva quando precisar entrar na App Store. |
| **Configuração do dispositivo bloqueando o acesso à App Store** | Os aplicativos podem ser instalados e atualizados pelo Portal da Empresa. | O convite para ingressar no Apple VPP exige o acesso à App Store. Se você tiver definido uma política para desabilitar a App Store, o licenciamento do usuário para aplicativos VPP não funcionará. |
| **Atualização automática do aplicativo** | Conforme configurado pelo administrador do Intune nas configurações de token VPP da Apple, em que o **tipo de atribuição** do aplicativo é **obrigatório**. <br> <br> Se o **tipo de atribuição** for **disponível para dispositivos registrados**, as atualizações de aplicativo disponíveis poderão ser instaladas pelo Portal da Empresa. | Conforme definido pelo usuário final nas configurações pessoais da App Store. Isso não pode ser gerenciado pelo administrador do Intune. |
| **Registro de Usuário** | Não há suporte. | Há suporte com o uso de IDs Gerenciadas da Apple. |
| **Livros** | Não há suporte. | Com suporte. |
| **Licenças usadas** | Uma licença por dispositivo. A licença é associada ao dispositivo. | Uma licença para até cinco dispositivos usando a mesma ID pessoal da Apple. A licença é associada ao usuário. <br> <br> Um usuário final associado a uma ID pessoal da Apple e uma ID Gerenciada da Apple no Intune consome duas licenças de aplicativo.|
| **Migração de licença** | Os aplicativos podem migrar silenciosamente de licenças de usuário para dispositivo. | Os aplicativos não podem migrar de licenças de dispositivo para usuário. |

> [!NOTE]  
> O Portal da Empresa não mostra os aplicativos licenciados para dispositivo nos dispositivos de Registro do Usuário, porque só os aplicativos licenciados pelo usuário podem ser instalados em dispositivos de Registro do Usuário.

## <a name="what-app-types-are-supported"></a>Há suporte para quais tipos de aplicativos?
Você pode comprar e distribuir aplicativos públicos e privados usando o Apple Business Manager.
- **Aplicativos da loja:** usando o Apple Business Manager, os Gerenciadores de Conteúdo podem comprar aplicativos gratuitos e pagos disponíveis na App Store.
- **Aplicativos personalizados:** usando o Apple Business Manager, os Gerenciadores de Conteúdo também podem comprar aplicativos personalizados disponibilizados de modo privado para a sua organização. Esses aplicativos são adaptados às necessidades específicas da sua organização pelos desenvolvedores com os quais você trabalha diretamente. Saiba mais sobre [como distribuir aplicativos personalizados](https://developer.apple.com/business/custom-apps/).

## <a name="prerequisites"></a>Pré-requisitos
- Uma conta do [Apple Business Manager](https://business.apple.com/) ou do [Apple School Manager](https://school.apple.com/) para a sua organização. 
- Licenças de aplicativo compradas atribuídas a um ou mais tokens de localização. 
- Tokens de localização baixados. 

> [!IMPORTANT]
> - Um token de localização só pode ser usado com uma solução de gerenciamento de dispositivo por vez. Antes de começar a usar os aplicativos comprados com o Intune, revogue e remova os tokens de localização existentes usados com outro fornecedor de MDM (gerenciamento de dispositivo móvel). 
> - Só há suporte a um token de localização para uso em um locatário do Intune por vez. Não reutilize o mesmo token para vários locatários do Intune.
> - Por padrão, o Intune sincroniza os tokens de localização com a Apple duas vezes por dia. Você pode iniciar uma sincronização manual a qualquer momento no Intune.
> - Depois de importar o token de localização para o Intune, não importe o mesmo token para qualquer outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.

## <a name="migrate-from-volume-purchase-program-vpp-to-apps-and-books"></a>Migração do VPP (Volume Purchase Program) para Aplicativos e Livros
Caso a sua organização ainda não tenha migrado para o Apple Business Manager nem para o Apple School Manager, examine as [diretrizes da Apple de como fazer a migração para Aplicativos e Livros](https://support.apple.com/HT208257) antes de prosseguir para gerenciar os aplicativos comprados no Intune.

> [!IMPORTANT]
> - Para obter a melhor experiência de migração, migre apenas um comprador do VPP por localização. Se cada comprador migrar para uma localização exclusiva, todas as licenças, atribuídas e não atribuídas, migrarão para Aplicativos e Livros.
> - Não exclua o token VPP herdado existente no Intune nem os aplicativos e as atribuições associadas ao token VPP herdado existente no Intune. Essas ações exigirão que todas as atribuições de aplicativo sejam recriadas no Intune.

Migre o conteúdo e os tokens VPP comprados existentes para Aplicativos e Livros no Apple Business Manager ou no Apple School Manager da seguinte maneira:

1. Convide os compradores do VPP a ingressar na sua organização e oriente cada usuário a selecionar uma localização exclusiva. 
2. Verifique se todos os compradores do VPP na sua organização concluíram a etapa 1 antes de continuar.
3. Verifique se todas as licenças e todos os aplicativos comprados foram migrados para Aplicativos e Livros no Apple Business Manager ou no Apple School Manager.
4. Baixe o novo token de localização acessando o **Apple Business (ou o School) Manager** > **Configurações** > **Aplicativos e Livros** > **Meus Tokens de Servidor**.
5. Atualize o token de localização no Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft acessando **Administração de locatários** > **Conectores e tokens** > **Tokens VPP da Apple** e sincronize o token.

## <a name="upload-an-apple-vpp-or-location-token"></a>Carregar um token de localização ou VPP da Apple

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecione **Administração de locatários** > **Conectores e tokens** > **Tokens VPP da Apple**.
4. Na lista do painel de tokens do VPP, selecione **Criar**.
5. No painel **Criar token do VPP**, especifique as seguintes informações:
    - **Arquivo de token VPP**: se você ainda não tiver feito isso, inscreva-se no Apple Business Manager ou no Apple School Manager. Depois de se inscrever, baixe o token do Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple**: insira a ID Gerenciada da Apple da conta associada ao token carregado.
    - **Assumir o controle do token de outro MDM**: se você definir esta opção como **Sim**, permitirá que o token seja reatribuído ao Intune de outra solução de MDM.
    - **Nome do token** – um campo administrativo para definir o nome do token.    
    - **País/região**: escolha a loja do país/região do VPP.  O Intune sincroniza aplicativos do VPP para todas as localidades da loja VPP especificada de um país/região.
        > [!WARNING]  
        > A alteração do país/da região atualizará os metadados de aplicativos e a URL da App Store na próxima sincronização com o serviço da Apple nos aplicativos criados com esse token. O aplicativo não será atualizado se não existir na loja do novo país/região.

    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
    - **Atualizações automáticas do aplicativo** – escolha ente **Ligado** ou **Desligado** para habilitar as atualizações automáticas. Quando habilitada, o Intune detecta as atualizações do aplicativo do VPP dentro da App Store e as envia por push automaticamente ao dispositivo durante seu check-in. 
        
        > [!NOTE] 
        > Atualizações automáticas do aplicativo para aplicativos do Apple VPP serão atualizadas automaticamente somente os aplicativos implantados com a intenção de instalação **Obrigatória**. Para aplicativos implantados com a intenção de instalação **Disponível**, a atualização automática gera uma mensagem de status para o administrador informando que uma nova versão do aplicativo está disponível. Essa mensagem de status pode ser exibida selecionando o aplicativo, selecionando Status de instalação do dispositivo e verificando os Detalhes do Status.  

    - **Eu concedo à Microsoft a permissão para enviar informações sobre o usuário e o dispositivo para a Apple.** – Você deve selecionar **Eu concordo** para continuar. Para examinar quais dados a Microsoft envia para a Apple, confira [Dados que o Intune envia para a Apple](~/protect/data-intune-sends-to-apple.md).

6. Quando terminar, selecione **Criar**. O token será exibido na lista do painel de tokens.

## <a name="synchronize-a-vpp-token"></a>Sincronizar um token VPP
Você pode sincronizar os nomes de aplicativos, os metadados e as informações de licença dos aplicativos comprados no Intune escolhendo **Sincronizar** em um token selecionado.

## <a name="assign-a-volume-purchased-app"></a>Atribuir um aplicativo comprado por volume

1. Selecione **Aplicativos** > **Todos os aplicativos**.
2. Na lista do painel de aplicativos, escolha o aplicativo que deseja atribuir e, em seguida, selecione **Atribuições**.
3. No painel **Nome do aplicativo** - **Atribuições**, escolha **Adicionar grupo** e, em seguida, no painel **Adicionar grupo**, escolha um **Tipo de atribuição** e selecione os grupos de usuários ou de dispositivos do Azure AD para os quais você deseja atribuir o aplicativo.
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
| 1 | BYOD: licenciado pelo usuário (não um dispositivo de Registro do Usuário)                             | S                                                                                               | S                                           | S                                 |
| 2 | Corp – usuário licenciado (dispositivo não supervisionado)     | S                                                                                               | S                                           | S                                 |
| 3 | Corp – usuário licenciado (dispositivo supervisionado)         | S                                                                                               | N                                           | S                                 |
| 4 | BYOD – dispositivo licenciado                           | N                                                                                               | S                                           | N                                 |
| 5 | CORP – dispositivo licenciado (dispositivo não supervisionado)                           | N                                                                                               | S                                           | N                                 |
| 6 | CORP – dispositivo licenciado (dispositivo supervisionado)                           | N                                                                                               | N                                           | N                                 |
| 7 | Modo de quiosque (dispositivo supervisionado) – dispositivo licenciado | N                                                                                               | N                                           | N                                 |
| 8 | Modo de quiosque (dispositivo supervisionado) – usuário licenciado   | --- | ---                                          | ---                                |

> [!Note]  
> Não é recomendável atribuir aplicativos VPP a dispositivos de modo de quiosque usando o licenciamento do usuário.

## <a name="revoking-app-licenses"></a>Revogação de licenças de aplicativos

Você pode revogar todas as licenças associadas de aplicativo do VPP (Volume Purchase Program) do iOS ou macOS com base em um determinado dispositivo, usuário ou aplicativo.  Porém, existem algumas diferenças entre as plataformas iOS e macOS. 

|   | iOS | macOS |
|-----|------------------|----------------|
| **Remover uma atribuição de aplicativo** | Quando você remove um aplicativo que foi atribuído a um usuário, o Intune recupera a licença do usuário ou do dispositivo e desinstala o aplicativo do dispositivo. | Quando você remove um aplicativo que foi atribuído a um usuário, o Intune recupera a licença do usuário ou do dispositivo. O aplicativo não é desinstalado do dispositivo. |
| **Revogar uma licença de aplicativo** | A revogação de uma licença de aplicativo recupera a licença de aplicativo do usuário ou do dispositivo. É necessário alterar a atribuição para **Desinstalar** para remover o aplicativo do dispositivo. | A revogação de uma licença de aplicativo recupera a licença de aplicativo do usuário ou do dispositivo. O aplicativo macOS com licença revogada permanece utilizável no dispositivo, mas não pode ser atualizado até que uma licença seja reatribuída ao usuário ou dispositivo. De acordo com a Apple, esses aplicativos são removidos após um período de carência de 30 dias. No entanto, a Apple não fornece um meio para o Intune remover o aplicativo usando a ação de atribuição Desinstalar.

>[!NOTE]
> - O Intune recupera as licenças de aplicativo quando um funcionário sai da empresa e deixa de fazer parte dos grupos do AAD.
> - Ao atribuir um aplicativo comprado com a intenção **Desinstalar**, o Intune recupera a licença e desinstala o aplicativo.
> - As licenças de aplicativo não são recuperadas quando um dispositivo é removido do gerenciamento do Intune. 

## <a name="deleting-vpp-tokens"></a>Como excluir tokens do VPP
<!-- 820879 -->  
É possível excluir um token do VPP (Volume Purchasing Program) da Apple usando o console. Isso pode ser necessário quando houver instâncias duplicadas de um token VPP. Excluir um token também excluirá os aplicativos e a atribuição associados. No entanto, a exclusão de um token não revoga as licenças de aplicativo ou desinstala aplicativos. 

>[!NOTE]
>O Intune não pode revogar licenças de aplicativo após a exclusão de um token. 

<!-- 820870 -->  
Para revogar a licença de todos os aplicativos VPP de um token VPP determinado, primeiro você deve revogar todas as licenças de aplicativo associadas ao token e, em seguida, excluir o token.

## <a name="renewing-app-licenses"></a>Renovação de licenças de aplicativos

Você pode renovar um token VPP da Apple baixando um novo token no Apple Business Manager ou no Apple School Manager e atualizando o token existente no Intune.

## <a name="deleting-a-vpp-app"></a>Como excluir um aplicativo VPP

No momento, não é possível excluir do Microsoft Intune um aplicativo iOS do VPP.

## <a name="assigning-custom-role-permissions-for-vpp"></a>Atribuir permissões de função personalizadas ao VPP

O acesso aos tokens do VPP da Apple e aos aplicativos VPP pode ser controlado de forma independente com as permissões atribuídas às funções personalizadas de administrador no Intune.

* Para permitir que uma função personalizada do Intune gerencie tokens VPP da Apple, em **Aplicativos** > **Tokens VPP da Apple**, atribua permissões para **Aplicativos gerenciados**.
* Para permitir que uma função personalizada do Intune gerencie aplicativos adquiridos usando tokens VPP do iOS, em **Aplicativos** > **Todos os aplicativos**, atribua permissões para **Aplicativos móveis**. 

## <a name="additional-information"></a>Informações adicionais

A Apple oferece assistência direta para criar e renovar tokens do VPP. Para obter mais informações, veja [Distribuir conteúdo para usuários com o Programa de compra por volume (VPP)](https://go.microsoft.com/fwlink/?linkid=2014661) na documentação da Apple. 

Se **Atribuído a MDM externo** estiver indicado no portal do Intune, você (o administrador) precisará remover o token do VPP do MDM de terceiros antes de usá-lo no Intune.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="how-many-tokens-can-i-upload"></a>Quantos tokens podem ser carregados?
Você pode carregar até 3 mil tokens no Intune.

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Quanto tempo o portal leva para atualizar a contagem de licenças depois que um aplicativo estiver instalado ou tiver sido removido do dispositivo?
A licença deve ser atualizada em algumas horas depois de instalar ou desinstalar um aplicativo. Observe que, se o usuário final remover o aplicativo do dispositivo, a licença ainda será atribuída a esse usuário ou dispositivo.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>É possível substituir um aplicativo e, em caso afirmativo, em que circunstância?
Sim. O administrador do Intune pode substituir um aplicativo. Por exemplo, se o administrador comprar 100 licenças para o aplicativo XYZ e, em seguida, direcionar o aplicativo a um grupo com 500 membros. Os 100 primeiros membros (usuários ou dispositivos) obterão a licença atribuída a eles; o restante dos membros falharão na atribuição de licença.


## <a name="next-steps"></a>Próximas etapas

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.

Confira [Como solucionar problemas de aplicativos](~/apps/troubleshoot-app-install.md) para obter informações sobre como solucionar problemas relacionados a aplicativos.
