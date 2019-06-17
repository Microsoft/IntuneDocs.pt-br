---
title: Adicionar e atribuir aplicativos Win32 ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar, atribuir e gerenciar aplicativos Win32 com o Microsoft Intune. Este tópico apresenta uma visão geral das funcionalidades de gerenciamento e da entrega de aplicativo do Intune Win32, bem como informações de solução de problemas de aplicativo do Win32.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d8c4813d94a269ed6b8f944585814b54f36fef8c
ms.sourcegitcommit: 6e07c35145f70b008cf170bae57143248a275b67
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2019
ms.locfileid: "66804692"
---
# <a name="intune-standalone---win32-app-management"></a>Intune autônomo – gerenciamento de aplicativos Win32

O [Intune autônomo](mdm-authority-set.md) agora permite melhores funcionalidades de gerenciamento de aplicativos Win32. Embora seja possível que os clientes conectados na nuvem usem o Configuration Manager para gerenciamento de aplicativos Win32, clientes apenas do Intune terão maiores funcionalidades de gerenciamento para seus aplicativos LOB (linha de negócios) Win32. Este tópico apresenta uma visão geral do recurso de gerenciamento de aplicativos Win32 e informações de solução de problemas do Intune.

> [!NOTE]
> Essa funcionalidade de gerenciamento de aplicativos dá suporte à arquitetura de sistemas operacionais de 32 e 64 bits para aplicativos do Windows.

## <a name="prerequisites"></a>Pré-requisitos

Para usar o gerenciamento de aplicativos Win32, verifique se você atende aos seguintes critérios:

- Windows 10 versão 1607 ou posterior (versões Education, Pro e Enterprise)
- O cliente do Windows 10 precisa ser: 
    - Os dispositivos precisam ser ingressados no Azure AD e registrados automaticamente. A extensão de gerenciamento do Intune dá suporte a dispositivos ingressados no Azure AD, ingressados no domínio híbrido e registrados por política de grupo. 
    > [!NOTE]
    > Para o cenário registrado por política de grupo – o usuário final usa a conta de usuário local para ingressar no AAD seu dispositivo Windows 10. O usuário precisa fazer logon no dispositivo usando sua conta de usuário do AAD e fazer o registro no Intune. O Intune instalará a extensão Gerenciamento do Intune no dispositivo se um script do PowerShell ou um aplicativo Win32 for direcionado ao usuário ou ao dispositivo.
- O tamanho do aplicativo do Windows tem um limite de 8 GB por aplicativo.

## <a name="prepare-the-win32-app-content-for-upload"></a>Preparar o conteúdo do aplicativo Win32 para upload

Use a [Ferramenta de Preparação de Conteúdo do Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730) para pré-processar aplicativos Clássicos do Windows (Win32). A ferramenta converte arquivos de instalação de aplicativo no formato *.intunewin*. Ela também detecta alguns dos recursos exigidos pelo Intune para determinar o estado de instalação do aplicativo. Depois de usar essa ferramenta na pasta do instalador do aplicativo, você poderá criar um aplicativo Win32 no console do Intune.

> [!IMPORTANT]
> A [Ferramenta de Preparação de Conteúdo do Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730) compacta todos os arquivos e as subpastas quando cria o arquivo *.intunewin*. Lembre-se de manter a Ferramenta de Preparação de Conteúdo do Microsoft Win32 separada das pastas e dos arquivos do instalador para não incluir a ferramenta nem outros arquivos e pastas desnecessários no arquivo *.intunewin*.

