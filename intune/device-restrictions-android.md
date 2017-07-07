---
title: "Configurações de restrição de dispositivo do Intune para Android"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44d80e1c72b58eccd4e69b1d561c7d651f39b3c3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo Android e Samsung KNOX Standard no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use essas configurações com uma política de restrição de dispositivo do Android para configurar dispositivos em sua organização.

## <a name="general"></a>Geral

|||||
|-|-|-|-|
|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX Standard|
|**Câmera**|Permite o uso da câmera do dispositivo.|Sim|Sim|
|**Copiar e colar**|Permite as funções de copiar e colar no dispositivo.|Não|Sim|
|**Compartilhamento da área de transferência entre aplicativos**|Permite o uso da área de transferência para copiar e colar entre aplicativos.|Não|Sim|
|**Envio de dados de diagnóstico**|Impede que o usuário envie dados de diagnóstico do dispositivo.|Não|Sim|
|**Redefinição de fábrica**|Permite que o usuário execute uma redefinição de fábrica no dispositivo.|Não|Sim|
|**Localização geográfica**|Permite que o dispositivo utilize informações de localização (somente Samsung KNOX Standard).|Não|Sim|
|**Desligar**|Permite que o usuário desligue o dispositivo.<br>Se estiver desabilitada, a opção **Número de falhas de entrada antes de apagar dispositivo** não poderá ser definida.|Não|Sim|
|**Captura de tela**|Permite que o usuário capture o conteúdo da tela como uma imagem.|Não|Sim|
|**Assistente de voz**|Permite o uso de software do assistente de voz no dispositivo.|Não|Sim|
|**YouTube**|Permite o uso do aplicativo YouTube no dispositivo.|Não|Sim|
|**Dispositivos compartilhados**|Configure um dispositivo Samsung KNOX Standard gerenciado como compartilhado. Nesse modo, os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure AD. O dispositivo permanece gerenciado, independentemente de estar ou não em uso.<br>Quando os usuários finais entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.|Não|Sim|

## <a name="password"></a>Senha

|||||
|-|-|-|-|
|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX Standard|
|**Senha**|Exige que o usuário final insira uma senha para acessar o dispositivo.|Sim|Sim|
|**Comprimento mínimo da senha**|Insira o tamanho mínimo da senha que um usuário deve configurar (entre 4 e 16 caracteres).|Sim|Sim|
|**Máximo de minutos de inatividade até a tela ser bloqueada**|Especifica o número de minutos de inatividade antes de a tela do dispositivo ser bloqueada automaticamente.|Sim|Sim|
|**Número de falhas de início de sessão antes de limpar o dispositivo**|Especifica o número de falhas de entrada repetidas permitido antes do dispositivo ser apagado.|Sim|Sim|
|**Expiração da senha (dias)**|Especifica o número de dias antes que a senha do dispositivo precise ser alterada.|Sim|Sim|
|**Tipo de senha necessária**|Especifica o nível de complexidade da senha necessário e se dispositivos biométricos podem ser usados. Escolha:<br><br>    -     **Padrão do dispositivo**<br>-     **Biométrico de segurança baixa**<br>    -     **Pelo menos, numérico**<br>    -     **Numérico complexo** (números repetidos ou consecutivos, como '1111' ou '1234' não são permitidos)<sup>1</sup><br>    -     **Pelo menos, alfabético**<br>    -     **Pelo menos, alfanumérico**<br>    -     **Pelo menos alfanumérico com símbolos**|Sim|Sim|
|**Evitar a reutilização de senhas anteriores**|Impede que o usuário final crie uma senha usada anteriormente.|Sim|Sim|
|**Desbloqueio por impressão digital**|Permite o uso de uma impressão digital para desbloquear os dispositivos com suporte.|Não|Sim|
|**Smart Lock e outros agentes de confiança**|Permite controlar o recurso de Smart Lock em dispositivos Android compatíveis (Samsung KNOX Standard 5.0 e posterior). Essa funcionalidade do telefone, às vezes conhecida como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo se o dispositivo está em uma localização confiável. Por exemplo, isso pode ser usado quando o dispositivo está conectado a um dispositivo Bluetooth específico ou quando está próximo a uma marcação NFC. Você pode usar essa configuração para impedir que os usuários configurem o Smart Lock.|Sim (5.0 e posterior)|Sim|
|**Criptografia**|Exige que os arquivos no dispositivo sejam criptografados.|Sim|Sim|

<sup>1</sup> Antes de atribuir essa configuração a dispositivos, lembre-se de atualizar o aplicativo do Portal da Empresa para a versão mais recente nesses dispositivos.

