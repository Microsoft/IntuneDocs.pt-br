---
title: "Configurações de política do iOS | Microsoft Intune"
description: "Crie políticas que controlam as configurações e os recursos nos dispositivos iOS que você gerencia com o Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 947328a5c28839d8227a9e5ae0dd8b1fc5ad8e81
ms.openlocfilehash: 63bc2cedf8d81b050a384a947a0b43827de5c352


---

# Configurações de política do iOS no Microsoft Intune

O Intune fornece uma variedade de configurações gerais internas que você pode definir em dispositivos iOS. Além disso, use a ferramenta Apple Configurator para criar configurações personalizadas que não estão disponíveis no Intune.

## Definições de política de configuração geral

Use a **Política de configuração geral do iOS** do Microsoft Intune para definir configurações para:

-   **Configurações gerais de segurança de dispositivo** – Escolha em uma lista de configurações predefinidas que permitem controlar uma variedade de recursos e funcionalidade do dispositivo.

-   **Modo de quiosque** - bloqueia um dispositivo para permitir que apenas alguns recursos funcionem. Por exemplo, você pode permitir que um dispositivo execute apenas um aplicativo gerenciado que você especificar ou pode desabilitar os botões de volume em um dispositivo. Essas configurações podem ser usadas para um modelo de demonstração de um dispositivo ou um dispositivo que é dedicado a apenas uma função, como um dispositivo de ponto de venda.

-   **Aplicativos compatíveis e não compatíveis** - especifique uma lista de aplicativos que são compatíveis ou não com sua empresa. Nos dispositivos Android e iOS, o **Relatório de aplicativos incompatíveis** pode ser usado para exibir a compatibilidade de aplicativos especificados na lista em relação as aplicativos que os usuários instalaram (mas não é possível realmente bloquear a instalação do aplicativo).

> [!TIP]
> Você pode configurar os termos e condições de usuários para garantir que eles reconhecem que aplicativos no seu dispositivo, incluindo aplicativos pessoais, serão avaliados, e aplicativos incompatíveis serão bloqueados, ou relatados como não compatível. Os usuários devem aceitar esses termos e condições antes de registrar seus dispositivos e usar o portal da empresa para obter aplicativos. Para saber mais sobre os termos e condições de uso, consulte [Terms and conditions policy settings in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md) (Configurações de políticas de termos e condições de uso no Microsoft Intune).

