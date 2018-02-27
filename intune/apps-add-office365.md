---
title: "Instalar aplicativos do Office 365 em dispositivos móveis usando o Intune"
titlesuffix: Azure portal
description: "Saiba como você pode usar o Intune para facilitar a instalação dos aplicativos do Office 365 em dispositivos Windows 10."
keywords: 
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f6ef1d1dab39a6939b80bd13ba090424a67c6f53
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="how-to-assign-office-365-proplus-apps-to-windows-10-devices-with-microsoft-intune"></a>Como atribuir aplicativos do Office 365 ProPlus a dispositivos Windows 10 com o Microsoft Intune

Esse tipo de aplicativo facilita a atribuição de aplicativos do Office 365 ProPlus aos dispositivos gerenciados que executam o Windows 10. Você também poderá instalar aplicativos para o cliente de desktop Microsoft Project Online e para o Microsoft Visio Pro para Office 365 se tiver licenças para eles. Os aplicativos que você desejar serão exibidos como uma entrada única na lista de aplicativos no console do Intune.


## <a name="before-you-start"></a>Antes de começar

>[!IMPORTANT]
>Somente haverá suporte para este método de instalação do Office se nenhuma outra versão do Microsoft Office estiver instalada no dispositivo.

- Os dispositivos nos quais você implanta esses aplicativos deverão estar em execução no Windows 10 Creators Update ou posterior.
- O Intune é compatível somente com aplicativos do Office do pacote Office 365 ProPlus.
- Se algum aplicativo do Office estiver aberto quando o Intune instalar o pacote de aplicativos, a instalação poderá falhar e os usuários finais poderão perder dados de arquivos não salvos.
- Esse método de instalação não é compatível com dispositivos Windows 10S, Windows Home, Windows Team, Windows Holographic e Windows Holographic for Business.
- O Intune não dá suporte à instalação de aplicativos de área de trabalho do Office 365 da Microsoft Store (conhecidos como aplicativos Office Centennial) em um dispositivo no qual você já implantou aplicativos do Office 365 com o Intune. Se essa configuração for instalada, poderá ocorrer perda ou corrupção de dados.
- Várias atribuições de aplicativo requeridas ou disponíveis não são aditivas. Uma atribuição de aplicativo posterior substituirá as atribuições de aplicativo pré-instaladas. Por exemplo, se o primeiro conjunto de aplicativos do Office contém o Word e o seguinte não, o Word será desinstalado. Isso não se aplica a nenhum aplicativo do Visio ou Project.


## <a name="get-started"></a>Introdução

1.  Entre no portal do Azure.
2.  Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3.  Na folha **Intune**, escolha **Aplicativos móveis**.
4.  Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.
5.  Acima da lista de aplicativos, escolha **Adicionar**.
6.  Na folha **Adicionar Aplicativo**, escolha **Office 365 ProPlus Suite (Windows 10)**.

## <a name="configure-the-app-suite"></a>Configurar o pacote de aplicativos

Nesta etapa, escolha os aplicativos do Office que você deseja atribuir aos dispositivos.

1.  Na folha **Adicionar Aplicativo**, escolha **Configurar Pacote de Aplicativos**.
2.  Na folha **Configurar Pacote de Aplicativos**, escolha os aplicativos do Office padrão que você deseja atribuir aos dispositivos. Além disso, você poderá instalar aplicativos para o cliente de desktop Microsoft Project Online e para o Microsoft Visio Pro para Office 365 se tiver licenças para eles.
3.  Quando terminar, clique em **OK**.

>[!IMPORTANT]
> Depois de criar o pacote de aplicativos, você não poderá editar suas propriedades. Para configurar propriedades diferentes, exclua o pacote de aplicativos e crie um novo.

## <a name="configure-app-information"></a>Configurar informações do aplicativo

Nesta etapa, forneça informações sobre o pacote de aplicativos. Essas informações ajudam a identificá-lo no Intune, além de ajudar os usuários a encontrá-lo no aplicativo Portal da Empresa.

