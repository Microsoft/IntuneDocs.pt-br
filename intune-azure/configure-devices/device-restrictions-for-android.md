---
title: "Configurações de restrição de dispositivo do Intune para Android | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: conheça as configurações do Intune que você pode usar para controlar as configurações do dispositivo e as funcionalidades dos dispositivos Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 74023866802eb4c13e7e9ff97e8048afe7d62409
ms.openlocfilehash: 40e04f1f8e7972bcd72cceae272d8295a496df7a


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-intune-azure-preview"></a>Configurações de restrição de dispositivo Android e Samsung KNOX Standard na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Geral
-   **Câmera** – Permite usar a câmera do dispositivo.
-   **Copiar e colar** – Permite usar as funções de copiar e colar no dispositivo.
-   **Compartilhamento de área de transferência entre os aplicativos** – Permite usar a área de transferência para copiar e colar entre aplicativos (somente Samsung KNOX Standard).
-   **Envio de dados de diagnóstico** – Impede que o usuário envie dados de diagnóstico do dispositivo.    
-   **Redefinição de fábrica** – Permite que o usuário execute uma redefinição de fábrica no dispositivo.
-   **Geolocalização** – Permite que o dispositivo utilize informações de localização (somente Samsung KNOX Standard).
-   **Desligar** – Permite que o usuário desligue o dispositivo.<br>Se essa configuração for desabilitada, a configuração **Número de falhas de entrada antes de apagar o dispositivo** não funcionará para dispositivos Samsung KNOX Standard.
-   **Captura de tela** – Permite que o usuário capture o conteúdo da tela como uma imagem.
-   **Assistente de voz** – Permite usar o software de assistente de voz no dispositivo (somente Samsung KNOX Standard).
-   **YouTube** – Permite usar o aplicativo do YouTube no dispositivo (somente Samsung KNOX Standard).

## <a name="password"></a>Senha
-   **Senha obrigatória** – Exigir que o usuário final insira uma senha para acessar o dispositivo.
-   **Tamanho mínimo da senha** – Insira o tamanho mínimo da senha que um usuário deve configurar (entre 4 e 16 caracteres).
-   **Máximo de minutos de inatividade para bloqueio da tela** – Especifica o número de minutos de inatividade antes que a tela do dispositivo seja bloqueada automaticamente.
-   **Número de falhas de entrada antes de apagar o dispositivo** – Especifica o número de falhas de entrada repetidas permitidas antes do dispositivo ser apagado.
-   **Expiração da senha (dias)** – Especifica o número de dias antes que a senha do dispositivo precise ser alterada.
-   **Tipo de senha exigida** – Especifica o nível necessário de complexidade de senha exigido e se dispositivos biométricos podem ser usados.
-   **Impedir a reutilização de senhas anteriores** – Impede que o usuário final crie uma senha usada anteriormente.
-   **Desbloqueio por impressão digital** – Permite o uso de uma impressão digital para desbloquear os dispositivos com suporte.
-   **Smart Lock e outros agentes de confiança** – Permite controlar o recurso de Smart Lock em dispositivos Android compatíveis (Samsung KNOX Standard 5.0 e posterior). Essa capacidade do telefone, às vezes conhecida como agente de confiança, permitirá desabilitar ou ignorar a senha da tela de bloqueio do dispositivo se o dispositivo estiver em um local confiável (por exemplo, quando ele está conectado a um dispositivo Bluetooth específico ou quando está perto de uma marca NFC). Você pode usar essa configuração para impedir que os usuários configurem o Smart Lock.
-   **Criptografia** – Exige que os arquivos no dispositivo sejam criptografados.

## <a name="google-play-store"></a>Google Play Store

-   **Google Play Store** – Permite que o usuário acesse a Google Play Store no dispositivo (somente Samsung KNOX Standard).

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

Uma lista de **Aplicativos proibidos** – Listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.
Uma lista de **Aplicativos aprovados** – Listar os aplicativos que os usuários têm permissão para instalar. Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.
Perfis de dispositivo que contêm configurações de aplicativo restrito devem ser implantados para grupos de usuários.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Como especificar a URL de um aplicativo na loja

Para especificar uma URL de aplicativo na lista de aplicativos compatíveis e incompatíveis, siga estas etapas:

Na [seção Aplicativos do Google Play](https://play.google.com/store/apps), pesquise o aplicativo que você deseja usar.

Abra a página de instalação do aplicativo e copie a URL para a área de transferência. Agora você pode usar essa URL na lista de aplicativos compatíveis ou incompatíveis.

Exemplo: pesquise Google Play para Microsoft Office Mobile. A URL usada será **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Opções adicionais

Você também pode clicar em **Importar** para popular a lista de um arquivo csv no formato <*url do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*>, ou clique em **Exportar** para criar um arquivo csv que inclui o conteúdo da lista de aplicativos restritos no mesmo formato.      

## <a name="browser"></a>Navegador
-   **Navegador da Web** – Especifica se o navegador da Web padrão do dispositivo pode ser usado.
-   **Preenchimento automático** – Permite que a função de preenchimento automático do navegador da Web seja usada.
-   **Cookies** – Permite que o navegador da Web do dispositivo use cookies.
-   **JavaScript** – Permite que o navegador da Web do dispositivo execute scripts Java.
-   **Pop-ups** – Permite usar o bloqueador de pop-ups no navegador da Web.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento
-   **Backup do Google** – Permite usar o backup do Google.
-   **Sincronização automática da conta do Google** – Permite que as configurações de conta do Google sejam sincronizadas automaticamente.
-   **Armazenamento removível** – Permite que o dispositivo use o armazenamento removível, como um cartão SD (somente Samsung KNOX Standard).
-   **Criptografia em cartões de memória** – Especifica se o cartão de memória do dispositivo deve ser criptografado.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade
-   **Roaming de dados** – Permite usar roaming de dados quando o dispositivo estiver em uma rede de celular (somente Samsung KNOX Standard).
-   **Mensagens SMS/MMS** – Permite usar mensagens SMS e MMS no dispositivo (somente Samsung KNOX Standard).
-   **Discagem por voz** – Habilita ou desabilita o recurso de discagem por voz no dispositivo (somente Samsung KNOX Standard).
-   **Roaming de voz** – Permite usar o roaming de voz quando o dispositivo estiver em uma rede de celular (somente Samsung KNOX Standard).
-   **Bluetooth** – Permite usar o Bluetooth no dispositivo (somente Samsung KNOX Standard).
-   **NFC** – Permite operações que usam comunicação a curta distância se o dispositivo der suporte a ela (somente Samsung KNOX Standard).
-   **Wi-Fi** – Permite usar os recursos de Wi-Fi do dispositivo (somente Samsung KNOX Standard).
-   **Compartilhamento de Internet por Wi-Fi** – Permite usar o compartilhamento de Internet por Wi-Fi no dispositivo (somente Samsung KNOX Standard).

## <a name="kiosk"></a>Quiosque
-   **Selecionar um aplicativo gerenciado** – Procure e selecione um aplicativo gerenciado que poderá ser executado quando o dispositivo estiver no modo de quiosque (não há suporte para aplicativos especificados como um link para a loja no momento). Nenhum outro aplicativo poderá ser executado no dispositivo.
-   **Botão de suspensão da tela** – Habilita ou desabilita o botão de suspensão e ativação da tela no dispositivo.
-   **Botões de volume** – habilita ou desabilita o uso dos botões de volume no dispositivo.



<!--HONumber=Feb17_HO1-->


