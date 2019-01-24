---
title: Configurações de dispositivo do Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos com Android Enterprise ou Android for Work, restrinja algumas configurações no dispositivo, como copiar e colar, mostrar notificações, permissões de aplicativo, compartilhamento de dados, tamanho de senha, falhas de entrada, usar impressão digital para desbloquear, reutilizar senhas e habilitar o compartilhamento de contatos de trabalho por Bluetooth. Configure os dispositivos como um quiosque para executar um aplicativo ou vários aplicativos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.openlocfilehash: 62c44768f17ecc82dc748eb4dfda74da421ee3b5
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2019
ms.locfileid: "54387006"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações do dispositivo do Android Enterprise para permitir ou restringir os recursos usando o Intune

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos Android Enterprise. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, executar aplicativos no modo de quiosque, segurança de controle e muito mais.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Somente proprietário do dispositivo

### <a name="general-settings"></a>Configurações gerais

- **Captura de tela**: Escolha **Bloquear** para impedir capturas de tela ou outras capturas no dispositivo. Ela também impede que o conteúdo seja exibido em dispositivos de vídeo que não tenham uma saída de vídeo segura. **Não configurado** permite que o usuário capture o conteúdo da tela como uma imagem.
- **Câmera**: Escolha **Bloquear** para impedir o acesso à câmera no dispositivo. **Não necessário** permite o acesso à câmera do dispositivo.
- **Política de permissão padrão**: Essa configuração define a política de permissão padrão para as solicitações de permissões do tempo de execução. Os valores possíveis incluem:
  - **Padrão do dispositivo**: Use a configuração padrão do dispositivo.
  - **Aviso**: O usuário recebe uma solicitação para aprovar a permissão.
  - **Concessão automática**: As permissões são concedidas automaticamente.
  - **Negação automática**: As permissões são negadas automaticamente.
