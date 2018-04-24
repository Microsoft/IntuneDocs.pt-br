---
title: Como adicionar aplicativos ao Microsoft Intune
titlesuffix: ''
description: Saiba como adicionar aplicativos ao Microsoft Intune para poder atribui-los a usuários e dispositivos. O Intune é compatível com uma ampla variedade de tipos de aplicativos diferentes.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b4e87c36c3aa0aaeae1e1bf265902100612db15
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Como adicionar um aplicativo no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Adicione os aplicativos ao Microsoft Intune antes de atribuir, monitorar, configurar ou protegê-los.

Os usuários de aplicativos e dispositivos na empresa (a força de trabalho da empresa) podem ter vários requisitos de aplicativo. Antes de adicionar aplicativos ao Intune e disponibilizá-los à sua força de trabalho, você precisa avaliar e entender alguns conceitos básicos sobre os aplicativos. Você precisa entender os diferentes tipos de aplicativos disponíveis para o Intune. É necessário avaliar os requisitos do aplicativo, como as plataformas necessárias e os recursos necessários para sua força de trabalho. Além disso, você precisará determinar se vai usar o Intune para gerenciar os dispositivos (incluindo aplicativos) ou usar o Intune para gerenciar aplicativos sem gerenciar os dispositivos. Você precisa determinar quem na sua força de trabalho precisará de recursos e aplicativos diferentes. As informações fornecidas neste artigo o ajudarão a começar.

## <a name="app-types-in-microsoft-intune"></a>Tipos de aplicativo no Microsoft Intune

O Intune é compatível com uma ampla variedade de tipos de aplicativos diferentes. As opções disponíveis são diferentes para cada tipo de aplicativo. O Intune permite que você adicione e atribua esses tipos de aplicativo:

| **Tipos de Aplicativo**                                     | **Instalação**                                                                  | **Atualizações**                       |
|------------------------------------------ |----------------------------------------------------------------------------   |---------------------------    |
| Aplicativos da loja (aplicativos da loja)          | O Intune instala o aplicativo no dispositivo                                       | As atualizações de aplicativo são automáticas     |
| Aplicativos escritos internamente (linha de negócios)  | O Intune instala o aplicativo no dispositivo (você fornece o arquivo de instalação)    | É necessário atualizar o aplicativo       |
| Aplicativos que são internos (aplicativos internos)    | O Intune instala o aplicativo no dispositivo                                       | As atualizações de aplicativo são automáticas     |
| Aplicativos na Web (link da Web)                | O Intune cria um atalho para o aplicativo Web na tela inicial do dispositivo          | As atualizações de aplicativo são automáticas     |

### <a name="specific-app-type-details"></a>Detalhes do tipo de aplicativo específico
 
A tabela a seguir lista os tipos de aplicativo específicos e como você pode adicioná-los usando a folha **Adicionar aplicativo** no Microsoft Intune:

