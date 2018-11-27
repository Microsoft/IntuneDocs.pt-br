---
title: Adicionar aplicativos ao Microsoft Intune
titlesuffix: ''
description: Saiba como adicionar aplicativos ao Microsoft Intune para poder atribui-los a usuários e dispositivos. O Intune é compatível com uma ampla variedade de tipos de aplicativos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2a0fb9aca406c1a49c979b59e5d879d66a730c1c
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185877"
---
# <a name="add-apps-to-microsoft-intune"></a>Adicionar aplicativos ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Adicione os aplicativos ao Microsoft Intune antes de atribuir, monitorar, configurar ou protegê-los.

Os usuários de aplicativos e dispositivos na empresa (a força de trabalho da empresa) podem ter vários requisitos de aplicativo. Antes de adicionar aplicativos ao Intune e disponibilizá-los à sua força de trabalho, você precisa avaliar e entender alguns conceitos básicos sobre os aplicativos. Você precisa entender os vários tipos de aplicativos disponíveis para o Intune. Você precisa avaliar os requisitos do aplicativo, como as plataformas e os recursos necessários à sua força de trabalho. Você precisa determinar se vai usar o Intune para gerenciar os dispositivos (incluindo aplicativos) ou se o próprio Intune gerenciará os aplicativos sem gerenciar os dispositivos. Por fim, você deve determinar os aplicativos e recursos de que a sua força de trabalho precisa e quem precisa deles. As informações neste artigo ajudarão você a começar.

## <a name="app-types-in-microsoft-intune"></a>Tipos de aplicativo no Microsoft Intune

O Intune é compatível com uma ampla variedade de tipos de aplicativos. As opções disponíveis são diferentes para cada tipo de aplicativo. O Intune permite que você adicione e atribua os seguintes tipos de aplicativo:

| Tipos de aplicativo | Instalação | Updates |
|---|---|---|
| Aplicativos da loja (aplicativos da loja) | O Intune instala o aplicativo no dispositivo.  | As atualizações de aplicativo são automáticas.   |
| Aplicativos escritos internamente (linha de negócios)  | O Intune instala o aplicativo no dispositivo (você fornece o arquivo de instalação).     | É necessário atualizar o aplicativo.  |
| Aplicativos que são internos (aplicativos internos)    | O Intune instala o aplicativo no dispositivo.  | As atualizações de aplicativo são automáticas.  |
| Aplicativos na Web (link da Web) | O Intune cria um atalho para o aplicativo Web na tela inicial do dispositivo.  | As atualizações de aplicativo são automáticas.    |

### <a name="specific-app-type-details"></a>Detalhes do tipo de aplicativo específico
 
A tabela a seguir lista os tipos de aplicativo específicos e como você pode adicioná-los usando o painel **Adicionar aplicativo**:

