---
title: Gerenciar contratos de licença de software para computadores que executam o cliente de software do Intune
titleSuffix: Microsoft Intune
description: Use o Intune para gerenciar contratos de licença para software adquirido por meio de contratos do Microsoft Volume Licensing e para software adquirido por outros meios.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: c59d8635-3f66-40f5-824a-a71c738e0341
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 92262a9d1f07b8756ced8788feee586ffa30088a
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798794"
---
# <a name="manage-license-agreements-for-windows-pc-software-in-microsoft-intune"></a>Gerenciar contratos de licença para software de PC com Windows no Microsoft Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

O Microsoft Intune permite adicionar e gerenciar informações de contrato de licença para software adquirido por meio de contratos de Licenciamento por Volume da Microsoft. Também é possível fazer isso para software da Microsoft e não Microsoft adquirido por outros meios. Você pode organizar essas informações em grupos lógicos.

> [!IMPORTANT]
> Esse recurso é fornecido apenas para conveniência e a precisão não é garantida. Você não deve confiar nele para confirmar a conformidade com os contratos de Licenciamento por Volume da Microsoft. A Microsoft não utilizará nenhum dado coletado para investigar possíveis violações dos contratos de licença que você possa ter conosco ou a conformidade com esses contratos.
>
> As licenças que você adiciona ao Intune não afetam seus contratos de licença ou direitos de uso do software. Por exemplo, se você excluir um par contrato/licença do Intune, você não excluirá nem anulará contratos de licença que existem entre você e a Microsoft.

No workspace de **Licenças** do console de administração do Intune, você pode:

-   Adicionar e editar contratos de Licenciamento por Volume da Microsoft.

-   Adicionar e editar outros contratos de licenciamento de software.

-   Gerenciar licenças e grupos.

-   Compare as informações sobre direitos que o Intune recupera do VLSC (Centro de Serviços de Licenciamento por Volume) com o inventário de softwares da Microsoft que o Intune detecta nos seus computadores Windows gerenciados.

Adicionalmente, você pode gerar relatórios que mostrem contagens de licenças e de instalação para títulos de software. Relatórios de licenças podem ajudar a avaliar a posição completa de licenças para títulos de softwares da Microsoft ou softwares não Microsoft.

> [!TIP]
> O workspace de **Licenças** não é exibido no console do administrador até que você esteja gerenciando pelo menos um computador Windows com o cliente do computador Windows Intune.