| **Tipo de Aplicativo Específico**                         | **Tipo Geral**             | **Procedimentos Específicos do Aplicativo**                                                                                                                                                 |
|---------------------------------------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aplicativos da loja do Android                        | Aplicativo da loja                  | Selecione **Android** como o **tipo de aplicativo** e digite a URL da loja Google Play do aplicativo.                                                                                       |
| Aplicativos da loja do iOS                            | Aplicativo da loja                  | Selecione **iOS** como o **tipo de aplicativo**, procure o aplicativo e selecione o aplicativo no Intune.                                                                                     |
| Aplicativos da loja do Windows Phone 8.1              | Aplicativo da loja                  | Selecione **Windows Phone 8.1** como o **tipo de aplicativo** e insira a URL da Microsoft Store do aplicativo.                                                                               |
| Aplicativos da Microsoft Store                      | Aplicativo da loja                  | Selecione **Windows** como o **tipo de aplicativo** e insira a URL da Microsoft Store do aplicativo.                                                                                         |
| Aplicativos Android for Work                     | Aplicativo da loja                  | Localize e aprove o aplicativo Android for Work na loja Google Play for Work.                                                                                        |
| Aplicativos do Office 365 para Windows 10            | Aplicativo da loja (Office 365)     | Selecione **Windows 10** no **Pacote do Office 365** como o **tipo de aplicativo** e, em seguida, selecione o aplicativo do Office 365 que você deseja instalar.                                                |
| Aplicativos do Office 365 para macOS                 | Aplicativo da loja (Office 365)     | Selecione **macOS** no **Pacote do Office 365** como o **tipo de aplicativo** e, em seguida, selecione o pacote do aplicativo do Office 365.                                                                     |
| Aplicativos de LOB (linha de negócios) Android       | Aplicativo de LOB (linha de negócios) | Selecione aplicativo de **Linha de negócios** como o **tipo de aplicativo**, selecione o **Arquivo do pacote do aplicativo** e, em seguida, insira um arquivo de instalação do Android com a extensão **.apk**.                    |
| Aplicativos de LOB (linha de negócios) iOS           | Aplicativo de LOB (linha de negócios) | Selecione aplicativo de **Linha de negócios** como o **tipo de aplicativo**, selecione o **Arquivo do pacote do aplicativo** e, em seguida, insira um arquivo de instalação do iOS com a extensão **.ipa**.                        |
| Aplicativos de LOB (linha de negócios) do Windows Phone | Aplicativo de LOB (linha de negócios) | Selecione aplicativo de **Linha de negócios** como o **tipo de aplicativo**, selecione o **Arquivo do pacote do aplicativo** e, em seguida, insira um arquivo de instalação do iOS com a extensão **.xap**.                        |
| Aplicativos de LOB (linha de negócios) do Windows       | Aplicativo de LOB (linha de negócios) | Selecione aplicativo de Linha de negócios como o tipo de aplicativo, selecione o Arquivo do pacote do aplicativo e, em seguida, insira um arquivo de instalação do iOS com a extensão **.msi**, **.appx** ou **.appxbundle**. |
| Aplicativo iOS interno                          | Aplicativo interno               | Selecione **aplicativo interno** como o **tipo de aplicativo** e, em seguida, selecione o aplicativo interno na lista de aplicativos fornecidos.                                                                  |
| Aplicativo interno Android                      | Aplicativo interno               | Selecione **aplicativo interno** como o **tipo de aplicativo** e, em seguida, selecione o aplicativo interno na lista de aplicativos fornecidos.                                                                  |
| Aplicativos Web                                  | Aplicativo Web                    | Selecione **link da Web** como o **tipo de aplicativo** e insira uma URL válida apontando para o aplicativo Web.                                                                                        |

   
Você pode adicionar um aplicativo no Microsoft Intune selecionando **Aplicativos móveis** > **Aplicativos** > **Adicionar**. A folha **Adicionar aplicativo** é exibida permitindo que você selecione o **Tipo de aplicativo**. 

>[!TIP]
> Um aplicativo de LOB (linha de negócios) é um aplicativo que pode ser adicionado de um arquivo de instalação do aplicativo. Por exemplo, para instalar um aplicativo de LOB do iOS, adicione o aplicativo escolhendo **Aplicativo de linha de negócios** como o **Tipo de aplicativo** na folha **Adicionar aplicativo**. Em seguida, selecione o arquivo do pacote do aplicativo (extensão .ipa). Normalmente, esses tipos de aplicativos são escritos internamente.

## <a name="assess-app-requirements"></a>Avalie os requisitos do aplicativo
Como um administrador de TI, você precisa não apenas determinar quais aplicativos seu grupo deve usar, mas precisa determinar também as funcionalidades necessárias para cada grupo e subgrupo. Para cada aplicativo, você precisa determinar as plataformas necessárias, os grupos de usuários que precisam do aplicativo, as políticas de configuração a serem aplicadas a esses grupos e as políticas de proteção a serem aplicadas.  

