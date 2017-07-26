---
title: "Configurações de política de proteção de aplicativo iOS"
titleSuffix: Intune on Azure
description: "Este tópico descreve as configurações de política de proteção de aplicativo para dispositivos iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 272628c501d15dc9661a1110e7dcab2d0e9f1d02
ms.sourcegitcommit: 21a9db380956a50031dbea360b4c76664cbc2768
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2017
---
#  <a name="ios-app-protection-policy-settings"></a>Configurações de política de proteção de aplicativo iOS
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As configurações de política descritas neste tópico podem ser [configuradas](app-protection-policies.md) para uma política de proteção de aplicativo na folha **Configurações** no Portal do Azure.

Há duas categorias de configurações de política: configurações de realocação de dados e configurações de acesso. Neste tópico, o termo ***aplicativos gerenciados por política*** refere-se a aplicativos configurados com políticas de proteção de aplicativo.

##  <a name="data-relocation-settings"></a>Configurações de realocação de dados

| Setting | Como usar | Valor padrão |
|------|------|------|
| **Impedir backups do iTunes e iCloud** | Escolha **Sim** para impedir que esse aplicativo faça backup de dados corporativos ou de estudante no iTunes e iCloud. Escolha **Não** para permitir que esse aplicativo faça backup de dados corporativos ou de estudante no iTunes e iCloud.| Sim |
| **Permitir que o aplicativo transfira dados para outros aplicativos** | Especifique quais aplicativos podem receber dados desse aplicativo: <ul><li> **Aplicativos gerenciados por política**: permita a transferência apenas para outros aplicativos gerenciados por política.</li> <li>**Todos os aplicativos**: permitir a transferência para qualquer aplicativo. </li> <li>**Nenhum**: não permitir a transferência de dados para nenhum aplicativo, incluindo outros aplicativos gerenciados por política.</li></ul> Além disso, se você definir essa opção como **Aplicativos gerenciados pela política** ou **Nenhum**, o recurso do iOS 9 que permite que a Busca do Spotlight pesquise dados em aplicativos será bloqueado. <br><br> Há algumas isenções de aplicativos e serviços para os quais o Intune pode permitir transferência de dados. Consulte [Isenções de transferência de dados](#Data-transfer-exemptions) para obter uma lista completa dos aplicativos e serviços. | Todos os aplicativos |
| **Permitir que o aplicativo receba dados de outros aplicativos** | Especifique quais aplicativos podem transferir dados para esse aplicativo: <ul><li>**Aplicativos gerenciados por política**: permita a transferência apenas de outros aplicativos gerenciados por política.</li><li>**Todos os aplicativos**: permitir a transferência de dados de qualquer aplicativo.</li><li>**Nenhum**: não permita a transferência de dados de nenhum aplicativo, incluindo outros aplicativos gerenciados por política.</li></ul> Há algumas isenções de aplicativos e serviços dos quais o Intune pode permitir transferência de dados. Consulte [Isenções de transferência de dados](#Data-transfer-exemptions) para obter uma lista completa dos aplicativos e serviços.  | Todos os aplicativos |
| **Impedir “Salvar Como”** | Escolha **Sim** para desabilitar o uso da opção Salvar Como nesse aplicativo. Escolha **Não** se quiser permitir o uso de Salvar Como. | Não |
| **Restringir recortar, copiar e colar com outros aplicativos** | Especifique quando as ações recortar, copiar e colar podem ser usadas com esse aplicativo. Escolha: <ul><li>**Bloqueado**: não permita ações recortar, copiar e colar entre esse aplicativo e outros aplicativos.</li><li>**Aplicativos gerenciados por política**: permita ações recortar, copiar e colar entre esse aplicativo e outros aplicativos gerenciados por política.</li><li>**Aplicativos gerenciados por política com Colar Em**: permita o recorte ou a cópia entre esse aplicativo e outros aplicativos gerenciados por política. Permita que dados de qualquer aplicativo sejam colados nesse aplicativo.</li><li>**Qualquer aplicativo**: sem restrições para recortar, copiar e colar para e desse aplicativo. | Qualquer aplicativo |
|**Restringir a exibição de conteúdo da Web no Managed Browser** | Escolha **Sim** para impor que os links da Web no aplicativo sejam abertos no aplicativo Managed Browser. <br><br> Para dispositivos não registrados no Intune, os links da Web em aplicativos gerenciados por política podem ser abertos apenas no aplicativo Managed Browser. <br><br> Se estiver usando o Intune para gerenciar seus dispositivos, consulte [Gerenciar o acesso à Internet usando políticas do navegador gerenciado com o Microsoft Intune](app-configuration-managed-browser.md). | Não |
| **Criptografar dados do aplicativo** | Para aplicativos gerenciados por política, os dados são criptografados em repouso usando o esquema de criptografia do dispositivo fornecido pelo iOS. Quando um PIN é necessário, os dados são criptografados de acordo com as configurações da política de proteção do aplicativo. <br><br> Acesse a documentação oficial da Apple [aqui](https://support.apple.com/HT202739) para ver quais módulos de criptografia do iOS têm certificação FIPS 140-2 ou cuja certificação FIPS 140-2 está pendente. <br><br> Especifique quando os dados corporativos ou de estudante nesse aplicativo são criptografados. Escolha: <ul><li>**Quando o dispositivo está bloqueado**: todos os dados de aplicativo associados a essa política são criptografados quando o dispositivo está bloqueado.</li><li>**Quando o dispositivo está bloqueado e há arquivos abertos**: todos os dados de aplicativo associados a essa política são criptografados quando o dispositivo está bloqueado, exceto pelos dados nos arquivos que estão abertos no aplicativo.</li><li>**Após a reinicialização do dispositivo**: todos os dados de aplicativo associados a essa política são criptografados quando o dispositivo é reiniciado, até que o dispositivo seja desbloqueado pela primeira vez.</li><li>**Usar configurações do dispositivo**: os dados do aplicativo são criptografados com base nas configurações padrão do dispositivo. </li></ul> Quando você habilita essa configuração, talvez o usuário tenha que configurar e usar um PIN para acessar o dispositivo.  Se não houver nenhum PIN de dispositivo e a criptografia for necessária, os aplicativos não serão abertos e o usuário deverá definir um PIN com a mensagem: “Para acessar este aplicativo, sua organização exige primeiro a habilitação de um PIN de dispositivo.”  | Quando o dispositivo está bloqueado |
| **Desabilitar a sincronização de contatos** | Escolha **Sim** para impedir que o aplicativo salve dados no aplicativo de Contatos nativo do dispositivo. Se você escolher **Não**, o aplicativo poderá salvar dados no aplicativo de Contatos nativo do dispositivo. <br><br>Ao realizar um apagamento seletivo para remover dados corporativos ou de estudante do aplicativo, os contatos sincronizados diretamente do aplicativo para o aplicativo de Contatos nativo são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook. | Não |
| **Desabilitar a impressão** | Escolha **Sim** para impedir que o aplicativo imprima dados corporativos ou de estudante. | Não |
| **Selecione em que serviços de armazenamento os dados empresariais podem ser guardados** | Os usuários podem salvar para os serviços selecionados (OneDrive for Business, SharePoint e Armazenamento Local). Todos os outros serviços serão bloqueados. | 0 selecionado |

> [!NOTE]
> Nenhuma das configurações de relocação de dados controla o recurso “Open-in” gerenciado pela Apple em dispositivos iOS. Para usar o recurso “Open-in” gerenciado pela Apple, consulte [Gerenciar a transferência de dados entre aplicativos iOS com o Microsoft Intune](data-transfer-between-apps-manage-ios.md).

## <a name="data-transfer-exemptions"></a>Isenções de transferência de dados

Há algumas isenções de aplicativos e serviços de plataforma em que a política de proteção de aplicativo do Intune pode permitir a transferência de dados de/para determinados cenários. Esta lista está sujeita a alterações e reflete os serviços e os aplicativos considerados úteis para produtividade segura.

| Nomes do aplicativo/serviço | Descrição |
| ---- | --- |
|tel; telprompt | Aplicativo de telefone nativo |
| skype | Skype |
| app-settings | Configurações do dispositivo |
| itms; itmss; itms-apps; itms-appss; itms-services | Loja de aplicativos |
| calshow | Calendário nativo |




## <a name="access-settings"></a>Configurações de acesso

| Setting | Como usar | Valor padrão |
|------|------|------|
| **Exigir PIN para acesso** | Escolha **Sim** para exigir um PIN para usar esse aplicativo. O usuário deverá configurar esse PIN na primeira vez que executar o aplicativo em um contexto corporativo ou de estudante. Valor padrão = **Sim**.<br><br> Defina as seguintes configurações de força do PIN: <ul><li>**Número de tentativas antes da redefinição do PIN**: especifique o número de tentativas que o usuário deverá inserir o PIN com êxito antes de precisar redefini-lo. Valor padrão = **5**.</li><li> **Permitir PIN simples**: escolha **Sim** para permitir que os usuários usem sequências de PIN simples como 1234 ou 1111. Escolha **Não** para impedi-los de usar sequências simples. Valor padrão = **Sim**. </li><li> **Tamanho do PIN**: especifique o número mínimo de dígitos em uma sequência de PIN. Valor padrão = **4**. </li><li> **Permitir impressão digital em vez do PIN (iOS 8.0+)**: escolha **Sim** para permitir que o usuário use uma [ID de Toque](https://support.apple.com/HT201371) em vez de um PIN para acesso ao aplicativo. Valor padrão = **Sim**</li></ul> Em dispositivos iOS, é possível permitir que o usuário prove sua identidade usando uma [ID de Toque](https://support.apple.com/HT201371) em vez de um PIN. Quando o usuário tenta usar esse aplicativo com sua conta corporativa ou de estudante, ele deve fornecer sua identidade de impressão digital em vez de inserir um PIN. Quando essa configuração for habilitada, a imagem de visualização do alternador de aplicativo será indefinida enquanto usar uma conta corporativa ou escolar. </li></ul>| Exigir PIN: Sim <br><br> Tentativas de redefinição do PIN: 5 <br><br> Permitir PIN simples: Sim <br><br> Tamanho do PIN: 4 <br><br> Permitir impressão digital: Sim |
| **Exigir credenciais corporativas para acesso** | Escolha **Sim** para exigir que o usuário se conecte com sua conta corporativa ou de estudante em vez de inserir um PIN para acesso ao aplicativo. Se você definir como **Sim**, ele substituirá os requisitos de PIN ou da ID de Toque.  | Não |
| **Impedir que aplicativos gerenciados sejam executados em dispositivos com jailbreak ou root** |  Escolha **Sim** para impedir que esse aplicativo seja executado em dispositivos com jailbreak ou root. O usuário continuará podendo usar esse aplicativo para tarefas pessoais, mas precisará usar um dispositivo diferente para acessar dados corporativos ou de estudante nesse aplicativo. | Sim |
| **Verificar novamente os requisitos de acesso após (minutos)** | Defina as seguintes configurações: <ul><li>**Tempo limite**: esse é o número de minutos antes que os requisitos de acesso (definidos anteriormente na política) sejam verificados novamente. Por exemplo, um administrador ativa o PIN na política, um usuário abre um aplicativo MAM e deve inserir um pin. Ao usar essa configuração, o usuário não precisa inserir um PIN em qualquer aplicativo MAM por mais **30 minutos** (valor padrão).</li><li>**Período de carência offline**: esse é o número de minutos em que os aplicativos MAM podem ser executados offline. Especifique o período (em minutos) antes que os requisitos de acesso do aplicativo sejam verificados novamente. Valor padrão = **720** minutos (12 horas). Após esse período expirar, o aplicativo exigirá a autenticação do usuário para o AAD para que o aplicativo possa continuar a ser executado.</li></ul>| Tempo limite: 30 <br><br> Offline: 720 |
| **Intervalo offline antes que os dados do aplicativo sejam apagados (dias)** | Após este número de dias (definido pelo administrador) de execução offline, o aplicativo fará um apagamento seletivo. Essa limpeza seletiva é a mesma limpeza que a que pode ser iniciada pelo administrador no fluxo de trabalho de apagamento MAM. <br><br> | 90 dias |
| **Desabilitar o PIN do aplicativo quando o PIN do dispositivo for gerenciado** | Escolha **Sim** para desabilitar o PIN do aplicativo quando um bloqueio de dispositivo for detectado em um dispositivo registrado. | Não |
| **Exigir o sistema operacional iOS mínimo** | Escolha **Sim** para exigir um sistema operacional iOS mínimo para usar este aplicativo. O usuário não poderá acessar se a versão do iOS no dispositivo não atender ao requisito. Esta política dá suporte a um único ponto decimal, por exemplo, iOS 10.3. | Não |
| **Exigir o sistema operacional iOS mínimo (Somente aviso)** | Escolha **Sim** para exigir um sistema operacional iOS mínimo para usar este aplicativo. O usuário verá uma notificação se a versão do iOS no dispositivo não atender ao requisito. Essa notificação pode ser descartada. Esta política dá suporte a um único ponto decimal, por exemplo, iOS 10.3. | Não |
| **Exigir versão mínima do aplicativo** | Escolha **Sim** para exigir uma versão mínima do aplicativo para poder usá-lo. O usuário tem o acesso bloqueado se a versão do aplicativo no dispositivo não atende ao requisito.<br><br>Como os aplicativos geralmente têm esquemas de controle de versão diferentes entre si, crie uma política com uma versão mínima de aplicativo que direciona um aplicativo (por exemplo, “política de versão do Outlook”). <br><br> | Não | 
| **Exigir versão mínima do aplicativo (somente Aviso)** | Escolha **Sim** para recomendar uma versão mínima de aplicativo para usar esse aplicativo. O usuário vê uma notificação se a versão do aplicativo no dispositivo não atende ao requisito. Essa notificação pode ser descartada.<br><br>Como os aplicativos geralmente têm esquemas de controle de versão diferentes entre si, crie uma política com uma versão mínima de aplicativo que direciona um aplicativo (por exemplo, “política de versão do Outlook”). <br><br> | Não | 
| **Exigir versão mínima do SDK de política de proteção de aplicativo do Intune** | Escolha **Sim** para exigir uma versão mínima do SDK de política de proteção de aplicativo do Intune no aplicativo. O usuário tem o acesso bloqueado se a versão do SDK da política de Proteção de Aplicativo do Intune do aplicativo não atende ao requisito. <br> <br> Para saber mais sobre o SDK de política de proteção de aplicativo do Intune, veja [Visão geral do SDK de aplicativo do Intune](app-sdk.md) <br><br> | Não |


##  <a name="add-ins-for-outlook-app"></a>Suplementos do aplicativo do Outlook

Recentemente, o Outlook trouxe suplementos para o Outlook para iOS que permitem integrar aplicativos populares ao cliente de email. Os suplementos para Outlook estão disponíveis na Web, Windows, Mac e Outlook para iOS. Como os suplementos são gerenciados pelo Microsoft Exchange, os usuários poderão compartilhar dados e mensagens entre o Outlook e aplicativos de suplementos não gerenciados, a menos que os suplementos sejam desativados para o usuário pelo Exchange.

Se você quiser impedir que os usuários finais acessem e instalem suplementos do Outlook (isso afeta todos os clientes do Outlook), verifique se você tem as seguintes alterações em funções no Centro de administração do Exchange:

- Para impedir que os usuários instalem os suplementos da Office Store, remova a função My Marketplace deles.
- Para impedir que usuários carreguem suplementos lateralmente, remova a função de Meus Aplicativos Personalizados deles.
- Para impedir que os usuários instalem todo e qualquer suplemento, remova ambas as funções Meus Aplicativos Personalizados e My Marketplace deles.

Essas instruções se aplicam ao Office 365, Exchange 2016 e Exchange 2013 no Outlook na Web, Windows, Mac e celular.

- Saiba mais sobre [suplementos do Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Saiba mais sobre [como especificar os administradores e usuários que podem instalar e gerenciar suplementos para aplicativos do Outlook](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).