Se a configuração que você está procurando não aparecer nesse tópico, você poderá criá-la usando uma política personalizada do iOS que lhe permite importar configurações criadas usando a [Ferramenta configuradora da Apple](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Para obter mais informações, consulte **Configurações de política personalizadas** mais adiante neste tópico.

### Configurações de segurança
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Exigir uma senha para desbloquear os dispositivos móveis**|Especifique se os usuários serão solicitados a inserir uma senha para acessar seu dispositivo.|
|**Tipo de senha necessária**|Especifica o tipo de senha necessária, por exemplo, apenas numérica ou alfanumérica.|
|**Número de caracteres complexos necessários na senha**|Isso especifica o número de caracteres de símbolo (como **#** ou **@**) que deve ser incluído na senha.|
|**Comprimento mínimo da senha**|Especifica o número mínimo de caracteres na senha.|
|**Permitir senha simples**|Permita senhas simples como '0000' e '1234'.|
|**Número de falhas de logon repetidas permitido antes do dispositivo ser apagado**|Apaga o dispositivo se houver falha neste número de tentativas de logon.|
|**Minutos de inatividade antes de a senha ser necessária**<sup>1</sup>|Especifica quanto tempo o dispositivo pode permanecer ocioso antes que o usuário precise digitar novamente sua senha.|
|**Expiração da senha (dias)**|Especifica o número de dias antes que a senha do dispositivo precise ser alterada.|
|**Lembrar de histórico de senha**|Especifica se o usuário pode usar senhas que tenha usado anteriormente.|
|**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**|Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.|
|**Minutos de inatividade antes que a tela se apague**<sup>1</sup>|Especifique o número de minutos antes de a tela do dispositivo ser desativada.|
|**Permitir desbloqueio de impressão digital**|Permitir usar a impressão digital para desbloquear o dispositivo.|
<sup>1</sup> Para dispositivos iOS, quando você define as configurações **Minutos de inatividade antes de a tela desligar** e **Minutos de inatividade antes de a senha ser solicitada**, eles são aplicados em sequência. Por exemplo, se você define o valor de ambas as configurações para **5** minutos, a tela desliga automaticamente após 5 minutos e o dispositivo é bloqueado após outros 5 minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo é bloqueado 5 minutos depois de o usuário desligar a tela.

### Configurações de sistema
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir captura de tela**|Permite ao usuário capturar os conteúdos da tela como uma imagem.|
|**Permitir centro de controle na tela de bloqueio**|Controla se o aplicativo do centro de controle pode ser acessado quando o dispositivo estiver bloqueado.|
|**Permitir exibir notificações na tela de bloqueio**|Permitir ao usuário acessar a exibição de notificações sem desbloquear o dispositivo.|
|**Permitir exibição atual na tela de bloqueio**|Controla se as notificações podem ser exibidas quando o dispositivo estiver bloqueado.|
|**Permitir certificados de TLS não confiáveis**|Permitir certificados do protocolo TLS não confiáveis no dispositivo.|
|**Permitir envio de dados diagnósticos**|Permitir ou bloquear a habilidade do dispositivo enviar dados de diagnóstico para a Apple.|
|**Permitir senha quando bloqueado**|Permitir ao usuário acessar o aplicativo de senha enquanto o dispositivo estiver bloqueado.|

### Configurações de nuvem – documentos e dados
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir backup no iCloud**|Permite ao usuário fazer backup do dispositivo no iCloud.|
|**Permitir sincronização do documento com o iCloud**|Permitir a sincronização de documento e chave-valor para o espaço de armazenamento no iCloud.|
|**Permitir sincronização do Photo Stream com o iCloud**|Permitir a sincronização de fotos no dispositivo com o iCloud.|
|**Requer Backup com criptografia**|Exigir que quaisquer backups de dispositivo sejam criptografados.|
|**Permitir que aplicativos gerenciados sincronizem dados no iCloud**|Permitir que os aplicativos que você gerencia com o Intune sincronizem dados com a conta do iCloud dos usuários.|
|**Permitir que a Entrega continue as atividades em outro dispositivo**|A Entrega permite que você continue o trabalho iniciado em um dispositivo iOS em outro dispositivo iOS ou Mac OS X.|

### Configurações de aplicativo - navegador
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir Safari**|Especifique se o navegador Safari pode ser usado no dispositivo.|
|**Permitir preenchimento automático**|O usuário pode alterar as configurações de preenchimento automático no navegador.|
|**Permitir bloqueador de pop-up**|Habilitar ou desabilitar o bloqueador de pop-up do navegador.|
|**Permitir cookies**|Permitir que o navegador da Web do dispositivo use cookies.|
|**Permitir scripts Java**|Permitir a execução de scripts Java no navegador.|
|**Permitir aviso de fraude**|Permitir avisos de fraude no navegador do dispositivo.|

### Configurações de aplicativo - aplicativos
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir loja de aplicativo**|Permite que o dispositivo acesse a loja de aplicativos.|
|**Exigir uma senha para acessar a loja de aplicativo**|Exigir que o usuário insira uma senha antes de poder visitar a loja de aplicativos.|
|**Permitir aquisições em aplicativo**|Permitir que aquisições da loja sejam feitas de um aplicativo em execução.|
|**Permitir documentos gerenciados em outros aplicativos não gerenciados**|Permite que documentos corporativos sejam exibidos em qualquer aplicativo.<br>**Exemplo:** você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox. Defina essa configuração como não. Depois que o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permitirá salvar.|
|**Permitir documentos não gerenciados em outros aplicativos gerenciados**|Permitir que qualquer documento seja exibido em aplicativos gerenciados corporativos.|
|**Permitir videoconferência**|Permitir aplicativos de videoconferência como Facetime no dispositivo.|
|**Permitir conteúdo de adulto na loja de mídia**|Permitir ao dispositivo acessar o conteúdo classificado como adulto na loja.|
|**Permitir que o usuário baixe o conteúdo da iBook Store sinalizado como 'Erotismo'**|Permitir que o usuário baixe livros da categoria “Erotismo”.|

### Configurações de aplicativo - Jogos
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir adição de amigos no Game Center**|Permitir que o usuário adicione amigos no Game Center.|
|**Permitir jogo multiplayer**|Permitir que o usuário execute jogos com vários participantes no dispositivo.|

### Configurações de recursos do dispositivo - hardware
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir câmera**|Especifica se a câmera no dispositivo pode ser usada.|
|**Exigir uma senha de emparelhamento para solicitações de saída do AirPlay**|O AirPlay permite transmitir conteúdo para outros dispositivos da Apple. Use essa configuração para exigir uma senha de emparelhamento para se conectar a outros dispositivos.|

### Configurações de recursos do dispositivo - celular
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir roaming de Voz**|Permitir roaming de voz quando o dispositivo estiver em uma rede de celular.|
|**Permitir roaming de Dados**|Permitir roaming de dados quando o dispositivo estiver em uma rede de celular.|
|**Permitir busca em segundo plano global durante roaming**|Permitir ao dispositivo buscar dados, como emails, durante roaming na rede celular.|

### Configurações de recursos do dispositivo - recursos
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir Siri**|Permitir o uso do Assistente de voz Siri no dispositivo.|
|**Permitir Siri enquanto o dispositivo está bloqueado**|Permitir o uso do Assistente de voz Siri no dispositivo enquanto ele estiver bloqueado.|
|**Permitir discagem de voz**|Permitir o uso do recurso de discagem por voz no dispositivo.|


### Configurações para aplicativos compatíveis e não compatíveis
Na lista **Aplicativos Compatíveis &amp; Incompatíveis**, especifique uma lista de aplicativos compatíveis ou incompatíveis usando as seguintes informações:

> [!NOTE]
> Uma única política só pode conter uma lista de compatibilidade ou de incompatibilidade. Não é possível especificar ambos na mesma política.

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Reportar não conformidade quando os usuários instalam os aplicativos listados**|Lista os aplicativos que não são gerenciados pelo Intune, para os quais os usuários não têm permissão para instalar e executar.|
|**Relatar não conformidade quando os usuários instalam aplicativos não listados**|Lista os aplicativos que os usuários têm permissão para instalar. Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.|
|**Adicionar**|Adiciona um aplicativo à lista selecionada. Especifique um nome da sua preferência, opcionalmente o editor do aplicativo, e a URL para o aplicativo na loja de aplicativos. Leia **Como especificar URLs para lojas de aplicativos** mais adiante neste tópico para obter mais ajuda.|
|**Importar aplicativos**|Importa uma lista dos aplicativos que você especificou em um arquivo de valores separados por vírgulas. Use o formato, nome do aplicativo, editor e a URL do aplicativo no arquivo.|
|**Editar**|Permite editar o nome, editor e a URL do aplicativo selecionado.|
|**Excluir**|Exclui o aplicativo selecionado da lista.|

### Configurações do modo de quiosque

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Selecione um aplicativo gerenciado que terá permissão para ser executado quando o dispositivo estiver em modo de quiosque**|Escolha **Procurar** e especifique o aplicativo gerenciado ou o aplicativo de uma loja que poderá ser executado quando o dispositivo estiver no modo de quiosque. Nenhum outro aplicativo poderá ser executado no dispositivo. Para obter mais ajuda, consulte **Como especificar URLs para lojas de aplicativos** mais adiante neste tópico.|
|**Permitir toque**|Habilita ou desabilita a tela sensível ao toque no dispositivo.|
|**Permitir rotação da tela**|Habilita ou desabilita a alteração da orientação da tela quando você gira o dispositivo.|
|**Permitir o uso dos botões de volume**|Habilita ou desabilita o uso dos botões de volume no dispositivo.|
|**Permitir alternador de toque**|Habilita ou desabilita a opção de alternar toque (mudo) no dispositivo.|
|**Permitir que o botão de ativação e suspensão da tela**|Habilita ou desabilita o botão de ativação e suspensão da tela no dispositivo.|
|**Permitir bloqueio automático**|Habilita ou desabilita o bloqueio automático do dispositivo.|
|**Habilitar o áudio mono**|Habilita ou desabilita a configuração de acessibilidade **áudio Mono**.|
|**Ativar leitura de texto**|Habilita ou desabilita a configuração de acessibilidade **Leitura de texto** que lê em voz alta o texto na tela do dispositivo.|
|**Ativar ajustes da leitura de texto**|Habilita ou desabilita os ajustes da leitura de texto que permitem que você ajuste a função Leitura de texto (por exemplo, a rapidez que o texto na tela é lido em voz alta).|
|**Habilitar o zoom**|Habilita ou desabilita a opção de acessibilidade de **Zoom** que permite usar o toque para ampliar a tela do dispositivo de acessibilidade.|
|**Habilitar ajustes de zoom**|Habilita ou desabilita os ajustes de zoom que permitem ajustar a função de zoom.|
|**Habilitar inverter cores**|Habilita ou desabilita a opção de acessibilidade **inverter cores** que ajusta a exibição para ajudar os usuários com deficiências visuais.|
|**Habilitar ajustes de inverter cores**|Habilita ou desabilita ajustes de inverter ajustes que permite ajustar a função inverter cores.|
|**Habilitar toque auxiliar**|Habilita ou desabilita a opção de acessibilidade **Toque auxiliar** , que ajuda os usuários a executarem gestos ne tela que podem ser difíceis de executar.|
|**Habilitar ajustes de toque auxiliar**|Habilita ou desabilita os ajustes de toque auxiliar que permitem ajustar a função de toque auxiliar.|
|**Habilitar a seleção de fala**|Habilita ou desabilita as configurações de acessibilidade **Seleção de fala** que podem ler em voz alta o texto que você selecionar.|
> [!NOTE]
> As observações a seguir aplicam-se às configurações do modo de quiosque para dispositivos iOS:
> 
> -   Antes de configurar um dispositivo iOS para o modo de quiosque, você deve usar o [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) ou o gerenciador de registros de dispositivos para colocar o dispositivo no modo supervisionado. Para obter mais informações sobre o Apple Configurator Tool, consulte sua documentação da Apple.
> -   Se o aplicativo iOS que você especificar for instalado depois de implantar a política de configuração, ele não entrará no modo de quiosque até depois de ser reiniciado.

### Informações de referência para aplicativos compatíveis e não compatíveis

#### Monitore aplicativos compatíveis e não compatíveis
Use o **Relatório de aplicativos incompatíveis** para exibir a compatibilidade de aplicativos permitidos e bloqueados.

##### Executar o relatório de aplicativos incompatíveis

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Relatórios** &gt; **Relatório de Aplicativos Incompatíveis**.

2.  Selecione os grupos de dispositivos que você deseja verificar, se deseja verificar se há aplicativos compatíveis, aplicativos incompatíveis ou ambos, e clique em **Exibir relatório**.

#### Como especificar URLs para lojas de aplicativos
Para especificar uma URL de aplicativo na lista de aplicativos compatíveis e não compatíveis, ou na opção **Selecionar um aplicativo gerenciado que poderá ser executado quando o dispositivo estiver no modo de quiosque** (somente iOS), use um dos seguintes formatos:

Usando um mecanismo de pesquisa, encontre o aplicativo que você deseja usar na iTunes App Store e abra a página do aplicativo.

Copie a URL da página e use-a como a URL para configurar a lista de aplicativos compatíveis ou incompatíveis ou o aplicativo que você deseja executar no modo de quiosque.

**Exemplo:** pesquise **Microsoft Word para iPad**. A URL usada será **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Você também pode usar o software iTunes para encontrar o aplicativo e usar o comando **Copiar Link** para obter a URL do aplicativo.

### Configurações de registro
Todas as configurações se aplicam ao iOS 7.1 e posterior.

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Permitir Bloqueio de Ativação quando o dispositivo estiver no modo supervisionado**|Habilita o Bloqueio de Ativação em dispositivos iOS supervisionados.|

### Supervisão
As configurações a seguir podem ser configuradas em dispositivos com iOS 7.1 e posterior que estão no modo supervisionado.

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Permitir modificação da conta**|Permitir que o usuário altere as configurações de conta, como configurações de email.|
|**Permitir o AirDrop**|Permitir o uso do recurso Airdrop para trocar conteúdo com dispositivos próximos.|
|**Permitir alterações nas configurações de uso de dados para celular do aplicativo**|Permitir ao usuário controlar quais aplicativos podem usar dados de celular.|
|**Permitir que o Siri consulte o conteúdo gerado por usuários da Internet**|Permitir que o Siri acesse sites para responder perguntas.|
|**Permitir o acesso à iBooks Store**|Permitir que o usuário procure e compre livros da iBooks Store.|
|**Permitir alterações nas configurações do aplicativo Find My Friends**|Permitir que o usuário altere as configurações do aplicativo Find My Friends.|
|**Permitir o uso da opção Apagar todo o conteúdo e as configurações do dispositivo**|Permitir que o usuário use a opção de apagar todo o conteúdo e as configurações no dispositivo.|
|**Permitir que o usuário habilite restrições nas configurações do dispositivo**|Permitir que o usuário configure restrições de dispositivo (controles dos pais) no dispositivo|
|**Permitir que a pesquisa do Spotlight retorne resultados da Internet**|Permite que a pesquisa do Spotlight se conecte à Internet para fornecer mais resultados.|
|**Permitir o uso do aplicativo Game Center**|Permitir o uso do aplicativo Game Center.|
|**Permitir que o emparelhamento de host controle os dispositivos que podem ser emparelhados com um dispositivo iOS**|O emparelhamento de host permite ao administrador controlar com quais dispositivos um dispositivo iOS 7 pode emparelhar.|
|**Permitir que o usuário instale perfis e certificados de configuração**|Permitir que o usuário instale certificados e perfis de configuração.|
|**Permitir o uso do aplicativo Mensagens no dispositivo**|Permitir o uso do aplicativo Mensagens para enviar mensagens de texto.|


## Configurações de política personalizada

Use a **política personalizada do iOS** do Microsoft Intune para implantar configurações que você criou usando a [ferramenta Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) em dispositivos iOS. Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração. Em seguida, você poderá importar este perfil de configuração para uma política personalizada do Intune iOS e implantar as configurações para usuários e dispositivos em sua organização.

Essa funcionalidade destina-se a permitir que você implante configurações do iOS que não possam ser configuradas com as política de configuração gerais do Intune.

### Pré-requisitos
Antes de começar, você precisa ter instalado o Apple Configurator e criado um arquivo de configuração que contém as configurações que deseja implantar para usuários ou dispositivos. Você pode baixar e aprender sobre o Apple Configurator na [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)

> [!NOTE]
> O Intune não relata a conformidade de configurações individuais em uma política personalizada do iOS. No entanto, a conformidade geral da política é informada.

### Configurações gerais

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para a política personalizada do iOS para ajudar a identificá-lo no console do Intune.|
    |**Descrição**|Forneça uma descrição que dê uma visão geral da política personalizada do iOS e outras informações relevantes que o ajudarão a localizá-la.|

### Configurações Personalizadas

|Nome da configuração|Detalhes|
    |----------------|--------------------|
|**Nome do perfil de configuração personalizada (exibido aos usuários)**|Forneça um nome para a política, como ela será exibida no dispositivo e em relatórios da política do Intune.|
|**Arquivo de configuração de perfil**|Clique em **Importar** e navegue até o perfil de configuração criado usando o Apple Configurador. **Observação:** certifique-se de que as configurações que você exportar da ferramenta Apple Configurator sejam compatíveis com a versão do iOS nos dispositivos nos quais você implantar a política personalizada do iOS. Para obter informações sobre como as incompatibilidades de configuração são resolvidas, pesquise a **Referência de Perfil de Configuração** e a **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).|
    |**Detalhes da configuração do perfil**|Exibe o código xml para o perfil de configuração que você importou.|

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO4-->


