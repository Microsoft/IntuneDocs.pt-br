---
# required metadata

title: Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune
As **Políticas** do Microsoft Intune são grupos de configurações que controlam as funcionalidades nos dispositivos móveis e computadores. Políticas são criadas usando modelos que contêm configurações recomendadas ou personalizadas e depois são implantadas em grupos de dispositivos ou usuários.

## Quais tipos de política você pode usar?

As políticas do Intune encaixam-se nas categorias a seguir. A categoria usada afeta como criar e implantar a política.


- **Políticas de configuração:** são normalmente usadas para gerenciar configurações de segurança e funcionalidades em seus dispositivos. Use as informações neste tópico para saber mais sobre como criar e implantar essas políticas e para explorar as configurações disponíveis.
- **Políticas de conformidade de dispositivo: ** definem as regras e configurações às quais um dispositivo deve obedecer para ser considerado compatível pelas políticas de acesso condicional. Você também pode usar as políticas de conformidade para monitorar e corrigir a conformidade de dispositivos, independentemente do acesso condicional.
Para ver mais detalhes, consulte [Device compliance policies in Microsoft Intune (Políticas de conformidade do dispositivo no Microsoft Intune)](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Políticas de cesso condicional:** ajudam a proteger emails e outros serviços com base nas condições especificadas.
Para ver mais detalhes, consulte [Restrict access to email and O365 services with Microsoft Intune (Restringir o acesso a email e serviços do O365 com o Microsoft Intune)](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Políticas de registro de dispositivo corporativo:** para obter informações sobre as políticas de registro de dispositivo corporativo, consulte [Set up iOS and Mac management with Microsoft Intune (Configurar gerenciamento de iOS e Mac com o Microsoft Intune)](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Políticas de acesso aos recursos:** esse grupo de políticas funciona em conjunto para ajudar os usuários a obter acesso a arquivos e recursos de que precisam para realizar seu trabalho com êxito, independentemente de onde estiverem.
Para obter detalhes, consulte [Enable access to company resources with Microsoft Intune (Habilitar o acesso aos recursos da empresa com o Microsoft Intune)](enable-access-to-company-resources-with-microsoft-intune.md).


Para obter uma lista completa de políticas do Intune, consulte [Microsoft Intune policy reference (Referência de política do Microsoft Intune)](microsoft-intune-policy-reference.md).




## Criar uma política de configuração

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Política** &gt; **Políticas de Configuração** &gt; **Adicionar**.

2.  Escolha a política desejada, opte por usar as configurações recomendadas para a política (quando disponíveis, você pode alterar essas configurações posteriormente) ou crie uma política personalizada com suas próprias configurações.

    > [!TIP]
    > Para obter ajuda sobre como escolher a política certa, consulte [Microsoft Intune policy reference (Referência de política do Microsoft Intune)](microsoft-intune-policy-reference.md).

3.  Quando estiver pronto, clique em **Criar Política**.

4.  Na tela **Criar Política** , configure um nome e uma descrição opcional para a política.

5.  Defina as configurações de política necessárias e clique em **Salvar Política**.

    Se você precisar de ajuda com qualquer configuração de política, escolha o tipo de política na lista a seguir:

    - [Configurações para dispositivos iOS](ios-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Android](android-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Windows 8 e Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos do Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Configurações de dispositivos móveis Windows 10 desktop](windows-10-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos da Equipe Windows](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Configurações de atualização de edição do Windows](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Configurações para dispositivos Mac OS X](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Configurações do Exchange ActiveSync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Configurações da política de termos e condições](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Configurações de política para dispositivos móveis (herdado)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Na caixa de diálogo de confirmação, clique em **Sim** para implantar a política agora, ou em **Não** para criar a política sem implantá-la.

Você pode exibir e editar a nova política navegando nas seções de cada tipo de política no espaço de trabalho **Política** .

Ao criar uma política que usa as configurações recomendadas, o nome da nova política é uma combinação do nome do modelo, da data e da hora. Ao editar a diretiva, o nome é atualizado com a hora e a data da edição.

Agora que você criou uma política, você geralmente deseja implantá-la em um ou mais grupos de usuários ou dispositivos.

> [!TIP]
> Você não implanta todos os tipos de política. Por exemplo, a política de gerenciamento de aplicativo móvel não está implantada. Esse tipo de política está associado um aplicativo, que então você implanta.

## Implantar uma política de configuração

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política** - Selecione um ou mais grupos nos quais deseja implantar a política e clique em **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - Clique em **Cancelar**.

Quando você seleciona uma política implantada, pode exibir mais informações sobre a implantação na parte inferior da lista de políticas.

## Gerenciar políticas

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Política**, encontre e selecione a política que você deseja gerenciar.

2.  Selecione uma das seguintes ações:

- **Editar:** abre as propriedades da política selecionada para permitir que você faça alterações.
- **Excluir** - Exclui a política selecionada.<br>Ao excluir uma diretiva, ela é removida de todos os grupos nos quais foi implantada.
- **Gerenciar Implantação** - seleciona o grupo no qual deseja implantar a política e clique em **Adicionar**.

## Tarefas para políticas do Intune

### Para atualizar as políticas em um dispositivo para garantir que eles estejam atualizadas (aplica-se apenas aos computadores Windows que executam software cliente do Intune)

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Grupos**e selecione um grupo de dispositivos.

2.  Selecione os dispositivos nos quais deseja atualizar as políticas e clique em **Tarefas Remotas** &gt; **Atualizar Políticas**.

3.  Clique em **Tarefas Remotas**, no canto inferior direito da janela do console de administração do Intune para verificar o status da tarefa.

## Informações de referência para políticas do Intune

### Quanto tempo leva para dispositivos móveis obterem a política ou os aplicativos depois de terem sido implantados?
Quando uma política ou aplicativo é implantado, o Intune imediatamente começa a tentar notificar o dispositivo de que ele deve fazer o check-in com o serviço do Intune. Isso geralmente leva menos de 5 minutos.

Se um dispositivo não fizer o check-in para obter a política após a primeira notificação ser enviada, são feitas mais três tentativas.  Se o dispositivo estiver offline (por exemplo, desativado ou desconectado da rede), ele pode não receber as notificações.

Nesse caso, o dispositivo receberá a política no próximo check-in agendado com o serviço do Intune da seguinte maneira:

- iOS - A cada 6 horas
- Android - A cada 8 horas
- Windows Phone - A cada 8 horas
- Computadores Windows registrados como dispositivos - A cada 24 horas

Se o dispositivo recém tiver sido registrado, a frequência de check-in será maior da seguinte maneira:

- iOS - A cada 15 minutos por 6 horas, depois a cada 6 horas
- Android - A cada 3 minutos por 15 minutos, então a cada 15 minutos por 2 horas e então a cada 8 horas
- Windows Phone- A cada 5 minutos por 15 minutos, então a cada 15 minutos por 2 horas e então a cada 8 horas
- Computadores Windows registrados como dispositivos - A cada 3 minutos para 30 minutos e a cada 24 horas

Os usuários também podem iniciar o aplicativo de Portal da empresa e sincronizar o dispositivo para verificar imediatamente a política a qualquer momento.

### Que ações fazem o Intune imediatamente enviar notificação a um dispositivo?
Os dispositivos conferem junto ao Intune quando recebem uma notificação para fazer check-in ou durante o check-in agendado regularmente conforme mostrado nas tabelas acima.  Quando você seleciona um dispositivo ou usuário especificamente com uma ação como apagamento, bloqueio, redefinição de senha, implantação de aplicativos, implantação do perfil (WiFi, VPN, email, etc.) ou implantação de política, o Intune imediatamente começa a tentar notificar o dispositivo de que ele deve fazer check-in com o serviço Intune para receber essas atualizações.

Outras alterações, como revisar as informações de contato no portal da empresa, não causam uma notificação imediata a dispositivos.

> [!TIP]
> Quando uma política que contém configurações é implantada em um dispositivo Android, o usuário é solicitado a agir de acordo com a política. Até que os usuários executem essa ação ou o dispositivo seja reiniciado, as novas configurações de política não terão efeito.

### Se várias políticas forem implantadas para o mesmo usuário ou dispositivo, como saber quais configurações serão aplicadas?
É importante saber que, quando duas ou mais políticas são implantadas para o mesmo usuário ou dispositivo, a avaliação de qual configuração é aplicada é feita no nível da configuração individual.

-   Configurações de política de conformidade sempre têm precedência sobre configurações da política

-   A configuração de política de conformidade mais restritiva é aplicada se avaliada em relação à mesma configuração em uma política de conformidade diferente

-   A definição de política de configuração mais restritiva é aplicada se avaliada em relação à mesma definição em uma política de configuração diferente

### O que acontece quando MAM (políticas de gerenciamento de aplicativo móvel) entram em conflito entre si? Qual delas será aplicada ao aplicativo?
Os valores de conflito são as configurações mais restritivas disponíveis em uma política de gerenciamento de aplicativos móveis, exceto pelo número de entrada de campos (como tentativas de PIN antes de redefinir).  O número de campos de entrada será definido para o mesmo que os valores como se você criasse uma política MAM no console usando a opção de configurações recomendadas.

Os conflitos ocorrem quando duas configurações de política são iguais.  Por exemplo, você configurou duas políticas MAM idênticas, exceto pela configuração de copiar/colar.  Nesse cenário, a configuração de copiar/colar será definida para o valor mais restritivo, mas o restante das configurações será aplicado como configurado.

Se uma política for implantada para o aplicativo e entrar em vigor, e então uma segunda for implantada, a primeira que foi implantada terá precedência e continuará em vigor, enquanto a segunda aparecerá como estando em conflito. No entanto, se eles forem ambos aplicados ao mesmo tempo, o que significa que não há nenhuma política anterior, eles estarão em conflito e quaisquer configurações conflitantes serão definidas para os valores mais restritivos.

### O que acontece quando há conflito de políticas personalizadas de iOS?
O Intune não avalia a carga de trabalho dos arquivos de configuração Apple nem a política OMA-URI personalizada, simplesmente serve como mecanismo de entrega.

Portanto, quando você implanta uma política personalizada, garanta que as configurações definidas não entrem em conflito com as políticas de conformidade, configuração ou outras políticas personalizadas. No caso de uma política personalizada com configurações entrar em conflitos, a ordem na qual as configurações são aplicadas é aleatória.

### O que acontece quando uma política é excluída ou não é mais aplicável
Quando você exclui uma política ou remove um dispositivo de um grupo no qual uma política foi implantada, a política e as configurações são removidas do dispositivo de acordo com as tabelas a seguir:

#### Dispositivos registrados

- Perfis de email, certificado, VPN e Wi-Fi - Esses perfis são removidos de todos os dispositivos com suporte.
- Todos os outros tipos de política
    - **Dispositivos Android e Windows** - As configurações não serão removidas do dispositivo.
    - **Dispositivos Windows Phone 8.1** - As configurações a seguir foram removidas:
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
        - Permitir Conta da Microsoft
        - Permitir copiar e colar
        - Permitir compartilhamento de Internet por Wi-Fi
        - Permitir conexão automática para liberar pontos de acesso Wi-Fi
        - Permitir relatórios de pontos de acesso Wi-Fi
        - Permitir redefinição de fábrica
        - Permitir Bluetooth
        - Permitir NFC
        - Permitir Wi-Fi
    
    - **iOS** - Todas as configurações são removidas, exceto:
        - Permitir roaming de Voz
        - Permitir roaming de Dados
        - Permitir sincronização automática durante roaming

#### Computadores Windows que executam o software cliente do Intune

- **Configurações do Endpoint Protection** – As configurações são restauradas para os valores recomendados. A única exceção é a configuração **Ingressar no Microsoft Active Protection Service** , cujo valor padrão é **Não**. Para ver mais detalhes, consulte [Help secure Windows PCs with Endpoint Protection for Microsoft Intune (Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune)](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Configurações de atualizações de software** – As configurações são redefinidas para o estado padrão do sistema operacional. Para ver mais detalhes, consulte [Keep Windows PCs up to date with software updates in Microsoft Intune (Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune)](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Configurações do Microsoft Intune Center** - Qualquer informação de contato para suporte configurada pela política será excluída dos computadores.
- **Configurações do Firewall do Windows** – As configurações são redefinidas para o padrão do sistema operacional do computador. Para ver mais detalhes, consulte [Help secure Windows PCs with Endpoint Protection for Microsoft Intune (Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune)](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).





<!--HONumber=May16_HO1-->


