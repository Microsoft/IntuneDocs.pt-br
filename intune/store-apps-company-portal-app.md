---
title: Adicionar manualmente o aplicativo Portal da Empresa ao Windows 10
titleSuffix: Microsoft Intune
description: Saiba como adicionar manualmente o aplicativo Portal da Empresa ao Windows 10.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 06ed9395d06e2d64edcedcaadfe819ad03f1d495
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2018
---
# <a name="manually-add-the-windows-10-company-portal-app-using-microsoft-intune"></a>Adicionar manualmente o aplicativo Portal da Empresa ao Windows 10 usando o Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Os usuários finais podem instalar o aplicativo do Portal da Empresa da Microsoft Store para gerenciar dispositivos e instalar aplicativos. No entanto, se a empresa precisar que você atribua o aplicativo do Portal da Empresa, é possível atribuir manualmente o aplicativo do Portal de Empresa do Windows 10 diretamente do Intune, mesmo se você ainda não tiver integrado o Intune com a Microsoft Store para Empresas.

 > [!NOTE]
 > Essa opção exigirá a atribuição manual das atualizações sempre que uma atualização do aplicativo for lançada.

## <a name="configure-settings-to-show-offline-apps"></a>Definir configurações para mostrar os aplicativos offline
1. Acesse a [Microsoft Store para Empresas](https://www.microsoft.com/business-store) e verifique se você está conectado com sua conta do administrador.
2. Selecione a guia **Gerenciar** na parte superior da janela.
3. Selecione **Configurações** na coluna de navegação à esquerda.
4. Definir **Mostrar aplicativos offline** na seção **Experiência de compra** para **Ativado**. Isso mostrará aplicativos licenciados offline na Microsoft Store for Business.

## <a name="download-the-offline-company-portal-app"></a>Baixe o aplicativo Portal da Empresa offline
1. Pesquisar e selecionar o aplicativo **Portal da empresa**.
2. Defina o **Tipo de licença** como **Offline**.
3. Clique em **Obter o aplicativo** para adquirir e adicionar o aplicativo Portal da Empresa offline ao seu inventário.
4. Clique em **Gerenciar** na página do aplicativo **Portal da empresa**.
5. Selecione **Todos os dispositivos do Windows 10** como a **Plataforma** e, em seguida, selecione os devidos valores de **Versão mínima**, **Arquitetura** e Baixar metadados do aplicativo**. 
6. Clique em **Baixar** para salvar o arquivo em seu computador local.

    ![Imagem de todos os dispositivos Windows 10 e detalhes do Pacote de Arquitetura X86 para Download](./media/Win10CP-all-devices.png)

7. Baixe todos os pacotes em "Estruturas Necessárias". Isto precisa ser feito para as arquiteturas x86, x64 e ARM – resultando em um total de 12 pacotes.
8. Antes de carregar o aplicativo Portal da Empresa no Intune, crie uma pasta (por exemplo: C:&#92;Portal da Empresa) com os pacotes estruturados da seguinte maneira:
  - Coloque o pacote Portal da Empresa em C:\Portal da Empresa. Crie uma subpasta Dependências nesse local também.  

    ![Imagem da pasta Dependências salva com o arquivo APPXBUN](./media/Win10CP-Dependencies-save.png)

  - Coloque os pacotes de dependências na pasta *Dependências*. 

     > [!NOTE]
     > Se as dependências não forem colocadas no formato correto, o Intune não conseguirá reconhecer e carregar os arquivos durante o upload do pacote, causando uma falha de upload e exibindo o erro a seguir.

9. Volte para o Microsoft Intune no Portal do Azure.
10. Carregue o aplicativo do Portal da Empresa como um novo aplicativo. Atribua-o como um aplicativo necessário para o conjunto de usuários de destino desejado.  

Consulte [Implantando um appxbundle com dependências via MDM do Microsoft Intune ](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) para obter mais informações sobre como o Intune lida com as dependências para os aplicativos Universal.  

## <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Como atualizo o Portal da Empresa nos dispositivos de meus usuários se eles já instalaram os aplicativos mais antigos na loja?
Se os usuários já instalaram os aplicativos Portal da Empresa para Windows 8.1 ou Windows Phone 8.1 na Store, então, eles deverão ser atualizados automaticamente para a nova versão sem nenhuma ação necessária tomada por você ou seu usuário. Se a atualização não acontecer, peça aos usuários que verifiquem se eles ativaram as atualizações automáticas dos aplicativos da Store em seus dispositivos.   

## <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Como atualizo meu aplicativo Portal da Empresa para Windows 8.1 carregado para o aplicativo Portal da Empresa para Windows 10?
Nosso caminho de migração recomendado é excluir a atribuição do aplicativo Portal da Empresa para Windows 8.1 definindo a ação de atribuição como “Desinstalar”. Depois que essa configuração for feita, o aplicativo Portal da Empresa do Windows 10 poderá ser atribuído usando qualquer uma das opções acima.  

Se você precisar carregar o aplicativo e atribuiu o Portal da Empresa para Windows 8.1 sem assiná-lo com o Certificado da Symantec, siga as etapas em Atribuir diretamente por meio da seção Intune acima para concluir a atualização.

Se você precisar carregar o aplicativo, assinou e atribuiu o Portal da Empresa para Windows 8.1 com o certificado de assinatura de código da Symantec, siga as etapas na seção abaixo.  

## <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Como atualizo meu aplicativo Portal da Empresa para Windows Phone 8.1 ou o aplicativo Portal da Empresa para Windows 8.1 carregado para o aplicativo Portal da Empresa para Windows 10?
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

## <a name="next-steps"></a>Próximas etapas

- [Como atribuir aplicativos aos grupos](apps-deploy.md)

