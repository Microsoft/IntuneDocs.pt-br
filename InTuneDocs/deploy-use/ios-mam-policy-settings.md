---
title: "Configurações da política de MAM do iOS | Microsoft Docs"
description: "Este tópico descreve as configurações de política de gerenciamento de aplicativo móvel para dispositivos iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d80f548f0c1382e1bd024bd31078d2a4e6366656
ms.openlocfilehash: a2130fa76f66528f6e77c720bc93286e0d01aba2


---

#  <a name="ios-mobile-app-management-policy-settings"></a>Configurações de política de gerenciamento de aplicativo móvel iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As configurações de política descritas neste tópico podem ser [configuradas](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para uma política de MAM (gerenciamento de aplicativo móvel) na folha **Configurações** no portal do Azure.

Há duas categorias de configurações de política: configurações de realocação de dados e configurações de acesso. Neste tópico, o termo _**aplicativos gerenciados por política**_ refere-se a aplicativos configurados com políticas de MAM.

##  <a name="data-relocation-settings"></a>Configurações de realocação de dados

| Setting | Como usar | Valor padrão |
|------|------|------|
| **Impedir backups do iTunes e iCloud** | Escolha **Sim** para impedir que esse aplicativo faça backup de dados corporativos ou de estudante no iTunes e iCloud. Escolha **Não** para permitir que esse aplicativo faça backup de dados corporativos ou de estudante no iTunes e iCloud.| Sim |
| **Permitir que o aplicativo transfira dados para outros aplicativos** | Especifique quais aplicativos podem receber dados desse aplicativo: <ul><li> **Aplicativos gerenciados por política**: permita a transferência apenas para outros aplicativos gerenciados por política.</li> <li>**Todos os aplicativos**: permitir a transferência para qualquer aplicativo. </li> <li>**Nenhum**: não permitir a transferência de dados para nenhum aplicativo, incluindo outros aplicativos gerenciados por política.</li></ul> Além disso, se você definir essa opção como **Aplicativos gerenciados pela política** ou **Nenhum**, o recurso do iOS 9 que permite que a Busca do Spotlight pesquise dados em aplicativos será bloqueado. <br><br> | Todos os aplicativos |
| **Permitir que o aplicativo receba dados de outros aplicativos** | Especifique quais aplicativos podem transferir dados para esse aplicativo: <ul><li>**Aplicativos gerenciados por política**: permita a transferência apenas de outros aplicativos gerenciados por política.</li><li>**Todos os aplicativos**: permitir a transferência de dados de qualquer aplicativo.</li><li>**Nenhum**: não permita a transferência de dados de nenhum aplicativo, incluindo outros aplicativos gerenciados por política. | Todos os aplicativos |
| **Impedir “Salvar Como”** | Escolha **Sim** para desabilitar o uso da opção Salvar Como nesse aplicativo. Escolha **Não** se quiser permitir o uso de Salvar Como. | Não |
| **Restringir recortar, copiar e colar com outros aplicativos** | Especifique quando as ações recortar, copiar e colar podem ser usadas com esse aplicativo. Escolha: <ul><li>**Bloqueado**: não permita ações recortar, copiar e colar entre esse aplicativo e outros aplicativos.</li><li>**Aplicativos gerenciados por política**: permita ações recortar, copiar e colar entre esse aplicativo e outros aplicativos gerenciados por política.</li><li>**Aplicativos gerenciados por política com Colar Em**: permita o recorte ou a cópia entre esse aplicativo e outros aplicativos gerenciados por política. Permita que dados de qualquer aplicativo sejam colados nesse aplicativo.</li><li>**Qualquer aplicativo**: sem restrições para recortar, copiar e colar para e desse aplicativo. | Qualquer aplicativo |
|**Restringir a exibição de conteúdo da Web no Managed Browser** | Escolha **Sim** para impor que os links da Web no aplicativo sejam abertos no aplicativo Managed Browser. <br><br> Para dispositivos não registrados no Intune, os links da Web em aplicativos gerenciados por política podem ser abertos apenas no aplicativo Managed Browser. <br><br> Se estiver usando o Intune para gerenciar seus dispositivos, consulte [Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune](manage-internet-access-using-managed-browser-policies.md). | Não |
| **Criptografar dados do aplicativo** | Para aplicativos gerenciados por política, os dados são criptografados em repouso usando o esquema de criptografia do dispositivo fornecido pelo iOS. Quando um PIN é necessário, os dados são criptografados de acordo com as configurações da política de proteção do aplicativo. <br><br> Acesse a documentação oficial da Apple [aqui](https://support.apple.com/HT202739) para ver quais módulos de criptografia do iOS têm certificação FIPS 140-2 ou cuja certificação FIPS 140-2 está pendente. <br><br> Especifique quando os dados corporativos ou de estudante nesse aplicativo são criptografados. Escolha: <ul><li>**Quando o dispositivo está bloqueado**: todos os dados de aplicativo associados a essa política são criptografados quando o dispositivo está bloqueado.</li><li>**Quando o dispositivo está bloqueado e há arquivos abertos**: todos os dados de aplicativo associados a essa política são criptografados quando o dispositivo está bloqueado, exceto pelos dados nos arquivos que estão abertos no aplicativo.</li><li>**Após a reinicialização do dispositivo**: todos os dados de aplicativo associados a essa política são criptografados quando o dispositivo é reiniciado, até que o dispositivo seja desbloqueado pela primeira vez.</li><li>**Usar configurações do dispositivo**: os dados do aplicativo são criptografados com base nas configurações padrão do dispositivo. <br><br> Quando você habilita essa configuração, é obrigatório que o usuário configure e use um PIN para acessar o dispositivo.  Se não houver nenhum PIN, os aplicativos não serão abertos e o usuário deverá definir um PIN com a mensagem: “Para acessar este aplicativo, sua organização exige primeiro a habilitação de um PIN de dispositivo”. </li></ul> | Quando o dispositivo está bloqueado |
| **Desabilitar a sincronização de contatos** | Escolha **Sim** para impedir que o aplicativo salve dados no aplicativo de Contatos nativo do dispositivo. Se você escolher **Não**, o aplicativo poderá salvar dados no aplicativo de Contatos nativo do dispositivo. <br><br>Ao realizar um apagamento seletivo para remover dados corporativos ou de estudante do aplicativo, os contatos sincronizados diretamente do aplicativo para o aplicativo de Contatos nativo são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook. | Não |
| **Desabilitar a impressão** | Escolha **Sim** para impedir que o aplicativo imprima dados corporativos ou de estudante. | Não |


> [!NOTE]
> Nenhuma das configurações de relocação de dados controla o recurso “Open-in” gerenciado pela Apple em dispositivos iOS. Para usar o recurso “Open-in” gerenciado pela Apple, consulte [Gerenciar a transferência de dados entre aplicativos iOS com o Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).


## <a name="access-settings"></a>Configurações de acesso

| Setting | Como usar | Valor padrão |
|------|------|------|
| **Exigir PIN para acesso** | Escolha **Sim** para exigir um PIN para usar esse aplicativo. O usuário deverá configurar esse PIN na primeira vez que executar o aplicativo em um contexto corporativo ou de estudante. Valor padrão = **Sim**.<br><br> Defina as seguintes configurações de força do PIN: <ul><li>**Número de tentativas antes da redefinição do PIN**: especifique o número de tentativas que o usuário deverá inserir o PIN com êxito antes de precisar redefini-lo. Valor padrão = **5**.</li><li> **Permitir PIN simples**: escolha **Sim** para permitir que os usuários usem sequências de PIN simples como 1234 ou 1111. Escolha **Não** para impedi-los de usar sequências simples. Valor padrão = **Sim**. </li><li> **Tamanho do PIN**: especifique o número mínimo de dígitos em uma sequência de PIN. Valor padrão = **4**. </li><li> **Permitir impressão digital em vez do PIN (iOS 8.0+)**: escolha **Sim** para permitir que o usuário use uma [ID de Toque](https://support.apple.com/en-us/HT201371) em vez de um PIN para acesso ao aplicativo. Valor padrão = **Sim**.<br><br> Em dispositivos iOS, é possível permitir que o usuário prove sua identidade usando uma [ID de Toque](https://support.apple.com/en-us/HT201371) em vez de um PIN. Quando o usuário tenta usar esse aplicativo com sua conta corporativa ou de estudante, ele deve fornecer sua identidade de impressão digital em vez de inserir um PIN. </li></ul>| Exigir PIN: Sim <br><br> Tentativas de redefinição do PIN: 5 <br><br> Permitir PIN simples: Sim <br><br> Tamanho do PIN: 4 <br><br> Permitir impressão digital: Sim |
| **Exigir credenciais corporativas para acesso** | Escolha **Sim** para exigir que o usuário se conecte com sua conta corporativa ou de estudante em vez de inserir um PIN para acesso ao aplicativo. Se você definir como **Sim**, ele substituirá os requisitos de PIN ou da ID de Toque.  | Não |
| **Impedir que aplicativos gerenciados sejam executados em dispositivos com jailbreak ou root** |  Escolha **Sim** para impedir que esse aplicativo seja executado em dispositivos com jailbreak ou root. O usuário continuará podendo usar esse aplicativo para tarefas pessoais, mas precisará usar um dispositivo diferente para acessar dados corporativos ou de estudante nesse aplicativo. | Sim |
| **Verificar novamente os requisitos de acesso após (minutos)** | Defina as seguintes configurações: <ul><li>**Tempo limite**: especifique o tempo (em minutos) antes que os requisitos de acesso ao aplicativo sejam verificados novamente. Valor padrão = **30** minutos.</li><li>**Período de carência offline**: se o dispositivo estiver offline, especifique o período (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente. Valor padrão = **720** minutos (12 horas).</li></ul>| Tempo limite: 30 <br><br> Offline: 720 |
| **Intervalo offline antes que os dados do aplicativo sejam apagados (dias)** | Os dados corporativos ou de estudante nesse aplicativo poderão ser apagados se um dispositivo tiver ficado offline por mais tempo que um período específico. Especifique o número de dias que um dispositivo pode ficar offline antes que os dados corporativos ou de estudante sejam removidos do dispositivo. <br><br> | 90 dias |



<!--HONumber=Dec16_HO3-->