| **Tipo específico a aplicativos** | **Tipo geral** | **Procedimentos específicos a aplicativos** |
| --- | --- | --- |
| Aplicativos da Android Store  | Aplicativo da Store  | Selecione **Android** como o **tipo de aplicativo** e digite a URL do Google Play do aplicativo. |
| Aplicativos da iOS Store  | Aplicativo da Store  | Selecione **iOS** como o **tipo de aplicativo**, procure o aplicativo e selecione o aplicativo no Intune. |
| Aplicativos da Windows Phone 8.1 Store  | Aplicativo da Store  | Selecione **Windows Phone 8.1** como o **tipo de aplicativo** e insira a URL da Microsoft Store do aplicativo. |
| Aplicativos da Microsoft Store  | Aplicativo da Store  | Selecione **Windows** como o **tipo de aplicativo** e insira a URL da Microsoft Store do aplicativo. |
| Aplicativos de perfil de trabalho do Android | Aplicativo da Store  | Localize e aprove o aplicativo do perfil de trabalho Android na Google Play Store gerenciada.  |
| Aplicativos do Office 365 para Windows 10  | Aplicativo da Store (Office 365) | Selecione **Windows 10** no **Pacote do Office 365** como o **tipo de aplicativo** e, em seguida, selecione o aplicativo do Office 365 que você deseja instalar.  |
| Aplicativos do Office 365 para macOS | Aplicativo da Store (Office 365) | Selecione **macOS** no **Pacote do Office 365** como o **tipo de aplicativo** e, em seguida, selecione o pacote do aplicativo do Office 365. |
| Aplicativos LOB para Android | Aplicativos LOB | Selecione aplicativo de **Linha de negócios** como o **tipo de aplicativo**, selecione o **Arquivo do pacote do aplicativo** e, em seguida, insira um arquivo de instalação do Android com a extensão **.apk**.  |
| Aplicativos LOB para iOS | Aplicativos LOB | Selecione aplicativo de **Linha de negócios** como o **tipo de aplicativo**, selecione o **Arquivo do pacote do aplicativo** e, em seguida, insira um arquivo de instalação do iOS com a extensão **.ipa**.  |
| Aplicativos LOB para Windows Phone | Aplicativos LOB | Selecione aplicativo de **Linha de negócios** como o **tipo de aplicativo**, selecione o **Arquivo do pacote do aplicativo** e, em seguida, insira um arquivo de instalação do Windows Phone com a extensão **.xap**.  |
| Aplicativos LOB para Windows | Aplicativos LOB | Selecione aplicativo de **Linha de negócios** como o tipo de aplicativo, selecione o **Arquivo do pacote do aplicativo** e, em seguida, insira um arquivo de instalação do Windows com a extensão **.msi**, **.appx**, **.appxbundle**, **.msix** e **.msixbundle**. |
| Aplicativo iOS interno  | Aplicativo interno | Selecione **Aplicativo interno** como o **tipo de aplicativo** e selecione o aplicativo interno na lista de aplicativos fornecidos.  |
| Aplicativo interno Android  | Aplicativo interno | Selecione **Aplicativo interno** como o **tipo de aplicativo** e selecione o aplicativo interno na lista de aplicativos fornecidos.  |
| Aplicativos Web  | Aplicativo Web  | Selecione **Link da Web** como o **tipo de aplicativo** e insira uma URL válida apontando para o aplicativo Web.  |
| Aplicativo do Windows (Win32)  | Aplicativos LOB  | Selecione **aplicativo do Windows (Win32)** como o **tipo de aplicativo**, selecione o **Arquivo do pacote do aplicativo** e, em seguida, um arquivo de instalação com a extensão **.intunewin**.  |

Você pode adicionar um aplicativo no Microsoft Intune, selecionando **Aplicativos clientes** > **Aplicativos** > **Adicionar**. O painel **Adicionar aplicativo** aparece e permite que você selecione o **Tipo de aplicativo**. 

>[!TIP]
> Um aplicativo LOB é um aplicativo que pode ser adicionado de um arquivo de instalação do aplicativo. Por exemplo, para instalar um aplicativo LOB do iOS, adicione o aplicativo selecionando **Aplicativo de linha de negócios** como o **Tipo de aplicativo** no painel **Adicionar aplicativo**. Em seguida, selecione o arquivo do pacote do aplicativo (extensão .ipa). Normalmente, esses tipos de aplicativos são escritos internamente.

## <a name="assess-app-requirements"></a>Avalie os requisitos do aplicativo
Como um administrador de TI, você não apenas determina quais aplicativos o seu grupo deve usar, mas também as funcionalidades necessárias para cada grupo e subgrupo. Para cada aplicativo, você determina as plataformas necessárias, os grupos de usuários que precisam do aplicativo, as políticas de configuração a serem aplicadas a esses grupos e as políticas de proteção a serem aplicadas.  

Além disso, você precisa determinar se quer se concentrar no MDM (gerenciamento de dispositivo móvel) ou somente no MAM (gerenciamento de aplicativo móvel). 

Usar o Intune para gerenciar o dispositivo com o MDM é útil quando:
- Os usuários precisam um perfil de conectividade corporativo por VPN ou Wi-Fi para serem produtivos.
- Os usuários precisam que um conjunto de aplicativos seja enviado por push para seus dispositivos.
- A sua organização precisa manter a conformidade com políticas regulatórias ou outras políticas que chamam controles específicos de MDM, como segurança ou criptografia.

Usar o Intune para gerenciar aplicativos com o MAM sem gerenciar o dispositivo é útil quando:
- Você quer permitir que os usuários usem seus próprios dispositivos (BYOD).
- Você quer fornecer uma mensagem pop-up única para que os usuários saibam que as proteções de MAM estão em vigor, em vez de notificações contínuas no nível do dispositivo.
- Você quer estar em conformidade com políticas que exigem menos recursos de gerenciamento de dispositivos pessoais. Por exemplo, você quer gerenciar os dados corporativos para os aplicativos, em vez de gerenciar os dados corporativos para todo o dispositivo.

Para obter mais informações, consulte [Comparar MDM e MAM](byod-technology-decisions.md).

### <a name="determine-who-will-use-the-app"></a>Determinar quem usará o aplicativo

