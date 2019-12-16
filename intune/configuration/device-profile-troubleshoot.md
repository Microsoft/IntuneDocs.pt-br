---
title: Solucionar problemas de perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Perguntas e respostas comuns para políticas e perfis de dispositivos, incluindo alterações de perfil não aplicadas a usuários ou dispositivos, quanto tempo leva para que novas políticas sejam enviadas por push a dispositivos, quais configurações são aplicadas quando há várias políticas, o que acontece quando um perfil é excluído ou removido e muito mais com o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/04/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d445b86359b2c5cde7b56a52a0cc6ee72a34c0ea
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74832609"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Perguntas, problemas e soluções comuns para perfis e políticas de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Obtenha respostas para perguntas comuns ao trabalhar com perfis e políticas de dispositivos no Intune. Este artigo também lista os intervalos de tempo de check-in, fornece mais detalhes sobre conflitos e muito mais.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Por que um usuário não obtém um novo perfil ao alterar uma senha ou frase secreta em um perfil de Wi-Fi existente?

Você cria um perfil de Wi-Fi corporativo, implanta o perfil em um grupo, altera a senha e salva o perfil. Quando o perfil é alterado, alguns usuários podem não receber o novo perfil.

Para atenuar esse problema, configure um Wi-Fi de convidado. Se o Wi-Fi corporativo falhar, os usuários poderão se conectar no Wi-Fi de convidado. Habilite todas as configurações de conexão automática. Implante o perfil de Wi-Fi de convidado para todos os usuários.

Algumas recomendações adicionais:  

- Se a rede Wi-Fi à qual você está se conectando usa uma senha ou frase secreta, certifique-se de poder se conectar ao roteador Wi-Fi diretamente. É possível testar com um dispositivo iOS.
- Depois de se conectar com êxito ao ponto de extremidade Wi-Fi (roteador Wi-Fi), observe o SSID e a credencial usada (esse valor é a senha ou a frase secreta).
- Insira o SSID e a credencial (senha ou frase secreta) no campo Chave pré-compartilhada. 
- Implante em um grupo de teste que tenha um número de usuários limitado, preferencialmente apenas a equipe de TI. 
- Sincronize seu dispositivo iOS com o Intune. Registre-se caso você ainda não tenha se registrado. 
- Teste a conexão com o mesmo ponto de extremidade Wi-Fi (conforme mencionado na primeira etapa) novamente.
- Expanda para grupos maiores e, eventualmente, para todos os usuários esperados em sua organização. 

## <a name="how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned"></a>Quanto tempo demora até os dispositivos obterem uma política, perfil ou aplicativo após a atribuição?

O Intune notifica o dispositivo para fazer check-in no serviço do Intune. Os tempos de notificação variam, podendo ser imediatos ou até algumas horas. Esses tempos de notificação também variam de acordo com as plataformas.

Se um dispositivo não fizer o check-in para obter a política ou o perfil após a primeira notificação, o Intune fará mais três tentativas. Um dispositivo offline, como quando está desligado ou não conectado a uma rede, pode não receber as notificações. Nesse caso, o dispositivo obtém a política ou o perfil no próximo check-in agendado no serviço do Intune. O mesmo se aplica às verificações de não conformidade, incluindo dispositivos que passam de um estado em conformidade para um estado de não conformidade.

Frequências **estimadas**:

| Plataforma | Ciclo de atualização|
| --- | --- |
| iOS | Aproximadamente a cada oito horas |
| macOS | Aproximadamente a cada oito horas |
| Android | Aproximadamente a cada oito horas |
| Computadores Windows 10 registrados como dispositivos | Aproximadamente a cada oito horas |
| Windows Phone | Aproximadamente a cada oito horas |
| Windows 8.1 | Aproximadamente a cada oito horas |

Se o dispositivo foi registrado recentemente, o check-in da configuração, da conformidade e da não conformidade é executado com mais frequência, com estas **estimativas**:

| Plataforma | Frequência |
| --- | --- |
| iOS | A cada 15 minutos por uma hora e, depois, a cada oito horas |  
| macOS | A cada 15 minutos por uma hora e, depois, a cada oito horas | 
| Android | A cada três minutos por 15 minutos e, depois, a cada 15 minutos por duas horas e, depois, a cada oito horas | 
| Computadores Windows 10 registrados como dispositivos | A cada três minutos por 15 minutos e, depois, a cada 15 minutos por duas horas e, depois, a cada oito horas | 
| Windows Phone | A cada cinco minutos por 15 minutos e, depois, a cada 15 minutos por duas horas e, depois, a cada oito horas | 
| Windows 8.1 | A cada cinco minutos por 15 minutos e, depois, a cada 15 minutos por duas horas e, depois, a cada oito horas | 

A qualquer momento, os usuários podem abrir o aplicativo Portal da Empresa, **Configurações** > **Sincronização** para verificar imediatamente se há atualizações de política ou perfil.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Que ações fazem com que o Intune envie imediatamente uma notificação para um dispositivo?

Há diferentes ações que disparam uma notificação, como quando uma política, um perfil ou um aplicativo é atribuído (ou removido), atualizado, excluído e assim por diante. Esses tempos de ação variam dependendo das plataformas.

