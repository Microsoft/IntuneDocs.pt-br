---
título: adicionar aplicativos do Win32 ao Microsoft Intune titlesuffix: descrição: Saiba como adicionar, entregar e gerenciar aplicativos do Win32 com o Microsoft Intune. Este tópico apresenta uma visão geral das funcionalidades de gerenciamento e da entrega de aplicativo do Intune Win32, bem como informações de solução de problemas de aplicativo do Win32. keywords: author: Erikre ms.author: erikre manager: dougeby <<<<<<< HEAD ms.date: 10/23/2018 ======= ms.date: 10/19/2018
>>>>>>> 14fdd9aac5e66324acfe83ae31b126d8216d7da4 ms.topic: article ms.prod: ms.service: microsoft-intune ms.technology: ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2

ms.reviewer: mghadial ms.suite: ems ms.custom: intune-azure
---

# <a name="intune-standalone---win32-app-management-public-preview"></a>Intune autônomo – gerenciamento de aplicativos Win32 (versão prévia pública)

O Intune autônomo permitirá maiores funcionalidades de gerenciamento de aplicativos Win32. Embora seja possível que os clientes conectados na nuvem usem o Configuration Manager para gerenciamento de aplicativos Win32, clientes apenas do Intune terão maiores funcionalidades de gerenciamento para seus aplicativos LOB (linha de negócios) Win32. Este tópico apresenta uma visão geral do recurso de gerenciamento de aplicativos Win32 e informações de solução de problemas do Intune.

## <a name="prerequisites-for-public-preview"></a>Pré-requisitos para versão prévia pública

- Windows 10 versão 1607 ou posterior (Enterprise)
- O cliente do Windows 10 precisa ser: 
    - ingressado no AAD (Azure Active Directory) ou Azure Active Directory Híbrido, e
    - registrado no Intune (gerenciado pelo MDM)
- O tamanho do aplicativo do Windows tem um limite de 8 GB por aplicativo na versão prévia pública 

> [!NOTE]
> No momento, estamos testando as edições Pro e Educação do Windows 10 versão 1607 e ficaremos felizes em receber seus comentários.


## <a name="prepare-the-win32-app-content-for-upload"></a>Preparar o conteúdo do aplicativo Win32 para upload

Use a [Ferramenta de preparação para upload de aplicativos Win32 do Microsoft Intune](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool) para pré-processar aplicativos Win32. A ferramenta de empacotamento converte arquivos de instalação de aplicativo no formato *.intunewin*. A ferramenta de empacotamento também detecta alguns dos recursos exigidos pelo Intune para determinar o estado de instalação do aplicativo. Depois de usar essa ferramenta na pasta do instalador do aplicativo, você poderá criar um aplicativo Win32 no console do Intune.

É possível baixar a [Ferramenta de preparação para upload de aplicativos Win32 do Microsoft Intune](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool) no GitHub.

### <a name="available-command-line-parameters"></a>Parâmetros de linha de comando disponíveis 

|    **Parâmetro de linha de comando**    |    **Descrição**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Ajuda    |
|    `-c <setup_folder>`     |    Pasta de instalação para todos os arquivos de instalação.    |
|   ` -s <setup_file>`     |    Arquivo de instalação (como *setup.exe* ou *setup.msi*).    |
|    `-o <output_folder>`     |    Pasta de saída para o arquivo *.intunewin* separado.    |
|    `-q`       |    Modo silencioso    |

### <a name="example-commands"></a>Comandos de exemplo

|    **Exemplo de comando**    |    **Descrição**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Esse comando exibirá informações de uso da ferramenta.    |
|    `IntuneWinAppUtil -c <setup_folder> -s <source_setup_file> -o <output_folder> <-q>`    |    Esse comando gerará o arquivo `.intunewin` da pasta de origem e do arquivo de instalação especificados. Para o arquivo de instalação do MSI, essa ferramenta recuperará as informações obrigatórias para o Intune. Se o `-q` for especificado, o comando será executado no modo silencioso e, se o arquivo de saída já existir, ele será substituído. Além disso, se a pasta de saída não existir, ela será criada automaticamente.    |

## <a name="create-assign-and-monitor-a-win32-app"></a>Criar, atribuir e monitorar um aplicativo Win32

De maneira muito semelhante a um aplicativo LOB (linha de negócios), é possível adicionar um aplicativo Win32 ao Microsoft Intune. Normalmente, esse tipo de aplicativo é escrito internamente ou por um terceiro. As etapas a seguir fornecem diretrizes para ajudar você a adicionar um aplicativo Windows ao Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Etapa 1: Especificar os arquivos de instalação de software

