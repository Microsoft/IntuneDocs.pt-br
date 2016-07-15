---
title: Adicionar aplicativos a dispositivos registrados | Microsoft Intune
description: "Antes de implantar um aplicativo, você deve adicioná-lo ao Intune. Em seguida, ele está disponível no console do Intune, em que você pode implantá-lo e gerenciá-lo."
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5b1f1ae-f177-450a-9af9-936a02d052e3
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: 5140c4943be630ea8e48f80f7e6b590d223beac1
ms.openlocfilehash: 795843f012434e1a50cd6abab05b6af2c811cf3e


---

# Adicionar aplicativos para dispositivos registrados ao Intune

Antes de implantar ou gerenciar um aplicativo, você deve adicioná-lo ao Microsoft Intune. Este tópico mostra como adicionar aplicativos para dispositivos registrados.


> [!IMPORTANT]
> As informações neste tópico ajudam você a adicionar aplicativos que você deseja implantar nos dispositivos e computadores Windows registrados. Se você quiser adicionar aplicativos para computadores Windows gerenciados por você usando o software cliente o Intune, consulte [Add apps for Windows PCs in Microsoft Intune](add-apps-for-windows-pcs-in-microsoft-intune.md) (Adicionar aplicativos para computadores Windows no Microsoft Intune).

## Adicionar o aplicativo
Use o Intune Software Publisher para configurar as propriedades do aplicativo e, onde aplicável, carregá-lo no seu espaço de armazenamento em nuvem usando o seguinte procedimento:

1.  No [Console do administrador do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** &gt; **Adicionar Aplicativos** para iniciar o editor de software do Intune.

    > [!TIP]
    > Talvez seja necessário inserir seu nome de usuário e senha do Intune antes de iniciar o editor.

2.  Na página **Instalação de software**, o fornecedor de software, escolha uma das seguintes opções para **Selecionar como este software é disponibilizado para dispositivos**:
    - **Instalador de software**, para aplicativos com a extensão **.msi** ou **.exe**, especifique:
        - **Selecione o tipo de arquivo do instalador de software**: isso indica o tipo de software que você deseja implantar. Por exemplo, se você quiser instalar um aplicativo iOS, escolha **Pacote do Aplicativo para iOS (&#42;arquivo .ipa)**.
        - **Especifique o local dos arquivos de configuração do software**: insira o local dos arquivos de instalação ou escolha **Procurar** para selecionar o local em uma lista.
        - **Incluir arquivos e subpastas adicionais da mesma pasta**: apenas para o tipo de arquivo do **Windows Installer**.<br>Alguns softwares que usam o Windows Installer requerem arquivos de suporte, que geralmente se encontram na mesma pasta que os arquivos de instalação. Selecione esta opção se você também deseja implantar esses arquivos.<br>Esse tipo de instalação usa uma parte do seu espaço de armazenamento em nuvem.

  -   **Link externo**, para aplicativos que você deseja criar, especificando um link para uma loja de aplicativos, especifique:

        - **Especificar a URL**: especifique a URL em um dos seguintes formatos:
            - A URL da Windows Store do aplicativo que você deseja implantar. Por exemplo, se você quiser implantar o aplicativo Microsoft Remote Desktop para o Android, especifique **https://play.google.com/store/apps/details?id=com.microsoft.rdc.android**. Para localizar a URL do aplicativo, use um mecanismo de pesquisa para localizar a página da loja contendo o aplicativo. Por exemplo, para localizar o aplicativo Remote Desktop, você pode pesquisar **Microsoft Remote Desktop Android**.
            - Um site. O Intune implantará um ícone de atalho para o site para o dispositivo (conhecido como um clipe da web).
            - Um aplicativo na web. O Intune implantará um ícone de atalho para o aplicativo no dispositivo.
        - **É necessário um navegador gerenciado para abrir este link (somente Android e iOS)**: quando você implanta um link para um site ou aplicativo Web para os usuários, eles só poderão abri-lo no navegador gerenciado do Intune que deve estar instalado em seu dispositivo.<br>Para mais detalhes sobre o navegador gerenciado, consulte [Manage Internet access using managed browser policies with Microsoft Intune](manage-internet-access-using-managed-browser-policies.md) (Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune).<br>Esse tipo de instalação não usa porção nenhuma do seu espaço de armazenamento em nuvem.

  -   **Aplicativo iOS gerenciado da loja de aplicativos**, para aplicativos gratuitos da iTunes Store que você deseja gerenciar com políticas de MAM, especifique:

        - **Especificar a URL**: insira a URL da loja de aplicativos do aplicativo que você deseja implantar. Por exemplo, se você deseja implantar o aplicativo Pastas de Trabalho da Microsoft para iOS, especifique **https://itunes.apple.com/us/app/work-folders/id950878067?mt=8**.<br>Esse tipo de instalação não usa porção nenhuma do seu espaço de armazenamento em nuvem.

        Por exemplo, se você quiser implantar o aplicativo do Microsoft Word da iTunes Store para os dispositivos, a página terá esta aparência:
        
        ![Intune Software Publisher](./media/publisher-for-mobile.png)

3.  Na página **Descrição do Software**, defina as seguintes configurações:

    > [!TIP]
    > Dependendo do tipo de instalador que você está usando, talvez alguns desses valores tenham sido inseridos automaticamente.

    - **Editor**: insira o nome do editor do aplicativo.
    - **Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa.<br>Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Isso será exibido para os usuários no portal da empresa.
    - **URL para informações do software**: disponível somente se você tiver selecionado **Instalador do software**. Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **URL privada**: disponível somente se você tiver selecionado **Instalador do software**. Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **Categoria**: (opcional) selecione uma das categorias de aplicativo interno. Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.

    - **Exibir isso como um aplicativo em destaque e realçá-lo no portal da empresa**: exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **Ícone**: (opcional) carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.

        Neste exemplo, você configurou uma descrição para o aplicativo Microsoft Word para iOS:

        ![Exemplo de descrição do software](./media/ios-software-description.png)

4.  Na página **Requisitos**, selecione os requisitos que devem ser atendidos antes que o aplicativo possa começar a ser instalado em um dispositivo. Por exemplo, para um pacote de aplicativos para iOS, você pode selecionar a versão mínima do iOS necessária e o tipo de dispositivo, como um iPhone ou um iPad.

    > [!TIP]
    > A página **Requisitos** não é exibida para todos os tipos de aplicativos.

5.  Mais páginas do assistente são exibidas quando você escolhe o tipo de arquivo do **Windows Installer**. Esse tipo de arquivo é usado quando você implanta software em PCs que executam o Windows 10 ou posterior e que são registrados com o Intune.

6.  Na página **Resumo**, examine as informações especificadas por você. Quando estiver pronto, selecione **Carregar**.

7.  Selecione **Fechar** para concluir.

O aplicativo é exibido no nó **Aplicativos** do espaço de trabalho **Aplicativos**.

## Exemplos

### Implantando aplicativos MSI para dispositivos Windows 10
Neste vídeo de quatro minutos, você aprenderá como implantar aplicativos do Microsoft Installer (msi) para dispositivos registrados que executam o Windows 10.<br><br>

<iframe src="https://channel9.msdn.com/Series/How-to-Control-the-Uncontrolled/6--How-to-Deploy-MSI-Applications-to-Windows-10-Using-Intune-and-Mobile-Device-Management-MDM/player" width="640" height="360" allowFullScreen frameBorder="0"></iframe>

## Próximas etapas

Depois de criar um aplicativo, a próxima etapa é implantá-lo. Para saber mais, consulte [Deploy apps in Microsoft Intune](deploy-apps.md) (Implantar aplicativos no Microsoft Intune)






<!--HONumber=Jul16_HO2-->


