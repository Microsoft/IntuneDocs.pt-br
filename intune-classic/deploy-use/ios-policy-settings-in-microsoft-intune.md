---
title: "Configurações da política do iOS | Microsoft Docs"
description: "Crie políticas que controlam as configurações e os recursos nos dispositivos iOS que você gerencia com o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3a59391aaf241e52f59bb3ff5de3eae84c496c51
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="ios-policy-settings-in-microsoft-intune"></a>Configurações de política do iOS no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune fornece uma variedade de configurações gerais internas que você pode definir em dispositivos iOS. Além disso, use a ferramenta Apple Configurator para criar configurações personalizadas que não estão disponíveis no Intune.

## <a name="general-configuration-policy-settings"></a>Definições de política de configuração geral

Use a **Política de configuração geral do iOS** do Microsoft Intune para definir configurações para:

-   **Configurações de segurança e do dispositivo em geral**. Escolha de uma lista de configurações predefinidas que permitem controlar uma variedade de recursos e funcionalidades no dispositivo.

-   **Modo de quiosque**. Bloqueie um dispositivo para permitir que apenas alguns recursos funcionem. Por exemplo, você pode permitir que um dispositivo execute apenas um aplicativo gerenciado que você especificar ou pode desabilitar os botões de volume em um dispositivo. Essas configurações podem ser usadas para um modelo de demonstração de um dispositivo ou um dispositivo que é dedicado a apenas uma função, como um dispositivo de ponto de venda.

-   **Aplicativos compatíveis e incompatíveis**. Especifique uma lista de aplicativos que são compatíveis ou não compatíveis em sua empresa. Nos dispositivos Android e iOS, o **Relatório de aplicativos incompatíveis** pode ser usado para exibir a conformidade de aplicativos especificados na lista em relação as aplicativos que os usuários instalaram (mas não é possível realmente bloquear a instalação do aplicativo).

> [!TIP]
> Você pode configurar os termos e condições de usuários para garantir que eles reconhecem que aplicativos no seu dispositivo, incluindo aplicativos pessoais, serão avaliados, e aplicativos incompatíveis serão bloqueados ou então relatados como não compatíveis. Os usuários devem aceitar esses termos e condições antes de registrar seus dispositivos e usar o portal da empresa para obter aplicativos. Para saber mais sobre os termos e condições de uso, consulte [Terms and conditions policy settings in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md) (Configurações de políticas de termos e condições de uso no Microsoft Intune).

