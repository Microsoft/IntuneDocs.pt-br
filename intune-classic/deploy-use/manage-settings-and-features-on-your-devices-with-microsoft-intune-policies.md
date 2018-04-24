---
title: Gerenciar as configurações do dispositivo com políticas
description: Use o Intune para criar e implantar políticas que controlam configurações e recursos nos dispositivos gerenciados que você gerencia.
keywords: ''
author: dougeby
ms.author: angrobe
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6e639dda2509ab51bfcf6d0976be517e220800e9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="manage-settings-and-features-on-your-devices-with-microsoft-intune-policies"></a>Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

As *políticas* do Microsoft Intune são grupos de configurações que controlam os recursos nos dispositivos móveis e computadores. Políticas são criadas usando modelos que contêm configurações recomendadas ou personalizadas e depois são implantadas em grupos de dispositivos ou de usuários.

## <a name="types-of-policies"></a>Tipos de políticas

As políticas do Intune encaixam-se nas categorias a seguir. A categoria usada afeta como criar e implantar a política.


- **Políticas de configuração:** são normalmente usadas para gerenciar configurações de segurança e recursos em seus dispositivos. Use as informações neste tópico para saber mais sobre como criar e implantar essas políticas e para explorar as configurações disponíveis.
- **Políticas de conformidade de dispositivo**: definem as regras e configurações às quais um dispositivo deve obedecer para ser considerado compatível pelas políticas de acesso condicional. Você também pode usar as políticas de conformidade para monitorar e corrigir a conformidade de dispositivos, independentemente do acesso condicional.
Para obter detalhes, consulte [Políticas de conformidade do dispositivo no Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Políticas de acesso condicional:** ajudam a proteger emails e outros serviços dependendo das condições especificadas.
Para obter detalhes, consulte [Restringir o acesso ao email e aos serviços O365 com o Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Políticas de registro de dispositivo corporativo:** para obter informações sobre as políticas de registro de dispositivo corporativo, consulte [Configurar gerenciamento de iOS e Mac com o Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Políticas de acesso aos recursos:** essas políticas funcionam em conjunto para ajudar os usuários a obter acesso a arquivos e recursos de que precisam para realizar seu trabalho com êxito, independentemente de onde estiverem.
Para obter detalhes, consulte [Enable access to company resources with Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md) (Habilitar o acesso aos recursos da empresa com o Microsoft Intune).


Para obter uma lista completa de políticas do Intune, consulte a [referência de política do Microsoft Intune](microsoft-intune-policy-reference.md).

## <a name="create-a-configuration-policy"></a>Criar uma política de configuração

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Política** &gt; **Políticas de Configuração** &gt; **Adicionar**.

2.  Escolha a política desejada, opte por usar as configurações recomendadas para a política (se disponíveis, você poderá alterar essas configurações posteriormente) ou opte por criar uma política personalizada com suas próprias configurações.

    > [!TIP]
    > Para obter ajuda sobre como escolher a política certa, consulte a [Referência da política do Microsoft Intune](microsoft-intune-policy-reference.md).

3.  Quando estiver pronto, clique em **Criar Política**.

4.  Na página **Criar Política**, configure um nome e uma descrição opcional para a política.

5.  Defina as configurações de política necessárias e selecione **Salvar Política**.

    Se você precisar de ajuda com qualquer configuração de política, escolha o tipo de política na lista a seguir:

    - [Configurações para dispositivos iOS](ios-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Android](android-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Android para Trabalho](android-for-work-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Windows 8 e Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Windows 10 móveis e desktop](windows-10-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Windows Team](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Configurações para atualização de edição do Windows](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Mac OS X](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Configurações para Exchange ActiveSync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Configurações para política de termos e condições](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Configurações gerais para dispositivos móveis (herdados)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Na caixa de diálogo de confirmação, escolha **Sim** para implantar a política agora ou **Não** para criar a política sem implantá-la.

Você pode exibir e editar a nova política navegando pelas seções de cada tipo de política no espaço de trabalho **Política**.

Ao criar uma política que usa as configurações recomendadas, o nome da nova política é uma combinação do nome do modelo, da data e da hora. Ao editar a política, o nome é atualizado com a hora e a data da edição.

Após criar uma política, geralmente você desejará implantá-la em um ou mais grupos de usuários ou dispositivos.

> [!TIP]
> Você não implanta todos os tipos de política. Por exemplo, a política de MAM (gerenciamento de aplicativo móvel) não é implantada. Esse tipo de política está associado um aplicativo, que então você implanta.

## <a name="deploy-a-configuration-policy"></a>Implantar uma política de configuração

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação**:

    -   Para implantar a política, selecione um ou mais grupos aos quais você deseja implantar a política e selecione **Adicionar** &gt; **OK**.

    -   Para fechar a caixa de diálogo sem implantar a política, selecione **Cancelar**.

Quando você seleciona uma política implantada, pode exibir mais informações sobre a implantação na parte inferior da lista de políticas.

## <a name="manage-policies"></a>Gerenciar políticas

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Política**, navegue até e selecione a política que você deseja gerenciar.

2.  Selecione uma das seguintes ações:

- **Editar:** abra as propriedades da política selecionada para que você possa fazer alterações.
- **Excluir**: exclui a política selecionada.<br>Ao excluir uma diretiva, ela é removida de todos os grupos nos quais foi implantada.
- **Gerenciar a Implantação**: selecione o grupo no qual você deseja implantar a política e clique em **Adicionar**.


## <a name="frequently-asked-questions-about-intune-policies"></a>Perguntas frequentes sobre as políticas do Intune

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-deployed"></a>Quanto tempo leva para dispositivos móveis obterem uma política ou os aplicativos depois de terem sido implantados?
Quando uma política ou um aplicativo é implantado, o Intune imediatamente começa a tentar notificar o dispositivo de que ele deve fazer o check-in com o serviço do Intune. Em geral, isso leva menos de cinco minutos.

Se um dispositivo não fizer o check-in para obter a política após a primeira notificação ser enviada, o Intune fará mais três tentativas.  Se o dispositivo estiver offline (por exemplo, desativado ou desconectado da rede), ele poderá não receber as notificações. Nesse caso, o dispositivo receberá a política no próximo check-in agendado com o serviço do Intune da seguinte maneira:

- iOS e Mac OS X: a cada 6 horas.
- Android: a cada 8 horas.
- Windows Phone: a cada 8 horas.
- Computadores Windows 8.1 e Windows 10 registrados como dispositivos: a cada 8 horas.

Se o dispositivo tiver sido registrado recentemente, a frequência de check-in será maior, da seguinte maneira:

- iOS e Mac OS X: a cada 15 minutos por 6 horas, depois a cada 6 horas.
- Android: a cada 3 minutos por 15 minutos, então a cada 15 minutos por 2 horas e então a cada 8 horas.
- Windows Phone: a cada 5 minutos por 15 minutos, então a cada 15 minutos por 2 horas e então a cada 8 horas.
- Computadores Windows registrados como dispositivos: a cada 3 minutos por 30 minutos e a cada 8 horas.

Os usuários também podem iniciar o aplicativo Portal da Empresa e sincronizar o dispositivo para verificar imediatamente a política a qualquer momento.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Que ações fazem com que o Intune envie imediatamente uma notificação para um dispositivo?
Os dispositivos fazem o check-in no Intune quando recebem uma notificação que os informa para fazer check-in ou durante o check-in agendado regularmente.  Quando você seleciona um dispositivo ou usuário especificamente com uma ação como apagamento, bloqueio, redefinição de senha, implantação de aplicativo, implantação do perfil (Wi-Fi, VPN, email, etc.) ou implantação de política, o Intune começa imediatamente a tentar notificar o dispositivo de que ele deve fazer check-in no serviço Intune para receber essas atualizações.

Outras alterações, como revisar as informações de contato no portal da empresa, não causam uma notificação imediata para os dispositivos.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Se várias políticas forem implantadas para o mesmo usuário ou dispositivo, como saber quais configurações serão aplicadas?
Quando duas ou mais políticas são implantadas para o mesmo usuário ou dispositivo, a avaliação de qual configuração é aplicada ocorre no nível da configuração individual:

-   Configurações de política de conformidade sempre têm precedência sobre configurações da política.

-   A configuração de política de conformidade mais restritiva é aplicada se avaliada em relação à mesma configuração em uma política de conformidade diferente.

-   Se a definição de uma política de configuração estiver em conflito com uma configuração em uma política de configuração diferente, esse conflito será exibido no console do Intune. Você deve resolver esses conflitos manualmente.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>O que acontece quando as políticas de gerenciamento de aplicativo móvel entram em conflito entre si? Qual delas será aplicada ao aplicativo?
Os valores de conflito são as configurações mais restritivas disponíveis em uma política de MAM, exceto pelos campos de entrada de número (como as tentativas de PIN antes de redefinir).  Os campos de entrada de número serão definidos com os mesmos valores, como se você criasse uma política de MAM no console usando a opção de configurações recomendadas.

Os conflitos ocorrem quando duas configurações de política são iguais.  Por exemplo, você configurou duas políticas MAM idênticas, exceto pela configuração de copiar/colar.  Nesse cenário, a configuração de copiar/colar será definida para o valor mais restritivo, mas o restante das configurações será aplicado como configurado.

Se uma política for implantada para o aplicativo e entrar em vigor e então uma segunda for implantada, a primeira terá precedência e continuará em vigor, enquanto a segunda aparecerá como estando em conflito. Se as duas forem aplicadas ao mesmo tempo, o que significa que não há política anterior, as duas estarão em conflito. Quaisquer configurações conflitantes serão definidas com os valores mais restritivos.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>O que acontece quando há conflito de políticas personalizadas de iOS?
O Intune não avalia o conteúdo dos arquivos de Configuração da Apple ou uma política personalizada de URI-OMA (Open Mobile Alliance Uniform Resource Identifier). Ele simplesmente serve como o mecanismo de entrega.

Quando você implantar uma política personalizada, garanta que as configurações definidas não entrem em conflito com as políticas de conformidade, configuração ou outras políticas personalizadas. No caso de uma política personalizada com configurações entrar em conflitos, a ordem na qual as configurações são aplicadas é aleatória.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>O que acontece quando uma política é excluída ou não é mais aplicável?
Quando você exclui uma política ou remove um dispositivo de um grupo no qual uma política foi implantada, a política e as configurações são removidas do dispositivo de acordo com as listas a seguir.

#### <a name="enrolled-devices"></a>Dispositivos registrados

- Perfis de email, certificado, VPN e Wi-Fi: esses perfis são removidos de todos os dispositivos registrados com suporte.
- Todos os outros tipos de política:
    - **Dispositivos Android e Windows**: as configurações não são removidas do dispositivo.
    - **Dispositivos Windows Phone 8.1**: as configurações a seguir são removidas:
        - Exigir uma senha para desbloquear os dispositivos móveis
        - Permitir senha simples
        - Comprimento mínimo da senha
        - Tipo de senha necessária
        - Expiração da senha (dias)
        - Lembrar de histórico de senha
        - Número de falhas de logon repetidas permitido antes do dispositivo ser apagado
        - Minutos de inatividade antes de a senha ser necessária
        - Tipo de senha necessária – o número mínimo de conjuntos de caracteres
        - Permitir câmera
        - Exigir criptografia no dispositivo móvel
        - Permitir armazenamento removível
        - Permitir navegador da web
        - Permitir loja de aplicativo
        - Permitir captura de tela
        - Permitir localização geográfica
        - Permitir conta da Microsoft
        - Permitir copiar e colar
        - Permitir compartilhamento de Internet por Wi-Fi
        - Permitir conexão automática para liberar pontos de acesso Wi-Fi
        - Permitir relatórios de pontos de acesso Wi-Fi
        - Permitir redefinição de fábrica
        - Permitir Bluetooth
        - Permitir NFC
        - Permitir Wi-Fi

    - **iOS**: todas as configurações são removidas, exceto:
        - Permitir roaming de Voz
        - Permitir roaming de Dados
        - Permitir sincronização automática durante roaming

#### <a name="windows-pcs-running-the-intune-client-software"></a>Computadores Windows que executam o software cliente do Intune

- **Configurações do Endpoint Protection**: as configurações são restauradas para os valores recomendados. A única exceção é a configuração **Ingressar no Microsoft Active Protection Service**, cujo valor padrão é **Não**. Para obter detalhes, consulte [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) (Ajude a proteger computadores Windows com o Endpoint Protection para Microsoft Intune).
- **Configurações de atualizações de software**: as configurações são redefinidas para o estado padrão do sistema operacional. Para obter detalhes, consulte [Manter os computadores Windows atualizados com as atualizações de software no Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Configurações do Microsoft Intune Center**: qualquer informação de contato para suporte configurada pela política é excluída dos computadores.
- **Configurações do Firewall do Windows**: as configurações são redefinidas para o padrão do sistema operacional do computador. Para obter detalhes, consulte [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) (Ajude a proteger computadores Windows com o Endpoint Protection para Microsoft Intune).


### <a name="how-can-i-refresh-the-policies-on-a-device-to-ensure-that-they-are-current-applies-to-windows-pcs-running-the-intune-client-software-only"></a>Como posso atualizar as políticas em um dispositivo para garantir que elas estejam atualizadas (aplica-se apenas aos computadores Windows que executam software cliente do Intune)?

1.  Em qualquer grupo de dispositivos selecione os dispositivos nos quais deseja atualizar as políticas e, em seguida, clique em **Tarefas Remotas** &gt; **Atualizar Políticas**.
2.  Selecione **Tarefas Remotas**, no canto inferior direito da janela do console de administração do Intune para verificar o status da tarefa.

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Onde posso encontrar ajuda para solucionar problemas de políticas?

Consulte [Troubleshoot policies in Microsoft Intune](/intune-classic/troubleshoot/troubleshoot-policies-in-microsoft-intune) (Políticas de solução de problemas no Microsoft Intune).
