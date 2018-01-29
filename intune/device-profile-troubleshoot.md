---
title: "Solução de problemas de perfis de dispositivo no Microsoft Intune"
titlesuffix: Azure portal
description: "Se estiver tendo dificuldades, use este tópico para ajudar a solucionar problemas com perfis de dispositivo do Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 1/17/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0bc5ad6e0467fe8a8c98c1ad2d71b967c18b8233
ms.sourcegitcommit: 967a7c23b863123398c40b812e2eb02c921a0afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2018
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a>Solução de problemas de perfis de dispositivo no Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As informações neste tópico podem ser usadas para ajudar a solucionar problemas comuns relacionados a perfis de dispositivo do Intune.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Por que um usuário não obtém um novo perfil ao alterar uma senha ou frase secreta em um perfil de Wi-Fi existente? 
Quando você cria um perfil de Wi-Fi corporativo, implanta-o em um grupo, altera a senha e salva o perfil, talvez você espere que o usuário obtenha o novo perfil. Contudo, o usuário pode não obter o novo perfil. 

Para atenuar esse problema, certifique-se de ter um Wi-Fi convidado configurado de forma que o usuário converterá o Wi-Fi convidado se o Wi-Fi corporativo falhar. A configuração de conexão automática precisa ser habilitada. Este perfil de Wi-Fi convidado precisa ser implantado em todos os usuários.

Há algumas outras práticas recomendadas que você pode seguir:
- Como a rede Wi-Fi à qual você está se conectando usa uma senha ou frase secreta, certifique-se de poder se conectar ao roteador Wi-Fi diretamente. É possível testar com um dispositivo iOS.
- Depois de se conectar com êxito ao ponto de extremidade Wi-Fi (roteador Wi-Fi), observe o SSID e a credencial usada (esta é a senha ou a frase secreta).
- Insira o SSID e a credencial (senha ou frase secreta) no campo Chave pré-compartilhada. 
- Implante em um grupo de teste que tenha um número de usuários limitado, preferencialmente apenas a equipe de TI. 
- Sincronize seu dispositivo iOS com o Intune. Registre-se caso você ainda não tenha se registrado. 
- Teste a conexão com o mesmo ponto de extremidade Wi-Fi (conforme mencionado na primeira etapa) novamente.
- Expanda para grupos maiores e, eventualmente, para todos os usuários esperados em sua organização. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Quanto tempo leva para dispositivos móveis obterem uma política ou os aplicativos depois de terem sido atribuídos?
Quando uma política ou um aplicativo é atribuído, o Intune imediatamente começa a tentar notificar o dispositivo de que ele deve fazer o check-in com o serviço do Intune. Em geral, isso leva menos de cinco minutos.

Se um dispositivo não fizer o check-in para obter a política após a primeira notificação ser enviada, o Intune fará mais três tentativas. Se o dispositivo estiver offline (por exemplo, desativado ou desconectado da rede), ele poderá não receber as notificações. Nesse caso, o dispositivo obterá a política em seu próximo check-in agendado com o serviço do Intune da seguinte maneira:

- iOS e macOS: a cada seis horas.
- Android: a cada oito horas.
- Windows Phone: a cada oito horas.
- Computadores Windows 8.1 e Windows 10 registrados como dispositivos: a cada oito horas.

Se o dispositivo tiver sido recém-registrado, a frequência do check-in será maior, desta forma:

- iOS e macOS: a cada 15 minutos por seis horas e, então, a cada seis horas.
- Android: a cada três minutos por 15 minutos, então, a cada 15 minutos por duas horas e, então, a cada oito horas.
- Windows Phone: a cada cinco minutos por 15 minutos, então, a cada 15 minutos por duas horas e, então, a cada oito horas.
- Computadores Windows registrados como dispositivos: a cada três minutos por 30 minutos e, então, a cada 8 horas.

Os usuários também podem iniciar o aplicativo Portal da Empresa e sincronizar o dispositivo para verificar imediatamente a política a qualquer momento.

Para dispositivos sem afinidade de usuário, a frequência de sincronização imediatamente após o registro pode variar de horas a um dia ou mais. O Intune envia solicitações em vários intervalos para que um dispositivo faça check-in no serviço. No entanto, essa ação ainda depende do dispositivo. Após o registro inicial, dependendo do tipo de registro do dispositivo e das políticas e dos perfis atribuídos ao dispositivo, não será possível prever o tempo que o dispositivo levará para concluir esse check-in. No entanto, quando o dispositivo for registrado e todas as políticas iniciais forem aplicadas, o dispositivo deverá verificar se há novas políticas a cada seis horas aproximadamente.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Que ações fazem com que o Intune envie imediatamente uma notificação para um dispositivo?
Os dispositivos fazem o check-in no Intune quando recebem uma notificação que os informa para fazer check-in ou durante o check-in agendado regularmente. Quando você direciona uma ação especificamente a um dispositivo ou usuário, como apagamento, bloqueio, redefinição de senha, atribuição de aplicativo, atribuição de perfil (Wi-Fi, VPN, email etc.) ou atribuição de política, o Intune começa imediatamente a tentar notificar o dispositivo de que ele deve fazer check-in no serviço do Intune para receber essas atualizações.