Além disso, você precisa determinar se é necessário se concentrar no MDM (gerenciamento de dispositivo móvel) ou somente no MAM (gerenciamento de aplicativo móvel). Usar o Intune para gerenciar o dispositivo (gerenciamento de dispositivo móvel) é útil quando:
- Os usuários precisam um perfil de conectividade corporativo por VPN ou WiFi para serem produtivos.
- Os usuários precisam que um conjunto de aplicativos seja enviado por push para seus dispositivos.
- Sua organização precisa manter a conformidade com políticas regulatórias ou outras políticas que chamam controles específicos de MDM (gerenciamento de dispositivo móvel), como segurança ou criptografia.

Usar o Intune para gerenciar aplicativos (gerenciamento de aplicativo móvel) sem gerenciar o dispositivo é útil quando:
- Você quer permitir que os usuários usem seus próprios dispositivos (BYOD).
- Você quer fornecer um pop-up único para que os usuários saibam que as proteções de MAM estão em vigor, em vez de notificações contínuas no nível do dispositivo.
- Você quer estar em conformidade com políticas que exigem menos recursos de gerenciamento de dispositivos pessoais. Por exemplo, você quer gerenciar os dados corporativos para os aplicativos, em vez de gerenciar os dados corporativos para todo o dispositivo.

Para obter mais informações, consulte [Comparar MDM e MAM](byod-technology-decisions.md).

### <a name="determine-who-will-use-the-app"></a>Determinar quem usará o aplicativo

Ao determinar os aplicativos necessários que sua força de trabalho precisa, considere os diferentes grupos de usuários que usam diferentes aplicativos. Também é interessante saber quais são esses grupos depois de adicionar um aplicativo. Depois de adicionar um aplicativo, é possível atribuir um grupo de usuários que poderão usá-lo. Primeiro, você precisa determinar o grupo apropriado que deve ter acesso ao aplicativo com base na confidencialidade dos dados que o aplicativo contém. Você precisa incluir ou excluir determinados tipos de funções na sua organização. Por exemplo, somente determinados aplicativos de LOB podem ser necessários para seu grupo de vendas, enquanto pessoas concentradas em engenharia, finanças, RH, ou jurídico podem não precisar usar os aplicativos de LOB. Além disso, seu grupo de vendas pode precisar de proteção de dados adicional e de acesso a serviços corporativos internos em seus dispositivos móveis. Você precisa determinar como esse grupo se conectará aos recursos usando o aplicativo. Os dados que o aplicativo acessa ficarão hospedados na nuvem ou localmente? Além disso, como os usuários se conectarão aos recursos usando o aplicativo? O Intune também dá suporte à habilitação do acesso a aplicativos móveis que precisam de acesso seguro aos dados locais, como servidores de aplicativos de linha de negócios. Normalmente, esse tipo de acesso é feito usando [certificados gerenciados pelo Intune](certificates-configure.md) para controle de acesso, em conjunto com um Gateway de VPN padrão ou proxy no perímetro, como o Proxy de Aplicativo do Microsoft Azure Active Directory. A [Ferramenta de Disposição do Aplicativo e o SDK do Aplicativo](apps-prepare-mobile-application-management.md) do Intune podem ajudar a conter os dados acessados no aplicativo de linha de negócios, de modo que ele não possa passar dados corporativos para serviços ou aplicativos de consumidor.

Use o [Guia de planejamento de implantação, design e implementação do Intune](planning-guide.md) para ajudar a determinar como você identifica os grupos organizacionais associados a cada cenário de caso de uso e caso de subuso do aplicativo. Para obter detalhes de como atribuir aplicativos a grupos, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

### <a name="determine-the-type-of-app-for-your-solution"></a>Determinar o tipo de aplicativo para sua solução

