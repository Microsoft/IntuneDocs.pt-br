---
title: Configurações de dispositivo do Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos com Android Enterprise ou Android for Work, restrinja algumas configurações no dispositivo, como copiar e colar, mostrar notificações, permissões de aplicativo, compartilhamento de dados, tamanho de senha, falhas de entrada, usar impressão digital para desbloquear, reutilizar senhas e habilitar o compartilhamento de contatos de trabalho por Bluetooth. Configure dispositivos como um quiosque de dispositivos dedicados para executar um ou vários aplicativos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/30/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 14fa330b0c158d98c96e0d151f8a4ec7d0c95b97
ms.sourcegitcommit: c38a856725993a4473ada75e669a57f75ab376f8
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73143032"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações do dispositivo do Android Enterprise para permitir ou restringir os recursos usando o Intune

Este artigo lista e descreve as diferentes configurações que você pode controlar em dispositivos Android Enterprise. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, executar aplicativos em dispositivos dedicados, segurança de controle e muito mais.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Somente proprietário do dispositivo

### <a name="general-settings"></a>Configurações gerais

- **Captura de tela**: escolha **Bloquear** para impedir capturas de tela ou outras capturas no dispositivo. Ela também impede que o conteúdo seja exibido em dispositivos de vídeo que não tenham uma saída de vídeo segura. **Não configurado** permite que o usuário capture o conteúdo da tela como uma imagem.
- **Câmera**: escolha **Bloquear** para impedir o acesso à câmera no dispositivo. **Não necessário** permite o acesso à câmera do dispositivo.
- **Política de permissão padrão**: essa configuração define a política de permissão padrão para as solicitações de permissões do runtime. Os valores possíveis incluem:
  - **Padrão do dispositivo**: usar a configuração padrão do dispositivo.
  - **Solicitar**: é solicitado que o usuário aprove a permissão.
  - **Concessão automática**: as permissões são concedidas automaticamente.
  - **Negação automática**: as permissões serão negadas automaticamente.
- **Alterações de data e hora**: escolha **Bloquear** para impedir que os usuários definam manualmente a data e a hora. **Não configurado** permite que os usuários definam a data e a hora do dispositivo.
- **Alterações de volume**: o **bloco** impede que os usuários alterem o volume do dispositivo e também faz mudo do volume mestre. **Não configurado** permite o uso de configurações de volume no dispositivo.
- **Redefinição de fábrica**: escolha **Bloquear** para impedir o uso da opção de redefinição de fábrica nas configurações do dispositivo. **Não configurado** permite o uso dessa configuração no dispositivo.
- **Inicialização segura**: escolha **Bloquear** para impedir que os usuários reiniciem o dispositivo no modo de segurança. **Não configurado** permite que os usuários reiniciem o dispositivo no modo de segurança.
- **Barra de status**: escolha **Bloquear** para impedir o acesso à barra de status, incluindo notificações e configurações rápidas. **Não configurado** permite aos usuários acesso à barra de status.
- **Serviços de dados de roaming**: escolha **Bloquear** para impedir o roaming de dados pela rede celular. **Não configurado** permite o roaming de dados quando o dispositivo estiver em uma rede celular.
- **Alterações de configuração de Wi-Fi**: escolha **Bloquear** para impedir que os usuários alterem as configurações de Wi-Fi criadas pelo proprietário do dispositivo. Os usuários podem criar suas próprias configurações de Wi-Fi. **Não configurado** permite que os usuários alterem as configurações de Wi-Fi no dispositivo.
- **Configuração de ponto de acesso Wi-Fi**: escolha **Bloquear** para impedir que os usuários criem ou alterem as configurações de Wi-Fi. **Não configurado** permite que os usuários alterem as configurações de Wi-Fi no dispositivo.
- **Configuração de Bluetooth**: escolha **Bloquear** para impedir que os usuários configurem o Bluetooth no dispositivo. **Não configurado** permite o uso de Bluetooth no dispositivo.
- **Compartilhamento e acesso a pontos de acesso**: escolha **Bloquear** para impedir o compartilhamento e o acesso a pontos de acesso portáteis. **Não configurado** permite o compartilhamento e acesso a pontos de acesso portáteis.
- **Armazenamento USB**: escolha **Permitir** para acessar o armazenamento USB no dispositivo. **Não configurado** impede o acesso ao armazenamento USB.
- **Transferência de arquivos USB**: escolha **Bloquear** para evitar a transferência de arquivos por USB. **Não configurado** permite a transferência de arquivos.
- **Mídia externa**: escolha **Bloquear** para evitar usar ou se conectar a qualquer mídia externa no dispositivo. **Não configurado** permite a conexão de mídias externas ao dispositivo.
- **Transmitir dados usando NFC**: escolha **Bloquear** para impedir o uso da tecnologia NFC (Near Field Communication, comunicação a curta distância) para transmitir dados de aplicativos. **Não configurado** permite o uso de NFC para compartilhar dados entre dispositivos.
- **Recursos de depuração**: escolha **Permitir** para permitir o uso dos recursos de depuração no dispositivo. **Não configurado** impede o uso dos recursos de depuração no dispositivo.
- **Ajuste de microfone**: escolha **Bloquear** para impedir que os usuários cancelem o mudo do microfone e ajustem o volume. **Não configurado** permite o uso e ajuste do volume do microfone no dispositivo.
- **Emails para proteção de redefinição de fábrica**: escolha **Endereços de email de conta do Google**. Insira os endereços de email dos administradores do dispositivo que podem desbloquear o dispositivo após ele ser apagado. Separe os endereços de email com um ponto e vírgula, como `admin1@gmail.com;admin2@gmail.com`. Se um email não for inserido, qualquer pessoa poderá desbloquear o dispositivo após ele ser restaurado para as configurações de fábrica. Esses emails se aplicam somente quando uma redefinição de fábrica que não é de usuário é executada, como executar uma redefinição de fábrica usando o menu de recuperação.
- **Hachura de escape de rede**: escolha **Habilitar** para permitir que os usuários ativem o recurso de hachura de escape de rede. Se não houver uma conexão de rede quando o dispositivo for iniciado, a hachura de escape solicitará a conexão temporária a uma rede e atualizará a política do dispositivo. Depois de aplicar a política, a rede temporária será esquecida e o dispositivo continuará com a inicialização. Esse recurso conecta os dispositivos a uma rede se:
  - Não houver uma rede adequada na última política.
  - O dispositivo iniciar em um aplicativo no modo de tarefa de bloqueio.
  - O usuário não conseguir acessar as configurações do dispositivo.

  **Não configurado** impede que os usuários ativem o recurso de hachura de escape de rede no dispositivo.