Outras alterações, como revisar as informações de contato no portal da empresa, não causam uma notificação imediata para os dispositivos.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Se várias políticas forem atribuídas ao mesmo usuário ou dispositivo, como saber quais configurações serão aplicadas?
Quando duas ou mais políticas são atribuídas ao mesmo usuário ou dispositivo, a avaliação de qual configuração é aplicada ocorre no nível da configuração individual:

-   Configurações de política de conformidade sempre têm precedência sobre configurações da política.

-   A configuração de política de conformidade mais restritiva é aplicada se avaliada em relação à mesma configuração em uma política de conformidade diferente.

-   Se a definição de uma política de configuração estiver em conflito com uma configuração em uma política de configuração diferente, esse conflito será exibido no Portal do Azure. Você deve resolver esses conflitos manualmente.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>O que acontece quando as políticas de proteção de aplicativo entram em conflito umas com as outras? Qual delas será aplicada ao aplicativo?
Os valores de conflito são as configurações mais restritivas disponíveis em uma política de proteção de aplicativo, exceto pelos campos de entrada de número (como as tentativas de PIN antes de redefinir). Os campos de entrada de número serão definidos com valores iguais aos de uma política de MAM criada no console usando a opção de configurações recomendadas.

Os conflitos ocorrem quando duas configurações de perfil são iguais. Por exemplo, você configurou duas políticas MAM idênticas, exceto pela configuração de copiar/colar. Nesse cenário, a configuração de copiar/colar será definida para o valor mais restritivo, mas o restante das configurações será aplicado como configurado.

Se um perfil for atribuído ao aplicativo e entrar em vigor e, em seguida, um segundo for atribuído, o primeiro terá precedência e continuará em vigor, enquanto o segundo aparecerá como em conflito. Se as duas forem aplicadas ao mesmo tempo, ou seja, sem que haja um perfil anterior, as duas estarão em conflito. As configurações conflitantes são definidas para os valores mais restritivos.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>O que acontece quando há conflito de políticas personalizadas de iOS?
O Intune não avalia o conteúdo dos arquivos de Configuração da Apple ou um perfil personalizado de URI-OMA (Open Mobile Alliance Uniform Resource Identifier). Ele simplesmente serve como o mecanismo de entrega.

Quando você atribui um perfil personalizado, garanta que as configurações definidas não entrem em conflito com as políticas de conformidade, configuração ou outras políticas personalizadas. No caso de um perfil personalizado com configurações entrar em conflitos, a ordem na qual as configurações são aplicadas é aleatória.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>O que acontece quando um perfil é excluído ou não é mais aplicável?
Quando você exclui um perfil ou remove um dispositivo de um grupo ao qual um perfil foi atribuído, o perfil e as configurações são removidos do dispositivo de acordo com as listas a seguir.

### <a name="enrolled-devices"></a>Dispositivos registrados

- Perfis de email, certificado, VPN e Wi-Fi: esses perfis são removidos de todos os dispositivos registrados com suporte.
- Todos os outros tipos de perfil:
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

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Alterei um perfil de restrição de dispositivo, mas as alterações não entraram em vigor
Dispositivos Windows Phone não permitem que políticas de segurança definidas por meio do MDM ou EAS sejam reduzidas em termos de segurança após terem sido configuradas. Por exemplo, você define um **Número mínimo de caracteres de senha** para 8 e tenta reduzi-lo a 4. O perfil mais restritivo já foi aplicado ao dispositivo.

Dependendo da plataforma do dispositivo, se você quiser alterar o perfil para um valor menos seguro, pode ser necessário redefinir as políticas de segurança.
Por exemplo, no Windows, na área de trabalho, passe o dedo da direita para a esquerda para abrir a barra **Botões** e escolha **Configurações** &gt; **Painel de Controle**. Selecione o miniaplicativo **Contas de Usuário**.
No menu de navegação à esquerda, há um link **Redefinir Políticas de Segurança** na parte inferior. Escolha-o e clique no botão **Redefinir Políticas**.
Outros dispositivos MDM, como Android, Windows Phone 8.1 e posterior e iOS, precisarão ser desativados e registrados novamente no serviço para que você possa aplicar um perfil menos restritivo.


### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](get-support.md) (Como obter suporte para o Microsoft Intune).