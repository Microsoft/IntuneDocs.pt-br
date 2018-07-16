---
title: Instalar aplicativos do Office 365 em dispositivos usando o Microsoft Intune
titlesuffix: ''
description: Saiba como você pode usar o Microsoft Intune para facilitar a instalação de aplicativos do Office 365 em dispositivos Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 09c4fdc6de0368e7ba7d4bebbc3ebfbf2c5ec378
ms.sourcegitcommit: 399f34cd169e2e352b49aad1dcb7e88294a4a9f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37869365"
---
# <a name="assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Atribua aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune

Esse tipo de aplicativo facilita a atribuição de aplicativos do Office 365 para os dispositivos que você gerencia e que executam o Windows 10. Você também pode instalar aplicativos para o cliente de área de trabalho Microsoft Project Online e para o Microsoft Visio Pro para Office 365 se tiver licenças para eles. Os aplicativos que você deseja são exibidos como uma única entrada na lista de aplicativos no console do Intune.


## <a name="before-you-start"></a>Antes de começar

>[!IMPORTANT]
>Esse método de instalar o Office terá suporte somente se nenhuma outra versão do Microsoft Office estiver instalada no dispositivo.

- Os dispositivos nos quais você implanta esses aplicativos deverão estar em execução no Windows 10 Creators Update ou posterior.
- O Intune é compatível com a adição de aplicativos Office do pacote do Office 365 apenas.
- Se algum aplicativo do Office estiver aberto quando o Intune instalar o pacote de aplicativos, a instalação poderá falhar e os usuários poderão perder dados de arquivos não salvos.
- Esse método de instalação não é compatível com dispositivos Windows 10 S, Windows Home, Windows Team, Windows Holographic ou Windows Holographic for Business.
- O Intune não dá suporte à instalação de aplicativos de área de trabalho do Office 365 da Microsoft Store (conhecidos como aplicativos Office Centennial) em um dispositivo no qual você já implantou aplicativos do Office 365 com o Intune. Se essa configuração for instalada, poderá ocorrer perda ou corrupção de dados.
- Várias atribuições de aplicativo requeridas ou disponíveis não são aditivas. Uma atribuição de aplicativo posterior substituirá as atribuições de aplicativo pré-instaladas. Por exemplo, se o primeiro conjunto de aplicativos Office contiver o Word e o último não, o Word será desinstalado. Isso não se aplica a nenhum aplicativo do Visio ou Project.


## <a name="get-started"></a>Introdução

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os Serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos móveis**.
4. No painel de carga de trabalho **Aplicativos móveis**, em **Gerenciar**, selecione **Aplicativos**.
5. Selecione **Adicionar**.
6. No painel **Adicionar aplicativos**, na lista **Tipo de aplicativo**, em **Office 365 Office**, selecione **Windows 10**.

Agora você pode configurar o pacote do aplicativo.

## <a name="configure-the-app-suite"></a>Configurar o pacote de aplicativos

Selecione os aplicativos do Office que você deseja atribuir a dispositivos.

1. No painel **Adicionar Aplicativo**, selecione **Configurar Pacote de Aplicativos**.
2. No painel **Configurar Pacote de Aplicativos**, selecione os aplicativos do Office padrão que você deseja atribuir a dispositivos.  
    Além disso, você poderá instalar aplicativos para o cliente de área de trabalho Microsoft Project Online e para o Microsoft Visio Pro para Office 365 se tiver licenças para eles.
3. Selecione **OK**.

>[!IMPORTANT]
> Depois de criar o pacote de aplicativos, você não poderá editar as propriedades dele. Para configurar propriedades diferentes, exclua o pacote de aplicativos e crie um novo.

## <a name="configure-app-information"></a>Configurar informações do aplicativo

Nesta etapa, você fornece informações sobre o pacote de aplicativos. Essas informações ajudam a identificar o pacote de aplicativos no Intune, e ajudam os usuários a encontrar o pacote de aplicativos no portal da empresa.

1. No painel **Adicionar Aplicativo**, selecione **Informações do Pacote de Aplicativos**.
2. No painel **Informações do Pacote de Aplicativos**, faça o seguinte:
    - **Nome do Pacote**: insira o nome do pacote de aplicativos da forma como ele é exibido no portal da empresa. Verifique se todos os nomes de pacotes usados são exclusivos. Se o mesmo nome de pacote de aplicativos for usado duas vezes, apenas um dos aplicativos será exibido aos usuários no Portal da Empresa.
    - **Descrição do Pacote**: insira uma descrição para o pacote de aplicativos. Por exemplo, você pode listar os aplicativos que você selecionou para serem incluídos.
    - **Editor**: a Microsoft aparece como o editor.
    - **Categoria**: como opção, selecione uma ou mais das categorias de aplicativo internas ou uma categoria criada por você. Essa configuração facilita para os usuários localizarem o pacote de aplicativos enquanto navegam pelo Portal da Empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: selecione esta opção para exibir o pacote de aplicativos de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: a Microsoft aparece como o desenvolvedor.
    - **Proprietário**: a Microsoft aparece como o proprietário.
    - **Observações**: digite as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: o logotipo do Office 365 é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3. Selecione **OK**.

