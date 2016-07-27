---
title: "Gerenciar contratos de licença para software de computador | Microsoft Intune"
description: "O Intune permite que você gerencie contratos de licença para software adquirido por meio de contratos de Licenciamento por Volume da Microsoft e para software adquirido por outros meios."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59d8635-3f66-40f5-824a-a71c738e0341
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1850e89830de61ccdeb81cb6ee9cc0f0c1d237a
ms.openlocfilehash: 6570c0cd42102e45171a39ccbaef609a494a27d6


---

# Gerenciar contratos de licença para software de PC com Windows no Microsoft Intune
O Microsoft Intune permite adicionar e gerenciar informações de contratos de licença para software adquirido via contratos de Licenciamento por Volume da Microsoft e para softwares Microsoft e não Microsoft adquiridos por outros meios. Você também pode organizar essas informações em grupos lógicos.

> [!IMPORTANT]
> Esse recurso é fornecido apenas para conveniência e a precisão não é garantida. Você não deve confiar nele para confirmar a conformidade com os contratos de Licenciamento por Volume da Microsoft. A Microsoft não utilizará nenhum dado coletado para investigar possíveis violações dos contratos de licença que você possa ter conosco ou a conformidade com esses contratos.
> 
> As licenças que você adiciona ao Intune não afetam seus contratos de licença ou direitos de uso do software.  Por exemplo, ao excluir um par contrato/licença do Intune, você não exclui nem anula contratos de licença que existem entre você e a Microsoft.

No espaço de trabalho **Licenças** do console de administração do Intune, você pode:

-   Adicionar e editar contratos de licenciamento por volume da Microsoft

-   Adicionar e editar outros contratos de licenciamento de software

-   Gerenciar licenças e grupos

-   Compare as informações sobre direitos que o Intune recupera do VLSC (Centro de Serviços de Licenciamento por Volume) com o inventário de softwares da Microsoft que o Intune detecta nos seus computadores Windows gerenciados.

Adicionalmente, você pode gerar relatórios que mostrem contagens de licenças e de instalação para títulos de software. Relatórios de licenças podem ajudar a avaliar a posição completa de licenças para títulos de softwares da Microsoft ou softwares não Microsoft.

> [!TIP]
> O espaço de trabalho **Licenças** não é exibido no console do administrador até que você esteja gerenciando pelo menos um computador Windows com o cliente do computador Windows Intune.