- **Alterações de data e hora**: Escolha **Bloquear** para impedir que os usuários definam manualmente a data e a hora. **Não configurado** permite que os usuários definam a data e a hora do dispositivo.
- **Alterações de volume**: Escolha **Bloquear** para impedir que usuários alterem o volume do dispositivo. **Não configurado** permite o uso de configurações de volume no dispositivo.
- **Redefinição de fábrica**: Escolha **Bloquear** para impedir o uso da opção de redefinição de fábrica nas configurações do dispositivo. **Não configurado** permite o uso dessa configuração no dispositivo.
- **Inicialização segura**: Escolha **Bloquear** para impedir que os usuários reiniciem o dispositivo no modo de segurança. **Não configurado** permite que os usuários reiniciem o dispositivo no modo de segurança.
- **Barra de status**: Escolha **Bloquear** para impedir o acesso à barra de status, incluindo notificações e configurações rápidas. **Não configurado** permite aos usuários acesso à barra de status.
- **Serviços de roaming de dados**: Escolha **Bloquear** para impedir o roaming de dados pela rede celular. **Não configurado** permite o roaming de dados quando o dispositivo estiver em uma rede celular.
- **Alterações na configuração de Wi-Fi**: Escolha **Bloquear** para impedir que os usuários alterem as configurações de Wi-Fi criadas pelo proprietário do dispositivo. Os usuários podem criar suas próprias configurações de Wi-Fi. **Não configurado** permite que os usuários alterem as configurações de Wi-Fi no dispositivo.
- **Configuração de ponto de acesso Wi-Fi**: Escolha **Bloquear** para impedir que os usuários criem ou alterem as configurações de Wi-Fi. **Não configurado** permite que os usuários alterem as configurações de Wi-Fi no dispositivo.
- **Configuração de Bluetooth**: Escolha **Bloquear** para impedir que os usuários configurem o Bluetooth no dispositivo. **Não configurado** permite o uso de Bluetooth no dispositivo.
- **Compartilhamento de contatos por Bluetooth**: Escolha **Bloquear** para impedir o acesso a contatos de trabalho de outro dispositivo, por exemplo, em um sistema de carro, quando o dispositivo Android estiver emparelhado via Bluetooth. **Não configurado** permite acesso aos contatos de trabalho em outro dispositivo Bluetooth que esteja emparelhado com o dispositivo Android.
- **Compartilhamento de internet e acesso a pontos de acesso**: Escolha **Bloquear** para impedir o compartilhamento e o acesso a pontos de acesso portáteis. **Não configurado** permite o compartilhamento e acesso a pontos de acesso portáteis.
- **Armazenamento USB**: Escolha **Permitir** para acessar o armazenamento USB no dispositivo. **Não configurado** impede o acesso ao armazenamento USB.
- **Transferência de arquivo por USB**: Escolha **Bloquear** para evitar a transferência de arquivos por USB. **Não configurado** permite a transferência de arquivos.
- **Mídia externa**: Escolha **Bloquear** para evitar usar ou se conectar a qualquer mídia externa no dispositivo. **Não configurado** permite a conexão de mídias externas ao dispositivo.
- **Transmissão de dados usando a NFC**: Escolha **Bloquear** para impedir o uso da tecnologia NFC (Near Field Communication) para transmitir dados de aplicativos. **Não configurado** permite o uso de NFC para compartilhar dados entre dispositivos.
- **Recursos de depuração**: Escolha **Permitir** para permitir o uso dos recursos de depuração no dispositivo. **Não configurado** impede o uso dos recursos de depuração no dispositivo.
- **Ajuste de microfone**: Escolha **Bloquear** para impedir que os usuários cancelem o mudo do microfone e ajustem o volume. **Não configurado** permite o uso e ajuste do volume do microfone no dispositivo.
- **Emails de proteção de redefinição de fábrica**: Escolha **Endereços de email da conta do Google**. Insira os endereços de email dos administradores do dispositivo que podem desbloquear o dispositivo após ele ser apagado. Separe os endereços de email com um ponto e vírgula, como `admin1@gmail.com;admin2@gmail.com`. Se um email não for inserido, qualquer pessoa poderá desbloquear o dispositivo após ele ser restaurado para as configurações de fábrica.
- **Hachura de escape de rede**: Escolha **Habilitar** para permitir que os usuários ativem o recurso de hachura de escape de rede. Se não houver uma conexão de rede quando o dispositivo for iniciado, a hachura de escape solicitará a conexão temporária a uma rede e atualizará a política do dispositivo. Depois de aplicar a política, a rede temporária será esquecida e o dispositivo continuará com a inicialização. Esse recurso conecta os dispositivos a uma rede se:
  - Não houver uma rede adequada na última política.
  - O dispositivo iniciar em um aplicativo no modo de tarefa de bloqueio.
  - O usuário não conseguir acessar as configurações do dispositivo.

  **Não configurado** impede que os usuários ativem o recurso de hachura de escape de rede no dispositivo.

- **Permitir instalação de fontes desconhecidas**: Escolha **Permitir** para que os usuários possam ativar as **Fontes desconhecidas**. Essa configuração permite que os aplicativos sejam instalados de fontes desconhecidas. **Não configurado** impede que os usuários ativem as **Fontes desconhecidas**.
- **Atualização do sistema**: Escolha uma opção para definir como o dispositivo trata as atualizações over-the-air:
  - **Padrão do dispositivo**: Use a configuração padrão do dispositivo.
  - **Automática**: As atualizações são instaladas automaticamente sem interação do usuário. A configuração dessa política instala imediatamente todas as atualizações pendentes.
  - **Adiado**: As atualizações são adiadas por 30 dias. Após 30 dias o Android solicita ao usuário a instalação da atualização. É possível que os fabricantes de dispositivos ou operadoras impeçam que as atualizações de segurança importantes (isenção) sejam adiadas. Uma atualização isenta mostra uma notificação do sistema para o usuário no dispositivo. 
  - **Janela de manutenção**: Instala as atualizações automaticamente durante uma janela de manutenção diária definida no Intune. A instalação ocorre diariamente por 30 dias, e pode falhar devido a espaço insuficiente ou aos níveis de bateria. Após 30 dias, o Android solicita ao usuário a instalação. Essa janela também é usada para instalar atualizações de aplicativos do Play. Use essa opção para dispositivos dedicados, como quiosques, pois é possível atualizar aplicativos de primeiro plano em quiosques de aplicativo único.