- **Atualização do sistema**: escolha uma opção para definir como o dispositivo trata as atualizações over-the-air:
  - **Padrão do dispositivo**: usar a configuração padrão do dispositivo.
  - **Automático**: as atualizações são instaladas automaticamente sem interação do usuário. A configuração dessa política instala imediatamente todas as atualizações pendentes.
  - **Adiado**: as atualizações são adiadas por 30 dias. Após 30 dias o Android solicita ao usuário a instalação da atualização. É possível que os fabricantes de dispositivos ou operadoras impeçam que as atualizações de segurança importantes (isenção) sejam adiadas. Uma atualização isenta mostra uma notificação do sistema para o usuário no dispositivo.
  - **Janela de manutenção**: instala as atualizações automaticamente durante uma janela de manutenção diária definida no Intune. A instalação ocorre diariamente por 30 dias, e pode falhar devido a espaço insuficiente ou aos níveis de bateria. Após 30 dias, o Android solicita ao usuário a instalação. Essa janela também é usada para instalar atualizações de aplicativos do Play. Use essa opção para dispositivos dedicados, como quiosques, pois é possível atualizar aplicativos de primeiro plano em dispositivos dedicados de aplicativo único.

- **Janelas de notificação**: quando essa opção é definida como **Desabilitar**, as notificações de janela, incluindo notificações do sistema, chamadas de entrada, chamadas de saída, alertas do sistema e erros do sistema, não são mostradas no dispositivo. Quando essa opção é definida como **Não configurado**, o padrão do sistema operacional é usado, que poderá ser mostrar as notificações.
- **Ignorar dicas de primeiro uso**: escolha **Habilitar** para ocultar ou ignorar as sugestões de aplicativos para percorrer os tutoriais ou ler dicas de introdução quando o aplicativo é iniciado. Quando essa opção é definida como **Não configurado**, o padrão do sistema operacional é usado, que poderá ser mostrar essas sugestões quando o aplicativo for iniciado.

### <a name="system-security-settings"></a>Configurações de segurança do sistema

- **Verificação de ameaças em aplicativos**: **Exigir** (padrão) permite que o Google Play Protect verifique os aplicativos antes e após a instalação. Se ela detectar uma ameaça, poderá avisar o usuário para remover o aplicativo do dispositivo. **Não configurado** não habilita nem executa o Google Play Protect para verificar os aplicativos.

### <a name="dedicated-device-settings"></a>Configurações do dispositivo dedicado

Use essas configurações para definir uma experiência de estilo de quiosque em seus dispositivos dedicados. É possível configurar um dispositivo para executar um ou vários aplicativos. Quando um dispositivo está no modo de quiosque, somente os aplicativos que você adiciona ficam disponíveis. Essas configurações aplicam-se a dispositivos dedicados com Android Enterprise. Elas não se aplicam a dispositivos totalmente gerenciados com Android Enterprise.

**Modo de quiosque**: escolha se o dispositivo executa um ou vários aplicativos.

- **Aplicativo individual**: os usuários só podem acessar um único aplicativo no dispositivo. Quando o dispositivo inicia, somente o aplicativo específico é exibido. Os usuários são impedidos de abrir novos aplicativos e alterar o aplicativo em execução.

  - **Selecione um aplicativo gerenciado**: escolha o aplicativo gerenciado da Google Play na lista.

    Se não houver aplicativos listados, [adicione alguns aplicativos Android](../apps/apps-add-android-for-work.md) ao dispositivo. Não se esqueça de [atribuir o aplicativo ao grupo de dispositivos criado para seus dispositivos dedicados](../apps/apps-deploy.md).

  > [!IMPORTANT]
  > Ao usar o modo de quiosque de aplicativo único, os aplicativos de discagem/telefone podem não funcionar corretamente. 
  
