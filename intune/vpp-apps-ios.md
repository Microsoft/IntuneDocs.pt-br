---
title: Gerenciar aplicativos adquiridos por volume no iOS
titlesuffix: Azure portal
description: "Saiba como você pode sincronizar no Intune os aplicativos comprados por volume na loja do iOS e, depois, gerenciar e acompanhar seu uso."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: addcc2c9a939b8dc62d708b3f9f000cb7c09cef3
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Como gerenciar aplicativos iOS adquiridos por meio de um programa de aquisição com base em volume com o Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Adquirir várias cópias de um aplicativo ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.

O Microsoft Intune ajuda você a gerenciar aplicativos comprados por meio desse programa ao:

- Relatar informações de licença da loja de aplicativos
- Acompanhar quantas licenças você usou
- Ajudar você a não instalar mais cópias do aplicativo além das que já possui

Há dois métodos que você pode usar para atribuir aplicativos comprados por volume:

### <a name="device-licensing"></a>Licenciamento de dispositivo

Quando você atribui um aplicativo a dispositivos, uma licença do aplicativo é usada e permanece associada ao dispositivo ao qual você a atribuiu.
Quando você atribuir aplicativos adquiridos por volume em um dispositivo, o usuário final do dispositivo não precisa fornecer uma ID Apple para acessar o armazenamento. 



### <a name="user-licensing"></a>Licenciamento do usuário

Quando você atribui um aplicativo a usuários, uma licença de aplicativo é usada e associada ao usuário. O aplicativo pode ser executado em vários dispositivos de propriedade do usuário (com um limite controlado pela Apple).
Quando você atribui um aplicativo comprado por volume aos usuários, cada usuário final deve ter uma ID da Apple válida e exclusiva para acessar a loja de aplicativos.


Além disso, você pode sincronizar, gerenciar e atribuir livros adquiridos na loja Apple de programas adquiridos por volume com o Intune. Para obter mais informações, consulte [Como gerenciar livros eletrônicos do iOS comprados por meio de um programa de compra por volume](vpp-ebooks-ios.md).


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Gerenciar aplicativos adquiridos por volume para dispositivos iOS
Compre várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

## <a name="before-you-start"></a>Antes de começar
Antes de começar, você precisará obter um token do VPP da Apple e carregá-lo em sua conta do Intune. Além disso, você deve compreender os seguintes critérios:

* Você pode associar vários tokens de programa de compra por volume a sua conta do Intune.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Antes de começar a usar o iOS VPP com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança. O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.
* O Intune dá suporte à adição de até 256 tokens VPP.
* Se você atribuir um aplicativo comprado por volume para um dispositivo registrado por meio de um Perfil de Registro de Dispositivo ou o Apple Configurator, apenas os aplicativos voltados para os dispositivos funcionarão. Não é possível direcionar aplicativos comprados por volume para os usuários de um dispositivo DEP, que não têm nenhuma afinidade de usuário.
Isso ocorre porque o licenciamento de usuário por VPP do iOS pode permitir que milhares de dispositivos sejam registrados usando a mesma conta de usuário. O licenciamento de usuário por VPP do iOS permite que um usuário final instale um aplicativo em 5 a 10 dispositivos.
Isso significa que os primeiros dispositivos do DEM registrados terão o aplicativo VPP instalado usando o licenciamento do usuário e os outros dispositivos não obterão o aplicativo.
* Só há suporte para um token VPP para uso em uma conta do Intune por vez. Não reutilize o mesmo token VPP para vários locatários do Intune.
* Quando você atribui aplicativos VPP usando o modelo de licenciamento de usuário para usuários ou dispositivos (com afinidade de usuário), cada usuário do Intune precisa ser associado com uma ID da Apple exclusiva ou um endereço de email ao aceitar os termos e condições da Apple em seu dispositivo.
Use a ID da Apple exclusiva ou o endereço de email do usuário ao configurar m dispositivo para um novo usuário do Intune. A ID da Apple ou o endereço de email e o usuário do Intune formam um par exclusivo e podem ser usado em até 5 dispositivos.

>[!IMPORTANT]
>Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Obter e carregar um token de VPP da Apple

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

## <a name="to-assign-a-volume-purchased-app"></a>Para atribuir um aplicativo comprado por volume

1.  Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Licenças de Aplicativos**.
2.  Na folha de lista de aplicativos, escolha o aplicativo que deseja atribuir e, em seguida, escolha '**...**' > **Atribuir Grupos**.
3.  Na folha *<app name>* - **Atribuições**, selecione **Gerenciar** > **Atribuições**.
4.  Escolha **Selecionar Grupos** e, na folha **Selecionar grupos**, escolha o usuário ou os grupos de dispositivos do Azure AD para os quais você deseja atribuir o aplicativo.
5.  Para cada grupo selecionado, escolha as configurações a seguir:
    - **Tipo** -Escolha se o aplicativo será **Disponível** (os usuários finais podem instalar o aplicativo do Portal da empresa), ou **Necessário** (dispositivos de usuários finais terão o aplicativo instalado automaticamente).
    - **Tipo de licença** -Selecione **Licenciamento de usuário**, ou **Licenciamento de dispositivo**.
6.  Quando terminar, escolha **Salvar**.


>[!NOTE]
>A lista de aplicativos exibida está associada um token. Se você tiver um aplicativo que está associado a vários tokens VPP, verá o mesmo aplicativo exibido várias vezes, uma vez para cada token.

## <a name="further-information"></a>Informações adicionais

Para recuperar uma licença, você deve alterar a ação de atribuição para Desinstalar. A licença será recuperada após a desinstalação do aplicativo. Se você remover um aplicativo que foi atribuído a um usuário, o Intune tentará recuperar todas as licenças de aplicativo associadas a esse usuário.

Quando um usuário com um dispositivo qualificado tentar instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. É necessário ingressar para continuar a instalação do aplicativo. O convite para ingressar no Apple Volume Purchase Program exige que o usuário possa usar o aplicativo do iTunes no dispositivo iOS. Se você tiver definido uma política para desabilitar o aplicativo da iTunes Store, o licenciamento baseado em usuário para aplicativos VPP não funcionará. A solução é permitir o aplicativo do iTunes removendo a política ou usar o licenciamento baseado em dispositivo.



## <a name="next-steps"></a>Próximas etapas

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.