- **Atualizações automáticas do aplicativo**: Escolha quando as atualizações automáticas são instaladas. Suas opções:
  - **Não configurado**
  - **Escolha do usuário**
  - **Nunca**
  - **Somente Wi-Fi**
  - **Sempre**

- **Janelas de notificação**: Quando essa opção é definida como **Desabilitar**, as notificações de janela, incluindo notificações do sistema, chamadas de entrada, chamadas de saída, alertas do sistema e erros do sistema, não são mostradas no dispositivo. Quando essa opção é definida como **Não configurado**, o padrão do sistema operacional é usado, que poderá ser mostrar as notificações.
- **Ignorar dicas de primeiro uso**: Escolha **Habilitar** para ocultar ou ignorar as sugestões de aplicativos para percorrer os tutoriais ou ler dicas de introdução quando o aplicativo é iniciado. Quando essa opção é definida como **Não configurado**, o padrão do sistema operacional é usado, que poderá ser mostrar essas sugestões quando o aplicativo for iniciado.


### <a name="system-security-settings"></a>Configurações de segurança do sistema

- **Verificação de ameaças em aplicativos**: **Obrigatório** garante que a configuração **Verificar aplicativos** esteja habilitada para perfis pessoais e corporativos.

### <a name="kiosk-settings"></a>Configurações do quiosque

É possível configurar um dispositivo para executar um ou vários aplicativos. Quando um dispositivo está no modo de quiosque, somente os aplicativos que você adiciona ficam disponíveis. Essas configurações se aplicam a dispositivos Android dedicados, mas não a dispositivos Android dedicados e totalmente gerenciados.

**Modo de quiosque**: Escolha se o dispositivo executará um ou vários aplicativos.

- **Quiosque de aplicativo único**: Os usuários só podem acessar um único aplicativo no dispositivo. Quando o dispositivo inicia, somente o aplicativo específico é exibido. Os usuários são impedidos de abrir novos aplicativos e alterar o aplicativo em execução.

  **Etapas**
  1. Escolha **Selecione um aplicativo gerenciado** e escolha o aplicativo gerenciado da Google Play na lista. 

      Se não houver aplicativos listados, [adicione alguns aplicativos Android](apps-add-android-for-work.md) ao dispositivo. Não se esqueça de [atribuir o aplicativo ao grupo de dispositivos criado para seus dispositivos de quiosque](apps-deploy.md).

  2. Escolha **OK** > **OK** para adicionar o aplicativo.