## <a name="configure-app-settings"></a>Definir configurações do aplicativo

Nesta etapa, configure as opções de instalação do pacote de aplicativos. As configurações aplicam-se a todos os aplicativos adicionados ao pacote.

1. No painel **Adicionar Aplicativo**, selecione **Configurações do Pacote de Aplicativos**.
2. No painel **Configurações do Pacote de Aplicativos**, faça o seguinte:
    - **Versão do Office**: escolha se você deseja atribuir a versão de 32 bits ou de 64 bits do Office. Você pode instalar a versão de 32 bits em dispositivos de 32 bits e 64 bits, mas você só pode instalar a versão de 64 bits em dispositivos de 64 bits.
    - **Canal de Atualização**: escolha como o Office é atualizado nos dispositivos. Para obter informações sobre os vários canais de atualização, consulte [Visão geral dos canais de atualização para Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Escolha:
        - **Mensalmente**
        - **Mensal (Direcionada)**
        - **Semestral**
        - **Semestral (Direcionada)**
    - **Aceitar automaticamente o contrato de licença de usuário final do aplicativo**: selecione essa opção se você não exigir que os usuários finais aceitem o contrato de licença. Com isso, o Intune aceitará automaticamente o contrato.
    - **Usar ativação do computador compartilhado**: selecione essa opção quando vários usuários compartilharem um computador. Para obter mais informações, confira Visão geral da ativação de computador compartilhado no Office 365.
    - **Idiomas**: o Office é instalado automaticamente em qualquer idioma com suporte instalado com o Windows no dispositivo do usuário final. Selecione essa opção se desejar instalar idiomas adicionais com o pacote de aplicativos.

>[!IMPORTANT]
> Depois de criar o pacote de aplicativos, você não poderá editar as propriedades dele. Para configurar propriedades diferentes, exclua o pacote de aplicativos e crie um novo.

## <a name="finish-up"></a>Concluir

Quando você terminar, no painel **Adicionar Aplicativo**, selecione **Adicionar**. O aplicativo criado é exibido na lista de aplicativos.

## <a name="errors-during-installation-of-the-app-suite"></a>Erros durante a instalação do pacote de aplicativos

A tabela a seguir lista os códigos de erro comuns que você pode encontrar e os respectivos significados.

### <a name="status-for-office-csp"></a>Status do CSP do Office

||||
|-|-|-|
|Status|Fase|Descrição|
|1460 (ERROR_TIMEOUT)|Baixar|Falha ao baixar a Ferramenta de Implantação do Office|    
|13 (ERROR_INVALID_DATA)|-|Não é possível verificar a assinatura da Ferramenta de Implantação do Office baixada|
|Código de erro de CertVerifyCertificateChainPolicy|-|Falha na verificação de certificação da Ferramenta de Implantação do Office baixada|    
|997|WIP|Instalando|
|0|Após a instalação|Instalação bem-sucedida|    
|1603 (ERROR_INSTALL_FAILURE)|-|Falha em qualquer verificação de pré-requisito, como:<ul><li>SxS (tentativa de instalação quando o MSI 2016 está instalado)</li><li>Incompatibilidade de versão</li><li>Outros</li></ul>|  
|0x8000ffff (E_UNEXPECTED)|-|Tentativa de desinstalação quando não há nenhum Clique para Executar do Office no computador|     
|17002|-|Falha ao concluir o cenário (instalar). Motivos possíveis:<ul><li>Instalação cancelada pelo usuário</li><li>Instalação cancelada por outra instalação</li><li>Espaço em disco esgotado durante a instalação</li><li>ID de idioma desconhecida</li></ul>|
|17004|-|SKUs desconhecidos|   


### <a name="office-deployment-tool-error-codes"></a>Códigos de erro da Ferramenta de Implantação do Office

|||||
|-|-|-|-|
|Cenário|Código de retorno|Interface do usuário|Observação|
|Esforço de desinstalação quando não há nenhuma instalação Clique para Executar ativa|– 2147418113, 0x8000ffff ou 2147549183|Código do erro: 30088-1008<br>Código do erro: 30125-1011 (404)|Ferramenta de Implantação do Office|
|Instalação quando há uma versão do MSI instalada|1603|-|Ferramenta de Implantação do Office|
|Instalação cancelada pelo usuário ou por outra instalação|17002|-|Clique para Executar|
|Tentativa de instalar 64 bits em um dispositivo com 32 bits instalados.|1603|-|Código de retorno da Ferramenta de Implantação do Office|
|Tentativa de instalar um SKU desconhecido (não é um caso de uso legítimo para o CSP do Office, já que devemos apenas passar em SKUs válidos)|17004|-|Clique para Executar|
|Falta de espaço|17002|-|Clique para Executar|
|Falha ao iniciar o cliente Clique para Executar (inesperada)|17000|-|Clique para Executar|
|Falha ao colocar na fila o cenário do cliente Clique para Executar (inesperada)|17001|-|Clique para Executar|

## <a name="next-steps"></a>Próximas etapas

- Para atribuir os aplicativos aos grupos que você escolher, consulte [Atribuir aplicativos a grupos](/intune-azure/manage-apps/deploy-apps).
