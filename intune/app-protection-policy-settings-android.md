---
title: "Configurações de política de proteção de aplicativo Android"
titlesuffix: Azure portal
description: "Este tópico descreve as configurações de política de proteção de aplicativo para dispositivos Android."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 635f99a0fd4857e9c0c2266371713c102ce37912
ms.sourcegitcommit: 4b776d1a87c0707244f4ae0122de882e0eef6fa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2017
---
# <a name="android-app-protection-policy-settings"></a>Configurações de política de proteção de aplicativo Android
As configurações de política descritas neste tópico podem ser [configuradas](app-protection-policies.md) para uma política de proteção de aplicativo na folha **Configurações** no Portal do Azure.
Há duas categorias de configurações de política: configurações de realocação de dados e configurações de acesso. Neste tópico, o termo *aplicativos gerenciados por política* refere-se a aplicativos configurados com políticas de proteção de aplicativo.

##  <a name="data-relocation-settings"></a>Configurações de realocação de dados

| Setting | Como usar | Valores padrão |
|------|------|------|
| **Impedir backups do Android** | Escolha **Sim** para impedir que esse aplicativo faça backup de dados corporativos ou de estudante no [Serviço de Backup do Android](https://developer.android.com/google/backup/index.html) Escolha **não** para permitir que esse aplicativo faça backup de dados corporativos ou de estudante.| Sim |
| **Permitir que o aplicativo transfira dados para outros aplicativos** | Especifique quais aplicativos podem receber dados desse aplicativo: <ul><li> **Aplicativos gerenciados por política**: permita a transferência apenas para outros aplicativos gerenciados por política.</li> <li>**Todos os aplicativos**: permitir a transferência para qualquer aplicativo. </li> <li>**Nenhum**: não permitir a transferência de dados para nenhum aplicativo, incluindo outros aplicativos gerenciados por política.</li></ul> <p>Há algumas isenções de aplicativos e serviços para os quais o Intune pode permitir transferência de dados. Consulte [Isenções de transferência de dados](#Data-transfer-exemptions) para obter uma lista completa dos aplicativos e serviços.<p>**Observação:** o Intune atualmente não dá suporte para o recurso de Aplicativos do instantâneos Android. O Intune bloqueará qualquer conexão de dados de ou para o aplicativo.  Consulte a documentação do Desenvolvedor Android para obter mais informações sobre [Aplicativos instantâneos Android](https://developer.android.com/topic/instant-apps/index.html).</p>| Todos os aplicativos |
| **Permitir que o aplicativo receba dados de outros aplicativos** | Especifique quais aplicativos podem transferir dados para esse aplicativo: <ul><li>**Aplicativos gerenciados por política**: permita a transferência apenas de outros aplicativos gerenciados por política.</li><li>**Todos os aplicativos**: permitir a transferência de dados de qualquer aplicativo.</li><li>**Nenhum**: não permita a transferência de dados de nenhum aplicativo, incluindo outros aplicativos gerenciados por política. </li></ul> <p>Há algumas isenções de aplicativos e serviços dos quais o Intune pode permitir transferência de dados. Consulte [Isenções de transferência de dados](#Data-transfer-exemptions) para obter uma lista completa dos aplicativos e serviços. | Todos os aplicativos |
| **Impedir “Salvar Como”** | Escolha **Sim** para desabilitar o uso da opção Salvar Como nesse aplicativo. Escolha **Não** se quiser permitir o uso de Salvar Como. <p><br>**Selecione em que serviços de armazenamento os dados empresariais podem ser guardados** <br>Os usuários são capazes de salvar os serviços selecionados (OneDrive for Busines, SharePoint e Armazenamento local). Todos os outros serviços serão bloqueados.</p> | Não <br><br> 0 selecionado |
| **Restringir recortar, copiar e colar com outros aplicativos** | Especifique quando as ações recortar, copiar e colar podem ser usadas com esse aplicativo. Escolha: <ul><li>**Bloqueado**: não permita ações recortar, copiar e colar entre esse aplicativo e outros aplicativos.</li><li>**Aplicativos gerenciados por política**: permita ações recortar, copiar e colar entre esse aplicativo e outros aplicativos gerenciados por política.</li><li>**Aplicativos gerenciados por política com Colar Em**: permita o recorte ou a cópia entre esse aplicativo e outros aplicativos gerenciados por política. Permita que dados de qualquer aplicativo sejam colados nesse aplicativo.</li><li>**Qualquer aplicativo**: sem restrições para recortar, copiar e colar para e desse aplicativo. | Qualquer aplicativo |
|**Restringir a exibição de conteúdo da Web no Managed Browser** | Escolha **Sim** para impor que os links da Web no aplicativo sejam abertos no aplicativo Managed Browser. <br><br> Para dispositivos não registrados no Intune, os links da Web em aplicativos gerenciados por política podem ser abertos apenas no aplicativo Managed Browser. <br><br> Se estiver usando o Intune para gerenciar seus dispositivos, consulte [Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune](app-configuration-managed-browser.md). | Não |
| **Criptografar dados do aplicativo** | Escolha **Sim** para habilitar a criptografia de dados corporativos ou de estudante nesse aplicativo. O Intune usa um esquema de criptografia do AES de 128 bits OpenSSL, juntamente com o sistema de Repositório de Chaves do Android, para criptografar os dados do aplicativo com segurança. Os dados são criptografados de forma síncrona durante tarefas de E/S de arquivo. O conteúdo no armazenamento do dispositivo sempre é criptografado. <br><br> O método de criptografia **não** tem certificação FIPS 140-2.  | Sim |
| **Desabilitar a criptografia do aplicativo quando a criptografia do dispositivo estiver habilitada** | Escolha **Sim** para desabilitar a criptografia de aplicativo para o armazenamento interno do aplicativo quando a criptografia do dispositivo for detectada em um dispositivo registrado. <br><br>**Observação:** O Intune só pode detectar o registro do dispositivo com o MDM do Intune. O armazenamento de aplicativo externo ainda será criptografado para garantir que dados não possam ser acessados por aplicativos não gerenciados. | Sim |
| **Desabilitar a sincronização de contatos** | Escolha **Sim** para impedir que o aplicativo salve dados no aplicativo de Contatos nativo do dispositivo. Se você escolher **Não**, o aplicativo poderá salvar dados no aplicativo de Contatos nativo do dispositivo. <br><br>Ao realizar um apagamento seletivo para remover dados corporativos ou de estudante do aplicativo, os contatos sincronizados diretamente do aplicativo para o aplicativo de Contatos nativo são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook. | Não |
| **Desabilitar a impressão** | Escolha **Sim** para impedir que o aplicativo imprima dados corporativos ou de estudante. | Não |

  >[!NOTE]
  >O método de criptografia para a configuração **Criptografar dados do aplicativo** **não** tem certificação FIPS 140-2.

  ## <a name="data-transfer-exemptions"></a>Isenções de transferência de dados

  Há algumas isenções de aplicativos e serviços de plataforma em que a política de proteção de aplicativo do Intune pode permitir a transferência de dados de/para eles. Por exemplo, todos os aplicativos orientados pelo Intune no Android devem ser capazes de transferir dados de e para a conversão de texto em fala do Google, para que o texto da tela do seu dispositivo móvel possa ser lido em voz alta. Esta lista está sujeita a alterações e reflete os serviços e os aplicativos considerados úteis para produtividade segura.

  ### <a name="full-exemptions"></a>Isenções completas

  Esses aplicativos e serviços têm permissão total para transferência de dados de/para aplicativos gerenciados pelo Intune.

  |Nome do aplicativo/serviço | Descrição |
  | ------ | ---- |
  | com.android.phone | Aplicativo de telefone nativo
  | com.android.vending | Google Play Store |
  | com.android.documentsui | Seletor de Documento do Android|
  | com.google.android.webview | [WebView](https://developer.android.com/reference/android/webkit/WebView.html), que é necessário para muitos aplicativos, incluindo o Outlook. |
  | com.android.webview |[WebView](https://developer.android.com/reference/android/webkit/WebView.html), que é necessário para muitos aplicativos, incluindo o Outlook.|
  | com.google.android.tts | Conversão de texto em fala do Google |
  | com.android.providers.settings | Configurações de sistema do Android |
  | com.azure.authenticator | Aplicativo Microsoft Authenticator, que é necessário para autenticação bem-sucedida em muitos cenários. |
  | com.microsoft.windowsintune.companyportal | Intune Portal da empresa|

  ### <a name="conditional-exemptions"></a>Isenções condicionais
  Esses aplicativos e serviços só têm permissão para transferência de dados de/para aplicativos gerenciados pelo Intune em determinadas condições.

  |Nome do aplicativo/serviço | Descrição | Condição de isenção|
  | ------ | ---- | --- |
  | com.android.chrome | Navegador do Google Chrome | O Chrome é usado para alguns componentes do WebView no Android 7.0 ou posterior e nunca fica oculto. Dados fluem de/para o aplicativo, no entanto, são sempre restritos.
  | com.skype.raider | Skype | O aplicativo Skype é permitido apenas para determinadas ações que resultam em uma chamada telefônica. |
  | com.android.providers.media | Provedor de conteúdo de mídia do Android | O provedor de conteúdo de mídia é permitido somente para a ação de seleção de toque. |
  | com.google.android.gms; com.google.android.gsf | Pacotes do Google Play Services | Esses pacotes são permitidos para ações do Google Cloud Messaging, como notificações por push. |



##  <a name="access-settings"></a>Configurações de acesso

| Setting | Como usar | Valores padrão |
|------|------|------|
| **Exigir PIN para acesso** | Escolha **Sim** para exigir um PIN para usar esse aplicativo. O usuário deverá configurar esse PIN na primeira vez que executar o aplicativo em um contexto corporativo ou de estudante. Valor padrão = **Sim**.<br><br> Defina as seguintes configurações de força do PIN: <ul><li>**Número de tentativas antes da redefinição do PIN**: especifique o número de tentativas que o usuário deverá inserir o PIN com êxito antes de precisar redefini-lo. Valor padrão = **5**.</li><li> **Permitir PIN simples**: escolha **Sim** para permitir que os usuários usem sequências de PIN simples como 1234 ou 1111. Escolha **Não** para impedi-los de usar sequências simples. Valor padrão = **Sim**. </li><li> **Tamanho do PIN**: especifique o número mínimo de dígitos em uma sequência de PIN. Valor padrão = **4**. </li><li> **Permitir impressão digital em vez do PIN (Android 6.0+)**: escolha **Sim** para permitir que o usuário use a [autenticação por impressão digital](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) em vez de um PIN para acesso ao aplicativo. Valor padrão = **Sim**.</li></ul> Em dispositivos Android, é possível permitir que o usuário prove sua identidade usando a [autenticação por impressão digital do Android](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) em vez de um PIN. Quando o usuário tenta usar esse aplicativo com sua conta corporativa ou de estudante, ele deve fornecer sua identidade de impressão digital em vez de inserir um PIN. </li></ul>| Exigir PIN: Sim <br><br> Tentativas de redefinição do PIN: 5 <br><br> Permitir PIN simples: Sim <br><br> Tamanho do PIN: 4 <br><br> Permitir impressão digital: Sim |
| **Exigir credenciais corporativas para acesso** | Escolha **Sim** para exigir que o usuário se conecte com sua conta corporativa ou de estudante em vez de inserir um PIN para acesso ao aplicativo. Se você definir como **Sim**, ele substituirá os requisitos de PIN ou da ID de Toque.  | Não |
| **Impedir que aplicativos gerenciados sejam executados em dispositivos com jailbreak ou root** |Escolha **Sim** para impedir que esse aplicativo seja executado em dispositivos com jailbreak ou root. O usuário continuará podendo usar esse aplicativo para tarefas pessoais, mas precisará usar um dispositivo diferente para acessar dados corporativos ou de estudante nesse aplicativo. | Sim |
| **Verificar novamente os requisitos de acesso após (minutos)** | Defina as seguintes configurações: <ul><li>**Tempo limite**: esse é o número de minutos antes que os requisitos de acesso (definidos anteriormente na política) sejam verificados novamente. Por exemplo, um administrador ativa o PIN na política, um usuário abre um aplicativo MAM e deve inserir um pin. Ao usar essa configuração, o usuário não precisa inserir um PIN em qualquer aplicativo MAM por mais **30 minutos** (valor padrão).</li><li>**Período de carência offline**: esse é o número de minutos em que os aplicativos MAM podem ser executados offline. Especifique o período (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente. Valor padrão = **720** minutos (12 horas). Após esse período expirar, o aplicativo exigirá a autenticação do usuário para o AAD para que o aplicativo possa continuar a ser executado.</li></ul>| Tempo limite: 30 <br><br> Offline: 720 |
| **Intervalo offline antes que os dados do aplicativo sejam apagados (dias)** | Após este número de dias (definido pelo administrador) de execução offline, o aplicativo exigirá que o usuário se conecte à rede e realize a autenticação novamente. Se o usuário for autenticado com êxito, ele poderá continuar a acessar seus dados e o intervalo offline será redefinido.  Se a autenticação do usuário falhar, o aplicativo realizará um apagamento seletivo dos dados e da conta do usuário.  Consulte [Como apagar somente dados corporativos de aplicativos gerenciados pelo Intune](https://docs.microsoft.com/en-us/intune/apps-selective-wipe) para obter mais informações sobre quais dados são removidos com um apagamento seletivo.<br><br> | 90 dias |
| **Bloquear captura de tela e Assistente do Android (Android 6.0+)** | Escolha **Sim** para bloquear capturas de tela e as funcionalidades do **Assistente do Android** do dispositivo ao usar esse aplicativo. Se você escolher **Sim**, a imagem de visualização do Gerenciador de Aplicativos também ficará desfocada ao usar esse aplicativo com uma conta corporativa ou de estudante. | Não |
| **Desabilitar o PIN do aplicativo quando o PIN do dispositivo for gerenciado** | Escolha **Sim** para desabilitar o PIN do aplicativo quando um bloqueio de dispositivo for detectado em um dispositivo registrado. | Não |
