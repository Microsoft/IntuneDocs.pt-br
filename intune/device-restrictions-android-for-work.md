---
title: Restrições do dispositivo para perfis de trabalho Android no Microsoft Intune – Azure | Microsoft Docs
description: Nos dispositivos de perfil do Android Enterprise, é possível restringir algumas configurações no dispositivo, como copiar e colar, mostrar notificações, permissões de aplicativo, compartilhamento de dados, tamanho de senha, falhas de entrada, usar impressão digital para desbloquear, reutilizar senhas e habilitar o compartilhamento de contatos de trabalho por Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f0270818a03c68afd24e32d86a9c1f847e2f2ee2
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181982"
---
# <a name="work-device-restriction-settings-in-intune"></a>Configurações de restrição de dispositivo de trabalho no Intune

Este artigo lista as configurações de restrições do dispositivo do Microsoft Intune que podem ser definidas para dispositivos de perfil do Android Enterprise.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Configurações de perfil de trabalho

### <a name="general-settings"></a>Configurações Gerais

- **Copiar e colar entre os perfis de trabalho e pessoais**: controla as ações de copiar e colar entre aplicativos pessoais e de trabalho. Escolha **Bloquear** para habilitar o bloqueio. Escolha **Não configurado** para desabilitar o bloqueio.
- **Compartilhamento de dados entre perfis de trabalho e pessoais**: controle se os aplicativos no perfil de trabalho podem ser compartilhados com aplicativos no perfil pessoal. Essa configuração controla as ações de compartilhamento em aplicativos, como a opção **Compartilhar…** no aplicativo de navegador Chrome. Essa configuração não é aplicável ao comportamento copiar/colar para a área de transferência. Ao contrário das [configurações da política de proteção do aplicativo](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), as configurações de restrição de dispositivo são gerenciadas no portal do Intune e usam a partição do perfil de trabalho Android para isolar os aplicativos gerenciados. Escolha:
  - **Restrições de compartilhamento padrão**: o comportamento de compartilhamento padrão do dispositivo, que varia dependendo da versão do Android. Por padrão, há permissão para o compartilhamento do perfil pessoal com o perfil de trabalho. Também por padrão, o compartilhamento do perfil de trabalho com o perfil pessoal é bloqueado. Essa configuração impede o compartilhamento de dados do perfil de trabalho com o perfil pessoal. Em dispositivos que executam as versões 6.0 e posteriores, o Google não bloqueia o compartilhamento do perfil pessoal par ao perfil corporativo.
  - **Os aplicativos no perfil de trabalho podem lidar com solicitações de compartilhamento do perfil pessoal**: habilita o recurso interno do Android que permite o compartilhamento do perfil pessoal para o perfil de trabalho. Quando habilitada, uma solicitação de compartilhamento de um aplicativo no perfil pessoal pode ser compartilhada com aplicativos no perfil de trabalho. Essa configuração é o comportamento padrão para dispositivos Android executando versões anteriores à 6.0.
  - **Permitir compartilhamento entre limites**: habilita o compartilhamento no limite do perfil de trabalho em ambas as orientações. Quando você seleciona essa configuração, os aplicativos no perfil de trabalho podem compartilhar dados com aplicativos sem selo no perfil pessoal. Essa configuração permite que os aplicativos gerenciados no perfil de trabalho sejam compartilhados com aplicativos no lado não gerenciado do dispositivo. Portanto, use essa configuração com cuidado.

- **Notificações de perfil de trabalho enquanto o dispositivo estiver bloqueado**: controla se os aplicativos no perfil de trabalho podem exibir dados em notificações quando o dispositivo está bloqueado.
- **Permissões de aplicativo padrão**: define a política de permissão padrão para todos os aplicativos no perfil de trabalho. A partir do Android 6, o usuário deve conceder determinadas permissões necessárias por aplicativos quando o aplicativo é iniciado. Essa configuração de política permite que você decida se os usuários deverão conceder permissões para todos os aplicativos no perfil de trabalho. Por exemplo, você atribui um aplicativo ao perfil de trabalho que exige o acesso à localização. Normalmente, esse aplicativo solicita que o usuário aprove ou negue o acesso à localização para o aplicativo. Use essa política para conceder permissões automaticamente sem um prompt, para negar automaticamente permissões sem um prompt ou permitir que o usuário final decida. Escolha:
  - **Padrão do dispositivo**
  - **Prompt**
  - **Concessão automática**
  - **Negação automática**

    Também é possível usar uma política de Configuração de Aplicativo para conceder permissões para aplicativos individuais (**Aplicativos Cliente** > **Políticas de configuração de aplicativo**).

- **Adicionar e remover contas**

   Impede que os usuários finais adicionem ou removam contas no perfil de trabalho.

   Por exemplo, ao implantar o aplicativo Gmail em um perfil de trabalho Android, é possível impedir que usuários finais adicionem ou removam contas nesse perfil de trabalho.

- **Contato com compartilhamento via Bluetooth**: permite o acesso a contatos de trabalho de outro dispositivo, como um carro, emparelhado usando Bluetooth. Por padrão, essa definição não está configurada, e os contatos do perfil de trabalho não são mostrados. Selecione **Habilitar** para permitir esse compartilhamento e mostrar contatos de perfil de trabalho. Essa configuração aplica-se a dispositivos de perfil de trabalho Android no sistema operacional Android v6.0 e mais recentes. Habilitar essa configuração pode permitir que determinados dispositivos Bluetooth armazenem em cache os contatos do trabalho após a primeira conexão. Desabilitar essa política após um emparelhamento/uma sincronização inicial pode não remover os contatos de trabalho de um dispositivo Bluetooth.