Se a configuração que você está procurando não aparecer nesse tópico, você poderá criá-la usando uma política personalizada do iOS que lhe permite importar configurações criadas usando a [Ferramenta configuradora da Apple](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Para obter mais informações, consulte “Configurações de política personalizadas” mais adiante neste tópico.

### <a name="security-settings"></a>Configurações de segurança
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Exigir uma senha para desbloquear os dispositivos móveis**|Especificar se será solicitado ou não que o usuário insira uma senha para acessar seu dispositivo.|
|**Tipo de senha necessária**|Especificar o tipo de senha necessária, como apenas numérica ou alfanumérica.|
|**Número de caracteres complexos necessários na senha**|Especificar o número de caracteres de símbolo (como **#** ou **@**) que deve ser incluído na senha.|
|**Comprimento mínimo da senha**|Especificar o número mínimo de caracteres na senha.|
|**Permitir senha simples**|Permitir senhas simples como **0000** e **1234**.|
|**Número de falhas de entrada repetidas permitidas antes que o dispositivo seja apagado**|Especificar o número de tentativas de logon antes de essa configuração apagar o dispositivo.|
|**Minutos de inatividade antes de a senha ser solicitada**<sup>1</sup>|Especificar quanto tempo o dispositivo pode permanecer ocioso antes que o usuário precise digitar novamente sua senha.|
|**Expiração da senha (dias)**|Especificar o número de dias antes que a senha do dispositivo precise ser alterada.|
|**Lembrar histórico de senha**|Especificar se o usuário pode usar senhas que tenha usado anteriormente.|
|**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**|Especificar o número de senhas usadas anteriormente que são lembradas pelo dispositivo.|
|**Minutos de inatividade antes que a tela se apague**<sup>1</sup>|Especifique o número de minutos antes de a tela do dispositivo ser desativada.|
|**Permitir desbloqueio por impressão digital**|Permitir usar a impressão digital para desbloquear o dispositivo.|
<sup>1</sup> Para dispositivos iOS, ao definir as configurações **Minutos de inatividade antes que a tela se apague** e **Minutos de inatividade antes de a senha ser solicitada**, elas são aplicadas em sequência. Por exemplo, se você define o valor de ambas as configurações para **5** minutos, a tela desliga automaticamente após 5 minutos e o dispositivo é bloqueado após outros 5 minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo é bloqueado 5 minutos depois de o usuário desligar a tela.

### <a name="system-settings"></a>Configurações de sistema
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir captura de tela**|Permitir ao usuário capturar os conteúdos da tela como uma imagem.|
|**Permitir centro de controle na tela de bloqueio**|Permitir ao usuário acessar o aplicativo de senha quando o dispositivo estiver bloqueado.|
|**Permitir exibição de notificação na tela de bloqueio**|Permitir ao usuário acessar a exibição de notificações sem desbloquear o dispositivo.|
|**Permitir exibição atual na tela de bloqueio**|Permitir ao usuário exibir notificações quando o dispositivo estiver bloqueado.|
|**Permitir certificados TLS não confiáveis**|Permitir certificados do protocolo TLS não confiáveis no dispositivo.|
|**Permitir envio de dados de diagnóstico**|Permitir ou bloquear a habilidade do dispositivo enviar dados de diagnóstico para a Apple.|
|**Permitir senha quando bloqueado**|Permitir ao usuário acessar o aplicativo de senha enquanto o dispositivo estiver bloqueado.|

### <a name="cloud-settings-for-documents-and-data"></a>Configurações de nuvem para documentos e dados
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir backup no iCloud**|Permitir ao usuário fazer backup do dispositivo no iCloud.|
|**Permitir sincronização de documento no iCloud**|Permitir a sincronização de documento e chave-valor para o espaço de armazenamento no iCloud.|
|**Permitir sincronização do Fluxo de Fotos para o iCloud**|Permite que os usuários habilitem **Meu Fluxo de Fotos** em seus dispositivos, o que permite que as fotos sejam sincronizadas com o iCloud e fiquem disponíveis em todos os dispositivos dos usuários.|
|**Exigir backup criptografado**|Exigir que quaisquer backups de dispositivo sejam criptografados.|
|**Permitir que aplicativos gerenciados sincronizem dados no iCloud**|Permitir que os aplicativos que você gerencia com o Intune sincronizem dados com a conta do iCloud do usuário.|
|**Permitir que a Entrega continue as atividades em outro dispositivo**|Permitir que o usuário continue, em outro dispositivo iOS ou Mac OS X, o trabalho iniciado em um dispositivo iOS.|
|**Permitir compartilhamento de fotos do iCloud**|Defina como **Não** para desabilitar o **Compartilhamento de Fotos do iCloud** no dispositivo.|
|**Permitir biblioteca de fotos do iCloud**|Se for definido como **Não**, desabilitará o uso da biblioteca de fotos do iCloud, o que permite aos usuários armazenar fotos e vídeos na nuvem.    As fotos que não forem totalmente baixadas na biblioteca de fotos do iCloud para o dispositivo serão removidas do dispositivo se essa opção for definida como **Não**.|

### <a name="application-settings-for-the-browser"></a>Configurações de aplicativo do navegador
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir Safari**|Especifique se o navegador Safari pode ser usado no dispositivo.|
|**Permitir preenchimento automático**|Permite que o usuário possa alterar as configurações de preenchimento automático no navegador.|
|**Permitir bloqueador de pop-up**|Habilitar ou desabilitar o bloqueador de pop-up do navegador.|
|**Permitir cookies**|Permitir que o navegador use cookies.|
|**Permitir scripts Java**|Permitir a execução de scripts Java no navegador.|
|**Permitir aviso de fraude**|Permitir avisos de fraude no navegador.|

### <a name="application-settings-for-apps"></a>Configurações de aplicativo para aplicativos
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir instalação de aplicativos**|Permitir que o dispositivo acesse a loja de aplicativos e instale aplicativos.|
|**Exigir uma senha para acessar o repositório de aplicativos**|Exigir que o usuário insira uma senha antes de poder visitar a loja de aplicativos.|
|**Permitir compras no aplicativo**|Permitir que aquisições da loja sejam feitas de um aplicativo em execução.|
|**Permitir documentos gerenciados em outros aplicativos não gerenciados**|Permitir que documentos corporativos sejam exibidos em qualquer aplicativo.<br>**Exemplo:** você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox. Defina essa configuração como não. Depois que o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permitirá mais salvar.|
|**Permitir documentos não gerenciados em outros aplicativos gerenciados**|Permitir que qualquer documento seja exibido em aplicativos gerenciados corporativos.|
|**Permitir videoconferência**|Permitir aplicativos de videoconferência como FaceTime no dispositivo.|
|**Permitir que o usuário confie em novos autores de aplicativos empresariais**|Permitir que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.|


### <a name="application-settings-for-games"></a>Configurações de aplicativo para jogos
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir adição de amigos no Game Center**|Permitir que o usuário adicione amigos no Game Center.|
|**Permitir jogo para vários participantes**|Permitir que o usuário execute jogos com vários participantes no dispositivo.|

### <a name="application-settings-for-media-content"></a>Configurações de aplicativo para conteúdo de mídia
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Região de classificações**|Selecione uma região e selecione a classificação máxima que os usuários podem baixar para **Filmes**, **Programas de TV** e **Aplicativos**.|
|**Permitir conteúdo somente para adultos no repositório de mídia**|Permitir ao dispositivo acessar o conteúdo classificado como adulto na loja.|
|**Permitir que o usuário baixe o conteúdo da iBook Store sinalizado como 'Erotismo'**|Permitir que o usuário baixe livros da categoria “Erotismo”.|


### <a name="device-capabilities-settings-for-hardware"></a>Configurações de recursos do dispositivo para hardware
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir câmera**|Especificar se a câmera no dispositivo pode ser usada.|
|**Forçar Apple Watches emparelhados a usar a detecção de pulso**|Quando habilitado, o Apple Watch não exibirá notificações quando não estiver sendo usado.|
|**Exigir uma senha de emparelhamento para solicitações de saída do AirPlay**|Exigir uma senha emparelhamento quando o usuário usar AirPlay para transmitir o conteúdo para outros dispositivos da Apple.|

### <a name="device-capabilities-settings-for-cellular"></a>Configurações de recursos do dispositivo para celular
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir roaming de voz**|Permitir roaming de voz quando o dispositivo estiver em uma rede de celular.|
|**Permitir roaming de dados**|Permitir roaming de dados quando o dispositivo estiver em uma rede de celular.|
|**Permitir busca em segundo plano global durante roaming**|Permitir ao dispositivo buscar dados, como emails, durante roaming na rede celular.|

### <a name="device-capabilities-settings-for-features"></a>Configurações de recursos do dispositivo para recursos
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|-------|
|**Permitir Siri**|Permitir o uso do Assistente de voz Siri no dispositivo.|
|**Permitir Siri enquanto o dispositivo está bloqueado**|Permitir o uso do Assistente de voz Siri no dispositivo enquanto ele estiver bloqueado.|
|**Permitir discagem de voz**|Permitir o uso do recurso de discagem por voz no dispositivo.|
|**Não permitir Airdrop de aplicativos gerenciados**|Impedir que aplicativos gerenciados sejam capazes de enviar dados por meio do Airdrop.|


### <a name="settings-for-compliant-and-noncompliant-apps"></a>Configurações para aplicativos compatíveis e não compatíveis
Na lista **Aplicativos Compatíveis &amp; Incompatíveis**, especifique uma lista de aplicativos compatíveis ou incompatíveis usando as informações a seguir.

> [!NOTE]
> Uma única política só pode conter somente uma lista de aplicativos compatíveis ou de aplicativos incompatíveis. Não é possível especificar ambos na mesma política.

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Relatar não conformidade quando os usuários instalarem os aplicativos listados**|Listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.|
|**Relatar não conformidade quando os usuários instalam aplicativos não listados**|Listar os aplicativos que os usuários têm permissão para instalar. Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.|
|**Adicionar**|Adicionar um aplicativo à lista selecionada. Especifique um nome da sua preferência, opcionalmente o editor do aplicativo, e a URL para o aplicativo na loja de aplicativos. Leia “Como especificar URLs para lojas de aplicativos” mais adiante neste tópico para obter mais ajuda.|
|**Importar aplicativos**|Importar uma lista dos aplicativos que você especificou em um arquivo de valores separados por vírgulas. No arquivo, use este formato: nome do aplicativo, editor, URL do aplicativo.|
|**Editarar**|Editar o nome, o editor e a URL do aplicativo selecionado.|
|**Excluir**|Excluir o aplicativo selecionado da lista.|

As políticas que contêm configurações de aplicativo que estão em conformidade e fora de conformidade devem ser implantadas em grupos de usuários.

### <a name="kiosk-mode-settings"></a>Configurações do modo de quiosque

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Selecione um aplicativo gerenciado que terá permissão para ser executado quando o dispositivo estiver em modo de quiosque**|Escolha **Procurar** e especifique o aplicativo gerenciado ou o aplicativo de uma loja que poderá ser executado quando o dispositivo estiver no modo de quiosque. Nenhum outro aplicativo poderá ser executado no dispositivo. Para obter mais ajuda, consulte "How to specify URLs to app stores" (Como especificar URLs para lojas de aplicativos) mais adiante neste tópico.|
|**Permitir toque**|Habilitar ou desabilitar a tela touch no dispositivo.|
|**Permitir rotação da tela**|Habilitar ou desabilitar a alteração da orientação da tela quando o usuário gira o dispositivo.|
|**Permitir botões de volume**|Habilitar ou desabilitar o uso dos botões de volume no dispositivo.|
|**Permitir alternador de toque**|Habilitar ou desabilitar a opção de mudar toque (mudo) no dispositivo.|
|**Permitir botão para ligar tela em modo de suspensão**|Habilitar ou desabilitar o botão de ativação e suspensão da tela no dispositivo.|
|**Permitir bloqueio automático**|Habilitar ou desabilitar o bloqueio automático do dispositivo.|
|**Habilitar o áudio mono**|Habilitar ou desabilitar a configuração de acessibilidade **Áudio mono**.|
|**Habilitar narração**|Habilitar ou desabilitar a configuração de acessibilidade **Narração**, que lê em voz alta o texto na tela do dispositivo.|
|**Habilitar ajustes de narração**|Habilitar ou desabilitar os ajustes de narração que permitem que o usuário ajuste a função Narração (por exemplo, a rapidez que o texto na tela é lido em voz alta).|
|**Habilitar o zoom**|Habilitar ou desabilitar a configuração de acessibilidade de **Zoom** que permite ao usuário utilizar o toque para ampliar a tela do dispositivo de acessibilidade.|
|**Habilitar ajustes de zoom**|Habilitar ou desabilitar os ajustes de zoom que permitem ao usuário ajustar a função de zoom.|
|**Habilitar inverter cores**|Habilitar ou desabilitar a configuração de acessibilidade **Inverter Cores** que ajusta a exibição para ajudar os usuários com deficiências visuais.|
|**Habilitar ajustes de inverter cores**|Habilitar ou desabilitar ajustes de inverter ajustes que permite ao usuário ajustar a função inverter cores.|
|**Habilitar toque auxiliar**|Habilitar ou desabilitar a configuração de acessibilidade **Toque auxiliar**, que ajuda o usuário a executar gestos na tela que podem ser difíceis de executar.|
|**Habilitar ajustes de toque auxiliar**|Habilitar ou desabilitar os ajustes de toque auxiliar que permitem ao usuário ajustar a função de toque auxiliar.|
|**Habilitar a seleção de fala**|Habilitar ou desabilitar as configurações de acessibilidade **Seleção de fala** que podem ler em voz alta o texto que o usuário selecionar.|
> [!NOTE]
> As observações a seguir aplicam-se às configurações do modo de quiosque para dispositivos iOS:
>
> -   Antes de configurar um dispositivo iOS para o modo de quiosque, você deve usar a [ferramenta Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) ou o [Programa de Registro do Dispositivo Apple](ios-device-enrollment-program-in-microsoft-intune.md) para colocar o dispositivo no modo supervisionado. Para obter mais informações sobre a ferramenta Apple Configurator, consulte sua documentação da Apple.
> -   Se o aplicativo iOS que você especificar for instalado depois de implantar a política de configuração, ele não entrará no modo de quiosque até depois de ser reiniciado.

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>Informações de referência para aplicativos compatíveis e não compatíveis

Use o **Relatório de aplicativos incompatíveis** para exibir a compatibilidade de aplicativos permitidos e bloqueados.

##### <a name="to-run-the-noncompliant-apps-report"></a>Executar o relatório de aplicativos incompatíveis

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Relatórios** &gt; **Relatório de Aplicativos Incompatíveis**.

2.  Selecione os grupos de dispositivos que você deseja verificar, se deseja verificar se há aplicativos compatíveis, aplicativos incompatíveis ou ambos e então escolha **Exibir Relatório**.

#### <a name="how-to-specify-urls-to-app-stores"></a>Como especificar URLs para lojas de aplicativos
Para especificar uma URL de aplicativo na lista de aplicativos compatíveis e não compatíveis, ou na opção **Selecionar um aplicativo gerenciado que poderá ser executado quando o dispositivo estiver no modo de quiosque** (somente iOS), use um dos seguintes formatos:

1. Usando um mecanismo de pesquisa, encontre o aplicativo que você deseja usar na iTunes App Store e abra a página do aplicativo.

2. Copie a URL da página e use-a como a URL para configurar a lista de aplicativos compatíveis ou incompatíveis ou o aplicativo que você deseja executar no modo de quiosque.

**Exemplo:** pesquise **Microsoft Word para iPad**. A URL usada será **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Você também pode usar o software iTunes para encontrar o aplicativo e usar o comando **Copiar Link** para obter a URL do aplicativo.

### <a name="enrollment-settings"></a>Configurações de registro
Todas as configurações se aplicam ao iOS 8.0 e posterior.

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Permitir Bloqueio de Ativação quando o dispositivo estiver no modo supervisionado**|Habilitar o Bloqueio de Ativação em dispositivos iOS supervisionados.|

### <a name="supervised-mode-settings"></a>Configurações do modo supervisionado
As configurações a seguir podem ser feitas em dispositivos com iOS 8.0 e posterior que estão no modo supervisionado.

### <a name="supervised-mode-settings-for-device-restrictions"></a>Configurações do modo supervisionado para restrições de dispositivo

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Permitir modificação da conta**|Permitir que o usuário altere as configurações de conta, como configurações de email.|
|**Permitir alterações nas configurações de uso de dados para celular do aplicativo**|Permitir ao usuário controlar quais aplicativos podem usar dados de celular.|
|**Permitir o uso da opção Apagar todo o conteúdo e as configurações do dispositivo**|Permitir que o usuário use a opção de apagar todo o conteúdo e as configurações no dispositivo.|
|**Permitir que o usuário habilite restrições nas configurações do dispositivo**|Permitir que o usuário configure restrições de dispositivo (controles dos pais) no dispositivo.|
|**Permitir que o emparelhamento de host controle os dispositivos que podem ser emparelhados com um dispositivo iOS**|Permitir o emparelhamento de host para que administrador possa controlar os dispositivos com os quais um dispositivo iOS pode ser emparelhado.|
|**Permitir que o usuário instale certificados e perfis de configuração**|Permitir que o usuário instale certificados e perfis de configuração.|
|**Permitir a modificação do nome do dispositivo**|Permitir que o usuário altere o nome do dispositivo.|
|**Permitir a modificação da senha**|Permitir que a senha do dispositivo seja adicionada, alterada ou removida.|
|**Permitir emparelhamento do Apple Watch**|Permitir que o dispositivo seja emparelhado com um Apple Watch.|
|**Permitir a modificação de configurações de notificação**|Permitir que o usuário altere as configurações de notificação do dispositivo.|
|**Permitir a modificação do papel de parede**|Permitir que o usuário altere o papel de parede do dispositivo.|

### <a name="supervised-mode-settings-for-feature-restrictions"></a>Configurações do modo supervisionado para restrições de recursos

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Permitir o AirDrop**|Permitir o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.|
|**Permitir que o Siri consulte o conteúdo gerado por usuários da Internet**|Permitir que o Siri acesse sites para responder perguntas.|
|**Usar filtro de profanidade da Siri**|Impede que a Siri dite ou use linguagem profana.|
|**Permitir que a pesquisa do Spotlight retorne resultados da Internet**|Permitir que a pesquisa do Spotlight se conecte à Internet para fornecer mais resultados.|
|**Permitir pesquisa de definição de palavra**|Permitir o recurso do iOS que permite realçar uma palavra e pesquisar sua definição.|
|**Permitir teclados preditivos**|Permitir o uso de teclados preditivos que sugerem palavras que o usuário pode querer.|
|**Permitir correção automática**|Permite que o dispositivo corrija automaticamente palavras incorretas.|
|**Permitir verificação ortográfica do teclado**|Permite o verificador de ortografia do dispositivo.|
|**Permitir atalhos de teclado**|Permite o uso de atalhos de teclado.|

### <a name="supervised-mode-settings-for-app-restrictions"></a>Configurações do modo supervisionado para restrições de aplicativo

|Nome da configuração|Detalhes|
|----------------|--------------------|
|**Permitir a modificação de configurações de confiança do aplicativo empresarial**|Permite que os usuários alterem as configurações de confiança para aplicativos empresariais.|
|**Permitir a instalação de aplicativos usando apenas a configuração da Apple e o iTunes**|Habilita ou desabilita a App Store da tela inicial do dispositivo. Os usuários ainda podem usar o iTunes ou a ferramenta Apple Configurator para instalar e atualizar aplicativos.|
|**Permitir downloads de aplicativo automáticos**|Permitir que aplicativos adquiridos em outros dispositivos sejam baixados automaticamente neste dispositivo. Esta configuração não afeta atualizações de aplicativo.|
|**Permitir alterações nas configurações do aplicativo Find My Friends**|Permitir que o usuário altere as configurações do aplicativo Find My Friends.|
|**Permitir o acesso à iBooks Store**|Permitir que o usuário procure e compre livros da iBooks Store.|
|**Permitir o uso do aplicativo Mensagens no dispositivo**|Permitir o uso do aplicativo Mensagens para enviar mensagens de texto.|
|**Permitir o uso de Podcasts**|Permitir o uso do aplicativo Podcasts.|
|**Permitir o uso do serviço Music**|Permitir o uso do aplicativo Apple Music.|
|**Permitir o serviço iTunes Radio**|Permitir o uso do aplicativo iTunes Radio.|
|**Permitir Notícias da Apple**|Permitir o uso do aplicativo Apple News.|
|**Permitir o Game Center**|Permitir o uso do aplicativo Game Center.|


### <a name="show-or-hide-apps"></a>Mostrar ou ocultar aplicativos

Use a **Lista de aplicativos ocultos e mostrados** para controlar o seguinte em dispositivos supervisionados com iOS 9.3 ou posterior:

- Especificar uma lista de aplicativos que serão ocultados dos usuários. Os usuários não podem exibir nem iniciar esses aplicativos.
- Especifique uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.


#### <a name="how-to-create-a-hidden-or-shown-app-list"></a>Como criar uma lista de aplicativos ocultos ou mostrados

Especifique as seguintes configurações:

|Nome da configuração|Detalhes|
|-|-|
|**Lista de aplicativos ocultos e mostrados**|Habilite esta configuração se quiser criar uma lista de aplicativos ocultos ou mostrados.|
|**Ocultar os aplicativos listados dos usuários**|Selecione esta opção se quiser criar uma lista de aplicativos que serão ocultados dos usuários.<br>Ao criar esse tipo de lista, todos os aplicativos, exceto pelos aplicativos de iOS **Configurações** e **Telefone** (para iPhones) ficam ocultos.|
|**Mostrar somente os aplicativos listados para os usuários**|Selecione esta opção se quiser criar uma lista de aplicativos que serão mostrados para os usuários.<br>Quando você cria esse tipo de lista, todos os outros aplicativos, exceto pelos aplicativos de iOS **Configurações** e **Telefone** (para iPhones) ficam ocultos.<br>Além disso, você deve adicionar o Portal da Empresa e quaisquer aplicativos que tiver implantado, e gerenciar com o Intune na lista.|
|**Adicionar**|Adiciona um aplicativo à lista selecionada.<br>Para obter a lista oculta, você deve especificar o **Nome**, **Editor** e **URL do Aplicativo ou ID do Pacote** de cada aplicativo que deseja ocultar.<br>Para obter a lista mostrada, você pode **Selecionar um aplicativo gerenciado**, o que fornece uma lista de aplicativos que você gerencia com o Intune e entre os quais pode selecionar, ou Selecionar uma loja de aplicativo e depois especificar o **Nome**, **Editor** e **URL do Aplicativo ou ID do Pacote** de cada aplicativo que você deseja mostrar.|
|**Importar aplicativos**|Importa uma lista dos aplicativos que você especificou em um arquivo de valores separados por vírgulas. Use o formato, nome do aplicativo, editor e a URL do aplicativo no arquivo.|
|**Editarar**|Permite editar o nome, editor e a URL do aplicativo selecionado.|
|**Excluir**|Exclui o aplicativo selecionado da lista.|

#### <a name="app-information-for-built-in-ios-apps"></a>Informações do aplicativo para aplicativos iOS internos

Use as informações nesta lista para identificar o nome, o editor e a ID do pacote dos aplicativos iOS internos que você pode mostrar ou ocultar. Se deseja mostrar ou ocultar todos os aplicativos na lista, você pode copiar os dados abaixo em um arquivo de texto com a extensão **.csv** e usar a opção **Importar Aplicativos** para importar todos os aplicativos simultaneamente.

```
App Store,Apple,com.apple.AppStore
Calculator,Apple,com.apple.calculator
Calendar,Apple,com.apple.mobilecal
Camera,Apple,com.apple.camera
Clock,Apple,com.apple.mobiletimer
Compass,Apple,com.apple.compass
Contacts,Apple,com.apple.MobileAddressBook
FaceTime,Apple,com.apple.facetime
Find Friends,Apple,com.apple.mobileme.fmf1
Find iPhone,Apple,com.apple.mobileme.fmip1
Game Center,Apple,com.apple.gamecenter
GarageBand,Apple,com.apple.mobilegarageband
Health,Apple,com.apple.Health
iBooks,Apple,com.apple.iBooks
iTunes Store,Apple,com.apple.MobileStore
iTunes U,Apple,com.apple.itunesu
Keynote,Apple,com.apple.Keynote
Mail,Apple,com.apple.mobilemail
Maps,Apple,com.apple.Maps
Messages,Apple,com.apple.MobileSMS
Music,Apple,com.apple.Music
News,Apple,com.apple.news
Notes,Apple,com.apple.mobilenotes
Numbers,Apple,com.apple.Numbers
Pages,Apple,com.apple.Pages
Photo Booth,Apple,com.apple.Photo-Booth
Photos,Apple,com.apple.mobileslideshow
Podcasts,Apple,com.apple.podcasts
Reminders,Apple,com.apple.reminders
Safari,Apple,com.apple.mobilesafari
Settings,Apple,com.apple.Preferences
Stocks,Apple,com.apple.stocks
Tips,Apple,com.apple.tips
Videos,Apple,com.apple.videos
VoiceMemos,Apple,com.apple.VoiceMemos
Wallet,Apple,com.apple.Passbook
Watch,Apple,com.apple.Bridge
Weather,Apple,com.apple.weather


```




## <a name="custom-policy-settings"></a>Configurações de política personalizada

Use a **política personalizada do iOS** do Microsoft Intune para implantar configurações que você criou usando a [ferramenta Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) em dispositivos iOS. Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração. Em seguida, você poderá importar este perfil de configuração para uma política personalizada do Intune iOS e implantar as configurações para usuários e dispositivos em sua organização.

Essa funcionalidade permite que você implante configurações do iOS que não possam ser configuradas com as políticas de configuração gerais do Intune.

### <a name="prerequisites"></a>Pré-requisitos
Antes de começar, você precisa ter instalado o Apple Configurator e criado um arquivo de configuração que contém as configurações que deseja implantar para usuários ou dispositivos. Você pode baixar o Apple Configurator e aprender sobre ele na [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12).

> [!NOTE]
> O Intune não relata a conformidade de configurações individuais em uma política personalizada do iOS. No entanto, a conformidade geral da política é informada.

### <a name="general-settings"></a>Configurações gerais

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para a política personalizada do iOS para ajudar a identificá-lo no console do Intune.|
    |**Descrição**|Forneça uma descrição que dê uma visão geral da política personalizada do iOS e outras informações relevantes que o ajudarão a localizá-la.|

### <a name="custom-settings"></a>Configurações Personalizadas

|Nome da configuração|Detalhes|
    |----------------|--------------------|
|**Nome do perfil de configuração personalizado (exibido a usuários)**|Forneça um nome para a política, como ela será exibida no dispositivo e em relatórios da política do Intune.|
|**Arquivo de configuração de perfil**|Clique em **Importar** e então navegue até o perfil de configuração criado usando o Apple Configurador. **Observação:** certifique-se de que as configurações que você exportar da ferramenta Apple Configurator sejam compatíveis com a versão do iOS nos dispositivos nos quais você implantar a política personalizada do iOS. Para obter informações sobre como as incompatibilidades de configuração são resolvidas, pesquise a **Referência de Perfil de Configuração** e a **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).|
    |**Detalhes do perfil de configuração**|Exibir o código XML para o perfil de configuração que você importou.|

### <a name="see-also"></a>Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

