---
title: Solucionar problemas de perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Problemas comuns com perfis de dispositivo, incluindo alterações de perfil não aplicadas a alguns usuários ou dispositivos, o tempo que leva para que uma nova política seja enviada por push para dispositivos, quais configurações são aplicadas quando há várias políticas, o que acontece quando um perfil é excluído ou removido e muito mais, com o Microsoft Intune no Portal do Azure
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 1/10/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 528e26ddca1b3327fb0afa2f5cff6f2dbdca1660
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846478"
---
# <a name="common-issues-and-resolutions-with-device-profiles-in-microsoft-intune"></a>Problemas comuns e resoluções com perfis de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Solucionar problemas comuns usando perfis de dispositivo do Intune.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Por que um usuário não obtém um novo perfil ao alterar uma senha ou frase secreta em um perfil de Wi-Fi existente? 
Você cria um perfil de Wi-Fi corporativo, implanta o perfil em um grupo, altera a senha e salva o perfil. Quando o perfil é alterado, alguns usuários podem não receber o novo perfil.

Para atenuar esse problema, configure um Wi-Fi de convidado. Se o Wi-Fi corporativo falhar, os usuários poderão se conectar no Wi-Fi de convidado. Habilite todas as configurações de conexão automática. Implante o perfil de Wi-Fi de convidado para todos os usuários.

Algumas recomendações adicionais:  

- Como a rede Wi-Fi à qual você está se conectando usa uma senha ou frase secreta, certifique-se de poder se conectar ao roteador Wi-Fi diretamente. É possível testar com um dispositivo iOS.
- Depois de se conectar com êxito ao ponto de extremidade Wi-Fi (roteador Wi-Fi), observe o SSID e a credencial usada (esse valor é a senha ou a frase secreta).
- Insira o SSID e a credencial (senha ou frase secreta) no campo Chave pré-compartilhada. 
- Implante em um grupo de teste que tenha um número de usuários limitado, preferencialmente apenas a equipe de TI. 
- Sincronize seu dispositivo iOS com o Intune. Registre-se caso você ainda não tenha se registrado. 
- Teste a conexão com o mesmo ponto de extremidade Wi-Fi (conforme mencionado na primeira etapa) novamente.
- Expanda para grupos maiores e, eventualmente, para todos os usuários esperados em sua organização. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Quanto tempo leva para dispositivos móveis obterem uma política ou os aplicativos depois de terem sido atribuídos?
Quando uma política ou um aplicativo é atribuído, o Intune imediatamente começa a notificar o dispositivo para fazer o check-in com o serviço do Intune. Em geral, essa notificação leva menos de cinco minutos.

Se um dispositivo não fizer o check-in para obter a política após a primeira notificação ser enviada, o Intune fará mais três tentativas. Se o dispositivo estiver offline (por exemplo, desligado ou não conectado a uma rede), ele poderá não receber as notificações. Nesse caso, o dispositivo obterá a política em seu próximo check-in agendado com o serviço do Intune da seguinte maneira:

- iOS e macOS: A cada seis horas
- Android: A cada oito horas
- Windows Phone: A cada oito horas
- Computadores Windows 8.1 e Windows 10 registrados como dispositivos: A cada oito horas

Se o dispositivo for recém-registrado, a frequência do check-in será maior, desta forma:

- iOS e macOS: A cada 15 minutos, durante seis horas e, posteriormente, a cada seis horas
- Android: A cada três minutos, durante 15 minutos; a cada 15 minutos, durante duas horas e, posteriormente, a cada oito horas
- Windows Phone: A cada cinco minutos, durante 15 minutos; a cada 15 minutos, durante duas horas e, posteriormente, a cada oito horas
- Computadores Windows registrados como dispositivos: A cada três minutos, durante 30 minutos e, posteriormente, a cada oito horas

Se quiserem verificar imediatamente a política a qualquer momento, os usuários também poderão abrir o aplicativo Portal da Empresa e sincronizar o dispositivo.

Para dispositivos sem afinidade de usuário, a frequência de sincronização imediatamente após o registro pode variar de horas a um dia ou mais. O Intune envia solicitações em vários intervalos para que um dispositivo faça check-in no serviço. No entanto, fazer check-in ainda depende do dispositivo. Após o registro inicial, dependendo do tipo de registro do dispositivo e das políticas e dos perfis atribuídos ao dispositivo, o tempo que um dispositivo levará para concluir o check-in será imprevisível. No entanto, uma vez registrado e após todas as políticas iniciais serem aplicadas, o dispositivo geralmente verificará se há novas políticas a cada seis horas, aproximadamente.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Que ações fazem com que o Intune envie imediatamente uma notificação para um dispositivo?
Os dispositivos fazem o check-in no Intune quando recebem uma notificação para fazer check-in ou durante o check-in agendado regularmente. Quando você direciona uma ação a um dispositivo ou usuário, como apagamento, bloqueio, redefinição de senha, atribuição de aplicativo, atribuição de perfil ou atribuição de política, o Intune notifica imediatamente o dispositivo para fazer check-in no serviço do Intune a fim de receber essas atualizações.