## Adicionar contratos de licenciamento por volume da Microsoft
Os contratos de Licenciamento por Volume do Intune fornecem informações sobre licença para softwares que foram adquiridos através de contratos de Licenciamento por Volume da Microsoft. É possível adicionar contratos de Licenciamento por Volume da Microsoft ao Intune fornecendo pares combinados de números de contrato. Os números de contrato ou autorização devem ser correspondentes aos números corretos de licença ou inscrição. Pares de números de contrato são obtidos no [Centro de Atendimento de Licenciamento por Volume (VLSC)](http://go.microsoft.com/fwlink/?LinkID=223842)quando você adquire seus contratos de licença.

1.  No [console de administrador do Microsoft Intune](https://account.manage.microsoft.com/admin/default.aspx), clique em **Licenças**.

2.  Na página **Adicionar Contratos** , na seção **Escolher Tipo de Contrato**, selecione **Contrato de Licenciamento por Volume**.

3.  Na seção **Adicionar Detalhes do Contrato** , escolha uma das opções a seguir:

    -   **Carregar um arquivo CSV que contém detalhes do contrato** - clique em Navegar e selecione o arquivo CSV que deseja carregar.

        -   O arquivo pode conter duas ou três colunas; duas somente para pares de contrato, ou três se desejar adicionar um nome amigável para cada par de contrato.

        -   O número total de caracteres em um par de números de contrato não pode exceder 16 caracteres ASCII.

        -   Somente caracteres ASCII contam com suporte.

        -   Os caracteres a seguir não são permitidos no nome do contrato: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. São permitidos espaços no nome.

        -   O nome de arquivo do contrato deve ter no máximo 128 caracteres.

        -   O arquivo deve conter pelo menos um par de contratos e não pode conter mais do que 5.000 pares de contratos.

        **Formato para o arquivo**

        Você pode criar esse arquivo adicionando seus pares de contrato a um documento de texto sem formatação em um dos formatos a seguir, dependendo do tipo de organização que você registrou com o VLSC. Especifique um par de números de contrato por linha.

        -   **Clientes do Open Value:** *Número do contrato*, *número de contrato repetido*, *nome do contrato*

        -   **Clientes do Open:** *Número da autorização*, *número da licença relacionado*, *nome do contrato*

        -   **Clientes do Select e Enterprise:** *Número do contrato*, *número de inscrição relacionado*, *nome do contrato*

        O formulário **Adicionar Contratos** solicitará que você procure esse arquivo quando estiver adicionando um novo contrato.

        Veja a seguir um exemplo de conteúdo de um arquivo .csv para um cliente do Open Value.

        `01-07001, 01-07001, Office agreements`

    -   **Adicionar detalhes do contrato manualmente** - forneça as informações a seguir e, em seguida, digite os pares de números de contrato nas caixas **Número de Autorização/Contrato** e **Número de Licença/Registro/Cliente**. Depois de digitar ambos os números, clique no ícone **Adicionar par** para salvar os números e opcionalmente adicionar um novo par.

        -   **Nome do contrato** - especifique um nome exclusivo para o contrato.

            O nome do contrato pode ter no máximo 256 caracteres e não pode conter os seguintes caracteres: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. São permitidos espaços no nome.

        -   **Número de Autorização/Contrato** - insira o número de autorização/contrato do par de licenças.

        -   **Número de Licença/Inscrição/Cliente** - insira o número de licença/registro/cliente do par de licença.

        > [!NOTE]
        > Se vários pares de números de contrato forem adicionados, o Intune criará um contrato com o nome que você especificar, e todos esses pares adicionais farão parte do contrato.

    Você pode clicar em **+** para adicionar outro par de números de contrato, ou em **-** para remover um par de números de contrato já inseridos.

4.  Na área **Selecionar Grupo de Licenças** , siga um destes procedimentos:

    -   **Adicionar contratos a um grupo de Contratos Não Atribuídos** selecione essa opção se não quiser adicionar os novos contratos a um grupo de licenças.

    -   **Adicionar contratos a um novo grupo de licenças** -forneça um nome para o novo grupo de licenças.

    -   **Adicionar contratos a um grupo de licenças existente** - na lista **Nome do grupo**, selecione o grupo de licenças ao qual você deseja adicionar os contratos.

5.  Clique em **OK**.

A exibição **Todos os Contratos** é exibida e o Intune se conecta ao Centro de Serviços de Licenciamento por Volume da Microsoft para validar os pares de números de contrato que você forneceu.

Para atualizar as informações de licenciamento por volume após adicionar os contratos de licença ao Intune, na página **Visão geral de licenças**, clique em **Atualizar agora**. Essa ação recupera as informações de licença atuais no [Centro de Serviços de Licenciamento por Volume da Microsoft (VLSC)](http://go.microsoft.com/fwlink/?LinkId=223842).

> [!IMPORTANT]
> Até que as informações de licenciamento por volume sejam atualizadas, talvez você veja informações diferentes na lista de contratos e informações de direito na página **Visão geral de contratos** .

Após atualizar as informações de licenciamento por volume, você pode comparar as informações de licença com o seu software da Microsoft detectado no espaço de trabalho **Aplicativos** . Você também pode executar os relatórios de licença a seguir:

-   **Relatórios de aquisição de licenças** - permite exibir os softwares licenciados em grupos de licenças selecionados por você para ajudá-lo a encontrar falhas na cobertura.

-   **Relatórios de instalação de licenças** - ajuda você a determinar se você tem cobertura de contrato de licença suficiente.

> [!NOTE]
> O **Título do produto** exibido para todos os contratos de Licenciamento por Volume da Microsoft é **Não disponível**.

## Adicionar e editar outros contratos de licenciamento de software
Também é possível adicionar outros tipos de contratos de licença ao Intune além dos contratos de licenciamento por volume da Microsoft. Esses contratos podem incluir softwares não Microsoft ou softwares Microsoft que foram adquiridos através de um revendedor.

> [!IMPORTANT]
> Você precisa ter pelo menos um computador Windows registrado no Intune antes poder adicionar um contrato.  Além disso, pelo menos um computador registrado deve ter carregado um pacote de software licenciável que você deseja usar para adicionar um contrato de licença.

### Para adicionar outros contratos de software

1.  No [console de administrador do Microsoft Intune](https://account.manage.microsoft.com/admin/default.aspx), clique em **Licenças**.

2.  Clique em **Adicionar Contratos** na seção **Outro contrato de licenciamento de software** .

3.  Selecione **Outro contrato de licenciamento de software** na seção **Escolher tipo de contrato** da página **Adicionar Contratos** .

4.  Na área **Adicionar Detalhes do Contrato** , especifique o seguinte:

    -   **Agreement name** (necessário). O nome do contrato pode ter no máximo 256 caracteres e não pode conter os seguintes caracteres: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. São permitidos espaços no nome.

    -   **Fornecedor** (necessário). Quando você começa a digitar um nome de fornecedor, o serviço recupera todos os nomes de fornecedores que contêm as letras digitadas. Por exemplo, se você digitar “soft”, o serviço irá recuperar todos os nomes de fornecedores que contêm “soft” como parte do nome, como “Microsoft” e “Microsoft Research”. Os nomes de fornecedores são recuperados do Catálogo de Ativos de Software. Você deve selecionar o fornecedor antes de inserir o título do produto.

        > [!IMPORTANT]
        > A empresa que você deseja adicionar pode não aparecer nessa lista. Você só pode adicionar contratos de software para empresas que já estão no catálogo de ativos de software. No entanto, a Microsoft trabalha continuamente para adicionar os títulos de software mais populares. Se quiser enviar uma solicitação para que uma empresa seja adicionada à lista, você pode fazer isso no [site Intune Uservoice](https://microsoftintune.uservoice.com/).

    -   **Título do produto** (necessário). Quando você começa a digitar um título de produto, o serviço recupera todos os títulos de produtos que contêm as letras digitadas. É necessário especificar um **Fornecedor** antes de especificar um **Título de produto**.

    -   **Contagem de licenças** (necessário). Insira o número de licenças adquiridas.

    -   **Data de início da licença**. Insira a data de início da cobertura da licença.

    -   **Data de término da licença**. Insira a data de término da cobertura da licença.

    -   **Detalhes do contrato**. Opcionalmente, você pode especificar informações de contato, chaves do Registro e outras informações.

5.  Na área **Selecionar Grupo de Licenças** , siga um destes procedimentos:

    -   Se não quiser adicionar os novos contratos a um grupo de licença novo ou existente, selecione **Adicionar os contratos ao grupo Contratos sem Atribuição** . Você pode adicionar os contratos a grupos de licenças definidos pelo usuário a qualquer momento.

    -   Para adicionar novos contratos a um novo grupo de licenças, selecione **Adicionar os contratos a um novo grupo de licenças** . Será solicitado que você forneça um nome para o novo grupo de licenças.

    -   Para adicionar novos contratos a um grupo de licenças existente, selecione **Adicionar os contratos a um grupo de licenças existente** . Na lista **Nome do grupo** , selecione o grupo de licenças ao qual você deseja adicionar os contratos.

6.  Clique em **OK**.

O modo de exibição de lista **Todos os Contratos** é exibido.

## Gerenciar contratos de licença
Os contratos de licenciamento de software podem ser adicionados aos grupos de licenças. Você pode usar grupos de licenças para organizar seus contratos de licença em unidades que são lógicas para a sua organização. Além disso, você pode excluir contratos de licença criados anteriormente.

|||
|-|-|
|Tarefa|Detalhes|
|Criar um grupo de licenças|Na página **Visão Geral** do espaço de trabalho **Licenças** , clique em **Criar Grupo de Licenças** no menu **Tarefas** . **Observação:** é possível criar um máximo total de 500 grupos de licenças.|
|Renomear um grupo de licenças|No espaço de trabalho **Licenças** , escolha um grupo de licenças e, em seguida, clique em **Editar Grupo de Licenças** no menu **Tarefas** .|
|Excluir um grupo de licenças|No espaço de trabalho **Licenças** , escolha um grupo de licenças e, em seguida, clique em **Excluir Grupo de Licenças** no menu **Tarefas** . **Dica:** Todas as licenças no grupo excluído são movidas para o grupo **Contratos não atribuídos**.|
|Excluir um contrato de licença|No espaço de trabalho **Licenças** , escolha um contrato e, em seguida, clique em **Excluir**. **Dica:** depois de excluir contratos de Licenciamento por Volume para atualizar as informações de licença, clique em **Atualizar Agora** na página **Visão Geral de Licenças** ou na guia **Geral** de um grupo de licenças específico.|






<!--HONumber=Jul16_HO3-->


