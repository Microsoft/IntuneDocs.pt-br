---
title: Adicionar aplicativos a computadores Windows que executam o cliente de software do Intune
titleSuffix: Microsoft Intune
description: Use as informações neste tópico para aprender a adicionar aplicativos para computadores Windows ao Intune antes de implantá-los.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/29/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: e4f6a8c3e460e9806aabadd710ec102aa77d44ab
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798886"
---
# <a name="add-apps-for-windows-pcs-that-run-the-intune-software-client"></a>Adicionar aplicativos a computadores Windows que executam o cliente de software do Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Use as informações neste tópico para aprender a adicionar aplicativos ao Intune antes de implantá-los.

> [!IMPORTANT]
> As informações neste tópico ajudam a adicionar aplicativos a computadores Windows que você gerencia usando o cliente de software do Intune. Caso deseje adicionar aplicativos a computadores Windows registrados e outros dispositivos móveis, confira [Adicionar aplicativos ao Microsoft Intune](apps-add.md).

Para instalar aplicativos em PCs, eles devem ser capazes de serem instalados silenciosamente, sem interação do usuário. Se esse não for o caso, a instalação falhará.

## <a name="additional-security-settings-for-windows-installer"></a>Configurações de segurança adicionais do Windows Installer
Você pode permitir que os usuários controlem as instalações de aplicativos. Se habilitadas, as instalações que, de outra forma, poderiam ser interrompidas devido a uma violação de segurança teriam permissão para continuar. Você pode direcionar o Windows Installer para usar permissões elevadas quando ele instalar algum programa em um sistema. Além disso, você pode habilitar itens de WIP (Proteção de Informações do Windows) a serem indexados e os metadados sobre eles armazenados em um local não criptografado. Quando a política é desabilitada, os itens protegidos pela WIP não são indexados e não aparecem nos resultados na Cortana ou no Explorador de Arquivos. A funcionalidade para essas opções está desabilitada por padrão. 

## <a name="add-the-app"></a>Adicionar o aplicativo
Você usa o Intune Software Publisher para configurar as propriedades do aplicativo e carregá-lo no seu espaço de armazenamento em nuvem usando o seguinte procedimento:

1. No [Console do administrador do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** &gt; **Adicionar Aplicativos** para iniciar o Intune Software Publisher.

   > [!TIP]
   > Talvez seja necessário inserir seu nome de usuário e senha do Intune antes de iniciar o editor.

2. Na página **Instalação de software** do editor, em **Selecionar como este software é disponibilizado para dispositivos**, selecione **Instalador do software** e especifique:

   - **Selecione o tipo de arquivo do instalador do software**. Isso indica o tipo de software que você deseja implantar. Para um computador Windows, escolha **Windows Installer**.
   - **Especifique o local dos arquivos de instalação do software**. Insira o local dos arquivos de instalação, ou escolha **Procurar** para selecionar o local em uma lista.
   - **Incluir arquivos e subpastas adicionais da mesma pasta**. Alguns softwares que usam o Windows Installer precisam de arquivos de suporte. Eles devem ser localizados na mesma pasta que o arquivo de instalação. Selecione esta opção se você também deseja implantar esses arquivos de suporte.

   Por exemplo, se você quiser publicar um aplicativo chamado Application.msi no Intune, a página terá esta aparência: ![Página de instalação de software do editor](media/publisher-for-pc.png)

   Esse tipo de instalação usa uma parte do seu espaço de armazenamento em nuvem.

3. Na página **Descrição do Software**, defina as seguintes configurações.

   > [!NOTE]
   > Dependendo do arquivo instalador que você está usando, talvez alguns desses valores tenham sido inseridos automaticamente ou não apareçam.

   - **Editor**. Insira o nome do editor do aplicativo.
   - **Nome**. Insira o nome do aplicativo como ele será exibido no portal da empresa.<br />Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
   - **Descrição**. Insira uma descrição para o aplicativo. Isso será exibido para os usuários no portal da empresa.
   - **URL para informações do software** (opcional). Insira uma URL de um site que contém informações sobre esse aplicativo. A URL será exibida para os usuários no portal da empresa.
   - **URL de privacidade** (opcional). Insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida para os usuários no portal da empresa.
   - **Categoria** (opcional). Selecione uma das categorias de aplicativo interno. Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.

   - **Ícone** (opcional). Carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.

4. Na página **Requisitos**, selecione os requisitos que devem ser atendidos antes que o aplicativo possa ser instalado. Escolha:

   - **Arquitetura**. Selecione se esse aplicativo pode ser instalado em sistemas operacionais de 32 bits, 64 bits ou ambos.
   - **Sistema operacional**. Selecione o sistema operacional mínimo em que esse aplicativo pode ser instalado.

5. Na página **Regras de detecção**, você pode configurar regras para detectar se o aplicativo que você está configurando já está instalado em um PC. Ou você pode usar as regras de detecção padrão para substituir automaticamente todas as versões anteriores do aplicativo. Essa opção é para o Windows Installer (somente arquivos .exe).

   As regras que você pode configurar são:
   - **Arquivo existente**. Especifique o caminho para o arquivo que deseja detectar. Você pode pesquisar em **%ProgramFiles%** (que procura em **Arquivos de Programas**\&lt;path&gt; e **Arquivos de Programas (x86)**\&lt;path&gt;) no PC ou **%SystemDrive%** (que pesquisa da unidade raiz do PC, geralmente, a unidade C).
   - **Código de produto MSI existente**. Escolha **Procurar** para escolher o arquivo do Windows Installer (msi) que você deseja detectar.
   - <strong>Chave do Registro existente</strong>. Especifique uma chave do Registro que comece com <strong>HKEY_LOCAL_MACHINE\</strong>. Os caminhos do Registro de 32 e 64 bits são pesquisados. Se a chave especificada existe em um dos locais, a regra de detecção é satisfeita.

   Se o aplicativo satisfizer alguma das regras que você configurou, ele não será instalado.

6. Somente para o tipo de arquivo do **Windows Installer** (.msi e .exe): na página **Argumentos de linha de comando**, escolha se deseja fornecer argumentos de linha de comando opcionais para o instalador.
   Os seguintes parâmetros são adicionados automaticamente pelo Intune:
   - Para arquivos .exe, **/install** é adicionado.
   - Para arquivos .msi, **/quiet** é adicionado.
   Observe que essas opções só funcionarão se o criador do pacote do aplicativo tiver habilitado a funcionalidade para tal.

7. Somente para o tipo de arquivo do **Windows Installer** (exe apenas): na página **Códigos de retorno**, você pode adicionar novos códigos de erro que são interpretados pelo Intune quando o aplicativo é instalado em um computador Windows gerenciado.

   Por padrão, o Intune usa códigos de retorno padrão do setor para reportar a falha ou o êxito da instalação de um pacote do aplicativo: **0** (Êxito) ou **3010** (Êxito com reinicialização). Você também pode adicionar seus próprios códigos de retorno a essa lista. Se você especificar uma lista de códigos de retorno e a instalação do aplicativo retornar um código não contido na lista, ele será interpretado como uma falha.

8. Na página **Resumo**, examine as informações especificadas por você. Quando estiver pronto, selecione **Carregar**.

9. Selecione **Fechar** para concluir.

O aplicativo é exibido no nó **Aplicativos** do workspace **Aplicativos**.

## <a name="next-steps"></a>Próximas etapas

Depois de criar um aplicativo, a próxima etapa é implantá-lo. Para saber mais, confira [Atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

Se você quiser ler mais informações sobre dicas e truques para implantar o software em PCs Windows, consulte o postagem no blog [Dica de suporte: práticas recomendadas para distribuição de Software do Intune para PCs](https://blogs.technet.microsoft.com/intunesupport/2016/06/13/support-tip-best-practices-for-intune-software-distribution-to-pcs/).