- **Captura de tela**: bloqueia a captura de tela do dispositivo no perfil de trabalho. Ela também impede que o conteúdo seja exibido em dispositivos de vídeo que não tenham uma saída de vídeo segura.

- **Exibir ID do chamador do contato de trabalho no perfil pessoal**: quando esta opção está habilitada (não configurada), os detalhes de contato comercial do chamador são exibidos no perfil pessoal. Quando bloqueado, o número de contato comercial do chamador não é exibido no perfil pessoal. Aplicável ao sistema operacional Android v6.0 e às versões mais recentes.

- **Câmera**: bloqueia a câmera do dispositivo no perfil de trabalho. A câmera no lado pessoal não é afetada pela configuração.

### <a name="work-profile-password"></a>Senha do perfil de trabalho

- **Exigir senha de perfil de trabalho**: aplica-se ao Android 7.0 e posterior com o perfil de trabalho habilitado. Defina uma política de senha que se aplica somente aos aplicativos no perfil de trabalho. Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou os usuários podem optar por combinar os PINs no mais forte entre eles.
- **Tamanho mínimo da senha**: insira o número mínimo de caracteres que a senha do usuário deve ter, de **4**-**16**.
- **Máximo de minutos de inatividade até o bloqueio do perfil de trabalho**: selecione a quantidade de tempo até o perfil de trabalho ser bloqueado. O usuário deve inserir suas credenciais para recuperar o acesso.
- **Número de falhas de entrada antes de apagar o dispositivo**: insira o número de vezes que uma senha incorreta pode ser inserida antes que o perfil de trabalho seja apagado do dispositivo.
- **Expiração da senha (dias)**: insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**).
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
- **Desbloqueio por impressão digital**: impede que usuários finais usem o scanner de impressão digital do dispositivo para desbloqueá-lo
- **Smart Lock e outros agentes de confiança**: controle o recurso Smart Lock em dispositivos compatíveis. Esse recurso do telefone, também conhecido como agente de confiança, permite desabilitar ou ignorar a senha do perfil de trabalho tela de bloqueio do dispositivo quando o dispositivo está em uma localização confiável. Por exemplo, ignore a senha do perfil de trabalho quando o dispositivo estiver conectado a um dispositivo Bluetooth específico ou quando ele estiver próximo a uma marca NFC. Use essa configuração para impedir que os usuários configurem o Smart Lock.

## <a name="device-password"></a>Senha do dispositivo

- **Tamanho mínimo da senha**: insira o número mínimo de caracteres que a senha do usuário deve ter, de **4**-**14**.
- **Máximo de minutos de inatividade até a tela ser bloqueada**: selecione o tempo decorrido até um dispositivo inativo ser bloqueado automaticamente
- **Número de falhas de entrada antes de apagar o dispositivo**: insira o número de vezes que uma senha incorreta pode ser inserida antes que todos os dados do dispositivo sejam apagados
- **Expiração da senha (dias)**: insira o número de dias até que a senha de um usuário final precise ser alterada (de **1**-**255**)
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
- **Desbloqueio por impressão digital**: impede que um usuário final use o scanner de impressão digital do dispositivo para desbloqueá-lo
- **Smart Lock e outros agentes de confiança**: controle o recurso Smart Lock em dispositivos compatíveis. Esse recurso do telefone, também conhecido como agente de confiança, permite desabilitar ou ignorar a senha da tela de bloqueio do dispositivo quando o dispositivo está em uma localização confiável. Por exemplo, ignore a senha do perfil de trabalho quando o dispositivo estiver conectado a um dispositivo Bluetooth específico ou quando ele estiver próximo a uma marca NFC. Use essa configuração para impedir que os usuários configurem o Smart Lock.

## <a name="system-security"></a>Segurança do sistema

- **Verificação de ameaças em aplicativos**: garanta que a configuração **Verificar aplicativos** esteja habilitada para perfis pessoais e de trabalho.

   > [!Note]
   > Essa configuração só funciona para dispositivos Android O e superior.

## <a name="connectivity"></a>Conectividade

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
    >  - O cliente VPN escolhido deve ser instalado no dispositivo e deve dar suporte à VPN por aplicativo em perfis de trabalho. Caso contrário, ocorrerá um erro. 
    >  - É necessário aprovar o aplicativo cliente VPN na **Google Play Store Gerenciada**, sincronizar o aplicativo com o Intune e implantá-lo no dispositivo. Após fazer isso, o aplicativo será instalado no perfil de trabalho do usuário.
    >  - Existem problemas conhecidos ao usar VPN por aplicativo com o Acesso por F5 para Android 3.0.3. Confira [Notas de versão do F5 para Acesso por F5 para Android 3.0.3](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-3.html#relnotes_known_issues_f5_access_android).

- **Modo de bloqueio**: **Habilite** para forçar todo o tráfego de rede a usar o túnel VPN. Se uma conexão com a VPN não for estabelecida, então o dispositivo não terá acesso à rede.

  Escolha **Não configurado** para permitir que o tráfego flua pelo túnel VPN ou por meio da rede móvel.

## <a name="next-step"></a>Próxima etapa

[Atribua perfis](device-profile-assign.md) a usuários e dispositivos.
