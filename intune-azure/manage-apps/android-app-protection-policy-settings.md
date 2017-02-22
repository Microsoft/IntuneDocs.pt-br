---
title: "Configurações de política de proteção de aplicativo Android | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: este tópico descreve as configurações de política de proteção de aplicativo para dispositivos Android."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 6720c163e712e9d27319b16b0e1515e9e7f13ee8


---

# <a name="android-app-protection-policy-settings"></a>Configurações de política de proteção de aplicativo Android
As configurações de política descritas neste tópico podem ser [configuradas](app-protection-policies.md) para uma política de proteção de aplicativo na folha **Configurações** no Portal do Azure.
Há duas categorias de configurações de política: configurações de realocação de dados e configurações de acesso. Neste tópico, o termo *aplicativos gerenciados por política* refere-se a aplicativos configurados com políticas de proteção de aplicativo.

##  <a name="data-relocation-settings"></a>Configurações de realocação de dados

| Setting | Como usar | Valores padrão |
|------|------|------|
| **Impedir backups do Android** | Escolha **Sim** para impedir que esse aplicativo faça backup de dados corporativos ou de estudante no [Serviço de Backup do Android](https://developer.android.com/google/backup/index.html) Escolha **não** para permitir que esse aplicativo faça backup de dados corporativos ou de estudante.| Sim |
| **Permitir que o aplicativo transfira dados para outros aplicativos** | Especifique quais aplicativos podem receber dados desse aplicativo: <ul><li> **Aplicativos gerenciados por política**: permita a transferência apenas para outros aplicativos gerenciados por política.</li> <li>**Todos os aplicativos**: permitir a transferência para qualquer aplicativo. </li> <li>**Nenhum**: não permitir a transferência de dados para nenhum aplicativo, incluindo outros aplicativos gerenciados por política.</li></ul> | Todos os aplicativos |
| **Permitir que o aplicativo receba dados de outros aplicativos** | Especifique quais aplicativos podem transferir dados para esse aplicativo: <ul><li>**Aplicativos gerenciados por política**: permita a transferência apenas de outros aplicativos gerenciados por política.</li><li>**Todos os aplicativos**: permitir a transferência de dados de qualquer aplicativo.</li><li>**Nenhum**: não permita a transferência de dados de nenhum aplicativo, incluindo outros aplicativos gerenciados por política. | Todos os aplicativos |
| **Impedir “Salvar Como”** | Escolha **Sim** para desabilitar o uso da opção Salvar Como nesse aplicativo. Escolha **Não** se quiser permitir o uso de Salvar Como. | Não |
| **Restringir recortar, copiar e colar com outros aplicativos** | Especifique quando as ações recortar, copiar e colar podem ser usadas com esse aplicativo. Escolha: <ul><li>**Bloqueado**: não permita ações recortar, copiar e colar entre esse aplicativo e outros aplicativos.</li><li>**Aplicativos gerenciados por política**: permita ações recortar, copiar e colar entre esse aplicativo e outros aplicativos gerenciados por política.</li><li>**Aplicativos gerenciados por política com Colar Em**: permita o recorte ou a cópia entre esse aplicativo e outros aplicativos gerenciados por política. Permita que dados de qualquer aplicativo sejam colados nesse aplicativo.</li><li>**Qualquer aplicativo**: sem restrições para recortar, copiar e colar para e desse aplicativo. | Qualquer aplicativo |
|**Restringir a exibição de conteúdo da Web no Managed Browser** | Escolha **Sim** para impor que os links da Web no aplicativo sejam abertos no aplicativo Managed Browser. <br><br> Para dispositivos não registrados no Intune, os links da Web em aplicativos gerenciados por política podem ser abertos apenas no aplicativo Managed Browser. <br><br> Se estiver usando o Intune para gerenciar seus dispositivos, consulte [Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-internet-access-using-managed-browser-policies). | Não |
| **Criptografar dados do aplicativo** | Escolha **Sim** para habilitar a criptografia de dados corporativos ou de estudante nesse aplicativo. O Intune usa um esquema de criptografia do OpenSSL, juntamente com o sistema de Repositório de Chaves do Android, para criptografar os dados do aplicativo com segurança. Os dados são criptografados de forma síncrona durante tarefas de E/S de arquivo. O conteúdo no armazenamento do dispositivo é Always Encrypted. <br><br> O método de criptografia **não** tem certificação FIPS 140-2.  | Sim |
| **Desabilitar a sincronização de contatos** | Escolha **Sim** para impedir que o aplicativo salve dados no aplicativo de Contatos nativo do dispositivo. Se você escolher **Não**, o aplicativo poderá salvar dados no aplicativo de Contatos nativo do dispositivo. <br><br>Ao realizar um apagamento seletivo para remover dados corporativos ou de estudante do aplicativo, os contatos sincronizados diretamente do aplicativo para o aplicativo de Contatos nativo são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook. | Não |
| **Desabilitar a impressão** | Escolha **Sim** para impedir que o aplicativo imprima dados corporativos ou de estudante. | Não |


  >[!NOTE]
  >O método de criptografia para a configuração **Criptografar dados do aplicativo** **não** tem certificação FIPS 140-2.




##  <a name="access-settings"></a>Configurações de acesso

| Setting | Como usar | Valores padrão |
|------|------|------|
| **Exigir PIN para acesso** | Escolha **Sim** para exigir um PIN para usar esse aplicativo. O usuário deverá configurar esse PIN na primeira vez que executar o aplicativo em um contexto corporativo ou de estudante. Valor padrão = **Sim**.<br><br> Defina as seguintes configurações de força do PIN: <ul><li>**Número de tentativas antes da redefinição do PIN**: especifique o número de tentativas que o usuário deverá inserir o PIN com êxito antes de precisar redefini-lo. Valor padrão = **5**.</li><li> **Permitir PIN simples**: escolha **Sim** para permitir que os usuários usem sequências de PIN simples como 1234 ou 1111. Escolha **Não** para impedi-los de usar sequências simples. Valor padrão = **Sim**. </li><li> **Tamanho do PIN**: especifique o número mínimo de dígitos em uma sequência de PIN. Valor padrão = **4**. </li><li> **Permitir impressão digital em vez do PIN (Android 6.0+)**: escolha **Sim** para permitir que o usuário use a [autenticação por impressão digital](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) em vez de um PIN para acesso ao aplicativo. Valor padrão = **Sim**.<br><br> Em dispositivos Android, é possível permitir que o usuário prove sua identidade usando a [autenticação por impressão digital do Android](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) em vez de um PIN. Quando o usuário tenta usar esse aplicativo com sua conta corporativa ou de estudante, ele deve fornecer sua identidade de impressão digital em vez de inserir um PIN. </li></ul>| Exigir PIN: Sim <br><br> Tentativas de redefinição do PIN: 5 <br><br> Permitir PIN simples: Sim <br><br> Tamanho do PIN: 4 <br><br> Permitir impressão digital: Sim |
| **Exigir credenciais corporativas para acesso** | Escolha **Sim** para exigir que o usuário se conecte com sua conta corporativa ou de estudante em vez de inserir um PIN para acesso ao aplicativo. Se você definir como **Sim**, ele substituirá os requisitos de PIN ou da ID de Toque.  | Não |
| **Impedir que aplicativos gerenciados sejam executados em dispositivos com jailbreak ou root** |  Escolha **Sim** para impedir que esse aplicativo seja executado em dispositivos com jailbreak ou root. O usuário continuará podendo usar esse aplicativo para tarefas pessoais, mas precisará usar um dispositivo diferente para acessar dados corporativos ou de estudante nesse aplicativo. | Sim |
| **Verificar novamente os requisitos de acesso após (minutos)** | Defina as seguintes configurações: <ul><li>**Tempo limite**: especifique o tempo (em minutos) antes que os requisitos de acesso ao aplicativo sejam verificados novamente. Valor padrão = **30** minutos.</li><li>**Período de carência offline**: se o dispositivo estiver offline, especifique o período (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente. Valor padrão = **720** minutos (12 horas).</li></ul>| Tempo limite: 30 <br><br> Offline: 720 |
| **Intervalo offline antes que os dados do aplicativo sejam apagados (dias)** | Os dados corporativos ou de estudante nesse aplicativo poderão ser apagados se um dispositivo tiver ficado offline por mais tempo que um período específico. Especifique o número de dias que um dispositivo pode ficar offline antes que os dados corporativos ou de estudante sejam removidos do dispositivo. <br><br> | 90 dias |
| **Bloquear captura de tela e Assistente do Android (Android 6.0+)** | Escolha **Sim** para bloquear capturas de tela e as funcionalidades do **Assistente do Android** do dispositivo ao usar esse aplicativo. Se você escolher **Sim**, a imagem de visualização do Gerenciador de Aplicativos também ficará desfocada ao usar esse aplicativo com uma conta corporativa ou de estudante. | Não |



<!--HONumber=Feb17_HO1-->


