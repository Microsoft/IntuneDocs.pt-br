---
title: Como adicionar aplicativos da Windows Store ao Microsoft Intune
titleSuffix: 
description: Saiba como adicionar aplicativos da Windows Store ao Microsoft Intune.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 815f780ef9f04870f19e75481ed74f0a1c3601f3
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Como adicionar aplicativos da Windows Store ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Antes que possa atribuir, monitorar, configurar ou proteger aplicativos, você precisa adicioná-los ao Intune. As etapas a seguir permitem que você adicione um aplicativo da Windows Store ao Microsoft Intune.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Aplicativos** na seção **Gerenciar**.
5. Escolha **Adicionar** acima da lista.
6. Selecione **Windows** dos tipos de **Loja de aplicativo** disponíveis na lista.
7. Escolha **Informações do aplicativo** para configurar as informações do aplicativo.
8. Na folha **Informações do aplicativo**, configure as seguintes informações: dependendo do aplicativo que você escolheu, alguns dos valores neste painel podem ser preenchidos automaticamente:
    - **Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Essa descrição será exibida para os usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos** – insira a URL da loja de aplicativos do aplicativo que você deseja criar. 
    - **Categoria** (opcional) – Selecione uma das categorias de aplicativo ou uma categoria criada por você. A adição dessa informação facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** (opcional) – insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **URL privada** (opcional) – insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **Desenvolvedor** (opcional) – insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** (opcional) – insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** (opcional) – insira as observações que você deseja associar a este aplicativo.
    - **Carregar Ícone** – Carregue um ícone que será associado ao aplicativo. Esse ícone será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
1. Clique em **OK** depois de inserir todas as informações necessárias do aplicativo.
2. Clique em **Adicionar**, na folha **Adicionar aplicativo**.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

## <a name="manually-assign-windows-10-company-portal-app"></a>Atribuir manualmente o aplicativo Portal da Empresa para Windows 10
Os usuários finais podem instalar o aplicativo do Portal da Empresa da Microsoft Store para gerenciar dispositivos e instalar aplicativos. No entanto, se a empresa precisar que você atribua o aplicativo do Portal da Empresa, é possível atribuir manualmente o aplicativo do Portal de Empresa do Windows 10 diretamente do Intune, mesmo se você ainda não tiver integrado o Intune com a Microsoft Store para Empresas.

 > [!NOTE]
 > Essa opção exigirá a atribuição manual das atualizações sempre que uma atualização do aplicativo for lançada.