1.  Entre no [Portal do Azure](https://portal.azure.com/).
2.  Selecione **Todos os serviços** > **Intune**. O Intune está na seção **Monitoramento + Gerenciamento**.
3.  No painel do **Intune**, selecione **Aplicativos cliente** > **Aplicativos** > **Adicionar**.
4.  No painel do aplicativo **Adicionar**, selecione **Aplicativo do Windows (Win32) – versão prévia** na lista suspensa fornecida.

    ![Captura de tela Adicionar aplicativo – Caixa Adicionar lista suspensa de tipo](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Etapa 2: Fazer upload do arquivo do pacote do aplicativo

1.  No painel **Adicionar aplicativo**, selecione **Arquivo do pacote do aplicativo** para selecionar um arquivo. O painel Arquivo do pacote do aplicativo será exibido.

    ![Captura de tela Arquivo do pacote do aplicativo](./media/apps-win32-app-02.png)

2.  No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do Windows com a extensão *.intunewin*.
3.  Quando tiver terminado, selecione **OK**.

### <a name="step-3-configure-app-information"></a>Etapa 3: Configurar informações do aplicativo

1.  Na folha **Adicionar aplicativo**, selecione **Informações do aplicativo** para configurar o aplicativo.
2.  No painel **Informações do aplicativo**, configure as seguintes informações. Alguns dos valores neste painel podem ser sido preenchidos automaticamente.
    - **Nome**: insira o nome do aplicativo como ele é exibido no portal da empresa. Se o mesmo nome de aplicativo existir duas vezes, cada aplicativo será exibido no Portal da Empresa.
    - **Descrição**: insira uma descrição para o aplicativo. A descrição será exibida no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Categoria**: selecione uma ou mais das categorias de aplicativo interno ou uma categoria criada por você. As categorias facilitam para os usuários a localização do aplicativo ao navegar no portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: exiba o aplicativo em destaque na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre o aplicativo. A URL será exibida no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade do aplicativo. A URL será exibida no portal da empresa.
    - **Desenvolvedor**: opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: opcionalmente, insira um nome para o proprietário desse aplicativo. Um exemplo é **Departamento de RH**.
    - **Observações**: digite as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: carregue um ícone que será associado ao aplicativo. O ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3.  Quando tiver terminado, selecione **OK**.

### <a name="step-4-configure-app-installation-details"></a>Etapa 4: Configurar detalhes de instalação do aplicativo
1.  No painel **Adicionar aplicativo**, selecione **Programa** para configurar a instalação do aplicativo e os comandos de remoção para o aplicativo.
2.  Adicionar linha de comando de instalação completa para instalar o aplicativo. 

    Por exemplo, se o nome de arquivo do aplicativo for **MyApp123**, adicione o seguinte: `msiexec /i “MyApp123.msi”`

3.  Adicione a linha de comando de desinstalação completa para desinstalar o aplicativo com base no GUID do aplicativo. 

    Por exemplo: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Você pode configurar um aplicativo Win32 a ser instalado no contexto de **Usuário** ou **Sistema**. O contexto de **Usuário** refere-se a somente um determinado usuário. O contexto de **Sistema** refere-se a todos os usuários de um dispositivo Windows 10.
    >
    > Os usuários finais não precisam fazer logon dispositivo para instalar aplicativos Win32.

4.  Quando tiver terminado, selecione **OK**.

### <a name="step-5-configure-app-requirements"></a>Etapa 5: Configurar requisitos do aplicativo

1.  No painel **Adicionar aplicativo**, selecione **Requisitos** para configurar os requisitos aos quais os dispositivos devem atender antes de o aplicativo ser instalado.
2.  No painel **Requisitos**, configure as seguintes informações. Alguns dos valores neste painel podem ser sido preenchidos automaticamente.
    - **Arquitetura do sistema operacional**: escolha as arquiteturas necessárias para instalar o aplicativo.
    - **Sistema operacional mínimo**: selecione o sistema operacional mínimo necessário para instalar o aplicativo.
    - **Espaço em disco necessário (MB)**: opcionalmente, adicione o espaço em disco livre necessário na unidade do sistema para instalar o aplicativo.
    - **Memória física necessária (MB)**: opcionalmente, adicione a memória física (RAM) necessária para instalar o aplicativo.
    - **Número mínimo de processadores lógicos necessários**: opcionalmente, adicione o número mínimo de processadores lógicos necessários para instalar o aplicativo.
    - **Velocidade mínima da CPU necessária (MHz)**: opcionalmente, adicione a velocidade mínima da CPU necessária para instalar o aplicativo.
3.  Quando tiver terminado, selecione **OK**.

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
            
            2.  Verifique se o valor de Registro existe (**Não disponível em versão prévia**).
        
                ![Captura de tela do painel da regra de detecção – o valor de Registro existe](./media/apps-win32-app-06.png)    
        
            3.  Verifique a igualdade da cadeia de caracteres do valor de Registro.
        
                ![Captura de tela do painel da regra de detecção – a cadeia de caracteres do valor de Registro é igual](./media/apps-win32-app-07.png)    
     
    - **Usar um script de detecção personalizado** – Especifique o script do PowerShell que será usado para detectar este aplicativo. 
    
        1.  **Arquivo de script** – Selecione um script do PowerShell que detectará a presença do aplicativo no cliente. O aplicativo será detectado quando o script retornar um código de saída de valor 0 e escrever um valor de cadeia de caracteres em STDOUT.
        2.  **Executar script como um processo de 32 bits em clientes de 64 bits** – Selecione **Sim** para executar o script usando as credenciais do usuário final conectado. Selecione **Não** (padrão) para executar o script no contexto do sistema.
        3.  **Impor a verificação da assinatura de script** – Selecione **Sim** para verificar se o script é assinado por um fornecedor confiável, que permitirá que o script seja executado sem a exibição de avisos ou prompts. O script será executado desbloqueado. Selecione **Não** (padrão) para executar o script com a confirmação do usuário final sem verificação de assinatura.
    
        O sidecar do Intune verifica os resultados do script. Ele lê os valores gravados pelo script no fluxo de saída padrão (STDOUT), no fluxo de erro padrão (STDERR) e no código de saída. Se o script for encerrado com um valor diferente de zero, o script falhará e o status de detecção do aplicativo não será instalado. Se o código de saída for zero e STDOUT tiver dados, o status de detecção do aplicativo será Instalado. 
    
        > [!NOTE]
        > Quando o script tiver sido encerrado com um valor de 0, a execução do script terá sido bem-sucedida. O segundo canal de saída indica que o aplicativo foi detectado – os dados STDOUT indicam que o aplicativo foi encontrado no cliente. Não procuramos uma cadeia de caracteres específica do STDOUT.
    
3.  Após adicionar suas regras, selecione **Adicionar** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Etapa 7: Configurar códigos de retorno do aplicativo

1.  No painel **Adicionar aplicativo**, selecione **Códigos de retorno** para adicionar os códigos de retorno usados para especificar o comportamento de repetição da instalação de aplicativo ou o comportamento pós-instalação. As entradas do código de retorno são adicionadas por padrão durante a criação do aplicativo. No entanto, é possível adicionar mais códigos de retorno ou alterar os existentes. 
2.  No painel **Códigos de retorno**, adicione mais códigos de retorno ou modifique os existentes.
    - **Com falha** – O valor retornado que indica uma falha na instalação do aplicativo.
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
    - **Disponível para dispositivos inscritos**: os usuários instalam o aplicativo no aplicativo ou no site do Portal da Empresa.
    - **Obrigatório**: o aplicativo é instalado nos dispositivos nos grupos selecionados.
    - **Desinstalar**: o aplicativo é desinstalado de dispositivos nos grupos selecionados.
4.  Selecione **Grupos incluídos** e atribua os grupos que usarão esse aplicativo.
5.  No painel **Atribuir**, selecione **OK** para concluir a seleção de grupos incluídos.
6.  Se desejar que alguns grupos de usuários não sejam afetados por esta atribuição de aplicativo, selecione **Excluir Grupos**.
7.  No painel **Adicionar grupo**, selecione **OK**.
8.  No painel **Atribuições** do aplicativo, selecione **Salvar**.

Nesse ponto, você concluiu as etapas para adicionar um aplicativo Win32 ao Intune. Para obter informações sobre a atribuição e monitoramento de aplicativos, confira [Atribuir aplicativos a grupos no Microsoft Intune](https://docs.microsoft.com/intune/apps-deploy) e [Monitor app information and assignments with Microsoft Intune](https://docs.microsoft.com/intune/apps-monitor) (Monitorar informações e atribuições de aplicativo com o Microsoft Intune).

## <a name="install-required-and-available-apps-on-devices"></a>Instalar aplicativos obrigatórios e disponíveis em dispositivos

O usuário final verá as Notificações do sistema do Windows para as instalações de aplicativo obrigatórios e disponíveis. A imagem a seguir mostra um exemplo de notificação do sistema em que a instalação do aplicativo não é concluída até que o dispositivo seja reiniciado. 

![Exemplo de captura de tela das notificações do sistema do Windows para uma instalação de aplicativo](./media/apps-win32-app-08.png)    

A imagem a seguir notifica o usuário final de que alterações no aplicativo estão sendo feitas no dispositivo.

![Exemplo de captura de tela da notificação do usuário final de que alterações no aplicativo estão sendo feitas no dispositivo](./media/apps-win32-app-09.png)    

## <a name="troubleshoot-win32-app-issues"></a>Solucionar problemas do aplicativo Win32
Os logons do agente no computador cliente estão comumente no `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. É possível usar o `CMTrace.exe` para exibir esses arquivos de log. *CMTrace.exe* pode ser baixado de [Ferramentas de cliente do SCCM](https://docs.microsoft.com/sccm/core/support/tools). 

![Captura de tela dos logs do agente](./media/apps-win32-app-10.png)    

### <a name="troubleshooting-areas-to-consider"></a>Áreas de solução de problemas a serem consideradas
- Verifique o direcionamento para garantir que o agente seja instalado no dispositivo – o aplicativo Win32 direcionado a um grupo ou o Script do PowerShell direcionado a um grupo criará a política de instalação do agente para o grupo de segurança.
- Verificar a versão do sistema operacional – Windows 10 1607 e posterior.  
- Verifique o SKU do Windows 10 – O Windows 10 S ou versões do Windows em execução com o modo S habilitado não são compatíveis com a instalação do MSI.

## <a name="next-steps"></a>Próximas etapas

- Para obter mais informações sobre como adicionar aplicativos ao Intune, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).
