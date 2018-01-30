---
title: "Configurações de restrição de dispositivo do Intune para Android"
titlesuffix: Azure portal
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos Android."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1dc50fe1018bae0c13ddba51e5351f463d0ec1c8
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo Android e Samsung Knox Standard no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use essas configurações com uma política de restrição de dispositivo do Android para configurar dispositivos em sua organização.

>[!TIP]
>Se as configurações que você deseja não estiverem disponíveis, é possível configurar os dispositivos usando um [perfil personalizado](custom-settings-android.md).

## <a name="general"></a>Geral

- **Câmera** – Permite usar a câmera do dispositivo.
- **Copiar e colar (somente Samsung Knox)** – permite usar as funções de copiar e colar no dispositivo.
- **Compartilhamento de área de transferência entre os aplicativos (somente Samsung Knox Standard)** – permite usar a área de transferência para copiar e colar entre aplicativos.
- **Envio de dados de diagnóstico (somente Samsung Knox)** – Impede que o usuário envie dados de diagnóstico do dispositivo.
- **Redefinição de fábrica (somente Samsung Knox)** – permite que o usuário execute uma redefinição de fábrica no dispositivo.
- **Geolocalização (somente Samsung Knox)** – permite que o dispositivo utilize informações de localização.
- **Desligar (somente Samsung Knox)** – permite que o usuário desligue o dispositivo.<br>Se estiver desabilitada, a opção **Número de falhas de entrada antes de apagar dispositivo** não poderá ser definida.
- **Captura de tela (somente Samsung Knox)** – permite que o usuário capture o conteúdo da tela como uma imagem.
- **Assistente de voz (somente Samsung Knox)** – permite usar o software de assistente de voz no dispositivo.
- **YouTube (somente Samsung Knox)** – permite usar o aplicativo do YouTube no dispositivo.
- **Dispositivos compartilhados (apenas Samsung Knox)** – configure um dispositivo Samsung Knox Standard gerenciado como compartilhado. Nesse modo, os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure AD. O dispositivo permanece gerenciado, independentemente de estar ou não em uso.<br>Quando usado juntamente com um perfil de certificado SCEP, esse recurso permite aos usuários finais compartilhar um dispositivo com o mesmo conjunto de aplicativos para todos os usuários, mas com seu próprio certificado de usuário SCEP.  Quando os usuários saem, todos os dados do aplicativo são removidos.  Esse recurso está limitado a aplicativos LOB apenas.
- **Bloquear alterações de data e hora (Samsung Knox)** – impeça que o usuário altere as configurações de data e hora no dispositivo. 

## <a name="password"></a>Senha

- **Senha** – Exige que o usuário final insira uma senha para acessar o dispositivo.|Sim|Sim|
- **Tamanho mínimo da senha** – Insira o tamanho mínimo da senha que um usuário deve configurar (entre 4 e 16 caracteres).
- **Máximo de minutos de inatividade para bloqueio da tela** – Especifica o número de minutos de inatividade antes que a tela do dispositivo seja bloqueada automaticamente.
- **Número de falhas de entrada antes de apagar o dispositivo** – Especifica o número de falhas de entrada repetidas permitidas antes do dispositivo ser apagado.
- **Expiração da senha (dias)** – Especifica o número de dias antes que a senha do dispositivo precise ser alterada.
-  **Tipo de senha exigida** – Especifica o nível de complexidade de senha exigido e se dispositivos biométricos podem ser usados. Escolha:
    - **Padrão do dispositivo**
    - **Biométrico de segurança baixa**
    - **Pelo menos, numérico**
    - **Numérico complexo** – Números repetidos ou consecutivos, como '1111' ou '1234' não são permitidos<sup>1</sup>
    - **Pelo menos, alfabético**
    - **Pelo menos, alfanumérico**
    - **Pelo menos alfanumérico com símbolos**
- **Impedir a reutilização de senhas anteriores** – Impede que o usuário final crie uma senha usada anteriormente.
- **Desbloqueio por impressão digital (somente Samsung Knox)** – permite o uso de uma impressão digital para desbloquear os dispositivos com suporte.
- **Smart Lock e outros agentes de confiança** – permite controlar o recurso de Smart Lock em dispositivos Android compatíveis (Samsung Knox Standard 5.0 e posterior). Essa funcionalidade do telefone, às vezes conhecida como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo se o dispositivo está em uma localização confiável. Por exemplo, isso pode ser usado quando o dispositivo está conectado a um dispositivo Bluetooth específico ou quando está próximo a uma marcação NFC. Você pode usar essa configuração para impedir que os usuários configurem o Smart Lock.
- **Criptografia** – Exige que os arquivos no dispositivo sejam criptografados.

<sup>1</sup> Antes de atribuir essa configuração a dispositivos, lembre-se de atualizar o aplicativo do Portal da Empresa para a versão mais recente nesses dispositivos.