Ao determinar de quais aplicativos a sua força de trabalho precisa, considere os vários grupos de usuários e de aplicativos que eles usam. Também é interessante saber quais são esses grupos depois de adicionar um aplicativo. Depois de adicionar um aplicativo, atribua um grupo de usuários que poderão usá-lo. 

Primeiro, você precisa determinar qual grupo deve ter acesso ao aplicativo com base na confidencialidade dos dados que o aplicativo contém. Talvez você precise incluir ou excluir determinados tipos de funções na sua organização. Por exemplo, somente determinados aplicativos LOB podem ser necessários para o seu grupo de vendas, enquanto pessoas concentradas na engenharia, nas finanças, no RH ou na parte jurídica podem não precisar usar os aplicativos LOB. Além disso, o seu grupo de vendas pode precisar de proteção de dados adicional e de acesso a serviços corporativos internos em seus dispositivos móveis. Você precisa determinar como esse grupo se conectará aos recursos usando o aplicativo. Os dados que o aplicativo acessa ficarão hospedados na nuvem ou localmente? Além disso, como os usuários se conectarão aos recursos usando o aplicativo? 

O Intune também dá suporte à habilitação do acesso a aplicativos cliente que precisam de acesso seguro aos dados locais, como servidores de aplicativos de linha de negócios. Normalmente, você fornece esse tipo de acesso usando [certificados gerenciados pelo Intune](certificates-configure.md) para controle de acesso, em conjunto com um Gateway de VPN padrão ou proxy no perímetro, como o Proxy de Aplicativo do Azure Active Directory. A [Ferramenta de Disposição do Aplicativo e o SDK do Aplicativo](apps-prepare-mobile-application-management.md) do Intune podem ajudar a conter os dados acessados no aplicativo de linha de negócios, de modo que ele não possa passar dados corporativos para serviços ou aplicativos de consumidor.