- **Vários aplicativos**: os usuários podem acessar um conjunto limitado de aplicativos no dispositivo. Quando o dispositivo inicia, somente os aplicativos adicionados são exibidos. Também é possível adicionar alguns links da Web que os usuários podem abrir. Ao aplicar a política, os usuários veem ícones para os aplicativos permitidos na tela inicial.

  > [!IMPORTANT]
  > Para dispositivos dedicados com vários aplicativos, o [aplicativo Tela Inicial Gerenciada](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) na Google Play **deve ser**:
  >   - [Adicionado como um aplicativo cliente](../apps/apps-add-android-for-work.md) no Intune
  >   - [Atribuído ao grupo de dispositivos](../apps/apps-deploy.md) criado para seus dispositivos dedicados
  >
  > O aplicativo **Tela Inicial Gerenciada** não precisa estar no perfil de configuração, mas precisa ser adicionado como um aplicativo cliente. Quando o aplicativo **Tela Inicial Gerenciada** é adicionado como um aplicativo cliente, quaisquer outros aplicativos que você adicionar ao perfil de configuração serão mostrados como ícones no aplicativo **Tela Inicial Gerenciada**.
  >
  > Ao usar o modo de quiosque de vários aplicativos, os aplicativos de discagem/telefone podem não funcionar corretamente. 

  - **Adicionar**: selecione seus aplicativos na lista.

    Se o aplicativo **Tela Inicial Gerenciada** não estiver listado, [adicione-o pela Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Não se esqueça de [atribuir o aplicativo](../apps/apps-deploy.md) ao grupo de dispositivos criado para seus dispositivos dedicados.

    Também é possível adicionar outros [aplicativos Android](../apps/apps-add-android-for-work.md) e [aplicativos Web](../apps/web-app.md) criados por sua organização ao dispositivo. Não se esqueça de [atribuir o aplicativo ao grupo de dispositivos criado para seus dispositivos dedicados](../apps/apps-deploy.md).

  - **Botão página inicial virtual**: um botão de chave flexível que retorna usuários para a tela inicial gerenciada para que os usuários possam alternar entre aplicativos. Suas opções:

    - **Não configurado** (padrão): um botão de página inicial não é mostrado. Os usuários devem usar o botão voltar para alternar entre aplicativos.
    - **Deslizar para cima**: um botão página inicial mostra quando um usuário passa o dedo para cima no dispositivo.
    - **Flutuante**: mostra um botão de página inicial persistente e flutuante no dispositivo.

  - **Sair do modo de quiosque**: escolha **Habilitar** para permitir que os administradores pausem temporariamente o modo de quiosque para atualizar o dispositivo. Para usar esse recurso, o administrador:
  
    1. Continue a selecionar o botão voltar até que o botão **Sair do quiosque** apareça. 
    2. Selecione o botão **Sair do quiosque** e insira o PIN do **Código para sair do modo de quiosque**.
    3. Quando terminar, selecione o aplicativo de **tela inicial gerenciado** . Esta etapa bloqueia novamente o dispositivo no modo de quiosque de vários aplicativos.

      Quando definido como **não configurado**, os administradores não podem pausar o modo de quiosque. Se o administrador continua selecionando o botão voltar e seleciona o botão **Sair do quiosque**, uma mensagem pede a senha.

    - **Sair do código do modo de quiosque**: insira um PIN numérico de 4 a 6 dígitos. O administrador usa esse PIN para pausar temporariamente o modo de quiosque.

  - **Definir a tela de fundo da URL personalizada**: insira uma URL para personalizar a tela de fundo no dispositivo dedicado.

    > [!NOTE]
    > Na maioria dos casos, é recomendável iniciar com imagens com pelo menos os seguintes tamanhos:
    >
    > - Celular: 1080x1920 px
    > - Tablet: 1920x1080 px
    >
    > Para obter a melhor experiência e detalhes nítidos, sugere-se que os ativos de imagem por dispositivo sejam criados de acordo com as especificações de exibição.
    >
    > Exibições modernas têm densidades de pixel mais altas e podem exibir imagens de definição 2K/4K equivalentes.

  - **Configuração de Wi-Fi**: **habilitar** mostra o controle Wi-Fi na tela inicial gerenciada e permite que os usuários finais conectem o dispositivo a redes wifi diferentes. Habilitar esse recurso também ativa a localização do dispositivo. **Não configurado** (padrão) não mostra o controle Wi-Fi na tela inicial gerenciada. Ele impede que os usuários se conectem a redes Wi-Fi usando a tela inicial gerenciada.

  - **Configuração de Bluetooth**: **habilitar** mostra o controle Bluetooth na tela inicial gerenciada e permite que os usuários finais Emparelhem dispositivos via Bluetooth. Habilitar esse recurso também ativa a localização do dispositivo. **Não configurado** (padrão) não mostra o controle Bluetooth na tela inicial gerenciada. Ele impede que os usuários configurem dispositivos Bluetooth e de emparelhamento ao usar a tela inicial gerenciada.

  - **Acesso à lanterna**: **habilitar** mostra o controle lanterna na tela inicial gerenciada e permite que os usuários finais ativem ou desativem a lanterna. **Não configurado** (padrão) não mostra o controle lanterna na tela inicial gerenciada. Ele impede que os usuários usem a lanterna ao usar a tela inicial gerenciada.

  - **Controle de volume de mídia**: **habilitar** mostra o controle de volume de mídia na tela inicial gerenciada e permite que os usuários finais ajustem o volume de mídia do dispositivo usando um controle deslizante. **Não configurado** (padrão) não mostra o controle de volume de mídia na tela inicial gerenciada. Ele impede que os usuários ajustem o volume de mídia do dispositivo ao usar a tela inicial gerenciada, a menos que seus botões de hardware ofereçam suporte a ele. 

  - **Modo de proteção de tela**: **habilitar** mostra uma barra de proteção na tela inicial gerenciada quando o dispositivo está bloqueado ou expira. **Não configurado** (padrão) não mostra uma barra de proteção na tela inicial gerenciada.

    Quando habilitado, configure também:

    - **Definir imagem de proteção de tela personalizada**: Insira a URL para uma imagem personalizada. Por exemplo, insira:

      - `http://www.contoso.com/image.jpg`
      - `www.contoso.com/image.bmp`
      - `https://www.contoso.com/image.html`

      Se você não inserir uma URL, a imagem padrão do dispositivo será usada, se houver uma imagem padrão.

    - **Número de segundos que o dispositivo mostra a proteção de tela antes**de desligar a tela: escolha por quanto tempo o dispositivo mostra a proteção. Digite um valor entre 0 e 9999999 segundos. O padrão é `0` segundos. Quando deixado em branco ou definido como zero (`0`), a proteção de tela estará ativa até que um usuário interaja com o dispositivo.
    - **Número de segundos em que o dispositivo fica inativo antes de mostrar a proteção de tela**: escolha por quanto tempo o dispositivo estará ocioso antes de mostrar a proteção. Digite um valor entre 1 e 9999999 segundos. O padrão é `30` segundos. Você deve inserir um número maior que zero (`0`).
    - **Detectar mídia antes de iniciar a proteção de tela**: **habilitar** (padrão) não mostrará a proteção de tela se áudio ou vídeo estiver sendo reproduzido no dispositivo. **Não configurado** mostra a proteção de tela, mesmo se o áudio ou vídeo estiver sendo reproduzido.

### <a name="device-password-settings"></a>Configurações de senha do dispositivo

- **Desabilitar tela de bloqueio**: escolha **Desabilitar** para impedir que os usuários usem o recurso de tela de bloqueio Keyguard no dispositivo. **Não configurado** permite o uso dos recursos de Keyguard.
- **Recursos da tela de bloqueio desabilitados**: quando o Keyguard estiver habilitado no dispositivo, escolha quais recursos desabilitar. Por exemplo, quando a **Câmera segura** estiver marcada, o recurso de câmera estará desabilitado no dispositivo. Os recursos não marcados estão habilitados no dispositivo.

  Esses recursos estão disponíveis para os usuários quando o dispositivo está bloqueado. Os usuários não verão nem acessarão recursos verificados.

- **Tipo de senha necessária**: defina o tipo de senha necessária para o dispositivo. Suas opções:
  - **Padrão do dispositivo**
  - **Senha obrigatória, sem restrições**
  - **Biometria fraca**: [Biometria forte vs. fraca](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (abre o site do Android)
  - **Numérica**: a senha só deve conter números, como `123456789`. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
  - **Complexo numérico**: números repetidos ou consecutivos, como "1111" ou "1234", não são permitidos. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
  - **Alfabética**: as letras do alfabeto são obrigatórias. Números e símbolos não são obrigatórios. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
  - **Alfanumérica**: inclui letras maiúsculas, letras minúsculas e caracteres numéricos. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
  - **Alfanumérica com símbolos**: inclui letras maiúsculas, letras minúsculas, caracteres numéricos, sinais de pontuação e símbolos. Insira também:

    - **Comprimento máximo da senha**: insira o comprimento máximo que uma senha deve ter, entre 4 e 16 caracteres.
    - **Número de caracteres obrigatórios**: insira o número de caracteres que a senha deve ter, entre 0 e 16 caracteres.
    - **Número de caracteres minúsculos obrigatórios**: insira o número de caracteres minúsculos que a senha deve ter, entre 0 e 16 caracteres.
    - **Número de caracteres maiúsculos obrigatórios**: insira o número de caracteres maiúsculos que a senha deve ter, entre 0 e 16 caracteres.
    - **Número de caracteres diferentes de letras obrigatórios**: insira o número de caracteres diferentes de letras (qualquer coisa diferente de letras do alfabeto) que a senha deve ter, entre 0 e 16 caracteres.
    - **Número de caracteres numéricos obrigatórios**: insira o número de caracteres numéricos (`1`, `2`, `3` e assim por diante) que a senha deve ter, entre 0 e 16 caracteres.
    - **Número de caracteres de símbolo obrigatórios**: insira o número de caracteres de símbolo (`&`, `#`, `%` e assim por diante) que a senha deve ter, entre 0 e 16 caracteres.

- **Número de dias até que a senha expire**: insira o número de dias, entre 1 e 365, até que a senha do dispositivo precise ser alterada. Por exemplo, para alterar a senha após 60 dias, insira `60`. Quando a senha expirar, o usuário deverá criar uma.
- **Número de senhas obrigatórias antes que o usuário possa reutilizar uma senha**: insira o número de senhas recentes que não podem ser utilizadas, entre 1 e 24. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.
- **Número de falhas de entrada antes de apagar o dispositivo**: insira o número, entre 4 e 11, de entradas com falha para permitir que o dispositivo seja apagado.

### <a name="power-settings"></a>Configurações da energia

- **Tempo para bloquear a tela**: Insira o tempo máximo que um usuário pode definir até que o dispositivo seja bloqueado. Por exemplo, se você definir essa configuração como **10 minutos**, os usuários poderão definir o tempo de 15 segundos até 10 minutos. Quando definido como **não configurado** (padrão), o Intune não altera nem controla essa configuração.

- **Tela ligada enquanto o dispositivo está conectado**: escolha quais fontes de alimentação fazem com que a tela do dispositivo permaneça ligada enquanto o dispositivo está conectado.

### <a name="users-and-accounts-settings"></a>Configurações de usuários e de contas

- **Adicionar novos usuários**: escolha **Bloquear** para impedir que os usuários adicionem novos usuários. Cada usuário tem um espaço pessoal no dispositivo para personalização da tela inicial, contas, aplicativos e configurações. **Não configurado** permite que os usuários adicionem outros usuários ao dispositivo.
- **Remoção de usuário**: escolha **Bloquear** para impedir que os usuários removam usuários. **Não configurado** permite que os usuários removam outros usuários do dispositivo.
- **Alterações de conta**: escolha **Bloquear** para impedir que os usuários modifiquem as contas. **Não configurado** permite que os usuários atualizem contas de usuário no dispositivo.

  > [!NOTE]
  > Essa configuração não é respeitada em dispositivos de proprietário do dispositivo (totalmente gerenciado). Se você definir essa configuração, a configuração será ignorada e não terá nenhum impacto.

### <a name="applications"></a>Aplicativos

- **Permitir instalação de fontes desconhecidas**: escolha **Permitir** para que os usuários possam ativar **Fontes desconhecidas**. Essa configuração permite aplicativos instalados de fontes desconhecidas, incluindo fontes diferentes da Google Play Store. **Não configurado** impede que os usuários ativem as **Fontes desconhecidas**.
- **Permitir acesso a todos os aplicativos na Google Play Store**: quando definido como **Permitir**, os usuários têm acesso a todos os aplicativos na Google Play Store. Eles não têm acesso aos aplicativos que o administrador bloqueia nos [Aplicativos cliente](../apps/apps-add-android-for-work.md). **Não configurado** força os usuários a acessar apenas os aplicativos que o administrador torna disponível na Google Play Store ou os aplicativos necessários nos [Aplicativos cliente](../apps/apps-add-android-for-work.md).
- **Atualizações automáticas do aplicativo**: escolha quando as atualizações automáticas são instaladas. Suas opções:
  - **Não configurado**
  - **Escolha do usuário**
  - **Nunca**
  - **Somente Wi-Fi**
  - **Sempre**

### <a name="connectivity"></a>Conectividade

- **VPN Always On**: escolha **Habilitar** para definir um cliente VPN para se conectar e se reconectar automaticamente à VPN. As conexões VPN Always On permanecem conectadas ou são reconectadas imediatamente quando o usuário bloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. 

  Escolha **Não configurado** para desabilitar a VPN Always On para todos os clientes VPN.

  > [!IMPORTANT]
  > Certifique-se de implantar apenas uma política de VPN Always On a um único dispositivo. Não há suporte para a implantação de várias políticas de VPN Always On a um único dispositivo.

- **Cliente VPN**: escolha um cliente VPN compatível com Always On. Suas opções:
  - Cisco AnyConnect
  - Acesso por F5
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Personalizado
    - **ID do pacote**: insira a ID do pacote do aplicativo na Google Play Store. Por exemplo, se a URL do aplicativo na Play Store for `https://play.google.com/store/details?id=com.contosovpn.android.prod`, então a ID do pacote será `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - O cliente VPN escolhido deve ser instalado no dispositivo e deve dar suporte à VPN por aplicativo em perfis de trabalho. Caso contrário, ocorrerá um erro. 
  > - É necessário aprovar o aplicativo cliente VPN na **Google Play Store Gerenciada**, sincronizar o aplicativo com o Intune e implantá-lo no dispositivo. Após fazer isso, o aplicativo será instalado no perfil de trabalho do usuário.
  > - Talvez ocorram problemas conhecidos ao usar VPN por aplicativo com o Acesso por F5 para Android 3.0.4. Confira [Notas de versão do F5 para Acesso por F5 para Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) para saber mais.

- **Modo de bloqueio**: escolha **Habilitar** para forçar todo o tráfego de rede a usar o túnel VPN. Se uma conexão com a VPN não for estabelecida, então o dispositivo não terá acesso à rede.

  Escolha **Não configurado** para permitir que o tráfego flua pelo túnel VPN ou por meio da rede móvel.

- **Proxy global recomendado**: escolha **habilitar** para adicionar um proxy global aos dispositivos. Quando habilitado, o tráfego HTTP e HTTPS, incluindo alguns aplicativos no dispositivo, use o proxy que você inserir. Esse proxy é apenas uma recomendação. É possível que alguns aplicativos não usem o proxy. **Não configurado** (padrão) não adiciona um proxy global recomendado.

  Para obter mais informações sobre esse recurso, consulte [setRecommendedGlobalProxy](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setRecommendedGlobalProxy(android.content.ComponentName,%20android.net.ProxyInfo)) (abre um site do Android).

  Quando habilitado, insira também o **tipo** de proxy. Suas opções:

  - **Direto**: escolha esta opção para inserir manualmente os detalhes do servidor proxy, incluindo:
    - **Host**: Insira o nome de host ou endereço IP do seu servidor proxy. Por exemplo, insira `proxy.contoso.com` ou `127.0.0.1`.
    - **Número da porta**: insira o número da porta TCP usado pelo servidor proxy. Por exemplo, insira `8080`.
    - **Hosts excluídos**: Insira uma lista de nomes de host ou endereços IP que não usarão o proxy. Essa lista pode incluir um asterisco (`*`) curinga e vários hosts separados por ponto e vírgula (`;`) sem espaços. Por exemplo, insira `127.0.0.1;web.contoso.com;*.microsoft.com`.

  - **Configuração automática de proxy**: Insira a **URL de PAC** para um script de configuração automática de proxy. Por exemplo, insira `https://proxy.contoso.com/proxy.pac`.

    Para obter mais informações sobre arquivos PAC, consulte o [Arquivo PAC (configuração automática de proxy)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (abre um site que não é da Microsoft).

## <a name="work-profile-only"></a>Somente perfil de trabalho

### <a name="work-profile-settings"></a>Configurações de perfil de trabalho

#### <a name="general"></a>Geral

- **Copiar e colar entre perfis pessoal e corporativo**: escolha **Bloquear** para impedir ações de copiar e colar entre aplicativos pessoais e corporativos. **Não configurado** permite que os usuários compartilhem dados usando ações de copiar e colar com aplicativos no perfil pessoal 
- **Compartilhamento de dados entre perfis pessoal e corporativo**: escolha se os aplicativos no perfil corporativo podem compartilhar com aplicativos no perfil pessoal. Por exemplo, é possível controlar as ações de compartilhamento em aplicativos, como a opção **Compartilhar…** no aplicativo de navegador Chrome. Essa configuração não é aplicável ao comportamento copiar/colar para a área de transferência. Suas opções de compartilhamento:
  - **Padrão do dispositivo**: o comportamento do compartilhamento padrão do dispositivo, que varia dependendo da versão do Android. Por padrão, há permissão para o compartilhamento do perfil pessoal com o perfil de trabalho. Também por padrão, o compartilhamento do perfil de trabalho com o perfil pessoal é bloqueado. Essa configuração impede o compartilhamento de dados do perfil de trabalho com o perfil pessoal. Em dispositivos que executam as versões 6.0 e posteriores, o Google não bloqueia o compartilhamento do perfil pessoal par ao perfil corporativo.
  - **Os aplicativos no perfil de trabalho podem lidar com solicitações de compartilhamento do perfil pessoal**: habilita o recurso interno do Android que permite o compartilhamento do perfil pessoal para o perfil de trabalho. Quando habilitada, uma solicitação de compartilhamento de um aplicativo no perfil pessoal pode ser compartilhada com aplicativos no perfil de trabalho. Essa configuração é o comportamento padrão para dispositivos Android executando versões anteriores à 6.0.
  - **Impedir qualquer compartilhamento entre limites**: impede o compartilhamento entre perfis pessoais e de trabalho.
  - **Sem restrições no compartilhamento**: habilita o compartilhamento entre o limite do perfil de trabalho em ambas as direções. Quando você seleciona essa configuração, os aplicativos no perfil de trabalho podem compartilhar dados com aplicativos sem selo no perfil pessoal. Essa configuração permite que os aplicativos gerenciados no perfil de trabalho sejam compartilhados com aplicativos no lado não gerenciado do dispositivo. Portanto, use essa configuração com cuidado.

- **Notificações do perfil de trabalho enquanto o dispositivo estiver bloqueado**: controla se os aplicativos no perfil corporativo podem exibir dados em notificações quando o dispositivo está bloqueado. **Bloquear** não mostra os dados. **Não configurado** mostra os dados.
- **Permissões de aplicativo padrão**: define a política de permissão padrão para todos os aplicativos no perfil de trabalho. A partir do Android 6, o usuário deve conceder determinadas permissões necessárias por aplicativos quando o aplicativo é iniciado. Essa configuração de política permite que você decida se os usuários deverão conceder permissões para todos os aplicativos no perfil de trabalho. Por exemplo, você atribui um aplicativo ao perfil de trabalho que exige o acesso à localização. Normalmente, esse aplicativo solicita que o usuário aprove ou negue o acesso à localização para o aplicativo. Use essa política para conceder permissões automaticamente sem um prompt, para negar automaticamente permissões sem um prompt ou permitir que o usuário final decida. Escolha:
  - **Padrão do dispositivo**
  - **Prompt**
  - **Concessão automática**
  - **Negação automática**

  Também é possível usar uma política de Configuração de Aplicativo para conceder permissões para aplicativos individuais (**Aplicativos Cliente** > **Políticas de configuração de aplicativo**).

- **Adicionar e remover contas**: escolha **Bloquear** para impedir que os usuários finais adicionem ou removam contas manualmente no perfil corporativo. Por exemplo, ao implantar o aplicativo Gmail em um perfil de trabalho Android, é possível impedir que usuários finais adicionem ou removam contas nesse perfil de trabalho. **Não configurado** permite a adição de contas no perfil corporativo.  

- **Contato com compartilhamento via Bluetooth**: permite o acesso a contatos de trabalho de outro dispositivo, como um carro, emparelhado usando Bluetooth. Por padrão, essa definição não está configurada, e os contatos do perfil de trabalho não são mostrados. Selecione **Habilitar** para permitir esse compartilhamento e mostrar contatos de perfil de trabalho. Essa configuração aplica-se a dispositivos de perfil de trabalho Android no sistema operacional Android v6.0 e mais recentes. Habilitar essa configuração pode permitir que determinados dispositivos Bluetooth armazenem em cache os contatos do trabalho após a primeira conexão. Desabilitar essa política após um emparelhamento/uma sincronização inicial pode não remover os contatos de trabalho de um dispositivo Bluetooth.

- **Captura de tela**: escolha **Bloquear** para impedir capturas de tela ou outras capturas no dispositivo que usa o perfil corporativo. Ela também impede que o conteúdo seja exibido em dispositivos de vídeo que não tenham uma saída de vídeo segura. **Não configurado** permite a obtenção de capturas de tela.

- **Exibir ID de chamador do contato de trabalho no perfil pessoal**: quando esta opção está habilitada (**Não configurado**), os detalhes de contato do chamador corporativo são exibidos no perfil pessoal. Quando definido como **Bloquear**, o número de chamador do contato corporativo não é exibido no perfil pessoal. Aplicável ao sistema operacional Android v6.0 e às versões mais recentes.

- **Pesquisar contatos de trabalho do perfil pessoal**: escolha **Bloquear** para impedir que os usuários pesquisem contatos corporativos em aplicativos no perfil pessoal. **Não obrigatório** permite pesquisar contatos corporativos no perfil pessoal.

- **Câmera**: escolha **Bloquear** para impedir o acesso à câmera no dispositivo que usa o perfil corporativo. A câmera no lado pessoal não é afetada pela configuração. **Não obrigatório** permite o acesso à câmera no perfil corporativo.

- **Permitir widgets de aplicativos de perfil de trabalho**: **habilitar** permite que os usuários finais coloquem widgets expostos por aplicativos na tela inicial. **Não configurado** (padrão) desabilita esse recurso.

  Por exemplo, o Outlook é instalado nos perfis de trabalho de seus usuários. Quando definido como **habilitar**, os usuários podem colocar o widget pauta na tela inicial do dispositivo.

#### <a name="work-profile-password"></a>Senha do perfil corporativo

- **Exigir senha de perfil de trabalho**: aplica-se ao Android 7.0 e posterior com o perfil de trabalho habilitado. Escolha **Exigir** para inserir uma política de senha que aplica-se somente aos aplicativos no perfil corporativo. Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou os usuários podem optar por combinar os PINs no mais forte entre eles. **Não configurado** permite o uso de aplicativos corporativos, sem inserir uma senha.
- **Tamanho mínimo da senha**: insira o número mínimo de caracteres que a senha do usuário deve ter, de **4**-**16**.
- **Máximo de minutos de inatividade até o bloqueio do perfil de trabalho**: selecione a quantidade de tempo até o perfil de trabalho ser bloqueado. O usuário deve inserir suas credenciais para recuperar o acesso.
- **Número de falhas de entrada antes de apagar o dispositivo**: insira o número de vezes que uma senha incorreta pode ser inserida antes que o perfil de trabalho seja apagado do dispositivo.
- **Expiração da senha (dias)** : insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**).
- **Tipo de senha necessária**: selecione o tipo de senha que deve ser definido no dispositivo. Escolha:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Numérico complexo**: números repetidos ou consecutivos, como "1111" ou "1234" não são permitidos
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Evitar a reutilização de senhas anteriores**: insira o número de novas senhas que devem ser usadas para que uma senha antiga possa ser reutilizada (de **1**-**24**).
- **Desbloqueio de impressão digital**: escolha **Bloquear** para impedir que usuários finais usem o scanner de impressão digital do dispositivo para desbloqueá-lo. **Não configurado** permite que os usuários desbloqueiem dispositivos com impressão digital no perfil corporativo.
- **Smart Lock e outros agentes de confiança**: escolha **Bloquear** para impedir que o Smart Lock ou outros agentes de confiança ajustem as configurações de tela de bloqueio em dispositivos compatíveis. Esse recurso, às vezes conhecido como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo quando este está em um local confiável. Por exemplo, ignore a senha do perfil de trabalho quando o dispositivo estiver conectado a um dispositivo Bluetooth específico ou quando ele estiver próximo a uma marca NFC. Use essa configuração para impedir que os usuários configurem o Smart Lock.

### <a name="device-password"></a>Senha do dispositivo

Essas configurações de senha aplicam-se a perfis pessoais em dispositivos que usam um perfil corporativo.

- **Tamanho mínimo da senha**: insira o número mínimo de caracteres que a senha do usuário deve ter, de **4**-**14**.
- **Máximo de minutos de inatividade até a tela ser bloqueada**: selecione o tempo decorrido até um dispositivo inativo ser bloqueado automaticamente
- **Número de falhas de entrada antes de apagar o dispositivo**: insira o número de vezes que uma senha incorreta pode ser inserida antes que todos os dados do dispositivo sejam apagados
- **Expiração da senha (dias)** : insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**)
- **Tipo de senha necessária**: selecione o tipo de senha que deve ser definido no dispositivo. Escolha:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Numérico complexo**: números repetidos ou consecutivos, como '1111' ou '1234' não são permitidos
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Evitar a reutilização de senhas anteriores**: insira o número de novas senhas que devem ser usadas para que uma senha antiga possa ser reutilizada (de **1**-**24**).
- **Desbloqueio de impressão digital**: escolha **Bloquear** para impedir que um usuário final use o scanner de impressão digital do dispositivo para desbloqueá-lo. **Não configurado** permite que o usuário desbloqueie o dispositivo usando uma impressão digital.
- **Smart Lock e outros agentes de confiança**: escolha **Bloquear** para impedir que o Smart Lock ou outros agentes de confiança ajustem as configurações de tela de bloqueio em dispositivos compatíveis. Esse recurso, às vezes conhecido como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo quando este está em um local confiável. Por exemplo, ignore a senha do perfil de trabalho quando o dispositivo estiver conectado a um dispositivo Bluetooth específico ou quando ele estiver próximo a uma marca NFC. Use essa configuração para impedir que os usuários configurem o Smart Lock.

### <a name="system-security"></a>Segurança do sistema

- **Examinar ameaças em aplicativos**: **Obrigatório** garante que a configuração **Verificar aplicativos** esteja habilitada para perfis pessoais e corporativos.

   > [!Note]
   > Essa configuração só funciona para dispositivos Android O e superior.

- **Impedir instalações de aplicativos de fontes desconhecidas no perfil pessoal**: por design, os dispositivos Android Enterprise Work Profile não podem instalar aplicativos de fontes diferentes da Play Store. Por natureza, os dispositivos de perfil de trabalho devem ser de perfil duplo:

  - Um perfil de trabalho gerenciado usando o MDM.
  - Um perfil pessoal isolado do gerenciamento de MDM.

  Essa configuração permite que os administradores tenham mais controle das instalações de aplicativos de fontes desconhecidas. **Não configurado** (padrão) permite instalações de aplicativos de fontes desconhecidas no perfil pessoal. **Bloquear** impede instalações de aplicativos de fontes diferentes da Play Store no perfil pessoal.

### <a name="connectivity"></a>Conectividade

- **VPN Always On**: escolha **Habilitar** para definir um cliente VPN para se conectar e se reconectar automaticamente à VPN. As conexões VPN Always On permanecem conectadas ou são reconectadas imediatamente quando o usuário bloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. 

  Escolha **Não configurado** para desabilitar a VPN Always On para todos os clientes VPN.

  > [!IMPORTANT]
  > Certifique-se de implantar apenas uma política de VPN Always On a um único dispositivo. Não há suporte para a implantação de várias políticas de VPN Always On a um único dispositivo.

- **Cliente VPN**: escolha um cliente VPN compatível com Always On. Suas opções:
  - Cisco AnyConnect
  - Acesso por F5
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Personalizado
    - **ID do pacote**: insira a ID do pacote do aplicativo na Google Play Store. Por exemplo, se a URL do aplicativo na Play Store for `https://play.google.com/store/details?id=com.contosovpn.android.prod`, então a ID do pacote será `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - O cliente VPN escolhido deve ser instalado no dispositivo e deve dar suporte à VPN por aplicativo em perfis de trabalho. Caso contrário, ocorrerá um erro. 
  > - É necessário aprovar o aplicativo cliente VPN na **Google Play Store Gerenciada**, sincronizar o aplicativo com o Intune e implantá-lo no dispositivo. Após fazer isso, o aplicativo será instalado no perfil de trabalho do usuário.
  > - Talvez ocorram problemas conhecidos ao usar VPN por aplicativo com o Acesso por F5 para Android 3.0.4. Confira [Notas de versão do F5 para Acesso por F5 para Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) para saber mais.

- **Modo de bloqueio**: escolha **Habilitar** para forçar todo o tráfego de rede a usar o túnel VPN. Se uma conexão com a VPN não for estabelecida, então o dispositivo não terá acesso à rede.

  Escolha **Não configurado** para permitir que o tráfego flua pelo túnel VPN ou por meio da rede móvel.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Também é possível criar perfis de quiosque de dispositivos dedicados para dispositivos com [Android](device-restrictions-android.md#kiosk) e [Windows 10](kiosk-settings.md).

## <a name="see-also"></a>Consulte também

[Configurando e solucionando problemas de dispositivos Android no Microsoft Intune](https://support.microsoft.com/help/4476974)