- **Quiosques de vários aplicativos**: Os usuários podem acessar um conjunto limitado de aplicativos no dispositivo. Quando o dispositivo inicia, somente os aplicativos adicionados são exibidos. Também é possível adicionar alguns links da Web que os usuários podem abrir. Ao aplicar a política, os usuários veem ícones para os aplicativos permitidos na tela inicial.

  > [IMPORTANTE] Para dispositivos de quiosque com vários aplicativos, o [aplicativo Tela Inicial Gerenciada](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) na Google Play **deve ser**:
  >   - [Adicionado como um aplicativo cliente](apps-add-android-for-work.md) no Intune
  >   - [Atribuído ao grupo de dispositivos](apps-deploy.md) criado para seus dispositivos de quiosque
  > 
  > O aplicativo **Tela Inicial Gerenciada** não precisa estar no perfil de configuração, mas precisa ser adicionado como um aplicativo cliente. Quando o aplicativo **Tela Inicial Gerenciada** é adicionado como um aplicativo cliente, quaisquer outros aplicativos que você adicionar ao perfil de configuração serão mostrados como ícones no aplicativo **Tela Inicial Gerenciada**. 

  - Escolha **Adicionar** e selecione seus aplicativos na lista.

    Se o aplicativo **Tela Inicial Gerenciada** não estiver listado, [adicione-o pela Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Não se esqueça de [atribuir o aplicativo](apps-deploy.md) ao grupo de dispositivos criado para seus dispositivos de quiosque.

    Também é possível adicionar outros [aplicativos Android](apps-add-android-for-work.md) e [aplicativos Web](web-app.md) criados por sua organização ao dispositivo. Não se esqueça de [atribuir o aplicativo ao grupo de dispositivos criado para seus dispositivos de quiosque](apps-deploy.md).

  - **Botão da página inicial virtual**: Escolha **Habilitar** para mostrar um botão da página inicial no dispositivo de quiosque. Quando selecionado, retorna o usuário à tela inicial do dispositivo para que os usuários possam alternar facilmente entre aplicativos. Em alguns dispositivos Android, os usuários precisam passar o dedo para cima na tela para mostrar o botão página inicial. **Desabilitar** não mostra um botão página inicial, portanto, os usuários devem usar o botão voltar para alternar entre aplicativos.
  - **Sair do modo de quiosque**: Escolha **Habilitar** para permitir que os administradores pausem temporariamente o modo de quiosque para atualizar o dispositivo. Para usar esse recurso, o administrador deve fazer o seguinte: 
  
    1. Continue para selecionar o botão voltar até que o botão "Sair do Quiosque" apareça. 
    2. Selecione o botão e insira o PIN de **Sair do código do modo de quiosque**.
    3. Ao terminar de fazer as alterações, selecione o aplicativo **Tela Inicial Gerenciada**. Esta etapa bloqueia novamente o dispositivo no modo de quiosque de vários aplicativos. 
    
    **Desabilitar** não oferece a capacidade de pausar o modo de quiosque. Se o administrador continua selecionando o botão voltar e seleciona o botão "Sair do Quiosque", uma mensagem pede uma senha.
    
    - **Código para sair do modo de quiosque**: Insira um PIN numérico de 4 a 6 dígitos. O administrador usa esse PIN para pausar temporariamente o modo de quiosque.
 
  - **Definir a tela de fundo da URL personalizada**: Insira uma URL para personalizar o plano de fundo no dispositivo de quiosque.

### <a name="device-password-settings"></a>Configurações de senha do dispositivo

- **Keyguard**: Escolha **Desabilitar** para impedir que os usuários usem o recurso de tela de bloqueio Keyguard no dispositivo. **Não configurado** permite o uso dos recursos de Keyguard.
- **Recursos do keyguard desabilitados**: Quando o keyguard estiver habilitado no dispositivo, escolha quais recursos desabilitar. Por exemplo, quando a **Câmera segura** estiver marcada, o recurso de câmera estará desabilitado no dispositivo. Os recursos não marcados estão habilitados no dispositivo.
- **Tipo de senha necessária**: Defina o tipo de senha necessária para o dispositivo. Suas opções:
  - **Pelo menos, numérico**
  - **Complexo numérico**: Números repetidos ou consecutivos, como "1111" ou "1234", não são permitidos.
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Comprimento mínimo da senha**: Insira o tamanho mínimo da senha que um usuário deve inserir (entre 4 e 16 caracteres).
- **Número de falhas de início de sessão antes de limpar o dispositivo**: Insira o número de falhas de entrada permitido antes do dispositivo ser apagado (entre 1 e 11).

### <a name="power-settings"></a>Configurações da energia

- **Tempo para bloquear a tela**: Defina a quantidade de tempo ocioso necessário para que o dispositivo seja bloqueado.
- **Tela ligada enquanto o dispositivo está conectado**: Escolha quais fontes de alimentação fazem com que a tela do dispositivo permaneça ligada enquanto o dispositivo está conectado.

### <a name="users-and-accounts-settings"></a>Configurações de usuários e de contas

- **Adicione novos usuários**: Escolha **Bloquear** para impedir que os usuários adicionem novos usuários. Cada usuário tem um espaço pessoal no dispositivo para personalização da tela inicial, contas, aplicativos e configurações. **Não configurado** permite que os usuários adicionem outros usuários ao dispositivo.
- **Remoção de usuários**: Escolha **Bloquear** para impedir que os usuários removam outros usuários. **Não configurado** permite que os usuários removam outros usuários do dispositivo.
- **Alterações da conta**: Escolha **Bloquear** para impedir que os usuários modifiquem as contas. **Não configurado** permite que os usuários atualizem contas de usuário no dispositivo.

### <a name="connectivity"></a>Conectividade

- **VPN sempre ativado**: Escolha **Habilitar** para definir um cliente VPN para se conectar e se reconectar automaticamente à VPN. As conexões VPN Always On permanecem conectadas ou são reconectadas imediatamente quando o usuário bloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. 

  Escolha **Não configurado** para desabilitar a VPN Always On para todos os clientes VPN.

  > [!IMPORTANT]
  > Certifique-se de implantar apenas uma política de VPN Always On a um único dispositivo. Não há suporte para a implantação de várias políticas de VPN Always On a um único dispositivo.

- **Cliente VPN**: Escolha um cliente VPN compatível com Always On. Suas opções:
  - Cisco AnyConnect
  - Acesso por F5
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Personalizado
    - **ID do Pacote**: Insira a ID do pacote do aplicativo na Google Play Store. Por exemplo, se a URL do aplicativo na Play Store for `https://play.google.com/store/details?id=com.contosovpn.android.prod`, então a ID do pacote será `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  >  - O cliente VPN escolhido deve ser instalado no dispositivo e deve dar suporte à VPN por aplicativo em perfis de trabalho. Caso contrário, ocorrerá um erro. 
  >  - É necessário aprovar o aplicativo cliente VPN na **Google Play Store Gerenciada**, sincronizar o aplicativo com o Intune e implantá-lo no dispositivo. Após fazer isso, o aplicativo será instalado no perfil de trabalho do usuário.
  >  - Talvez ocorram problemas conhecidos ao usar VPN por aplicativo com o Acesso por F5 para Android 3.0.4. Confira [Notas de versão do F5 para Acesso por F5 para Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) para saber mais.

- **Modo de bloqueio**: Escolha **Habilitar** para forçar todo o tráfego de rede a usar o túnel VPN. Se uma conexão com a VPN não for estabelecida, então o dispositivo não terá acesso à rede.

  Escolha **Não configurado** para permitir que o tráfego flua pelo túnel VPN ou por meio da rede móvel.

## <a name="work-profile-only"></a>Somente perfil de trabalho 

### <a name="work-profile-settings"></a>Configurações de perfil de trabalho

#### <a name="general"></a>Geral

- **Copiar e colar entre perfis de trabalho e pessoais**: Escolha **Bloquear** para evitar ações de copiar e colar entre aplicativos pessoais e de trabalho. **Não configurado** permite que os usuários compartilhem dados usando ações de copiar e colar com aplicativos no perfil pessoal 
- **Compartilhamento de dados entre perfis pessoais e de trabalho**: Escolha se os aplicativos no perfil de trabalho podem compartilhar com os aplicativos do perfil pessoal do usuário. Por exemplo, é possível controlar as ações de compartilhamento em aplicativos, como a opção **Compartilhar…** no aplicativo de navegador Chrome. Essa configuração não é aplicável ao comportamento copiar/colar para a área de transferência. Suas opções de compartilhamento:
  - **Restrições de compartilhamento padrão**: O comportamento de compartilhamento padrão do dispositivo, que varia dependendo da versão do Android. Por padrão, há permissão para o compartilhamento do perfil pessoal com o perfil de trabalho. Também por padrão, o compartilhamento do perfil de trabalho com o perfil pessoal é bloqueado. Essa configuração impede o compartilhamento de dados do perfil de trabalho com o perfil pessoal. Em dispositivos que executam as versões 6.0 e posteriores, o Google não bloqueia o compartilhamento do perfil pessoal par ao perfil corporativo.
  - **Os aplicativos no perfil de trabalho podem lidar com a solicitação de compartilhamento do perfil pessoal**: Habilita o recurso interno do Android que permite o compartilhamento do perfil pessoal para o perfil de trabalho. Quando habilitada, uma solicitação de compartilhamento de um aplicativo no perfil pessoal pode ser compartilhada com aplicativos no perfil de trabalho. Essa configuração é o comportamento padrão para dispositivos Android executando versões anteriores à 6.0.
  - **Permitir o compartilhamento entre limites**: Habilita o compartilhamento no limite do perfil de trabalho em ambas as orientações. Quando você seleciona essa configuração, os aplicativos no perfil de trabalho podem compartilhar dados com aplicativos sem selo no perfil pessoal. Essa configuração permite que os aplicativos gerenciados no perfil de trabalho sejam compartilhados com aplicativos no lado não gerenciado do dispositivo. Portanto, use essa configuração com cuidado.

- **Notificações do perfil de trabalho enquanto o dispositivo estiver bloqueado**: Controla se os aplicativos no perfil corporativo podem exibir dados em notificações quando o dispositivo está bloqueado. **Bloquear** não mostra os dados. **Não configurado** mostra os dados.
- **Permissões do aplicativo padrão**: Define a política de permissão padrão para todos os aplicativos no perfil de trabalho. A partir do Android 6, o usuário deve conceder determinadas permissões necessárias por aplicativos quando o aplicativo é iniciado. Essa configuração de política permite que você decida se os usuários deverão conceder permissões para todos os aplicativos no perfil de trabalho. Por exemplo, você atribui um aplicativo ao perfil de trabalho que exige o acesso à localização. Normalmente, esse aplicativo solicita que o usuário aprove ou negue o acesso à localização para o aplicativo. Use essa política para conceder permissões automaticamente sem um prompt, para negar automaticamente permissões sem um prompt ou permitir que o usuário final decida. Escolha:
  - **Padrão do dispositivo**
  - **Prompt**
  - **Concessão automática**
  - **Negação automática**

  Também é possível usar uma política de Configuração de Aplicativo para conceder permissões para aplicativos individuais (**Aplicativos Cliente** > **Políticas de configuração de aplicativo**).

- **Adicionar e remover contas**: Escolha **Bloquear** para impedir que os usuários finais adicionem ou removam contas manualmente no perfil de trabalho. Por exemplo, ao implantar o aplicativo Gmail em um perfil de trabalho Android, é possível impedir que usuários finais adicionem ou removam contas nesse perfil de trabalho. **Não configurado** permite a adição de contas no perfil corporativo.  

- **Compartilhamento de contatos por Bluetooth**: Permite o acesso a contatos de trabalho de outro dispositivo, como um carro, emparelhado usando Bluetooth. Por padrão, essa definição não está configurada, e os contatos do perfil de trabalho não são mostrados. Selecione **Habilitar** para permitir esse compartilhamento e mostrar contatos de perfil de trabalho. Essa configuração aplica-se a dispositivos de perfil de trabalho Android no sistema operacional Android v6.0 e mais recentes. Habilitar essa configuração pode permitir que determinados dispositivos Bluetooth armazenem em cache os contatos do trabalho após a primeira conexão. Desabilitar essa política após um emparelhamento/uma sincronização inicial pode não remover os contatos de trabalho de um dispositivo Bluetooth.

- **Captura de tela**: Escolha **Bloquear** para impedir capturas de tela ou outras capturas no dispositivo que usa o perfil corporativo. Ela também impede que o conteúdo seja exibido em dispositivos de vídeo que não tenham uma saída de vídeo segura. **Não configurado** permite a obtenção de capturas de tela.

- **Exibir a identificação do chamador do contato de trabalho no perfil pessoal**: Quando esta opção está habilitada (**Não configurada**), os detalhes de contato comercial do chamador são exibidos no perfil pessoal. Quando definido como **Bloquear**, o número de chamador do contato corporativo não é exibido no perfil pessoal. Aplicável ao sistema operacional Android v6.0 e às versões mais recentes.

- **Pesquisar contatos de trabalho do perfil pessoal**: Escolha **Bloquear** para impedir que os usuários pesquisem contatos corporativos em aplicativos no perfil pessoal. **Não obrigatório** permite pesquisar contatos corporativos no perfil pessoal.

- **Câmera**: Escolha **Bloquear** para impedir o acesso à câmera no dispositivo que usa o perfil corporativo. A câmera no lado pessoal não é afetada pela configuração. **Não obrigatório** permite o acesso à câmera no perfil corporativo.

#### <a name="work-profile-password"></a>Senha do perfil corporativo

- **Exigir senha do perfil de trabalho**: Aplica-se ao Android 7.0 e posterior com o perfil de trabalho habilitado. Escolha **Exigir** para inserir uma política de senha que aplica-se somente aos aplicativos no perfil corporativo. Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou os usuários podem optar por combinar os PINs no mais forte entre eles. **Não configurado** permite o uso de aplicativos corporativos, sem inserir uma senha.
- **Comprimento mínimo da senha**: Insira o número mínimo de caracteres que a senha do usuário deve ter, de **4**-**16**.
- **Máximo de minutos de inatividade até o perfil de trabalho ser bloqueado**: Selecione quanto tempo até o bloqueio do perfil de trabalho. O usuário deve inserir suas credenciais para recuperar o acesso.
- **Número de falhas de início de sessão antes de limpar o dispositivo**: Insira o número de vezes que uma senha incorreta pode ser inserida antes que o perfil de trabalho seja apagado do dispositivo.
- **Expiração da senha (dias)**: Insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**).
- **Tipo de senha necessária**: Selecione o tipo de senha que deve ser definido no dispositivo. Escolha:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Complexo numérico**: Números repetidos ou consecutivos, como "1111" ou "1234" não são permitidos
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Evitar a reutilização de senhas anteriores**: Insira o número de novas senhas que devem ser usadas para que uma senha antiga possa ser reutilizada (de **1**-**24**).
- **Desbloqueio por impressão digital**: Escolha **Bloquear** para impedir que usuários finais usem o scanner de impressão digital do dispositivo para desbloqueá-lo. **Não configurado** permite que os usuários desbloqueiem dispositivos com impressão digital no perfil corporativo.
- **Smart Lock e outros agentes de confiança**: Escolha **Bloquear** para impedir que o Smart Lock ou outros agentes de confiança ajustem as configurações de tela de bloqueio em dispositivos compatíveis. Esse recurso, às vezes conhecido como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo quando este está em um local confiável. Por exemplo, ignore a senha do perfil de trabalho quando o dispositivo estiver conectado a um dispositivo Bluetooth específico ou quando ele estiver próximo a uma marca NFC. Use essa configuração para impedir que os usuários configurem o Smart Lock.

### <a name="device-password"></a>Senha do dispositivo

Essas configurações de senha aplicam-se a perfis pessoais em dispositivos que usam um perfil corporativo.

- **Comprimento mínimo da senha**: Insira o número mínimo de caracteres que a senha do usuário deve ter, de **4**-**14**.
- **Máximo de minutos de inatividade até a tela ser bloqueada**: Selecione quanto tempo até que um dispositivo inativo seja bloqueado automaticamente
- **Número de falhas de início de sessão antes de limpar o dispositivo**: Especifica o número de vezes que uma senha incorreta pode ser inserida antes que todos os dados sejam eliminados do dispositivo
- **Expiração da senha (dias)**: Insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**)
- **Tipo de senha necessária**: Selecione o tipo de senha que deve ser definido no dispositivo. Escolha:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Complexo numérico**: Números repetidos ou consecutivos, como '1111' ou '1234' não são permitidos
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Evitar a reutilização de senhas anteriores**: Insira o número de novas senhas que devem ser usadas para que uma senha antiga possa ser reutilizada (de **1**-**24**).
- **Desbloqueio por impressão digital**: Escolha **Bloquear** para impedir que um usuário final use o scanner de impressão digital do dispositivo para desbloqueá-lo. **Não configurado** permite que o usuário desbloqueie o dispositivo usando uma impressão digital.
- **Smart Lock e outros agentes de confiança**: Escolha **Bloquear** para impedir que o Smart Lock ou outros agentes de confiança ajustem as configurações de tela de bloqueio em dispositivos compatíveis. Esse recurso, às vezes conhecido como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo quando este está em um local confiável. Por exemplo, ignore a senha do perfil de trabalho quando o dispositivo estiver conectado a um dispositivo Bluetooth específico ou quando ele estiver próximo a uma marca NFC. Use essa configuração para impedir que os usuários configurem o Smart Lock.

### <a name="system-security"></a>Segurança do sistema

- **Verificação de ameaças em aplicativos**: **Obrigatório** garante que a configuração **Verificar aplicativos** esteja habilitada para perfis pessoais e corporativos.

   > [!Note]
   > Essa configuração só funciona para dispositivos Android O e superior.

### <a name="connectivity"></a>Conectividade

- **VPN sempre ativado**: Escolha **Habilitar** para definir um cliente VPN para se conectar e se reconectar automaticamente à VPN. As conexões VPN Always On permanecem conectadas ou são reconectadas imediatamente quando o usuário bloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. 

  Escolha **Não configurado** para desabilitar a VPN Always On para todos os clientes VPN.

  > [!IMPORTANT]
  > Certifique-se de implantar apenas uma política de VPN Always On a um único dispositivo. Não há suporte para a implantação de várias políticas de VPN Always On a um único dispositivo.

- **Cliente VPN**: Escolha um cliente VPN compatível com Always On. Suas opções:
  - Cisco AnyConnect
  - Acesso por F5
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Personalizado
    - **ID do Pacote**: Insira a ID do pacote do aplicativo na Google Play Store. Por exemplo, se a URL do aplicativo na Play Store for `https://play.google.com/store/details?id=com.contosovpn.android.prod`, então a ID do pacote será `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  >  - O cliente VPN escolhido deve ser instalado no dispositivo e deve dar suporte à VPN por aplicativo em perfis de trabalho. Caso contrário, ocorrerá um erro. 
  >  - É necessário aprovar o aplicativo cliente VPN na **Google Play Store Gerenciada**, sincronizar o aplicativo com o Intune e implantá-lo no dispositivo. Após fazer isso, o aplicativo será instalado no perfil de trabalho do usuário.
  >  - Talvez ocorram problemas conhecidos ao usar VPN por aplicativo com o Acesso por F5 para Android 3.0.4. Confira [Notas de versão do F5 para Acesso por F5 para Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) para saber mais.

- **Modo de bloqueio**: Escolha **Habilitar** para forçar todo o tráfego de rede a usar o túnel VPN. Se uma conexão com a VPN não for estabelecida, então o dispositivo não terá acesso à rede.

  Escolha **Não configurado** para permitir que o tráfego flua pelo túnel VPN ou por meio da rede móvel.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Também é possível criar perfis de quiosque para dispositivos com [Android](device-restrictions-android.md#kiosk) e [Windows 10](kiosk-settings.md).