Use o [Guia de planejamento de implantação, design e implementação do Intune](planning-guide.md) para ajudar a determinar como você identifica os grupos organizacionais associados a cada cenário de caso de uso e caso de subuso do aplicativo. Para obter informações sobre como atribuir aplicativos a grupos, veja [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

### <a name="determine-the-type-of-app-for-your-solution"></a>Determinar o tipo de aplicativo para sua solução

Você pode escolher entre os seguintes tipos de aplicativo:
- **Aplicativos da Store**: aplicativos que foram carregados na Microsoft Store, na Store do iOS ou na Store do Android são aplicativos da Store. O provedor de um aplicativo da Store mantém e fornece atualizações do aplicativo. Selecione o aplicativo na lista da Store e adicione-o usando o Intune como um aplicativo disponível para seus usuários.
- **Aplicativos escritos internamente (linha de negócios)**: aplicativos criados internamente são aplicativos LOB (linha de negócios). A funcionalidade desse tipo de aplicativo foi criada para uma das plataformas compatíveis com o Intune, como Windows, iOS ou Android. Sua organização cria e lhe fornece atualizações como um arquivo separado. Você fornece atualizações do aplicativo aos usuários adicionando e implantando as atualizações usando o Intune.
- **Aplicativos na Web**: aplicativos Web são aplicativos de cliente-servidor. O servidor fornece o aplicativo Web, que inclui a interface do usuário, o conteúdo e a funcionalidade. Além disso, plataformas modernas de hospedagem na Web geralmente oferecem segurança, balanceamento de carga e outros benefícios. Este tipo de aplicativo é mantido separadamente na Web. Você usa o Intune para apontar para esse tipo de aplicativo. Além disso, você especifica quais grupos de usuários podem acessar o aplicativo. Observe que Android não dá suporte a aplicativos Web.

Ao determinar os aplicativos necessários para a sua organização, considere como os aplicativos são integrados a serviços de nuvem, quais dados os aplicativos acessam, se os aplicativos estão disponíveis para os usuários de BYOD e se os aplicativos precisam de acesso à Internet.

Para saber mais sobre os tipos de aplicativo de que a sua organização precisa, veja "Aplicativos" na seção "Requisitos de recursos" de [Criar um design](planning-guide-design.md#feature-requirements).

### <a name="understanding-app-management-and-protection-policies"></a>Entendendo as políticas de proteção e gerenciamento de aplicativos
O Intune permite modificar a funcionalidade dos aplicativos que você implanta para ajudar a alinhá-los às políticas de conformidade e segurança da empresa. Esse controle permite determinar como os dados da empresa são protegidos. Aplicativos gerenciados pelo Intune têm um amplo conjunto de políticas de proteção de aplicativos móveis habilitadas, como:

- Restringir as funções de copiar e colar e de salvar.
- Configurar links da Web para abrir no aplicativo Intune Managed Browser.
- Habilitar o uso de várias identidades e o acesso condicional no nível do aplicativo.

Os aplicativos gerenciados pelo Intune também podem habilitar a proteção do aplicativo sem a necessidade de registro, o que lhe oferece a opção de aplicar políticas de prevenção contra perda de dados sem gerenciar o dispositivo do usuário. Além disso, você pode incorporar o gerenciamento de aplicativos móveis em seus aplicativos móveis e de linha de negócios usando a SDK de aplicativo do Intune e a Ferramenta de encapsulamento de aplicativo. Para obter mais informações sobre essas ferramentas, confira [Visão geral do SDK do Aplicativo do Intune](app-sdk.md).

### <a name="understanding-licensed-apps"></a>Noções básicas sobre aplicativos licenciados
Além de entender os aplicativos Web, os aplicativos da Store e os aplicativos LOB, você também deve saber qual é o destino dos aplicativos do programa de compra por volume e dos aplicativos licenciados, como: 
- **Programa de Compra por Volume da Apple para Empresas (iOS)**: a App Store do iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Comprar várias cópias ajuda você a gerenciar com eficiência os aplicativos em sua empresa. Para obter mais informações, consulte [Gerenciar aplicativos iOS adquiridos por volume](vpp-apps-ios.md).
- **Perfil de trabalho Android**: a maneira de atribuir aplicativos a dispositivos de perfil de trabalho Android é diferente da maneira de atribuí-los a dispositivos Android padrão. Todos os aplicativos instalados nos perfis de trabalho Android vêm da Google Play Store gerenciada. Faça logon na Store, procure os aplicativos desejados e aprove-os. O aplicativo aparece no nó **Aplicativos licenciados** do Portal do Azure e você pode gerenciar a atribuição do aplicativo como faria com qualquer outro aplicativo.
- **Microsoft Store para Empresas (Windows 10)**: a Microsoft Store para Empresas oferece um local para encontrar e comprar aplicativos para a sua organização, individualmente ou em volume. Conectando a Store ao Microsoft Intune, você pode gerenciar os aplicativos comprados por volume no Portal do Azure. Para saber mais, veja [Gerenciar aplicativos da Microsoft Store para Empresas](windows-store-for-business.md).

    > [!NOTE]
    > As extensões de arquivo para aplicativos do Windows incluem **.msi**, **.appx**, **.appxbundle**, **.msix** e **.msixbundle**.  

## <a name="before-you-add-apps"></a>Antes de adicionar aplicativos
Considere os pontos a seguir antes de começar a adicionar e atribuir aplicativos:

- Quando você adiciona e atribui um aplicativo de uma Store, os usuários devem ter uma conta nessa Store para poderem instalar o aplicativo.
- Alguns aplicativos ou itens que você atribui podem depender de aplicativos internos do iOS. Por exemplo, quando você atribui um livro na iOS Store, o aplicativo iBooks deve estar presente no dispositivo. Se você tiver removido o aplicativo interno iBooks, não será possível usar o Intune para reabilitá-lo.

> [!IMPORTANT]
> Se você alterar o nome do aplicativo por meio do portal do Azure do Intune depois de ter implantado e instalado o aplicativo, o aplicativo não poderá mais ser direcionado usando comandos.

## <a name="cloud-storage-space"></a>Espaço de armazenamento em nuvem
Todos os aplicativos que você cria usando o tipo de instalação do instalador do software (por exemplo, um aplicativo LOB) são empacotados e carregados no armazenamento em nuvem do Microsoft Intune. Uma assinatura de avaliação do Intune inclui 2 GB de armazenamento baseado em nuvem que é usado para armazenar aplicativos gerenciados e atualizações. Uma assinatura completa não limita a quantidade total de espaço de armazenamento.

Os requisitos de espaço de armazenamento em nuvem são os seguintes:

- Todos os arquivos de instalação do aplicativo devem estar na mesma pasta.
- O tamanho máximo do arquivo para qualquer arquivo que você faz upload é de 8 GB.

## <a name="create-and-edit-categories-for-apps"></a>Criar e editar categorias para aplicativos

As categorias de aplicativo podem ser usadas para ajudar a classificar aplicativos para que os usuários possam encontrá-los com mais facilidade no portal da empresa. Você pode atribuir uma ou mais categorias a um aplicativo, por exemplo, *Aplicativos de desenvolvedor* ou *Aplicativos de comunicação*.

Quando você adiciona um aplicativo ao Intune, terá a opção de selecionar a categoria desejada. Use os tópicos específicos da plataforma para adicionar um aplicativo e atribuir categorias. Para criar e editar suas próprias categorias, use o procedimento a seguir:

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos clientes**.
4. No painel de carga de trabalho **Aplicativos clientes**, em **Instalação**, selecione **Categorias de aplicativo**.  
    O painel **Categorias de aplicativo** exibe uma lista de categorias atuais. 
5. Siga um destes procedimentos:
    - Para adicionar uma categoria no painel **Criar categoria**, selecione **Adicionar** e digite um nome para a categoria.  
    Os nomes podem ser inseridos em apenas um idioma e não são traduzidos pelo Intune.
    - Para editar uma categoria, selecione as reticências (**...** ) próximas à categoria e, em seguida, selecione **Fixar no painel** ou **Excluir**.
6. Selecione **Criar**.

## <a name="apps-that-are-added-automatically-by-intune"></a>Aplicativos adicionados automaticamente pelo Intune

Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente. Com base nos comentários do cliente do Intune, removemos essa lista e os aplicativos internos não são mais exibidos. No entanto, se você já atribuiu aplicativos internos, eles permanecerão visíveis na lista de aplicativos. Você pode continuar a atribuir os aplicativos conforme necessário.

> [!NOTE]
> Para a instalação de um aplicativo não de linha de negócios necessário, o Intune tentará instalar o aplicativo enviando um comando de instalação sempre que o dispositivo fizer check-in, considerando que o aplicativo não é detectado e o estado de instalação do aplicativo não é *Instalação Pendente*.

## <a name="installing-updating-or-removing-required-apps"></a>Instalação, atualização ou remoção de aplicativos necessários

O Intune reinstalará, atualizará ou removerá automaticamente o aplicativo necessário dentro de 24 horas em vez de aguardar o ciclo de reavaliação de sete dias.

O Intune reinstalará, atualizará ou removerá automaticamente um aplicativo necessário com base nas seguintes condições:
- Se um usuário final desinstalar um aplicativo que você exigiu que fosse instalado no dispositivo do usuário final, o Intune o reinstalará automaticamente quando esse agendamento expirar.
- Se houver falha na instalação de um aplicativo necessário ou se o aplicativo não estiver presente no dispositivo, o Intune avaliará a conformidade e o reinstalará quando esse agendamento expirar.  
- Um administrador tem como alvo um aplicativo como disponível para um grupo de usuários e um usuário final instala o aplicativo do portal da empresa no dispositivo. Posteriormente, o administrador atualiza o aplicativo da v1 para a v2. O Intune atualizará o aplicativo quando este agendamento expirar, desde que nenhuma versão anterior do aplicativo ainda esteja presente no dispositivo.
- Se o administrador implantar a tentativa de desinstalar e o aplicativo estiver presente no dispositivo e tiver falhado na desinstalação, o Intune avaliará a conformidade e o desinstalará quando esse agendamento expirar.   

## <a name="app-installation-errors"></a>Erros de instalação do aplicativo

Para obter detalhes sobre erros de instalação do aplicativo Intune, consulte [Erros de instalação de aplicativo](troubleshoot-app-install.md#app-installation-errors).

## <a name="next-steps"></a>Próximas etapas

Para saber como adicionar aplicativos de cada plataforma ao Intune, veja:

- [Aplicativos da Android Store](store-apps-android.md)
- [Aplicativos LOB para Android](lob-apps-android.md)
- [Aplicativos da iOS Store](store-apps-ios.md)
- [Aplicativos LOB para iOS](lob-apps-ios.md)
- [Aplicativos Web (para todas as plataformas)](web-app.md)
- [Aplicação da loja do Windows Phone 8.1](store-apps-windows-phone-8-1.md)
- [Aplicativos LOB para Windows Phone](lob-apps-windows-phone.md)
- [Aplicativos da Microsoft Store](store-apps-windows.md)
- [Aplicativos LOB para Windows](lob-apps-windows.md)
- [Aplicativos do Office 365 para Windows 10](apps-add-office365.md)
- [Aplicativos do Office 365 para macOS](apps-add-office365-macos.md)
- [Aplicativos internos](apps-add-built-in.md)
- [Aplicativos Win32](apps-win32-app-management.md) 