Outras alterações, como revisar as informações de contato no portal da empresa, não causam uma notificação imediata para os dispositivos.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Se várias políticas forem atribuídas ao mesmo usuário ou dispositivo, como saber quais configurações serão aplicadas?
Se duas ou mais políticas forem atribuídas ao mesmo usuário ou dispositivo, a decisão de qual configuração aplicar ocorrerá no nível da configuração individual:

- Configurações de política de conformidade sempre têm precedência sobre configurações da política

- Se uma política de conformidade for avaliada em relação à mesma configuração em uma política de conformidade diferente, a configuração de política de conformidade mais restritiva será aplicada.

- Se uma definição de uma política de configuração estiver em conflito com uma configuração em uma política de configuração diferente, esse conflito será exibido no Portal do Azure. Nessa situação, resolva os conflitos manualmente.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>O que acontece quando as políticas de proteção de aplicativo entram em conflito umas com as outras? Qual delas será aplicada ao aplicativo?
Os valores de conflito são as configurações mais restritivas disponíveis em uma política de proteção de aplicativo, exceto pelos campos de entrada de número (como as tentativas de PIN antes de redefinir). Os campos de entrada de número serão definidos com valores iguais aos de uma política de MAM criada no console usando a opção de configurações recomendadas.

Os conflitos ocorrem quando duas configurações de perfil são iguais. Por exemplo, você configurou duas políticas MAM idênticas, exceto pela configuração de copiar/colar. Nesse cenário, a configuração de copiar/colar será definida para o valor mais restritivo, mas o restante das configurações será aplicado como configurado.

Se um perfil for atribuído ao aplicativo e entrar em vigor e, em seguida, um segundo perfil for atribuído, o primeiro terá precedência e continuará aplicado, enquanto que o segundo aparecerá como em conflito. Se as duas forem aplicadas ao mesmo tempo, ou seja, sem que haja um perfil anterior, as duas estarão em conflito. As configurações conflitantes são definidas para os valores mais restritivos.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>O que acontece quando há conflito de políticas personalizadas de iOS?
O Intune não avalia o conteúdo dos arquivos de Configuração da Apple ou um perfil personalizado de URI-OMA (Open Mobile Alliance Uniform Resource Identifier). Ele simplesmente serve como o mecanismo de entrega.

Quando você atribui um perfil personalizado, garanta que as configurações definidas não entrem em conflito com as políticas de conformidade, configuração ou outras políticas personalizadas. Se um perfil personalizado e suas configurações entrarem em conflito, as configurações serão aplicadas aleatoriamente.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>O que acontece quando um perfil é excluído ou não é mais aplicável?
Quando você exclui um perfil ou remove um dispositivo de um grupo que tenha o perfil, o perfil e as configurações são removidos do dispositivo de acordo com as listas a seguir:

- Perfis de Wi-Fi, VPN, certificado e email: Esses perfis são removidos de todos os dispositivos registrados compatíveis.
- Todos os outros tipos de perfil:  

  - **Dispositivos Windows e Android**: As configurações não são removidas do dispositivo
  - **Dispositivos Windows Phone 8.1**: As seguintes configurações são removidas:  
  
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
    - Permitir apagamento
    - Permitir Bluetooth
    - Permitir NFC
    - Permitir Wi-Fi

  - **iOS**: Todas as configurações são removidas, exceto:
  
    - Permitir roaming de Voz
    - Permitir roaming de Dados
    - Permitir sincronização automática durante roaming

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Alterei um perfil de restrição de dispositivo, mas as alterações não entraram em vigor
Os dispositivos Windows Phone não permitem que as políticas de segurança definidas com uso de MDM ou EAS sejam reduzidas em termos de segurança após terem sido configuradas. Por exemplo, você define uma **Senha com um número mínimo de caracteres** igual a 8 e tenta reduzi-la a 4. O perfil mais restritivo já foi aplicado ao dispositivo.

Se você quiser alterar o perfil para um valor menos seguro, redefina as políticas de segurança. Por exemplo, no Windows 8.1, na área de trabalho, passe o dedo da direita para a esquerda e selecione **Configurações** > **Painel de Controle**. Selecione o miniaplicativo **Contas de Usuário**. No menu de navegação à esquerda, há um link **Redefinir Políticas de Segurança** (em direção à parte inferior). Selecione-o e, em seguida, escolha **Redefinir Políticas**.

Outros dispositivos MDM, como Android, Windows Phone 8.1 e posteriores, iOS e Windows 10, precisarão ser desativados e registrados novamente no serviço para aplicar um perfil menos restritivo.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Algumas configurações em um perfil do Windows 10 retornam "Não Aplicável"
Algumas configurações em dispositivos Windows 10 pode ser exibidas como "Não Aplicável". Quando isso acontecer, essa configuração específica não será compatível com a versão ou a edição do Windows em execução no dispositivo. Essa mensagem pode ocorrer pelos seguintes motivos:

- A configuração só está disponível para versões mais recentes do Windows, não para a versão atual de sistema operacional do dispositivo.
- A configuração só está disponível para edições ou SKUs específicos do Windows, como Home, Professional, Enterprise e Education.

Para saber mais sobre os requisitos de versão e SKU para as diferentes configurações, confira a [Referência do CSP (Provedor de Serviços de Configuração)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="next-steps"></a>Próximas etapas
Precisa de mais ajuda? Veja [Como obter suporte para o Microsoft Intune](get-support.md).