Baixe a [Ferramenta de Preparação de Conteúdo do Microsoft Win32](https://go.microsoft.com/fwlink/?linkid=2065730) no GitHub como um arquivo zip. O arquivo compactado contém uma pasta chamada **Microsoft-Win32-Content-Prep-Tool-master**. A pasta contém a ferramenta de preparação, a licença, um arquivo Leiame e as notas sobre a versão. 

### <a name="process-flow-to-create-intunewin-file"></a>Fluxo do processo para criação do arquivo .intunewin

   ![Fluxo do processo para criação de um arquivo .intunewin](./media/prepare-win32-app.svg)

### <a name="run-the-microsoft-win32-content-prep-tool"></a>Executar a Ferramenta de Preparação de Conteúdo do Microsoft Win32

Se você executar `IntuneWinAppUtil.exe` na janela Comando sem parâmetros, a ferramenta orientará você passo a passo na inserção dos parâmetros necessários. Se preferir, adicione os parâmetros ao comando com base nos parâmetros de linha de comando disponíveis a seguir.

### <a name="available-command-line-parameters"></a>Parâmetros de linha de comando disponíveis 

|    **Parâmetro de linha de comando**    |    **Descrição**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Ajuda    |
|    `-c <setup_folder>`     |    Pasta para todos os arquivos de instalação. Todos os arquivos dessa pasta serão compactados no arquivo *.intunewin*.    |
|   ` -s <setup_file>`     |    Arquivo de instalação (como *setup.exe* ou *setup.msi*).    |
|    `-o <output_folder>`     |    Pasta de saída para o arquivo *.intunewin* separado.    |
|    `-q`       |    Modo silencioso    |

### <a name="example-commands"></a>Comandos de exemplo

|    **Exemplo de comando**    |    **Descrição**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Esse comando exibirá informações de uso da ferramenta.    |
|    `IntuneWinAppUtil -c c:\testapp\v1.0 -s c:\testapp\v1.0\setup.exe -o c:\testappoutput\v1.0 -q`    |    Esse comando gerará o arquivo `.intunewin` da pasta de origem e do arquivo de instalação especificados. Para o arquivo de instalação do MSI, essa ferramenta recuperará as informações obrigatórias para o Intune. Se o `-q` for especificado, o comando será executado no modo silencioso e, se o arquivo de saída já existir, ele será substituído. Além disso, se a pasta de saída não existir, ela será criada automaticamente.    |

Ao gerar um arquivo *.intunewin*, coloque os arquivos que precisam ser referenciados em uma subpasta da pasta de instalação. Em seguida, use um caminho relativo para referenciar o arquivo específico de que você precisa. Por exemplo:

**Pasta de origem de instalação:** *c:\testapp\v1.0*<br>
**Arquivo de licença:** *c:\testapp\v1.0\licenses\license.txt*

Consulte o arquivo *license. txt* usando o caminho relativo *licenses\license.txt*.

## <a name="create-assign-and-monitor-a-win32-app"></a>Criar, atribuir e monitorar um aplicativo Win32

De maneira muito semelhante a um aplicativo LOB (linha de negócios), é possível adicionar um aplicativo Win32 ao Microsoft Intune. Normalmente, esse tipo de aplicativo é escrito internamente ou por um terceiro. 

### <a name="process-flow-to-add-a-win32-app-to-intune"></a>Fluxo do processo para adição de um aplicativo Win32 ao Intune

   ![Fluxo do processo para adição de um aplicativo Win32 ao Intune](./media/add-win32-app.svg)

### <a name="add-a-win32-app-to-intune"></a>Adicionar um aplicativo Win32 ao Intune

As etapas a seguir fornecem diretrizes para ajudar você a adicionar um aplicativo Windows ao Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Etapa 1: Especificar o arquivo de instalação do software

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3.  No painel do **Intune**, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**.
4.  No painel do aplicativo **Adicionar**, selecione **Aplicativo do Windows (Win32)** na lista suspensa fornecida.

    ![Captura de tela da folha Adicionar aplicativo – Caixa de lista suspensa Adicionar tipo](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Etapa 2: Fazer upload do arquivo do pacote do aplicativo

1.  No painel **Adicionar aplicativo**, selecione **Arquivo do pacote do aplicativo** para selecionar um arquivo. O painel Arquivo do pacote do aplicativo será exibido.

    ![Captura de tela da folha do arquivo de pacote do Aplicativo](./media/apps-win32-app-02.png)

2.  No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do Windows com a extensão *.intunewin*.

    > [!IMPORTANT]
    > Certifique-se de usar a versão mais recente da Ferramenta de Preparação de Conteúdo do Microsoft Win32. Se você não usar a versão mais recente, verá um aviso indicando que o aplicativo foi empacotado usando uma versão mais antiga da Ferramenta de Preparação de Conteúdo do Microsoft Win32. 

3.  Quando tiver terminado, selecione **OK**.

### <a name="step-3-configure-app-information"></a>Etapa 3: Configurar informações do aplicativo

1.  Na folha **Adicionar aplicativo**, selecione **Informações do aplicativo** para configurar o aplicativo.
2.  No painel **Informações do aplicativo**, configure as seguintes informações. Alguns dos valores neste painel podem ser sido preenchidos automaticamente.
    - **Nome**: Insira o nome do aplicativo como ele é exibido no portal da empresa. Se o mesmo nome de aplicativo existir duas vezes, cada aplicativo será exibido no Portal da Empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. A descrição será exibida no portal da empresa.
    - **Editor**: Insira o nome do editor do aplicativo.
    - **Categoria**: Selecione uma ou mais das categorias de aplicativo interno ou uma categoria criada por você. As categorias facilitam para os usuários a localização do aplicativo ao navegar no portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: Exiba o aplicativo de maneira proeminente em na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, Insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida no portal da empresa.
    - **URL de Privacidade**: Opcionalmente, Insira a URL de um site que contém informações de privacidade desse aplicativo. A URL será exibida no portal da empresa.
    - **Desenvolvedor**: Opcionalmente, Insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: Opcionalmente, Insira o nome do proprietário desse aplicativo. Um exemplo é **Departamento de RH**.
    - **Observações**: Insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: Carregue um ícone associado ao aplicativo. O ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3.  Quando tiver terminado, selecione **OK**.

### <a name="step-4-configure-app-installation-details"></a>Etapa 4: Configurar detalhes de instalação do aplicativo
1.  No painel **Adicionar aplicativo**, selecione **Programa** para configurar a instalação do aplicativo e os comandos de remoção para o aplicativo.
2.  Adicionar linha de comando de instalação completa para instalar o aplicativo. 

    Por exemplo, se o nome de arquivo do aplicativo for **MyApp123**, adicione o seguinte:<br>
    `msiexec /p “MyApp123.msp”`<p>
    Se o aplicativo for `ApplicationName.exe`, o comando será o nome do aplicativo seguido dos argumentos de comando (opções) compatíveis com o pacote. <br>Por exemplo:<br>
    `ApplicationName.exe /quiet`<br>
    No comando acima, o pacote `ApplicationName.exe` dá suporte ao argumento de comando `/quiet`.<p> Para obter os argumentos específicos compatíveis com o pacote de aplicativos, contate o fornecedor do aplicativo.

3.  Adicione a linha de comando de desinstalação completa para desinstalar o aplicativo com base no GUID do aplicativo. 

    Por exemplo: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Você pode configurar um aplicativo Win32 a ser instalado no contexto de **Usuário** ou **Sistema**. O contexto de **Usuário** refere-se a somente um determinado usuário. O contexto de **Sistema** refere-se a todos os usuários de um dispositivo Windows 10.
    >
    > Os usuários finais não precisam fazer logon dispositivo para instalar aplicativos Win32.
    > 
    > A instalação e a desinstalação do aplicativo Win32 será executada sob privilégio de administrador (por padrão) quando o aplicativo estiver configurado para instalação no contexto do usuário e o usuário final do dispositivo tiver privilégios de administrador.

4.  Quando tiver terminado, selecione **OK**.

### <a name="step-5-configure-app-requirements"></a>Etapa 5: Configurar requisitos do aplicativo

1.  No painel **Adicionar aplicativo**, selecione **Requisitos** para configurar os requisitos aos quais os dispositivos devem atender antes de o aplicativo ser instalado.
2.  No painel **Adicionar uma regra de Requisitos**, configure as informações a seguir. Alguns dos valores neste painel podem ser sido preenchidos automaticamente.
    - **Arquitetura do sistema operacional**: Escolha as arquiteturas necessárias para instalar o aplicativo.
    - **Sistema operacional mínimo**: Selecione o sistema operacional mínimo necessário para instalar o aplicativo.
    - **Espaço em disco necessário (MB)** : Opcionalmente, adicione o espaço em disco livre necessário na unidade do sistema para instalar o aplicativo.
    - **Memória física necessária (MB)** : Opcionalmente, adicione a memória física (RAM) necessária para instalar o aplicativo.
    - **Número mínimo necessário de processadores lógicos**: Opcionalmente, adicione o número mínimo de processadores lógicos necessários para instalar o aplicativo.
    - **Velocidade mínima necessária de CPU (MHz)** : Opcionalmente, adicione o número mínimo necessário de processadores lógicos para instalar o aplicativo.

3. Clique em **Adicionar** para exibir a folha **Adicionar uma regra de Requisito** e configurar regras de requisitos adicionais. Selecione o **Tipo de requisito** para escolher o tipo de regra que você usará para determinar como um requisito é validado. As regras de requisitos podem ser baseadas em informações do sistema de arquivos, valores do Registro ou scripts do PowerShell. 
    - **Arquivo**: Quando você escolhe **Arquivo** como o **Tipo de requisito**, a regra de requisito precisa detectar um arquivo ou uma pasta, uma data, uma versão ou um tamanho. 
        - **Caminho** – O caminho completo da pasta que contém o arquivo ou a pasta a ser detectado.
        - **Arquivo ou pasta** – O arquivo ou pasta a ser detectado.
        - **Propriedade** – selecione o tipo de regra usado para validar a presença do aplicativo.
        - **Associado a um aplicativo de 32 bits em clientes de 64 bits** – Selecione **Sim** para expandir as variáveis de ambiente do caminho no contexto de 32 bits em clientes de 64 bits. Selecione **Não** (padrão) para expandir quaisquer variáveis de caminho no contexto de 64 bits em clientes de 64 bits. Clientes de 32 bits sempre usarão o contexto de 32 bits.
    - **Registro**: Quando você escolhe **Registro** como o **Tipo de requisito**, a regra de requisito precisa detectar uma configuração do Registro com base no valor, na cadeia de caracteres, no inteiro ou na versão.
        - **Caminho da chave** – O caminho completo da entrada do Registro que contém o valor a ser detectado.
        - **Nome do valor** – O nome do valor de Registro a ser detectado. Se esse valor estiver vazio, a detecção ocorrerá na chave. O valor (padrão) de uma chave será usado como valor de detecção se o método de detecção for diferente da existência do arquivo ou da pasta.
        - **Requisito de chave do Registro** – selecione o tipo de comparação de chave do Registro usado para determinar como a regra de requisito é validada.
        - **Associado a um aplicativo de 32 bits em clientes de 64 bits** – Selecione **Sim** para pesquisar o Registro de 32 bits em clientes de 64 bits. Selecione **Não** (padrão) para pesquisar o Registro de 64 bits em clientes de 64 bits. Clientes de 32 bits sempre pesquisarão o Registro de 32 bits.
    - **Script**: Escolha **Script** como o **Tipo de requisito** quando você não puder criar uma regra de requisito baseada em arquivo, no Registro ou em qualquer outro método disponível para você no console do Intune.
        - **Arquivo de script** – para a regra de requisito baseada em script do PowerShell, se o código existente for 0, detectaremos o StdOut com mais detalhes. Por exemplo, podemos detectar StdOut como um inteiro que tem um valor igual a 1.
        - **Executar script como um processo de 32 bits em clientes de 64 bits**: selecione **Sim** para executar o script como um processo de 32 bits em clientes de 64 bits. Selecione **Não** (padrão) para executar o script como um processo de 64 bits em clientes de 64 bits. Os clientes de 32 bits executam o script em um processo de 32 bits.
        - **Executar este script usando as credenciais de logon**: Selecione **Sim** para executar o script usando as credenciais de logon do dispositivo**.
        - **Impor a verificação da assinatura de script** – Selecione **Sim** para verificar se o script é assinado por um fornecedor confiável, que permitirá que o script seja executado sem a exibição de avisos ou prompts. O script será executado desbloqueado. Selecione **Não** (padrão) para executar o script com a confirmação do usuário final sem verificação de assinatura.
        - **Selecionar o tipo de dados de saída**: Selecione o tipo de dados usado para determinar uma correspondência da regra de requisito.
4.  Quando tiver terminado, selecione **OK**.

### <a name="step-6-configure-app-detection-rules"></a>Etapa 6: Configurar regras de detecção de aplicativo

1.  No painel **Adicionar aplicativo**, selecione **Regras de detecção** para configurar as regras para detectar a presença do aplicativo.
2.  No campo **Formato de regras**, selecione como a presença do aplicativo será detectada. É possível optar por configurar manualmente as regras de detecção ou usar um script personalizado para detectar a presença do aplicativo. É necessário escolher pelo menos uma regra de detecção. 

    > [!NOTE]
    > No painel **Regras de detecção**, é possível optar por adicionar várias regras. As condições para **todas** as regras devem ser atendidas para detectar o aplicativo.

    - **Configurar manualmente as regras de detecção** – é possível selecionar um dos seguintes tipos de regra:
        1.  **MSI** – Verificar com base na verificação de versão do MSI. Essa opção só pode ser adicionada uma vez. Quando você escolhe esse tipo de regra, você tem duas configurações:
            - **Código de produto MSI** – Adicionar um código de produto MSI válido para o aplicativo.
            - **Verificação da versão de produto MSI** – selecione **Sim** para verificar a versão do produto MSI, além do código de produto MSI.
        2.  **Arquivo** – Verificar com base na detecção de pasta ou arquivo, data, versão ou tamanho.
            - **Caminho** – O caminho completo da pasta que contém o arquivo ou a pasta a ser detectado.
            - **Arquivo ou pasta** – O arquivo ou pasta a ser detectado.
            - **Método de detecção** – selecione o tipo de método de detecção usado para validar a presença do aplicativo.
            - **Associado a um aplicativo de 32 bits em clientes de 64 bits** – Selecione **Sim** para expandir as variáveis de ambiente do caminho no contexto de 32 bits em clientes de 64 bits. Selecione **Não** (padrão) para expandir quaisquer variáveis de caminho no contexto de 64 bits em clientes de 64 bits. Clientes de 32 bits sempre usarão o contexto de 32 bits.
            
            **Exemplos de detecção baseada em arquivo**
            1.  Verifique a existência do arquivo.
         
                ![Captura de tela do painel da regra de detecção – existência do arquivo](./media/apps-win32-app-03.png)
        
            2.  Verifique a existência da pasta.
         
                ![Captura de tela do painel da regra de detecção – existência da pasta](./media/apps-win32-app-04.png)
        
        3. **Registro** – Verificar com base no valor, cadeia de caracteres, inteiro ou versão.
            - **Caminho da chave** – O caminho completo da entrada do Registro que contém o valor a ser detectado.
            - **Nome do valor** – O nome do valor de Registro a ser detectado. Se esse valor estiver vazio, a detecção ocorrerá na chave. O valor (padrão) de uma chave será usado como valor de detecção se o método de detecção for diferente da existência do arquivo ou da pasta.
            - **Método de detecção** – selecione o tipo de método de detecção usado para validar a presença do aplicativo.
            - **Associado a um aplicativo de 32 bits em clientes de 64 bits** – Selecione **Sim** para pesquisar o Registro de 32 bits em clientes de 64 bits. Selecione **Não** (padrão) para pesquisar o Registro de 64 bits em clientes de 64 bits. Clientes de 32 bits sempre pesquisarão o Registro de 32 bits.
            
            **Exemplos para a detecção baseada no Registro**
            1.  Verifique se a chave do Registro existe.
            
                ![Captura de tela do painel da regra de detecção – a chave do Registro existe](./media/apps-win32-app-05.png)    
            
            2.  Verifique se o valor do registro existe.
        
                ![Captura de tela do painel da regra de detecção – o valor de Registro existe](./media/apps-win32-app-06.png)    
        
            3.  Verifique a igualdade da cadeia de caracteres do valor de Registro.
        
                ![Captura de tela do painel da regra de detecção – a cadeia de caracteres do valor de Registro é igual](./media/apps-win32-app-07.png)    
     
    - **Usar um script de detecção personalizado** – Especifique o script do PowerShell que será usado para detectar este aplicativo. 
    
        1.  **Arquivo de script** – Selecione um script do PowerShell que detectará a presença do aplicativo no cliente. O aplicativo será detectado quando o script retornar um código de saída de valor 0 e escrever um valor de cadeia de caracteres em STDOUT.

        2.  **Executar script como um processo de 32 bits em clientes de 64 bits**: selecione **Sim** para executar o script como um processo de 32 bits em clientes de 64 bits. Selecione **Não** (padrão) para executar o script como um processo de 64 bits em clientes de 64 bits. Os clientes de 32 bits executam o script em um processo de 32 bits.

        3.  **Impor a verificação da assinatura de script** – Selecione **Sim** para verificar se o script é assinado por um fornecedor confiável, que permitirá que o script seja executado sem a exibição de avisos ou prompts. O script será executado desbloqueado. Selecione **Não** (padrão) para executar o script com a confirmação do usuário final sem verificação de assinatura.
    
            O agente do Intune verifica os resultados do script. Ele lê os valores gravados pelo script no fluxo de saída padrão (STDOUT), no fluxo de erro padrão (STDERR) e no código de saída. Se o script for encerrado com um valor diferente de zero, o script falhará e o status de detecção do aplicativo não será instalado. Se o código de saída for zero e STDOUT tiver dados, o status de detecção do aplicativo será Instalado. 

            > [!NOTE]
            > A Microsoft recomenda a codificação de seu script como UTF-8. Quando o script tiver sido encerrado com um valor de 0, a execução do script terá sido bem-sucedida. O segundo canal de saída indica que o aplicativo foi detectado – os dados STDOUT indicam que o aplicativo foi encontrado no cliente. Não procuramos uma cadeia de caracteres específica do STDOUT.

        4.  Após adicionar suas regras, selecione **Adicionar** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Etapa 7: Configurar códigos de retorno do aplicativo

1.  No painel **Adicionar aplicativo**, selecione **Códigos de retorno** para adicionar os códigos de retorno usados para especificar o comportamento de repetição da instalação de aplicativo ou o comportamento pós-instalação. As entradas do código de retorno são adicionadas por padrão durante a criação do aplicativo. No entanto, é possível adicionar mais códigos de retorno ou alterar os existentes. 
2.  No painel **Códigos de retorno**, adicione mais códigos de retorno ou modifique os existentes.
    - **Com falha**: o valor retornado que indica uma falha na instalação do aplicativo.
    - **Reinicialização forçada** – o código de retorno de reinicialização forçada não permite que aplicativos Win32 próximos sejam instalados no cliente sem reinicialização. 
    - **Reinicialização suave** – O código de retorno de reinicialização suave permite que o aplicativo Win32 próximo seja instalado sem a necessidade de uma reinicialização do cliente. A reinicialização é necessária para concluir a instalação do aplicativo atual.
    - **Repetição** – O agente do código de retorno de repetição tentará instalar o aplicativo três vezes. Ele aguardará 5 minutos entre cada tentativa. 
    - **Sucesso** – O valor retornado que indica o aplicativo foi instalado com êxito.
3.  Selecione **OK** após adicionar ou modificar sua lista de códigos de retorno.

### <a name="step-8-add-the-app"></a>Etapa 8: Adicionar o aplicativo

1.  No painel **Adicionar aplicativo**, verifique se você configurou as informações do aplicativo corretamente.
2.  Selecione **Adicionar** para carregar o aplicativo no Intune.

### <a name="step-9-assign-the-app"></a>Etapa 9: Atribuir o aplicativo

1.  No painel de aplicativos, selecione **Atribuições**.
2.  Selecione **Adicionar Grupo** para abrir o painel **Adicionar grupo** relacionado ao aplicativo.
3.  Para o aplicativo específico, selecione um **tipo de atribuição**:
    - **Disponível para dispositivos registrados**: Os usuários instalam o aplicativo no site ou aplicativo do Portal da Empresa.
    - **Obrigatório**: O aplicativo é instalado nos dispositivos dos grupos selecionados.
    - **Desinstalação**: O aplicativo é desinstalado dos dispositivos nos grupos selecionados.
4.  Selecione **Grupos incluídos** e atribua os grupos que usarão esse aplicativo.
5.  No painel **Atribuir**, selecione **OK** para concluir a seleção de grupos incluídos.
6.  Se desejar que alguns grupos de usuários não sejam afetados por esta atribuição de aplicativo, selecione **Excluir Grupos**.
7.  No painel **Adicionar grupo**, selecione **OK**.
8.  No painel **Atribuições** do aplicativo, selecione **Salvar**.

Nesta altura, você concluiu as etapas necessárias para adicionar um aplicativo Win32 ao Intune. Para obter informações sobre a atribuição e monitoramento de aplicativos, confira [Atribuir aplicativos a grupos no Microsoft Intune](https://docs.microsoft.com/intune/apps-deploy) e [Monitor app information and assignments with Microsoft Intune](https://docs.microsoft.com/intune/apps-monitor) (Monitorar informações e atribuições de aplicativo com o Microsoft Intune).

## <a name="app-dependencies"></a>Dependências de aplicativo

As dependências de aplicativo são aplicativos que precisam ser instalados antes que o aplicativo Win32 possa ser instalado. Você pode exigir que outros aplicativos sejam instalados como dependências. Especificamente, o dispositivo precisa instalar os aplicativos dependentes antes de instalar o aplicativo Win32. Há um máximo de 100 dependências, que incluem as dependências das dependências incluídas, bem como o próprio aplicativo. Você poderá adicionar dependências de aplicativo Win32 somente depois que o aplicativo Win32 for adicionado ao Intune e carregado nele. Depois que o aplicativo Win32 for adicionado, você verá a opção **Dependências** na folha do aplicativo Win32. 

Ao adicionar uma dependência de aplicativo, você poderá fazer uma pesquisa com base no nome do aplicativo e no editor. Além disso, você poderá classificar as dependências adicionadas com base no nome do aplicativo e no editor. As dependências de aplicativo adicionadas anteriormente não podem ser selecionadas na lista de dependências de aplicativo adicionadas. 

Você pode escolher se deseja ou não instalar cada aplicativo dependente automaticamente. Por padrão, a opção **Instalar automaticamente** é definida como **Sim** para cada dependência. Ao instalar automaticamente um aplicativo dependente, mesmo se o aplicativo dependente não for direcionado ao usuário ou ao dispositivo, o Intune instalará o aplicativo no dispositivo para atender à dependência antes de instalar o aplicativo Win32. É importante observar que uma dependência pode ter subdependências recursivas e cada subdependência será instalada antes da instalação da dependência principal. Além disso, a instalação de dependências não segue uma ordem de instalação em um nível de dependência especificado.

Para adicionar uma dependência de aplicativo ao aplicativo Win32, use as seguintes etapas:

1. No Intune, selecione **Aplicativos cliente** > **Aplicativos** para exibir a lista de aplicativos cliente adicionados. 
2. Selecione um **Aplicativo do Windows (Win32)** adicionado. 
3. Selecione **Dependências** para adicionar os aplicativos dependentes que precisam ser instalados para que o aplicativo Win32 possa ser instalado. 
4. Clique em **Adicionar** para adicionar uma dependência de aplicativo.
5. Depois de adicionar os aplicativos dependentes, clique em **Selecionar**.
6. Escolha se deseja instalar automaticamente o aplicativo dependente selecionando **Sim** ou **Não** em **Instalar automaticamente**.
7. Clique em **Salvar**.

O usuário final verá notificações do sistema do Windows que indicam se os aplicativos dependentes estão sendo baixados e instalados como parte do processo de instalação do aplicativo Win32. Além disso, quando um aplicativo dependente não for instalado, o usuário final geralmente verá uma das seguintes notificações:
- Falha na instalação de um ou mais aplicativos dependentes
- Um ou mais requisitos de aplicativo dependente não atendidos
- Um ou mais aplicativos dependentes estão aguardando uma reinicialização do dispositivo

Se você optar por não **Instalar automaticamente** uma dependência, não haverá uma tentativa de instalar o aplicativo Win32. Além disso, o relatório do aplicativo mostrará que a dependência foi sinalizada como `failed` e também fornecerá um motivo da falha. Exiba a falha de instalação de dependência clicando em uma falha (ou um aviso) fornecido nos [detalhes da instalação](troubleshoot-app-install.md#win32-app-installation-troubleshooting) do aplicativo Win32. 

Cada dependência seguirá a lógica de repetição do aplicativo Win32 do Intune (três tentativas de instalação após uma espera de cinco minutos) e ao agendamento de reavaliação global. Além disso, as dependências só são aplicáveis no momento da instalação do aplicativo Win32 no dispositivo. As dependências não são aplicáveis à desinstalação de um aplicativo Win32. Para excluir uma dependência, clique nas reticências (três pontos) à esquerda do aplicativo dependente localizadas no final da linha da lista de dependências. 

## <a name="delivery-optimization"></a>Otimização de Entrega

Os clientes do Windows 10 1709 e posterior baixarão o conteúdo do aplicativo Win32 do Intune usando um componente de Otimização de Entrega no cliente do Windows 10. A otimização de entrega tem a funcionalidade de ponto a ponto ativada por padrão. A Otimização de Entrega pode ser definida por política de grupo e por meio da configuração de Dispositivo do Intune. Para saber mais, consulte [Otimização de entrega para Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

## <a name="install-required-and-available-apps-on-devices"></a>Instalar aplicativos obrigatórios e disponíveis em dispositivos

O usuário final verá as Notificações do sistema do Windows para as instalações de aplicativo obrigatórias e disponíveis. A imagem a seguir mostra um exemplo de notificação do sistema em que a instalação do aplicativo não é concluída até que o dispositivo seja reiniciado. 

![Captura de tela das notificações do sistema do Windows para uma instalação de aplicativo](./media/apps-win32-app-08.png)    

A imagem a seguir notifica o usuário final de há alterações do aplicativo sendo feitas no dispositivo.

![Captura de tela notificando o usuário de que estão sendo feitas alterações no aplicativo](./media/apps-win32-app-09.png)    

## <a name="toast-notifications-for-win32-apps"></a>Notificações do sistema para aplicativos Win32 
Se for necessário, você poderá suprimir a exibição de notificações do sistema ao usuário final por atribuição de aplicativo. No Intune, selecione **Aplicativos cliente** > **Aplicativos** > selecione o aplicativo > **Atribuições** > **Incluir Grupos**. 

> [!NOTE]
> Os aplicativos Win32 instalados pela extensão de gerenciamento do Intune não serão desinstalados em dispositivos não registrados. Os administradores podem aproveitar a exclusão de atribuição para não oferecer aplicativos Win32 em dispositivos BYOD.

## <a name="troubleshoot-win32-app-issues"></a>Solucionar problemas do aplicativo Win32
Os logons do agente no computador cliente estão comumente no `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. É possível usar o `CMTrace.exe` para exibir esses arquivos de log. *CMTrace.exe* pode ser baixado em [Ferramentas de Cliente do Configuration Manager](https://docs.microsoft.com/sccm/core/support/tools). 

![Captura de tela de logs do Agente no computador cliente](./media/apps-win32-app-10.png)    

> [!IMPORTANT]
> Para permitir a instalação e a execução corretas de aplicativos Win32 LOB, as configurações de antimalware devem excluir os seguintes diretórios da verificação:<p>
> **Em computadores cliente x64**:<br>
> *C:\Arquivos de Programa (x86)\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **Em computadores cliente x86**:<br>
> *C:\Arquivos de Programa\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*

### <a name="detecting-the-win32-app-file-version-using-powershell"></a>Detectando a versão do arquivo de aplicativo Win32 usando o PowerShell

Se você tiver dificuldade para detectar a versão do arquivo de aplicativo Win32, considere usar ou modificar o seguinte comando do PowerShell:

``` PowerShell

$FileVersion = [System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion
#The below line trims the spaces before and after the version name
$FileVersion = $FileVersion.Trim();
if ("<file version of successfully detected file>" -eq $FileVersion)
{
#Write the version to STDOUT by default
$FileVersion
exit 0
}
else
{
#Exit with non-zero failure code
exit 1
}

```
No comando do PowerShell acima, substitua a cadeia de caracteres `<path to binary file>` com o caminho para o arquivo de aplicativo Win32. Um caminho de exemplo seria semelhante ao seguinte:<br>
`C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\ssms.exe`

Além disso, substitua a cadeia de caracteres `<file version of successfully detected file>` com a versão do arquivo que você precisa detectar. Uma cadeia de caracteres de versão de arquivo de exemplo seria semelhante à seguinte:<br>
`2019.0150.18118.00 ((SSMS_Rel).190420-0019)`

Se você precisar obter as informações de versão do seu aplicativo Win32, poderá usar o seguinte comando do PowerShell:

``` PowerShell

[System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion

```

No comando do PowerShell acima, substitua `<path to binary file>` por seu caminho do arquivo.

### <a name="additional-troubleshooting-areas-to-consider"></a>Áreas de solução de problemas adicionais a serem consideradas
- Verifique o direcionamento para garantir que o agente seja instalado no dispositivo – o aplicativo Win32 direcionado a um grupo ou o Script do PowerShell direcionado a um grupo criará a política de instalação do agente para o grupo de segurança.
- Verificar a versão do sistema operacional – Windows 10 1607 e posterior.  
- Verifique o SKU do Windows 10 – O Windows 10 S ou versões do Windows em execução com o modo S habilitado não são compatíveis com a instalação do MSI.

Para obter mais informações sobre como solucionar problemas de aplicativos Win32, confira [Solução de problemas de instalação de aplicativos Win32](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

## <a name="next-steps"></a>Próximas etapas

- Para obter mais informações sobre como adicionar aplicativos ao Intune, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).
