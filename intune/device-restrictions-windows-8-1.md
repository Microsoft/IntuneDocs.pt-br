---
title: "Configurações de restrição de dispositivo do Intune para Windows 8.1"
titleSuffix: Azure portal
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos Windows 8.1."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fe5785e9-8d35-4ad7-95e8-d50f8d87154a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e9b31f9d4e784358d5672b0b8de68d34532b72c8
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
# <a name="windows-81-and-later-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo do Windows 8.1 e posterior no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Geral

-   **Envio de dados de diagnóstico** – Permite que o dispositivo envie informações de diagnóstico à Microsoft.
-   **Firewall** – Exige que o Firewall do Windows esteja ativado.
-   **Controle de Conta de Usuário** – Exige o uso de UAC (Controle de Conta de Usuário) nos dispositivos.

## <a name="password"></a>Senha
-   **Tipo de senha exigida** – Exigir que o usuário final insira uma senha para acessar o dispositivo.
-   **Tamanho mínimo de senha** – Define o tamanho mínimo necessário (em caracteres) para a senha.
-   **Número de falhas de entrada antes de apagar o dispositivo** – Apaga o dispositivo se as tentativas de entrada falharem esse número de vezes.
-   **Máximo de minutos de inatividade para bloquear a tela** – Especifica o número de minutos que um dispositivo deve permanecer ocioso antes que uma senha seja necessária para desbloqueá-lo.
-   **Expiração da senha (dias)** – Especifica o número de dias antes que a senha do dispositivo precise ser alterada.
-   **Impedir a reutilização de senhas anteriores** – Especifica se o usuário pode definir senhas usadas anteriormente.
-   **Senha com imagem e PIN** – Habilita o uso de uma senha com imagem e PIN. Uma senha com imagem permite que o usuário entre fazendo gestos em uma imagem. Um PIN permite que os usuários entrem rapidamente com um código de quatro dígitos.
-   **Criptografia** – Exige que os arquivos no dispositivo sejam criptografados.<br>Para impor a criptografia em dispositivos que executam o Windows 8.1, você deve instalar a [Atualização do cliente do MDM de dezembro de 2014 para Windows](https://support.microsoft.com/kb/3013816) em cada dispositivo.
Se você habilitar essa configuração para dispositivos Windows 8.1, todos os usuários do dispositivo precisarão ter uma conta da Microsoft.
Para a criptografia funcionar, o dispositivo deve atender aos requisitos de certificação de hardware [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97).
Quando você impõe a criptografia em um dispositivo, a chave de recuperação fica acessível apenas da conta da Microsoft do usuário, que é acessada de sua conta do OneDrive. Não é possível recuperar essa chave em nome de um usuário.     



## <a name="browser"></a>Navegador
-   **Preenchimento automático** – Habilita os usuários a alterarem as configurações de preenchimento automático no navegador.
-   **Aviso de fraude** – Habilita ou desabilita avisos de sites fraudulentos potenciais.
-   **SmartScreen** – Habilita ou desabilita avisos de sites fraudulentos potenciais.
-   **JavaScript** – Habilita o navegador a executar scripts, como scripts Java.
-   **Pop-ups** – Habilita ou desabilita o bloqueador de pop-ups do navegador.
-   **Enviar cabeçalhos Do Not Track** – Envia um cabeçalho Do Not Track para os sites visitados no Internet Explorer.
-   **Plug-ins** – Habilita os usuários a adicionar plug-ins ao Internet Explorer.
-   **Entrada de palavra única no site da intranet** – Habilita o uso de uma única palavra para direcionar o Internet Explorer a um site, como o Bing.
-   **Detectar site da intranet automaticamente** – Permite configurar a segurança para sites de intranet no Internet Explorer.
-   **Nível de segurança da Internet** – Define o nível de segurança do Internet Explorer para sites da Internet.
-   **Nível de segurança da Intranet** – Define o nível de segurança do Internet Explorer para sites da Intranet.
-   **Nível de segurança de sites confiáveis** – Configura o nível de segurança para a zona de sites confiáveis.
-   **Segurança alta para sites restritos** – Configura o nível de segurança para a zona de sites restritos.
-   **Acesso ao menu no modo Empresarial** – Permite aos usuários acessar as opções de menu do modo Empresarial do Internet Explorer.
Se selecionar essa configuração, você também poderá especificar um **Local de relatório de log**, que contém uma URL para um relatório que mostra os sites para os quais os usuários ativaram o acesso do modo Empresarial.
-   **Local da lista de site do modo Empresarial** – Especifica o local da lista de sites que usarão o modo Empresarial quando ele estiver ativo.

## <a name="cellular"></a>Celular
-   **Roaming de dados** – Habilita o roaming de dados quando o dispositivo estiver em uma rede de celular.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento
-   **URL de pastas de trabalho** – Define a URL da pasta de trabalho para permitir que os documentos sejam sincronizados em todos os dispositivos.
-   **Acesso ao aplicativo Windows Mail sem uma conta da Microsoft** – Habilita o acesso ao aplicativo Windows Mail sem uma conta da Microsoft.    