## <a name="add-microsoft-volume-licensing-agreements"></a>Adicionar contratos de licenciamento por volume da Microsoft
Os contratos de Licenciamento por Volume do Intune fornecem informações sobre licença para softwares que foram adquiridos através de contratos de Licenciamento por Volume da Microsoft. É possível adicionar contratos de Licenciamento por Volume da Microsoft ao Intune fornecendo pares combinados de números de contrato. Os números de contrato ou autorização devem ser correspondentes aos números corretos de licença ou inscrição. Pares de números de contrato são obtidos no [Centro de Atendimento de Licenciamento por Volume (VLSC)](http://go.microsoft.com/fwlink/?LinkID=223842)quando você adquire seus contratos de licença.

1.  No [Console do administrador do Microsoft Intune](https://account.manage.microsoft.com/admin/default.aspx), escolha **Licenças**.

2.  Na página **Adicionar Contratos** , na seção **Escolher Tipo de Contrato**, selecione **Contrato de Licenciamento por Volume**.

3.  Na seção **Adicionar Detalhes do Contrato**, escolha se deseja carregar um arquivo ou adicionar os detalhes manualmente.

    -   **Carregar um arquivo CSV que contém detalhes do contrato**. Escolha **Procurar** e selecione o arquivo CSV que você deseja carregar.

        -   O arquivo pode conter duas ou três colunas; duas somente para pares de contrato, ou três se desejar adicionar um nome amigável para cada par de contrato.

        -   O número total de caracteres em um par de números de contrato não pode exceder 16 caracteres ASCII.

        -   Somente caracteres ASCII contam com suporte.

        -   Os caracteres a seguir não são permitidos no nome do contrato: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. São permitidos espaços no nome.

        -   O nome de arquivo do contrato deve ter no máximo 128 caracteres.

        -   O arquivo deve conter, pelo menos, um par de contratos e não pode conter mais de 5.000 pares de contratos.

        **Formato do arquivo**

        Você pode criar esse arquivo adicionando seus pares de contrato a um documento de texto sem formatação em um dos formatos a seguir, dependendo do tipo de organização que você registrou com o VLSC. Especifique um par de números de contrato por linha.

        -   **Clientes do Open Value:** *número do contrato*, *repetir número do contrato*, *nome do contrato*

        -   **Clientes do Open:** *número da autorização*, *número da licença relacionado*, *nome do contrato*

        -   **Clientes do Select e Enterprise:** *número do contrato*, *número de registro relacionado*, *nome do contrato*

        O formulário **Adicionar Contratos** solicitará que você procure esse arquivo quando estiver adicionando um novo contrato.

        Veja a seguir um exemplo de conteúdo de um arquivo .csv para um cliente do Open Value.

        `01-07001, 01-07001, Office agreements`

    -   **Adicionar os detalhes do contrato manualmente**. Forneça as informações a seguir e digite os pares de números de contrato nas caixas **Número de Autorização/Contrato** e **Número de Licença/Registro/Cliente**. Depois de digitar ambos os números, escolha o ícone **Adicionar par** para salvar os números e, opcionalmente, adicionar um novo par.

        -   **Nome do contrato** - especifique um nome exclusivo para o contrato.

            O nome do contrato pode ter, no máximo, 256 caracteres e não pode conter os seguintes caracteres: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. São permitidos espaços no nome.

        -   **Número de Autorização/Contrato** - insira o número de autorização/contrato do par de licenças.

        -   **Número de Licença/Inscrição/Cliente** - insira o número de licença/registro/cliente do par de licença.

        > [!NOTE]
        > Se vários pares de números de contrato forem adicionados, o Intune criará um contrato com o nome que você especificar, e todos esses pares adicionados farão parte do contrato.

    Você pode escolher **+** para adicionar outro par de números de contrato ou **-** para remover um par de números de contrato já inserido.

4.  Na área **Selecionar Grupo de Licenças** , siga um destes procedimentos:

    -   **Adicionar os contratos ao grupo Contratos sem Atribuição**. Selecione essa opção se não desejar adicionar novos contratos a um grupo de licenças.

    -   **Adicionar os contratos a um novo grupo de licenças**. Forneça um nome para o novo grupo de licenças.

    -   **Adicionar os contratos a um grupo de licenças existente**. Na lista **Nome do grupo** , selecione o grupo de licenças ao qual você deseja adicionar os contratos.

5.  Selecione **OK**.

A exibição **Todos os Contratos** é mostrada e o Intune se conecta ao VLSC da Microsoft para validar os pares de números de contrato fornecidos.

Para atualizar as informações de licença de volume depois de adicionar os contratos de licença no Intune, na página **Visão Geral de Licenças**, escolha **Atualizar Agora**. Essa ação recupera as informações de licença atuais no [Centro de Serviços de Licenciamento por Volume da Microsoft (VLSC)](http://go.microsoft.com/fwlink/?LinkId=223842).

> [!IMPORTANT]
> Até que as informações de licenciamento por volume sejam atualizadas, talvez você veja informações diferentes na lista de contratos e informações de direito na página **Visão geral de contratos** .

Após atualizar as informações de licenciamento por volume, você pode comparar as informações de licença com o seu software da Microsoft detectado no workspace **Aplicativos**. Você também pode executar os relatórios de licença a seguir:

-   **Relatórios de aquisição de licenças** - permite exibir os softwares licenciados em grupos de licenças selecionados por você para ajudá-lo a encontrar falhas na cobertura.

-   **Relatórios de instalação de licenças** - ajuda você a determinar se você tem cobertura de contrato de licença suficiente.

> [!NOTE]
> O **Título do produto** exibido para todos os contratos de Licenciamento por Volume da Microsoft é **Não disponível**.

## <a name="add-and-edit-other-software-licensing-agreements"></a>Adicionar e editar outros contratos de licenciamento de software
Também é possível adicionar outros tipos de contratos de licença ao Intune além dos contratos de licenciamento por volume da Microsoft. Esses contratos podem incluir software não Microsoft ou software Microsoft adquirido por meio de um revendedor.

> [!IMPORTANT]
> Você precisa ter pelo menos um computador Windows registrado no Intune antes poder adicionar um contrato.  Além disso, pelo menos um computador registrado deve ter carregado um pacote de software licenciável que você deseja usar para adicionar um contrato de licença.

### <a name="to-add-other-software-agreements"></a>Para adicionar outros contratos de software

1.  No [Console do administrador do Microsoft Intune](https://account.manage.microsoft.com/admin/default.aspx), escolha **Licenças**.

2.  Escolha **Adicionar Contratos** na seção **Outros Contratos de Licenciamento de Software**.

3.  Selecione **Outro contrato de licenciamento de software** na seção **Escolher tipo de contrato** da página **Adicionar Contratos** .

4.  Na área **Adicionar Detalhes do Contrato** , especifique o seguinte:

    -   **Agreement name** (necessário). O nome do contrato pode ter, no máximo, 256 caracteres e não pode conter os seguintes caracteres: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. São permitidos espaços no nome.

    -   **Fornecedor** (necessário). Quando você começa a digitar um nome de fornecedor, o serviço recupera todos os nomes de fornecedores que contêm as letras digitadas. Por exemplo, se você digitar “soft”, o serviço irá recuperar todos os nomes de fornecedores que contêm “soft” como parte do nome, como “Microsoft” e “Microsoft Research”. Os nomes de fornecedores são recuperados do Catálogo de Ativos de Software. Você deve selecionar o fornecedor antes de inserir o título do produto.

        > [!IMPORTANT]
        > A empresa que você deseja adicionar pode não aparecer nessa lista. Você só pode adicionar contratos de software para empresas que já estão no catálogo de ativos de software. No entanto, a Microsoft trabalha continuamente para adicionar os títulos de software mais populares. Se quiser enviar uma solicitação para que uma empresa seja adicionada à lista, é possível fazer isso no [site Intune UserVoice](https://microsoftintune.uservoice.com/).

    -   **Título do produto** (necessário). Quando você começa a digitar um título de produto, o serviço recupera todos os títulos de produtos que contêm as letras digitadas. É necessário especificar um **Fornecedor** antes de especificar um **Título de produto**.

    -   **Contagem de licenças** (necessário). Insira o número de licenças adquiridas.

    -   **Data de início da licença**. Insira a data de início da cobertura da licença.

    -   **Data de término da licença**. Insira a data de término da cobertura da licença.

    -   **Detalhes do contrato**. Opcionalmente, você pode especificar informações de contato, chaves do Registro e outras informações.

5.  Na área **Selecionar Grupo de Licenças** , siga um destes procedimentos:

    -   Se não quiser adicionar os novos contratos a um grupo de licença novo ou existente, selecione **Adicionar os contratos ao grupo Contratos sem Atribuição** . Você pode adicionar os contratos a grupos de licenças definidos pelo usuário a qualquer momento.

    -   Para adicionar novos contratos a um novo grupo de licenças, selecione **Adicionar os contratos a um novo grupo de licenças** . Será solicitado que você forneça um nome para o novo grupo de licenças.

    -   Para adicionar novos contratos a um grupo de licenças existente, selecione **Adicionar os contratos a um grupo de licenças existente** . Na lista **Nome do grupo** , selecione o grupo de licenças ao qual você deseja adicionar os contratos.

6.  Selecione **OK**.

O modo de exibição de lista **Todos os Contratos** é exibido.

## <a name="manage-license-agreements"></a>Gerenciar contratos de licença
Os contratos de licenciamento de software podem ser adicionados aos grupos de licenças. Você pode usar grupos de licenças para organizar seus contratos de licença em unidades que são lógicas para a sua organização. Além disso, você pode excluir contratos de licença criados anteriormente.


|                            |                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            Tarefa            |                                                                                                                                                                                 Detalhes                                                                                                                                                                                  |
|   Criar um grupo de licenças   |                                                            Na página <strong>Visão Geral</strong> do workspace de <strong>Licenças</strong>, escolha <strong>Criar Grupo de Licenças</strong> no menu <strong>Tarefas</strong>. <strong>Observação:</strong> é possível criar um total máximo de 500 grupos de licenças.                                                             |
|   Renomear um grupo de licenças   |                                                                                                      No workspace de <strong>Licenças</strong>, escolha um grupo de licenças e <strong>Editar Grupo de Licenças</strong> no menu <strong>Tarefas</strong>.                                                                                                       |
|   Excluir um grupo de licenças   |                                 No workspace de <strong>Licenças</strong>, escolha um grupo de licenças e, após, escolha <strong>Excluir Grupo de Licenças</strong> no menu <strong>Tarefas</strong>. <strong>Dica:</strong> Todas as licenças no grupo excluído são movidas para o grupo <strong>Contratos não atribuídos</strong>.                                 |
| Excluir um contrato de licença | No workspace de <strong>Licenças</strong>, escolha um contrato e, após, escolha <strong>Excluir</strong>. <strong>Dica:</strong> depois de excluir contratos de Licenciamento por Volume, para atualizar as informações de licença, escolha <strong>Atualizar Agora</strong> na página <strong>Visão Geral de Licenças</strong> ou na guia <strong>Geral</strong> de um grupo de licenças específico. |