Se você definir a configuração do **Numérico complexo** e depois atribuí-la a um dispositivo que executa uma versão do Android anterior à 5.0, o seguinte comportamento se aplicará.
- Se o aplicativo do Portal da Empresa estiver executando uma versão anterior à 1704, nenhuma política de PIN será aplicada ao dispositivo e um erro será exibido no Portal do Azure.
- Se o aplicativo do Portal da Empresa executar a versão 1704 ou posterior, apenas um PIN simples poderá ser aplicado. Versões do Android anteriores à 5.0 não dão suporte a essa configuração. Nenhum erro é exibido no Portal do Azure.


## <a name="google-play-store"></a>Google Play Store

- **Google Play Store (somente Samsung Knox)** – permite que o usuário acesse a Google Play Store no dispositivo.

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, configure uma das seguintes listas em dispositivos Android e Samsung Knox Standard:

Uma lista de **Aplicativos proibidos** – Liste os aplicativos (não gerenciados pelo Intune) que serão reportados se os usuários instalarem e executarem.
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

- **Navegador da Web (somente Samsung Knox)** – especifica se o navegador da Web padrão do dispositivo pode ser usado.
- **Preenchimento automático (somente Samsung Knox)** – permite que a função de preenchimento automático do navegador da Web seja usada.
- **Cookies (somente Samsung Knox)** – permite que o navegador da Web do dispositivo use cookies.
- **Javascript (somente Samsung Knox)** – permite que o navegador da Web do dispositivo execute scripts Java.
- **Pop-ups (somente Samsung Knox)** – permite usar o bloqueador de pop-ups no navegador da Web.

## <a name="allow-or-block-apps"></a>Permitir ou bloquear aplicativos

Essas configurações podem ser usadas para especificar os aplicativos que podem ser instalados ou iniciados em dispositivos que executam somente o Samsung Knox Standard.
Além disso, você também pode especificar os aplicativos instalados que serão ocultados do usuário do dispositivo. Os usuários não podem executar esses aplicativos.

- **Aplicativos com permissão de instalação (Somente Samsung Knox Standard)**
- **Aplicativos impedidos de iniciar (Somente Samsung Knox Standard)**
- **Aplicativos escondidos do usuário (Somente Samsung Knox Standard)**

Para cada configuração, configure uma lista de aplicativos usando um destes procedimentos:

- **Adicionar aplicativos pelo nome do pacote** - principalmente usados para a aplicativos de linha de negócios. Insira o nome do aplicativo e o nome do pacote do aplicativo.
- **Adicionar aplicativos pela URL** - insira o nome do aplicativo e sua URL na Google Play Store.
- **Adicionar aplicativos gerenciados** - na lista de aplicativos que você gerencia com o Intune, selecione o aplicativo que você precisa.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

- **Backup do Google (somente Samsung Knox)** – permite usar o backup do Google.
- **Sincronização automática da conta do Google (somente Samsung Knox)** – permite que as configurações de conta do Google sejam sincronizadas automaticamente.
- **Armazenamento removível (somente Samsung Knox)** – permite que o dispositivo use o armazenamento removível, como um cartão SD.
- **Criptografia em cartões de memória (somente Samsung Knox)** – especifica se o cartão de memória do dispositivo deve ser criptografado.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

- **Roaming de dados (somente Samsung Knox)** – permite usar roaming de dados quando o dispositivo estiver em uma rede de celular.
- **Mensagens SMS/MMS (somente Samsung Knox)** – permite usar mensagens SMS e MMS no dispositivo.
- **Discagem por voz (somente Samsung Knox)** – habilita ou desabilita o recurso de discagem por voz no dispositivo.
- **Roaming de voz (somente Samsung Knox)** – permite usar o roaming de voz quando o dispositivo estiver em uma rede de celular.
- **Bluetooth (somente Samsung Knox)** – permite usar o Bluetooth no dispositivo.
- **NFC (somente Samsung Knox)** – permite operações que usam a comunicação a curta distância nos dispositivos com suporte.
- **Wi-Fi (somente Samsung Knox)** – permite usar os recursos de Wi-Fi do dispositivo.
- **Compartilhamento de Internet por Wi-Fi (somente Samsung Knox)** – permite usar o compartilhamento de Internet por Wi-Fi no dispositivo.

## <a name="kiosk"></a>Quiosque

As configurações de quiosque se aplicam somente a dispositivos Samsung Knox Standard, e apenas a aplicativos gerenciados usando o Intune.

- **Selecionar um aplicativo gerenciado** – Escolha uma das opções a seguir para adicionar um ou mais aplicativos gerenciados que poderão ser executados quando o dispositivo estiver no modo de quiosque. Nenhum outro aplicativo pode ser executado no dispositivo.
    - **Adicionar aplicativos pelo nome do pacote**
    - **Adicionar aplicativos pela URL**
    - **Adicionar aplicativos gerenciados**.
- **Botão de suspensão da tela** – Habilita ou desabilita o botão de suspensão e ativação da tela no dispositivo.
- **Botões de volume** – habilita ou desabilita o uso dos botões de volume no dispositivo.


## <a name="next-steps"></a>Próximas etapas

Continue usando as instruções em [Como definir as configurações de restrição de dispositivo](device-restrictions-configure.md) para criar e, em seguida, atribuir o perfil de restrição do dispositivo.
