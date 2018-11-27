---
title: Atualizar ou usar o modo S em dispositivos Windows 10 com o Microsoft Intune – Azure | Microsoft Docs
description: Crie um perfil de dispositivo no Microsoft Intune para atualizar dispositivos Windows 10 para edições diferentes. Por exemplo, você pode atualizar do Windows 10 Professional para o Windows 10 Enterprise. Você também pode habilitar ou sair do modo S em um dispositivo usando o perfil de configuração. Consulte também os caminhos de atualização de software para o Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic e Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: eb44647e50e406b9ef5052c576660c9b7eebf6dd
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189751"
---
# <a name="use-a-configuration-profile-to-upgrade-windows-10-or-switch-from-s-mode-in-intune"></a>Use um perfil de configuração para atualizar o Windows 10, ou sair do modo S no Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Configure um perfil de atualização no Intune para fazer atualização automaticamente dos dispositivos que executam o Windows 10 para uma edição diferente. Consulte também os caminhos de atualização com suporte.

## <a name="before-you-begin"></a>Antes de começar
Antes de atualizar os dispositivos para a versão mais recente, você precisa dos seguintes pré-requisitos:

- Uma chave do produto (Product Key) válida para instalar a versão atualizada do Windows em todos os dispositivos de destino com a política (para edições do Windows 10 Desktop). Você pode usar chaves MAK (Chaves de Ativação Múltipla) ou KMS (Servidor de Gerenciamento de Chaves). Para as edições Windows 10 Mobile e Windows 10 Holographic, você pode usar um arquivo de licença da Microsoft que inclua as informações de licenciamento para instalar a versão atualizada do Windows em todos os dispositivos de destino com a política.
- Os dispositivos Windows 10 aos quais você atribuir a política são registrados no Microsoft Intune. Você não pode usar a política de atualização de edição com computadores que executam o software cliente do Intune PC.

## <a name="supported-upgrade-paths"></a>Caminhos de atualização com suporte
A tabela a seguir lista os caminhos de atualização com suporte para o perfil de atualização de edição do Windows 10.

| Atualizar a partir do | Fazer upgrade para |
|---|---|
| Windows 10 Pro | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education |
| Edição Windows 10 Pro N | Windows 10 Education N edition <br/>Edição Windows 10 Enterprise N <br/>Edição Windows 10 Pro Education N | 
| Windows 10 Pro Education | Windows 10 Education | 
| Edição Windows 10 Pro Education N | Windows 10 Education N edition |
| Windows 10 Cloud | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro <br/>Windows 10 Pro Education | 
| Edição Windows 10 Cloud N | Windows 10 Education N edition <br/>Edição Windows 10 Enterprise N <br/>Edição Windows 10 Pro N <br/>Edição Windows 10 Pro Education N | 
| Windows 10 Enterprise | Windows 10 Education | 
| Edição Windows 10 Enterprise N | Windows 10 Education N edition | 
| Windows 10 Core | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education | 
| Edição Windows 10 Core N | Windows 10 Education N edition <br/>Edição Windows 10 Enterprise N <br/>Edição Windows 10 Pro Education N | 
| Windows 10 Holographic | Windows 10 Holographic for Business |
| Windows 10 Mobile | Windows 10 Mobile Enterprise |


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="upgrade-the-edition"></a>Atualizar a edição

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.
3. Digite um **Nome** e uma **Descrição** para o perfil. Por exemplo, insira algo como `Windows 10 edition upgrade`
4. Em **Plataforma**, selecione **Windows 10 e posteriores**.
5. Para **Tipo de perfil**, selecione **Atualização da edição**.
6. Nas propriedades **Atualização de Edição**, insira as seguintes configurações:

   - **Edição para a qual atualizar**: selecione a edição do Windows 10 que você está atualizando. Os dispositivos de destino desta política são atualizados para a edição que você escolher.
   - **Chave do Produto (Product Key)**: insira a chave do produto (Product Key) que você recebeu da Microsoft. Depois de criar a política com a chave do produto (Product Key), a chave não pode ser atualizada e é ocultada por motivos de segurança. Para alterar a chave do produto (Product Key), insira a chave inteira novamente.
   - **Arquivo de Licença**: para o **Windows 10 Holographic for Business** ou o **Windows 10 Mobile Edition**, escolha **Procurar** para selecionar o arquivo de licença que você recebeu do Microsoft. Esse arquivo de licença inclui informações de licença das edições para as quais você está atualizando os dispositivos de destino.

7. Selecione **OK** para salvar suas alterações. Selecione **Criar** para criar o perfil.

## <a name="switch-out-of-s-mode"></a>Sair do modo S

[O Modo S do Windows 10](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) foi projetado para segurança e desempenho. Se os dispositivos apenas executarem aplicativos da Microsoft Store, você poderá usar o modo S para ajudar a proteger seus dispositivos. Se os dispositivos exigirem aplicativos que não estão disponíveis no Microsoft Store, você sairá do modo S. Sair do modo S é uma maneira. Depois de sair do modo S, você não pode voltar para o modo S do Windows 10.

As etapas a seguir mostram como criar um perfil que controla o modo S em dispositivos Windows 10 (1809 ou posteriores).

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.
3. Digite um **Nome** e uma **Descrição** para o perfil. Por exemplo, insira algo como `Windows 10 switch off S mode`
4. Em **Plataforma**, selecione **Windows 10 e posteriores**.
5. Para **Tipo de perfil**, selecione **Atualização da edição**.
6. Selecione **Mudança de modo (somente Participante do Programa Windows Insider)** e defina a propriedade **Sair do modo S**. Suas opções:

    - **Nenhuma configuração**: um dispositivo no modo S permanece no modo S. Um usuário final pode tirar o dispositivo do modo S.
    - **Ficar no modo S**: impede o usuário final de tirar o dispositivo do modo S.
    - **Alternância**: tira o dispositivo do modo S.

7. Selecione **OK** para salvar suas alterações. Selecione **Criar** para criar o perfil.

O perfil é criado e listado nos perfis.

## <a name="next-steps"></a>Próximas etapas

[Atribua este perfil](device-profile-assign.md) aos seus grupos.

>[!NOTE]
>Se você depois remover a atribuição de política, a versão do Windows no dispositivo não será revertida e continuará a funcionar normalmente.
