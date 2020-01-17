---
title: Configurações de restrições de dispositivo para Android no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações de dispositivo Android que você pode controlar e restringir no Microsoft Intune. Use essas configurações para controlar a senha, acessar o Google Play, permitir ou proibir aplicativos, controlar as configurações do navegador, bloquear aplicativos, fazer backup na nuvem do Google e controlar as opções de mensagem, voz, roaming de dados e conexões Wi-Fi e Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e7709eac2b360aa09415249c1c3f704b52a492b
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206577"
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-lists-in-intune"></a>Listas de configurações de restrições de dispositivo Android e Samsung Knox Standard no Intune

Este artigo mostra todas as configurações de restrições de dispositivo do Microsoft Intune que você pode definir para dispositivos que executam o Android.

>[!TIP]
>Se as configurações que você deseja não estiverem disponíveis, é possível configurar os dispositivos usando um [perfil personalizado](../custom-settings-android.md).

## <a name="general"></a>Geral

- **Câmera**: Escolha a opção **Bloquear** para impedir o acesso à câmera. **Não configurado** permite o acesso à câmera do dispositivo.
- **Copiar e colar (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o procedimento de copiar e colar. **Não configurado** permite usar as funções de copiar e colar no dispositivo.
- **Compartilhamento de área de transferência entre aplicativos (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o uso da área de transferência para copiar e colar entre aplicativos. **Não configurado** permite o uso da área de transferência para copiar e colar entre aplicativos.
- **Envio de dados de diagnóstico (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir que o usuário envie dados de diagnóstico do dispositivo. **Não configurado** permite que o usuário envie os dados.
- **Apagar (somente Samsung KNOX)** : permite que o usuário execute uma ação de [apagamento](../remote-actions/devices-wipe.md) no dispositivo.
- **Geolocalização (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir que o dispositivo use as informações de localização. **Não configurado** permite que o dispositivo utilize informações de localização.
- **Desligar (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir que o usuário desligue o dispositivo. Se essa configuração estiver desabilitada, a opção **Número de falhas de entrada antes de apagar o dispositivo** não poderá ser definida e não funcionará. **Não configurado** permite que o usuário desligue o dispositivo.
- **Captura de tela (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir a captura de telas. **Não configurado** permite que o usuário capture o conteúdo da tela como uma imagem.
- **Assistente de voz (somente Samsung KNOX)** : escolha a opção **Bloquear** para desabilitar o serviço S Voice. **Não configurado** permite o uso do serviço e do aplicativo S Voice no dispositivo. Essa configuração não se aplica ao Bixby nem ao assistente de voz para acessibilidade, que lê em voz alta o conteúdo da tela.
- **YouTube (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o uso do aplicativo YouTube. **Não configurado** permite o uso do aplicativo YouTube no dispositivo.
- **Dispositivos compartilhados (somente Samsung Knox)** : configure um dispositivo Samsung KNOX Standard gerenciado como compartilhado. Quando estiver configurado como **Permitir**, os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure AD. O dispositivo permanece gerenciado, independentemente de estar ou não em uso.</br>Quando usado com um perfil de certificado SCEP, esse recurso permite aos usuários finais compartilhar um dispositivo com os mesmos aplicativos para todos os usuários. Porém, cada usuário tem seu próprio certificado de usuário de SCEP. Quando os usuários saem, todos os dados do aplicativo são removidos. Esse recurso está limitado a aplicativos LOB apenas. </br>**Não configurado** impede que vários usuários finais entrem no aplicativo do Portal da Empresa no dispositivo usando suas credenciais do Azure AD.
- **Bloquear as alterações de data e hora (Samsung KNOX)** : escolha a opção **Bloquear** para impedir que o usuário altere as configurações de data e hora no dispositivo. **Não configurado** permite que os usuários alterem as configurações de data e hora.

## <a name="password"></a>Senha

- **Senha**: a opção **Exigir** torna necessário que o usuário final insira uma senha para acessar o dispositivo. **Não configurado** permite que os usuários acessem o dispositivo sem inserir uma senha.

    > [!NOTE]
    > Os dispositivos Samsung Knox automaticamente exigem um PIN de quatro dígitos durante o registro do MDM. Dispositivos Android nativos podem automaticamente exigir que um PIN fique em conformidade com Acesso Condicional.

- **Comprimento mínimo da senha**: Insira o tamanho mínimo da senha que um usuário deve inserir (entre 4 e 16 caracteres).
- **Máximo de minutos de inatividade até a tela ser bloqueada**: Insira o número máximo de minutos de inatividade permitido no dispositivo até a tela ser bloqueada. O usuário final não pode definir um valor temporal superior ao tempo configurado no perfil do dispositivo. O usuário final pode definir um valor temporal inferior. Por exemplo, se o perfil estiver definido para 15 minutos, o usuário final poderá definir o valor para cinco minutos. Entretanto, ele não poderá definir o valor para 30 minutos. 
- **Número de falhas de início de sessão antes de limpar o dispositivo**: Insira o número de falhas de entrada repetidas permitido antes do dispositivo ser apagado.
- **Expiração da senha (dias)** : Insira o número de dias antes que a senha do dispositivo precise ser alterada.
- **Tipo de senha necessária**: Insira o nível de complexidade da senha necessário e se dispositivos biométricos podem ser usados. Suas opções:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Pelo menos, numérico**
  - **Complexo numérico**: Números repetidos ou consecutivos, como "1111" ou "1234", não são permitidos.<sup>1</sup>
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Evitar a reutilização de senhas anteriores**: Impede que o usuário final crie uma senha usada anteriormente.
- **Desbloquear impressão digital (somente Samsung KNOX)** : Escolha **Bloquear** para impedir o uso de uma impressão digital para desbloquear o dispositivo. **Não configurado** permite que o usuário desbloqueie o dispositivo usando uma impressão digital.
- **Smart Lock e outros agentes de confiança**: Escolha a opção **Bloquear** para impedir que o Smart Lock ou outros agentes de confiança ajustem as configurações de tela de bloqueio (Samsung KNOX Standard 5.0+). Esse recurso do telefone, às vezes conhecido como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo quando este está em uma localização confiável. Por exemplo, esse dispositivo pode ser usado quando o dispositivo está conectado a um dispositivo Bluetooth específico ou quando está próximo a uma marca NFC. Você pode usar essa configuração para impedir que os usuários configurem o Smart Lock.
- **Criptografia**: Escolha a opção **Exigir** para que os arquivos no dispositivo sejam criptografados. Nem todos os dispositivos são compatíveis com a criptografia. Para usar esse recurso, também é possível: 
  1. Definir **Senha** como **Exigir**.
  2. Definir **Tipo de senha necessária** como **Pelo menos numérica**.
  3. Definir **Comprimento mínimo da senha** para pelo menos 4 caracteres a fim de reportar corretamente a conformidade para essa configuração.

  > [!NOTE]
  > Quando uma política de criptografia é imposta, os dispositivos Samsung Knox exigem que os usuários definam uma senha complexa de 6 caracteres como a senha do dispositivo.

<sup>1</sup> Antes de atribuir essa configuração a dispositivos, lembre-se de atualizar o aplicativo Portal da Empresa para a versão mais recente nesses dispositivos.

Se você definir a configuração **Tipo de senha necessária** como **Complexo numérico** e, depois, atribuí-la a um dispositivo que executa uma versão do Android anterior à 5.0, o seguinte comportamento se aplicará:

- Se o aplicativo Portal da Empresa estiver executando uma versão anterior à 1704, nenhuma política de PIN será aplicada ao dispositivo e será exibido um erro no centro de administração do Gerenciador de Ponto de Extremidade da Microsoft.
- Se o aplicativo do Portal da Empresa executar a versão 1704 ou posterior, apenas um PIN simples poderá ser aplicado. Versões do Android anteriores à 5.0 não oferecem suporte a essa configuração. Nenhum erro é mostrado no centro de administração do Microsoft Endpoint Manager.

## <a name="google-play-store"></a>Google Play Store

- **Google Play Store (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o uso da Google Play Store. **Não configurado** permite ao usuário acessar a Google Play Store no dispositivo.

## <a name="restricted-apps"></a>Aplicativos restritos

Use essas configurações para permitir ou impedir aplicativos específicos no dispositivo. Esse recurso é compatível com dispositivos Android e Samsung Knox Standard:

- **Aplicativos proibidos**: Uma lista de aplicativos não gerenciados pelo Intune que você não deseja que sejam instalados no dispositivo. Se um usuário instalar um aplicativo dessa lista, você será notificado pelo Intune.
- **Aplicativos aprovados**: Uma lista de aplicativos que os usuários têm permissão para instalar. Para permanecer em conformidade, os usuários não devem instalar outros aplicativos. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.

Para adicionar o aplicativo a essas listas, você pode:

- **Adicionar** a URL da Google Play Store para o aplicativo desejado. Por exemplo, para adicionar o aplicativo Área de Trabalho Remota da Microsoft para Android, insira `https://play.google.com/store/apps/details?id=com.microsoft.rdc.android`. Para localizar a URL de um aplicativo, abra a [Google Play Store](https://play.google.com/store/apps) e procure o aplicativo. Por exemplo, pesquise por `Microsoft Remote Desktop Play Store` ou `Microsoft Planner`. Selecione o aplicativo e copie a URL.
- Importe um arquivo CSV com detalhes sobre o aplicativo, incluindo a URL. Use o formato <*url do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*>. Ou **exporte** uma lista existente que contenha a lista de aplicativos restritos no mesmo formato.

> [!IMPORTANT]
> Os perfis de dispositivo que usam configurações de aplicativo restrito devem ser atribuídos a grupos de usuários.

## <a name="browser"></a>Navegador

- **Navegador da Web (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir que o navegador da Web padrão seja usado no dispositivo. **Não configurado** permite que o navegador da Web padrão do dispositivo seja usado.
- **Preenchimento automático (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o preenchimento automático de texto no navegador. **Não configurado** permite o uso da função de preenchimento automático no navegador da Web.
- **Cookies (somente Samsung KNOX)** : escolha como você deseja lidar com cookies de sites no dispositivo. Suas opções:
  - Allow
  - Bloquear todos os cookies
  - Permitir cookies dos sites visitados
  - Permitir cookies do site atual
- **JavaScript (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir que o navegador da Web execute scripts Java. **Não configurado** permite que o navegador da Web do dispositivo execute scripts Java.
- **Pop-ups (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir pop-ups no navegador da Web. **Não configurado** permite pop-ups no navegador da Web.

## <a name="allow-or-block-apps"></a>Permitir ou bloquear aplicativos

Use essas configurações para permitir, bloquear ou ocultar aplicativos específicos em dispositivos Samsung Knox Standard. Os aplicativos que estão ocultos não podem ser abertos ou executados pelo usuário.

Suas opções:

- **Aplicativos com permissão de instalação (Somente Samsung Knox Standard)**
- **Aplicativos impedidos de iniciar (Somente Samsung Knox Standard)**
- **Aplicativos escondidos do usuário (Somente Samsung Knox Standard)**

Para cada configuração, adicione uma lista de aplicativos. Suas opções:

- **Adicionar aplicativos pelo nome do pacote**: usado principalmente para aplicativos de linha de negócios. Insira o nome do aplicativo e o nome do pacote do aplicativo.
- **Adicionar aplicativos por URL**: insira o nome do aplicativo e sua URL na Google Play Store.
- **Adicionar aplicativo da loja**: selecione um aplicativo da lista existente de aplicativos gerenciados no Intune.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

- **Backup do Google (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir que o dispositivo sincronize com o backup do Google. **Não configurado** permite usar o backup do Google.
- **Sincronização automática da conta do Google (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o recurso de sincronização automática de contas do Google no dispositivo. **Não configurado** permite que as configurações de conta do Google sejam sincronizadas automaticamente.
- **Armazenamento removível (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir que o dispositivo use armazenamento removível. **Não configurado** permite que o dispositivo use o armazenamento removível, como um cartão SD.
- **Criptografia em cartões de memória (somente Samsung KNOX)** : a opção **Exigir** impõe que os cartões de memória sejam criptografados. **Não configurado** permite o uso de cartões de memória não criptografados. Nem todos os dispositivos oferecem suporte à criptografia de cartão de memória. Para confirmar, verifique as informações com o fabricante do dispositivo.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

- **Roaming de dados (somente Samsung KNOX)** : Escolha **Bloquear** para impedir o roaming de dados pela rede celular. **Não configurado** permite o roaming de dados quando o dispositivo estiver em uma rede celular.
- **Mensagens SMS/MMS (somente Samsung KNOX)** : escolha a opção **Bloquear** para evitar mensagens de texto no dispositivo. **Não configurado** permite o uso de mensagens SMS e MMS no dispositivo.
- **Discagem de voz (somente Samsung KNOX)** : Escolha **Bloquear** para impedir os usuários de usar o recurso de discagem de voz no dispositivo. **Não configurado** permite a discagem por voz no dispositivo.
- **Roaming de voz (somente Samsung KNOX)** : Escolha **Bloquear** para impedir o roaming de voz na rede celular. **Não configurado** permite o roaming de voz quando o dispositivo estiver em uma rede celular.
- **Bluetooth (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o uso do Bluetooth no dispositivo. **Não configurado** permite o uso de Bluetooth no dispositivo.
- **NFC (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o uso da tecnologia NFC (comunicação a curta distância). **Não configurado** permite operações que usam a comunicação a curta distância em dispositivos compatíveis.
- **Wi-Fi (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o uso de Wi-Fi no dispositivo. **Não configurado** permite o uso de recursos de Wi-Fi no dispositivo.
- **Compartilhamento da Internet por Wi-Fi (somente Samsung KNOX)** : escolha a opção **Bloquear** para impedir o uso de compartilhamento da Internet por Wi-Fi no dispositivo. **Não configurado** permite o uso do compartilhamento da Internet Wi-Fi no dispositivo.

## <a name="kiosk"></a>Quiosque

As configurações de quiosque se aplicam somente a dispositivos Samsung Knox Standard, e apenas a aplicativos gerenciados usando o Intune.

- Adicione aplicativos que você deseja executar quando o dispositivo estiver no modo de quiosque. No modo de quiosque, somente os aplicativos que você adicionar são executados. Os navegadores pré-instalados não são executados como um aplicativo quando o dispositivo estiver no modo de quiosque. Se um navegador for necessário, use o [Managed Browser](../apps/app-configuration-managed-browser.md).

  Suas opções de aplicativo:

  - **Adicionar aplicativos pelo nome do pacote**: usado principalmente para aplicativos de linha de negócios. Insira o nome do aplicativo e o nome do pacote do aplicativo.
  - **Adicionar aplicativos por URL**: insira o nome do aplicativo e sua URL na Google Play Store.
  - **Adicionar aplicativo da loja**: selecione um aplicativo da lista existente de aplicativos gerenciados no Intune.

- **Botão Suspender tela**: escolha a opção **Bloquear** para evitar ou ocultar o botão para colocar a tela em suspensão. **Não configurado** habilita ou desabilita o botão de ativação e suspensão da tela no dispositivo.
- **Botões de volume**: escolha **Bloquear** para impedir que o usuário ajuste o volume, desabilitando os botões de volume. **Não configurado** permite o uso dos botões de volume no dispositivo.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../device-profile-assign.md) e [monitorar seu status](../device-profile-monitor.md).

Também é possível criar perfis de quiosque para dispositivos com [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) e [Windows 10](kiosk-settings.md).