Se você definir a configuração do **Numérico complexo** e depois atribuí-la a um dispositivo que executa uma versão do Android anterior à 5.0, o seguinte comportamento se aplicará.
- Se o aplicativo do Portal da Empresa estiver executando uma versão anterior à 1704, nenhuma política de PIN será aplicada ao dispositivo e um erro será exibido no portal do Intune.
- Se o aplicativo do Portal da Empresa executar a versão 1704 ou posterior, apenas um PIN simples poderá ser aplicado. Versões do Android anteriores à 5.0 não dão suporte a essa configuração. Nenhum erro é exibido no portal do Intune.


## <a name="google-play-store"></a>Google Play Store

|||||
|-|-|-|-|
|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX Standard|
|**Google Play Store**|Permite ao usuário acessar o Google Play Store no dispositivo|Não|Sim|

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, configure uma das seguintes listas em dispositivos Android e Samsung KNOX Standard:

Uma lista de **Aplicativos proibidos** – Listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.
Uma lista de **Aplicativos aprovados** – Listar os aplicativos que os usuários têm permissão para instalar. Para permanecer em conformidade, os usuários não devem instalar outros aplicativos. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.
Os perfis de dispositivo que contêm configurações de aplicativo restrito devem ser atribuídos para grupos de usuários.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Como especificar a URL de um aplicativo na loja

Para especificar uma URL de aplicativo na lista de aplicativos compatíveis e incompatíveis, siga estas etapas:

Na [seção Aplicativos do Google Play](https://play.google.com/store/apps), pesquise o aplicativo que você deseja usar.

Abra a página de instalação do aplicativo e copie a URL para a área de transferência. Agora você pode usar essa URL na lista de aplicativos em conformidade ou fora de conformidade.

Exemplo: pesquise Google Play para Microsoft Office Mobile. Use a URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Opções adicionais

Você também pode clicar em **Importar** para obter a lista de um arquivo csv. Use o formato <*URL do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*> ou clique em **Exportar** no arquivo csv que contém o conteúdo da lista de aplicativos restritos no mesmo formato.      

## <a name="browser"></a>Navegador
|||||
|-|-|-|-|
|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX Standard|
|**Navegador da Web**|Especifica se o navegador da Web padrão do dispositivo pode ser usado.|Não|Sim|
|**Preenchimento automático**|Permite que a função de preenchimento automático do navegador da Web seja usada.|Não|Sim|
|**Cookies**|Permite que o navegador da Web do dispositivo use cookies.|Não|Sim|
|**Javascript**|Permite que o navegador da Web do dispositivo execute scripts Java.|Não|Sim|
|**Pop-ups**|Permite o uso do bloqueador de pop-up no navegador da Web.|Não|Sim|

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento
|||||
|-|-|-|-|
|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX Standard|
|**Backup do Google**|Permite o uso do backup do Google.|Não|Sim|
|**Sincronização automática da conta do Google**|Permite que as configurações de conta do Google sejam sincronizadas automaticamente.|Não|Sim|
|**Armazenamento removível**|Permite que o dispositivo use o armazenamento removível, como um cartão SD.|Não|Sim|
|**Criptografia em cartões de armazenamento**|Especifica se o cartão de memória do dispositivo deve ser criptografado.|Não|Sim|

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade
|||||
|-|-|-|-|
|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX Standard|
|**Roaming de dados**|Permite roaming de dados quando o dispositivo estiver em uma rede de celular.|Não|Sim|
|**Mensagens SMS/MMS**|Permite o uso de mensagens SMS e MMS no dispositivo.|Não|Sim|
|**Discagem de voz**|Habilita ou desabilita o recurso de discagem de voz no dispositivo.|Não|Sim|
|**Roaming de voz**|Permite roaming de voz quando o dispositivo estiver em uma rede de celular.|Não|Sim|
|**Bluetooth**|Permite o uso de Bluetooth no dispositivo.|Não|Sim|
|**NFC**|Permite operações que usam a comunicação a curta distância nos dispositivos com suporte.|Não|Sim|
|**Wi-Fi**|Permite o uso das funcionalidades de Wi-Fi do dispositivo.|Não|Sim|
|**Compartilhamento da Internet por Wi-Fi**|Permite o uso de compartilhamento de Internet por Wi-Fi no dispositivo.|Não|Sim|

## <a name="kiosk"></a>Quiosque
|||||
|-|-|-|-|
|Nome da configuração|Detalhes|Android 4.0+|Samsung KNOX Standard|
|**Selecionar um aplicativo gerenciado**|Escolha uma das opções a seguir para adicionar um ou mais aplicativos que poderão ser executados quando o dispositivo estiver no modo de quiosque. Nenhum outro aplicativo pode ser executado no dispositivo.<br><br>- **Adicionar aplicativos pelo nome do pacote**<br>- **Adicionar aplicativos pela URL**<br>- **Adicionar aplicativos gerenciados**|Não|Sim|
|**Botão Suspender tela**|Habilita ou desabilita o botão de ativação e suspensão da tela no dispositivo.|Não|Sim|
|**Botões de volume**|Habilita ou desabilita o uso dos botões de volume no dispositivo.|Não|Sim|
