---
title: "Importar configurações de Wi-Fi para Windows 8.1 e posterior"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: como importar configurações de Wi-Fi do Windows para um perfil de Wi-Fi do Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b0157f1021ae7c98392dc3c96481a4514758b059
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Como importar configurações de Wi-Fi para dispositivos Windows 8.1 e posteriores no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Para dispositivos que executam o Windows 8.1 ou o Windows 10 Desktop ou Mobile, você pode importar um perfil de configuração de Wi-Fi que já foi exportado em um arquivo.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Exportar configurações Wi-Fi de um dispositivo do Windows

No Windows, você pode usar o utilitário **netsh wlan** para exportar um perfil de Wi-Fi existente para um arquivo XML legível pelo Intune. Em um computador Windows que já tenha o perfil de WiFi necessário instalado, siga o procedimento a seguir.
1. Crie uma pasta local para os perfis Wi-Fi exportados, como **c:\WiFi**.
1. Abra um Prompt de Comando como Administrador.
1. Execute o comando **netsh wlan show profiles**, e observe o nome do perfil que você deseja exportar. Neste exemplo, o nome do perfil é **WiFiName**.
1. Execute este comando: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Isso criará um arquivo de perfil de Wi-Fi chamado **Wi-Fi-WiFiName.xml** na sua pasta de destino.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importar as configurações de Wi-Fi para o Intune

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, clique em **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.
5. Na lista suspensa **Plataforma**, escolha **Windows 8.1 e posterior**.
6. Na lista suspensa de tipos de **Perfil**, escolha **Importar Wi-Fi**.
7. Na folha **Wi-Fi básico**, configure o seguinte:
    - **Nome da Conexão** insira o nome da conexão de Wi-Fi. Esse nome será exibido aos usuários finais que acessam redes Wi-Fi disponíveis.
    - **Perfil XML** Clique no botão Procurar para selecionar o arquivo XML que contém as configurações de perfil de Wi-Fi que você deseja importar para o Intune.
    - **Conteúdo do arquivo** Exibe o código XML para o perfil de configuração selecionado.
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.

