---
title: Adicionar manualmente o aplicativo Portal da Empresa ao Windows 10
titleSuffix: Microsoft Intune
description: Saiba como sua força de trabalho pode adicionar manualmente o aplicativo Portal da Empresa do Windows 10 aos seus PCs na Microsoft Store.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d6f148c98c31f53626d78a91aacedb4c92571109
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851642"
---
# <a name="manually-add-the-windows-10-company-portal-app-by-using-microsoft-intune"></a>Adicionar manualmente o aplicativo do Portal da Empresa ao Windows 10 usando o Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Para gerenciar dispositivos e instalar aplicativos, os usuários podem instalar o aplicativo do Portal da Empresa da Microsoft Store. No entanto, se a empresa precisar que você atribua o aplicativo de Portal da empresa, você poderá atribuir manualmente o aplicativo de Portal da Empresa do Windows 10 diretamente do Intune. Você pode fazer isso mesmo se ainda não tiver integrado o Intune com o Microsoft Store para Empresas.

 > [!NOTE]
 > A opção descrita neste artigo requer que você atribua atualizações manuais sempre que uma atualização de aplicativo for liberada.

## <a name="configure-settings-to-show-offline-apps"></a>Definir configurações para mostrar os aplicativos offline
1. Conecte-se ao [Microsoft Store para Empresas](https://www.microsoft.com/business-store) com sua conta do administrador.
2. Selecione a guia **Gerenciar** na parte superior da janela.
3. No painel esquerdo, selecione **Configurações**.
4. Defina **Mostrar aplicativos offline**, em **Experiência de compra**, para **Ativado**.  
    Os aplicativos licenciados offline são exibidos.

## <a name="download-the-offline-company-portal-app"></a>Baixe o aplicativo Portal da Empresa offline
1. Pesquise e selecione o aplicativo **Portal da Empresa**.
2. Defina o **Tipo de licença** como **Offline**.
3. Selecione **Obter o aplicativo** para adquirir e adicionar o aplicativo do Portal da Empresa offline ao seu inventário.
4. Selecione **Gerenciar** na página do aplicativo **Portal da Empresa**.
5. Selecione **Todos os dispositivos do Windows 10** como a **Plataforma** e selecione os devidos valores de **Versão mínima**, **Arquitetura** e **Baixar metadados do aplicativo**. 
6. Selecione **Baixar** para salvar o arquivo em seu computador local.

    ![Os dispositivos Windows 10 nos quais a arquitetura é igual a x86 estão selecionados](./media/Win10CP-all-devices.png)

7. Baixe todos os pacotes em "Estruturas Necessárias" ao selecionar **Download**.  
    Essa ação deve ser concluída para as arquiteturas x86, x64 e ARM, resultando em um total de 12 pacotes.
8. Antes de carregar o aplicativo do Portal da Empresa no Intune, crie uma pasta (por exemplo: C:\Portal da Empresa) com os pacotes estruturados da seguinte maneira:
   - Coloque o pacote Portal da Empresa em C:\Portal da Empresa. Crie uma subpasta *Dependências* nesse local também.  

     ![Pasta Dependências salva com o arquivo APPXBUN](./media/Win10CP-Dependencies-save.png)

   - Coloque os pacotes de dependências na pasta *Dependências*. 

     > [!NOTE]
     > Se as dependências não forem colocadas no formato correto, o Intune não reconhecerá e carregará os arquivos durante o upload do pacote, causando uma falha de upload e exibindo o erro a seguir.

9. No Microsoft Intune no Portal do Azure, carregue o aplicativo de Portal da Empresa como um novo aplicativo. 
10. Atribua o aplicativo do Portal da Empresa como um aplicativo necessário para o conjunto de usuários de destino selecionado.  

Para obter mais informações sobre como o Intune lida com as dependências para os aplicativos Universal, veja [Implantando um appxbundle com dependências via MDM do Microsoft Intune](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

## <a name="frequently-asked-questions"></a>Perguntas frequentes 
### <a name="how-do-i-update-the-company-portal-app-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Como atualizo o aplicativo do Portal da Empresa nos dispositivos de meus usuários se eles já instalaram os aplicativos mais antigos da loja?
Se os usuários já instalaram os aplicativos Portal da Empresa para Windows 8.1 ou Windows Phone 8.1 na Microsoft Store, eles deverão ser atualizados automaticamente para a versão mais recente sem nenhuma ação necessária tomada por você ou seus usuários. Se a atualização não acontecer, peça aos usuários que verifiquem se eles habilitaram as atualizações automáticas dos aplicativos da Store em seus dispositivos.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Como atualizo meu aplicativo Portal da Empresa para Windows 8.1 carregado para o aplicativo Portal da Empresa para Windows 10?
Nosso caminho de migração recomendado é excluir a atribuição do aplicativo do Portal da Empresa para Windows 8.1 definindo a ação de atribuição como **Desinstalar**. Depois de selecionar essa configuração, você poderá atribuir o aplicativo do Portal da Empresa do Windows 10 usando qualquer uma das opções discutidas anteriormente.  

Se precisar executar sideload do aplicativo e tiver atribuído o Portal da Empresa para Windows 8.1 sem assiná-lo com o Certificado da Symantec, siga as etapas nas seções anteriores desse artigo para concluir a atualização.

Se precisar executar sideload do aplicativo e tiver assinado e atribuído o aplicativo Portal da Empresa para Windows 8.1 com o certificado de assinatura de código da Symantec, siga as etapas na seção abaixo.

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Como atualizo meu aplicativo Portal da Empresa para Windows Phone 8.1 ou o aplicativo Portal da Empresa para Windows 8.1 carregado para o aplicativo Portal da Empresa para Windows 10?
Nosso caminho de migração recomendado é excluir a atribuição existente do aplicativo do Portal da Empresa para Windows Phone 8.1 ou do aplicativo do Portal da Empresa para Windows 8.1 definindo a ação de atribuição como **Desinstalar**. Depois de selecionar essa configuração, você poderá atribuir o aplicativo do Portal da Empresa do Windows 10 normalmente.  

Caso contrário, o aplicativo do Portal da Empresa para Windows 10 precisará ser atualizado e assinado devidamente para garantir que o caminho de atualização seja respeitado.  

Se atribuiu e assinou o aplicativo do Portal da Empresa para Windows 10 dessa forma, você precisará repetir o processo para cada nova atualização do aplicativo quando ela ficar disponível na loja. O aplicativo não será atualizado automaticamente quando a loja for atualizada.  

Veja como assinar e atribuir o aplicativo desta forma:

1. Baixe o [aplicativo do Portal da Empresa para Windows 10 do Microsoft Intune assinando o script](https://aka.ms/win10cpscript).  
    Esse script requer o SDK do Windows para o Windows 10 ser instalado no computador host. [Baixar o SDK do Windows para Windows 10](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Baixe o aplicativo do Portal da Empresa para Windows 10 na Microsoft Store para Empresas, como descrito acima.  
3. Para assinar o aplicativo do Portal da Empresa para Windows 10, execute o script com os parâmetros de entrada detalhados no cabeçalho do script, conforme mostrado na tabela a seguir.  
    As dependências não precisam ser passada para o script. Só são necessárias quando o aplicativo está sendo carregado para o Console de Administração do Intune.

| Parâmetro |  Descrição  |
|---|---|
| InputWin10AppxBundle  |  O caminho para o arquivo appxbundle de origem. |
| OutputWin10AppxBundle | O caminho de saída para o arquivo assinado appxbundle. 
| Win81Appx  | O caminho para o arquivo do Portal da Empresa para Windows 8.1 ou Windows Phone 8.1 (.APPX). |
| PfxFilePath  |  O caminho para o arquivo do Certificado de Autenticação do Código do Symantec Enterprise Mobile (.PFX).  |
| PfxPassword  | A senha do Certificado de Autenticação do Código do Symantec Enterprise Mobile. |
| PublisherId | A ID do Editor da empresa. Se ausente, o campo Assunto do Certificado de Autenticação do Código do Symantec Enterprise Mobile será usado. |
| SdkPath | O caminho para a pasta-raiz do SDK do Windows para o Windows 10. Esse argumento é opcional e o padrão é ${env:ProgramFiles(x86)}\Windows Kits\10.  |

Quando o script terminar a execução, ele produzirá a versão assinada do aplicativo do Portal da Empresa para Windows 10. Você pode atribuir a versão assinada do aplicativo como um aplicativo LOB (linha de negócios) via Intune, que atualizará as versões atualmente atribuídas para esse novo aplicativo.  

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)