Você pode escolher entre os seguintes tipos de aplicativo:
- **Aplicativos da loja** – um aplicativo da loja é um aplicativo que foi carregado na Microsoft Store, na loja do iOS ou na loja do Android. O provedor do aplicativo da loja mantém e fornece atualizações do aplicativo. Selecione o aplicativo na lista da loja e adicione-o usando o Intune como um aplicativo disponível para seus usuários.
- **Aplicativos escritos internamente (linha de negócios)** – aplicativos criados internamente são aplicativos de LOB (linha de negócios). A funcionalidade desse tipo de aplicativo foi criada para uma das plataformas compatíveis com o Intune, como Windows, iOS ou Android. Sua organização cria e lhe fornece atualizações como um arquivo separado. Você fornece atualizações do aplicativo aos usuários adicionando e implantando as atualizações usando o Intune.
- **Aplicativos na Web** – um aplicativo Web é um aplicativo cliente-servidor. O servidor fornece o aplicativo Web, que inclui a interface do usuário, o conteúdo e a funcionalidade. Além disso, plataformas modernas de hospedagem na Web geralmente oferecem segurança, balanceamento de carga e outros benefícios. Este tipo de aplicativo é mantido separadamente na Web. Você usa o Intune para apontar para esse tipo de aplicativo. Além disso, você atribui quais grupos de usuários podem acessar o aplicativo. Observe que Android não dá suporte a aplicativos Web.

Ao determinar os aplicativos necessários para sua organização, considere como esses aplicativos são integrados a serviços de nuvem, quais dados os aplicativos acessam, se os aplicativos estão disponíveis para os usuários de BYOD e se os aplicativos exigem acesso à Internet.

