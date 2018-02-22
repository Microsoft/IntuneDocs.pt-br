---
title: "Importar configurações de Wi-Fi para Windows 8.1 e posterior"
titleSuffix: Azure portal
description: "Como importar configurações de Wi-Fi do Windows para um perfil de Wi-Fi do Intune."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/25/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5b4b77f9c9c1c957e3332c20e010a5e8e8ec2b56
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Como importar configurações de Wi-Fi para dispositivos Windows 8.1 e posteriores no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Para dispositivos que executam Windows 8.1 e Windows 10 para área de trabalho ou dispositivos móveis, ou Windows Holographic for Business, você pode importar um perfil de configuração de Wi-Fi que já foi exportado em um arquivo.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Exportar configurações Wi-Fi de um dispositivo do Windows

No Windows, você pode usar o utilitário **netsh wlan** para exportar um perfil de Wi-Fi existente para um arquivo XML legível pelo Intune. Em um computador Windows que já tenha o perfil de WiFi necessário instalado, siga o procedimento a seguir.
1. Crie uma pasta local para os perfis Wi-Fi exportados, como **c:\WiFi**.
1. Abra um Prompt de Comando como Administrador.
1. Execute o comando **netsh wlan show profiles**, e observe o nome do perfil que você deseja exportar. Neste exemplo, o nome do perfil é **WiFiName**.
1. Execute este comando: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Esse comando cria um arquivo de perfil de Wi-Fi chamado **Wi-Fi-WiFiName.xml** na sua pasta de destino.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importar as configurações de Wi-Fi para o Intune

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, clique em **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.

   > [!WARNING]
   > O nome **deve** ser o mesmo que o atributo name no XML do perfil de Wi-Fi, caso contrário ocorrerá falha.

5. Na lista suspensa **Plataforma**, escolha **Windows 8.1 e posterior**.
6. Na lista suspensa de tipos de **Perfil**, escolha **Importar Wi-Fi**.
7. Na folha **Wi-Fi Básico**, defina as seguintes configurações:
    - **Nome da Conexão** insira o nome da conexão de Wi-Fi. Esse nome é exibido aos usuários finais ao procurarem por redes Wi-Fi disponíveis.
    - **Perfil XML** Clique no botão Procurar para selecionar o arquivo XML que contém as configurações de perfil de Wi-Fi que você deseja importar para o Intune.
    - **Conteúdo do arquivo** Exibe o código XML para o perfil de configuração selecionado.
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil é criado e exibido na folha da lista de perfis.
