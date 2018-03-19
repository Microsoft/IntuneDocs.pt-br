---
title: "Importar configurações de Wi-Fi para Windows 8.1 e posterior"
titleSuffix: Microsoft Intune
description: "Como importar configurações de Wi-Fi do Windows para um perfil de Wi-Fi do Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 890a10ecf4212656c189adaf46bb2839898758c1
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Importar configurações de Wi-Fi para dispositivos Windows 8.1 e posteriores no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Para dispositivos que executam Windows 8.1 e Windows 10 para área de trabalho ou dispositivos móveis, ou Windows Holographic for Business, você pode importar um perfil de configuração de Wi-Fi que já foi exportado em um arquivo.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Exportar configurações Wi-Fi de um dispositivo do Windows

No Windows, você pode usar o utilitário **netsh wlan** para exportar um perfil de Wi-Fi existente para um arquivo XML legível pelo Intune. Em um computador Windows que já tenha o perfil de WiFi necessário instalado, siga o procedimento a seguir.
1. Crie uma pasta local para os perfis Wi-Fi exportados, como **c:\WiFi**.
1. Abra um Prompt de Comando como Administrador.
1. Execute o comando **netsh wlan show profiles**, e observe o nome do perfil que você deseja exportar. Neste exemplo, o nome do perfil é **WiFiName**.
1. Execute este comando: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Esse comando cria um arquivo de perfil de Wi-Fi chamado **Wi-Fi-WiFiName.xml** na sua pasta de destino.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importar as configurações de Wi-Fi para o Intune

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
4. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
5. No painel de perfis, clique em **Criar perfil**.
6. No painel **Criar perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.


   > [!WARNING]
   > O nome **deve** ser o mesmo que o atributo name no XML do perfil de Wi-Fi, caso contrário ocorrerá falha.

7. Na lista suspensa **Plataforma**, escolha **Windows 8.1 e posterior**.
8. Na lista suspensa **Tipos de perfil**, escolha **Importar Wi-Fi**.
9. No painel **Wi-Fi**, defina as seguintes configurações:
    - **Nome da Conexão** insira o nome da conexão de Wi-Fi. Esse nome é exibido aos usuários finais ao procurarem por redes Wi-Fi disponíveis.
    - **Perfil XML** Clique no botão Procurar para selecionar o arquivo XML que contém as configurações de perfil de Wi-Fi que você deseja importar para o Intune.
    - **Conteúdo do arquivo** Exibe o código XML para o perfil de configuração selecionado.
10. Quando terminar, selecione **OK**, volte para o painel **Criar perfil** e escolha **Criar**.

O perfil é criado e aparece no painel da lista de perfis.