Os dispositivos fazem o check-in no Intune quando recebem uma notificação ou durante o check-in agendado. Ao direcionar uma ação a um dispositivo ou usuário, como bloqueio, redefinição de senha, atribuição de aplicativo, atribuição de perfil ou atribuição de política, o Intune notifica imediatamente o dispositivo para fazer check-in a fim de receber essas atualizações.

Outras alterações, como revisar as informações de contato no aplicativo Portal da Empresa, não causam uma notificação imediata para os dispositivos.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Se várias políticas forem atribuídas ao mesmo usuário ou dispositivo, como saber quais configurações serão aplicadas?

Quando duas ou mais políticas são atribuídas ao mesmo usuário ou dispositivo, a configuração que se aplica ocorre no nível da configuração individual:

- as configurações da política de conformidade sempre têm precedência sobre as definições da configuração do perfil.

- Se uma política de conformidade é avaliada em relação à mesma configuração em outra política de conformidade, a configuração de política de conformidade mais restritiva é aplicada.

- Se a definição de uma política de configuração está em conflito com uma configuração em outra política de configuração, esse conflito é exibido no Intune. Resolva esses conflitos manualmente.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>O que acontece quando as políticas de proteção de aplicativo entram em conflito umas com as outras? Qual delas será aplicada ao aplicativo?

Os valores de conflito são as configurações mais restritivas disponíveis em uma política de proteção do aplicativo, *exceto* pelos campos de inserção de números, como as tentativas de PIN antes de redefinir. Os campos de inserção de número são definidos com valores iguais aos de uma política de MAM criada usando a opção de configurações recomendadas.

Ocorrem conflitos quando duas configurações de perfil são iguais. Por exemplo, você configurou duas políticas MAM idênticas, exceto pela configuração de copiar/colar. Nesse cenário, a configuração de copiar/colar é definida para o valor mais restritivo, mas o restante das configurações é aplicado conforme a definição.

Uma política é implantada para o aplicativo e entra em vigor. Uma segunda política é implantada. Nesse cenário, a primeira política tem precedência e continua sendo aplicada. A segunda política mostra um conflito. Se as duas são aplicadas ao mesmo tempo, o que significa que não há uma política anterior, as duas ficam em conflito. As configurações conflitantes são definidas para os valores mais restritivos.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>O que acontece quando há conflito de políticas personalizadas de iOS?

O Intune não avalia o conteúdo dos arquivos de Configuração da Apple nem uma política personalizada de OMA-URI (Uniform Resource Identifier da Open Mobile Alliance). Ele simplesmente serve como o mecanismo de entrega.

Ao atribuir uma política personalizada, confirme se as configurações definidas não entram em conflito com as políticas de conformidade e de configuração ou com outras políticas personalizadas. Se uma política personalizada e suas configurações entram em conflito, as configurações são aplicadas aleatoriamente.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>O que acontece quando um perfil é excluído ou não é mais aplicável?

Ao excluir um perfil ou remover um dispositivo de um grupo que tenha o perfil, o perfil e as configurações são removidos do dispositivo conforme descrito a seguir:

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

Os dispositivos Windows Phone não permitem que as políticas de segurança definidas usando o MDM ou o EAS sejam reduzidas em termos de segurança após terem sido configuradas. Por exemplo, você define uma **Senha com um número mínimo de caracteres** igual a 8. E tenta reduzi-la a 4. O perfil mais restritivo já foi aplicado ao dispositivo.

Para alterar o perfil para um valor menos seguro, redefina as políticas de segurança. Por exemplo, no Windows 8.1, na área de trabalho, passe o dedo da direita para a esquerda > escolha **Configurações** > **Painel de Controle**. Selecione o miniaplicativo **Contas de Usuário**. No menu de navegação à esquerda, há um link **Redefinir Políticas de Segurança** (perto da parte inferior). Selecione-o e, em seguida, escolha **Redefinir Políticas**.

Outros dispositivos de MDM, como Android, Windows Phone 8.1 e posteriores, iOS e Windows 10, talvez tenham que ser desativados e registrados novamente no Intune para aplicar um perfil menos restritivo.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Algumas configurações em um perfil do Windows 10 retornam "Não Aplicável"

Algumas configurações em dispositivos Windows 10 pode ser exibidas como "Não Aplicável". Quando isso acontecer, essa configuração específica não será compatível com a versão ou a edição do Windows em execução no dispositivo. Essa mensagem pode ocorrer pelos seguintes motivos:

- A configuração só está disponível para versões mais recentes do Windows, não para a versão atual de sistema operacional do dispositivo.
- A configuração só está disponível para edições ou SKUs específicos do Windows, como Home, Professional, Enterprise e Education.

Para saber mais sobre os requisitos de versão e SKU para as diferentes configurações, confira a [Referência do CSP (Provedor de Serviços de Configuração)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="next-steps"></a>Próximas etapas

Precisa de mais ajuda? Veja [Como obter suporte para o Microsoft Intune](../fundamentals/get-support.md).