1. Faça logon na sua conta da [Microsoft Store para Empresas](https://www.microsoft.com/business-store) e adquira a versão do aplicativo Portal da Empresa com **licença offline**.  
2. Assim que o aplicativo for adquirido, selecione-o na página **Inventário**.  
3. Selecione **Todos os dispositivos do Windows 10** como a **Plataforma**, em seguida, a devida **Arquitetura** e baixe. Um arquivo de licença do aplicativo não é necessário para este aplicativo.

    ![Imagem de todos os dispositivos Windows 10 e detalhes do Pacote de Arquitetura X86 para Download](./media/Win10CP-all-devices.png)

4. Baixe todos os pacotes em "Estruturas Necessárias". Isto deve ser feito para as arquiteturas do x86, x64 e ARM – resultando em um total de nove pacotes, como mostrado abaixo.

    ![Imagem dos arquivos de dependência para Download](./media/Win10CP-dependent-files.png)

5. Antes de carregar o aplicativo Portal da Empresa no Intune, crie uma pasta (por exemplo: C:&#92;Portal da Empresa) com os pacotes estruturados da seguinte maneira:
  - Coloque o pacote Portal da Empresa em C:\Portal da Empresa. Crie uma subpasta Dependências nesse local também.  
  
    ![Imagem da pasta Dependências salva com o arquivo APPXBUN](./media/Win10CP-Dependencies-save.png)

  - Coloque os nove pacotes de dependências na pasta Dependências. Se as dependências não forem colocadas nesse formato, o Intune não conseguirá reconhecê-las e carregá-las durante o upload do pacote, fazendo com que ocorra uma falha com o seguinte erro: 

      ![A dependência de aplicativo do Windows para este instalador do software não foi encontrada na pasta do aplicativo. Você pode continuar a criar e atribuir esse aplicativo, mas ele não será executado até que a dependência ausente do aplicativo do Windows seja fornecida.](./media/Win10CP-error-message.png)

6. Retorne ao Intune, em seguida, carregue o aplicativo Portal da Empresa como um novo aplicativo. Atribua-o como um aplicativo necessário para o conjunto de usuários de destino desejado.  

Consulte [Implantando um appxbundle com dependências via MDM do Microsoft Intune ](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) para obter mais informações sobre como o Intune lida com as dependências para os aplicativos Universal.  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Como atualizo o Portal da Empresa nos dispositivos de meus usuários se eles já instalaram os aplicativos mais antigos na loja?
Se os usuários já instalaram os aplicativos Portal da Empresa para Windows 8.1 ou Windows Phone 8.1 na Store, então, eles deverão ser atualizados automaticamente para a nova versão sem nenhuma ação necessária tomada por você ou seu usuário. Se a atualização não acontecer, peça aos usuários que verifiquem se eles ativaram as atualizações automáticas dos aplicativos da Store em seus dispositivos.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Como atualizo meu aplicativo Portal da Empresa para Windows 8.1 carregado para o aplicativo Portal da Empresa para Windows 10?
Nosso caminho de migração recomendado é excluir a atribuição do aplicativo Portal da Empresa para Windows 8.1 definindo a ação de atribuição como "Desinstalar". Depois que essa configuração for feita, o aplicativo Portal da Empresa do Windows 10 poderá ser atribuído usando qualquer uma das opções acima.  

Se você precisar carregar o aplicativo e atribuiu o Portal da Empresa para Windows 8.1 sem assiná-lo com o Certificado da Symantec, siga as etapas em Atribuir diretamente por meio da seção Intune acima para concluir a atualização.

Se você precisar carregar o aplicativo, assinou e atribuiu o Portal da Empresa para Windows 8.1 com o certificado de assinatura de código da Symantec, siga as etapas na seção abaixo.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Como atualizo meu aplicativo Portal da Empresa para Windows Phone 8.1 ou o aplicativo Portal da Empresa para Windows 8.1 carregado para o aplicativo Portal da Empresa para Windows 10?
Nosso caminho de migração recomendado é excluir a atribuição existente do aplicativo Portal da Empresa para Windows Phone 8.1 ou do aplicativo Portal da Empresa para Windows 8.1 definindo a ação de atribuição como "Desinstalar". Depois que essa configuração for feita, o aplicativo Portal da Empresa do Windows 10 poderá ser atribuído normalmente.  

Caso contrário, o aplicativo Portal da Empresa para Windows 10 precisará ser atualizado e assinado devidamente para garantir que o caminho de atualização seja respeitado.  

Se o aplicativo Portal da Empresa para Windows 10 for assinado e atribuído dessa forma, você precisará repetir o processo para cada nova atualização do aplicativo quando ela ficar disponível na loja. O aplicativo não será atualizado automaticamente quando a loja for atualizada.  

Veja como assinar e atribuir o aplicativo desta forma:

1. Baixe o Aplicativo Portal da Empresa para Windows 10 do Microsoft Intune Assinando o Script em [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Esse script requer o SDK do Windows para o Windows 10 ser instalado no computador host. Para baixar o SDK do Windows para o Windows 10, visite [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Baixe o aplicativo Portal da Empresa para Windows 10 na Microsoft Store para Empresas, como descrito acima.  
3. Execute o script com os parâmetros de entrada detalhados no cabeçalho do script para assinar o aplicativo Portal da Empresa para Windows 10 (extraído abaixo). As dependências não precisam ser passada para o script. Só são necessárias quando o aplicativo está sendo carregado para o Console de Administração do Intune.

|Parâmetro | Descrição|
| ------------- | ------------- |
|InputWin10AppxBundle |O caminho para onde está localizado o arquivo de origem appxbundle |
|OutputWin10AppxBundle |O caminho de saída para o arquivo assinado appxbundle.  Win81Appx O caminho para onde o arquivo do Portal da Empresa para Windows 8.1 ou Windows Phone 8.1 (.APPX) está localizado.|
|PfxFilePath |O caminho para o arquivo do Certificado de Autenticação do Código do Symantec Enterprise Mobile (.PFX). |
|PfxPassword| A senha do Certificado de Autenticação do Código do Symantec Enterprise Mobile. |
|PublisherId |A ID do Editor da empresa. Se ausente, o campo 'Assunto' da Symantec Enterprise Mobile Code Signing Certificate será usado.|
|SdkPath | O caminho para a pasta-raiz do SDK do Windows para o Windows 10. Esse argumento é opcional e o padrão é ${env:ProgramFiles(x86)}\Windows Kits\10|
O script produzirá a versão assinada do aplicativo Portal da Empresa para Windows 10 quando terminar a execução. Você pode atribuir a versão assinada do aplicativo como um aplicativo LOB via Intune, que atualizará as versões atualmente atribuídas para esse novo aplicativo.  