1.  Na folha **Adicionar Aplicativo**, escolha **Informações do Pacote de Aplicativos**.
2.  Na folha **Informações do Pacote de Aplicativos**, especifique as seguintes informações:
    - **Nome do Pacote** – insira o nome do pacote de aplicativos como ele é exibido no Portal da Empresa. Verifique se todos os nomes de pacotes de aplicativos usados são exclusivos. Se o mesmo nome de pacote de aplicativos for usado duas vezes, apenas um dos aplicativos será exibido aos usuários no Portal da Empresa.
    - **Descrição do Pacote** – insira uma descrição para o pacote de aplicativos. Por exemplo, você pode listar os aplicativos que você selecionou para serem incluídos.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Categoria** – como opção, selecione uma ou mais das categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do pacote de aplicativos pelos usuários quando navegam pelo Portal da Empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa** – exiba o pacote de aplicativos de forma proeminente na página principal do Portal da Empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Carregar Ícone** – carregue um ícone que será exibido com o aplicativo quando os usuários navegarem pelo Portal da Empresa.
3.  Quando terminar, clique em **OK**.

## <a name="configure-app-settings"></a>Definir configurações do aplicativo

Nesta etapa, configure as opções de instalação do pacote de aplicativos. As configurações aplicam-se a todos os aplicativos adicionados ao pacote.

1.  Na folha **Adicionar Aplicativo**, escolha **Configurações do Pacote de Aplicativos**.
2.  Na folha **Configurações do Pacote de Aplicativos**, especifique as seguintes informações:
    - **Versão do Office** – escolha se deseja atribuir a versão de 32 bits ou de 64 bits do Office. Você pode instalar a versão de 32 bits em dispositivos de 32 bits e de 64 bits, mas só é possível instalar a versão de 64 bits em dispositivos de 64 bits.
    - **Canal de Atualização** – escolha como o Office é atualizado nos dispositivos. Para obter informações sobre os diferentes canais de atualização, consulte Visão geral dos canais de atualização para Office 365 ProPlus. Escolha:
        - **Atual**
        - **Adiado**
        - **Primeira Versão Atual**
        - **Primeira Versão Adiada**
    - **Aceitar automaticamente o contrato de licença de usuário final do aplicativo** – selecione essa opção se você não exigir que os usuários finais aceitem o contrato de licença. Com isso, o Intune aceitará automaticamente o contrato.
    - **Usar ativação do computador compartilhado** – a ativação do computador compartilhado é usada quando vários usuários compartilham um computador. Para obter mais informações, consulte Visão geral da ativação de computador compartilhado do Office 365 ProPlus.
    - **Idiomas** – o Office é instalado automaticamente em qualquer idioma com suporte instalado com o Windows no dispositivo dos usuários finais. Selecione essa opção se desejar instalar idiomas adicionais com o pacote de aplicativos.

>[!IMPORTANT]
> Depois de criar o pacote de aplicativos, você não poderá editar suas propriedades. Para configurar propriedades diferentes, exclua o pacote de aplicativos e crie um novo.

## <a name="finish-up"></a>Concluir

Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**. O aplicativo que você criou é exibido na lista de aplicativos.

## <a name="error-codes-when-installing-the-app-suite"></a>Códigos de erro ao instalar o pacote de aplicativos

A tabela a seguir lista os códigos de erro comuns que você pode encontrar e seus significados.

### <a name="status-for-office-csp"></a>Status do CSP do Office:

||||
|-|-|-|
|Status|Fase|Descrição|
|1460 (ERROR_TIMEOUT)|Baixar|Falha ao baixar a Ferramenta de Implantação do Office|    
|13 (ERROR_INVALID_DATA)|-|Não é possível verificar a assinatura da Ferramenta de Implantação do Office baixada|
|Código de erro de CertVerifyCertificateChainPolicy|-|Falha na verificação de certificação da Ferramenta de Implantação do Office baixada|    
|997|WIP|Instalando|
|0|Após a instalação|Instalação bem-sucedida|    
|1603 (ERROR_INSTALL_FAILURE)|-|Falha em qualquer verificação de pré-requisito, como:<br>– SxS (tentativa de instalação quando o 2016 MSI está instalado)<br>– incompatibilidade de versão<br>– etc.|     
|0x8000ffff (E_UNEXPECTED)|-|Tentativa de desinstalação quando não há nenhum Clique para Executar do Office no computador.|    
|17002|-|Falha ao concluir o cenário (instalar). Motivos possíveis:<br>– Instalação cancelada pelo usuário<br>– Instalação cancelada por outra instalação<br>– Espaço em disco esgotado durante a instalação<br>– ID de idioma desconhecida|
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

Agora você pode atribuir os aplicativos aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](/intune-azure/manage-apps/deploy-apps).