Para obter mais informações sobre como determinar o tipo de aplicativo de que sua organização precisa, consulte **Aplicativos** na seção **Requisitos de recursos** de [Criar um design](planning-guide-design.md#feature-requirements).

### <a name="understanding-app-management-and-protection-policies"></a>Entendendo as políticas de proteção e gerenciamento de aplicativos
O Intune permite modificar a funcionalidade dos aplicativos que você implanta para ajudar a alinhá-los às políticas de conformidade e segurança da empresa. Esse controle permite determinar como os dados da empresa são protegidos. Aplicativos gerenciados pelo Intune têm um amplo conjunto de políticas de proteção de aplicativos móveis habilitadas, como:

- Restringir as funções de copiar e colar e de salvar
- Configurar links da Web para abrir no aplicativo Intune Managed Browser
- Habilitar o uso de várias identidades e o acesso condicional no nível do aplicativo

Aplicativos gerenciados pelo Intune também podem habilitar a proteção do aplicativo sem a necessidade de registro, oferecendo a opção de aplicar políticas de prevenção contra perda de dados sem gerenciar o dispositivo do usuário. Além disso, você pode incorporar o gerenciamento de aplicativos móveis em seus aplicativos móveis e de linha de negócios usando o Software Development Kit do aplicativo do Intune e a ferramenta de encapsulamento de aplicativo. Para obter mais informações sobre essas ferramentas, confira [Visão geral do SDK do Aplicativo do Intune](app-sdk.md).

### <a name="understanding-licensed-apps"></a>Noções básicas sobre aplicativos licenciados
Além de saber quais são os aplicativos Web, os aplicativos da loja e os aplicativos de LOB, você também deve saber qual é o destino dos aplicativos do programa de compra por volume e dos aplicativos licenciados, como:     
- **Programa de Compra por Volume da Apple para Empresas (iOS e macOS)** – a App Store do iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Comprar várias cópias ajuda você a gerenciar com eficiência os aplicativos em sua empresa. Para obter mais informações, consulte [Gerenciar aplicativos iOS adquiridos por volume](vpp-apps-ios.md).
- **Android for Work (Android)** – a maneira como os aplicativos são atribuídos em dispositivos Android for Work e em dispositivos Android padrão é diferente. Todos os aplicativos instalados no Android for Work são obtidos na loja do Google Play for Work. Faça logon na loja, procure os aplicativos desejados e aprove-os. Então, o aplicativo aparecerá no nó Aplicativos licenciados do Portal do Azure. A partir desse momento, é possível gerenciar a atribuição do aplicativo do mesmo modo que você atribui qualquer outro aplicativo.
- **Microsoft Store para Empresas (Windows 10)** – a Microsoft Store para Empresas oferece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em volume. Conectando a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados por volume no Portal do Azure. Para saber mais, veja [Gerenciar aplicativos da Microsoft Store para Empresas](windows-store-for-business.md).

## <a name="before-you-add-apps"></a>Antes de adicionar aplicativos
Considere os pontos a seguir antes de começar a adicionar e atribuir aplicativos.

- Quando você adiciona e atribui um aplicativo de uma loja, os usuários finais devem ter uma conta nessa loja para poder instalar o aplicativo.
- Alguns aplicativos ou itens que você atribui podem ser dependentes de aplicativos internos do iOS. Por exemplo, quando você atribui um livro da iOS Store, o aplicativo iBooks deve estar presente no dispositivo. Se você tiver removido o aplicativo interno iBooks, não será possível usar o Intune para reabilitá-lo.

## <a name="cloud-storage-space"></a>Espaço de armazenamento em nuvem
Todos os aplicativos que você cria usando o tipo de instalação do instalador do software (por exemplo, um aplicativo LOB) são empacotados e carregados no armazenamento em nuvem do Microsoft Intune. Uma assinatura de avaliação do Intune inclui 2 GB de armazenamento baseado em nuvem que é usado para armazenar aplicativos gerenciados e atualizações. A assinatura completa inclui 20 GB de espaço de armazenamento.

Você pode adquirir armazenamento adicional para o Intune usando seu método de compra original. Se você paga por cartão de crédito ou fatura, visite o [portal de Gerenciamento de Assinatura](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions). Caso contrário, entre em contato com seu parceiro ou associado de vendas.

Os requisitos de espaço de armazenamento em nuvem são os seguintes:

-   Todos os arquivos de instalação do aplicativo devem estar na mesma pasta.
-   O tamanho máximo do arquivo para qualquer arquivo que você carregar é de 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Como criar e editar categorias para aplicativos

As categorias de aplicativo podem ser usadas para ajudar a classificar aplicativos para que os usuários possam encontrá-los com mais facilidade no portal da empresa. Você pode atribuir uma ou mais categorias a um aplicativo, por exemplo, **Aplicativos de desenvolvedor** ou **Aplicativos de comunicação**.
Quando você adiciona um aplicativo ao Intune, terá a opção de selecionar a categoria desejada. Use os tópicos específicos da plataforma para adicionar um aplicativo e atribuir categorias. Para criar e editar suas próprias categorias, use o procedimento a seguir:

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Categorias de aplicativo** na seção **Instalação**. 
5. Na folha **Categorias de aplicativos**, é mostrada uma lista de categorias atuais. Escolha uma das seguintes ações:
    - **Criar uma categoria** – selecione **Adicionar** para exibir a folha **Criar categoria** e, em seguida, adicione um nome para a nova categoria. Os nomes podem ser inseridos em apenas um idioma e não são traduzidos pelo Intune. Quando terminar, clique em **Criar**.
    - **Editar uma categoria** – Para qualquer categoria na lista, escolha “**...** “. Essa opção exibe um menu pop-up que permite **Fixar no painel** ou **Excluir** a categoria.

## <a name="apps-added-automatically-by-intune"></a>Aplicativos adicionados automaticamente pelo Intune

Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente. Com base em seus comentários, essa lista foi removida e você não precisa mais ver os aplicativos internos.
No entanto, se você já tiver atribuído aplicativos internos, eles ainda estarão visíveis na lista de aplicativos. Você pode continuar a atribuir esses aplicativos conforme necessário.

## <a name="next-steps"></a>Próximas etapas

Escolha um dos tópicos a seguir para saber como adicionar aplicativos para cada plataforma no Microsoft Intune:

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
