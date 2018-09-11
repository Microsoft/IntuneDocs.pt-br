---
title: Políticas, perfis e P e R de dispositivo com o Intune – Azure | Microsoft Docs
description: Leia sobre as diferentes políticas e perfis que você pode usar no Microsoft Intune, incluindo políticas para configurar dispositivos, obter acesso aos recursos da empresa, habilitar o acesso condicional e registrar dispositivos corporativos. Além disso, obtenha respostas para perguntas frequentes.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8a7a7405fe40d3568e736c244d9fcb308350709
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43317893"
---
# <a name="manage-settings-and-features-on-your-devices-with-intune-policies"></a>Gerenciar configurações e recursos em seus dispositivos com políticas do Intune

As *políticas* do Microsoft Intune são grupos de configurações que controlam os recursos nos dispositivos móveis e computadores. Você pode criar políticas usando modelos que incluem configurações recomendadas ou personalizadas. Em seguida, você pode implantá-los em grupos de dispositivos ou de usuários.

## <a name="types-of-policies"></a>Tipos de políticas

As políticas do Intune encaixam-se nas categorias a seguir. A categoria usada afeta como criar e implantar a política.

- **Políticas de configuração**: normalmente usadas para gerenciar configurações de segurança e recursos em seus dispositivos, incluindo o acesso aos recursos da empresa. Introdução aos [perfis de dispositivo do Intune](device-profiles.md).
- **Políticas de conformidade de dispositivos**: definem as regras e as configurações que um dispositivo precisa cumprir para ser considerado em conformidade pelas políticas de acesso condicional. Você também pode usar as políticas de conformidade para monitorar e corrigir a conformidade de dispositivos, independentemente do acesso condicional. Introdução às [políticas de conformidade de dispositivos](device-compliance-get-started.md).
- **Políticas de acesso condicional**: ajudam a proteger emails e outros serviços, com base nas condições que você insere. [O que é acesso condicional](conditional-access.md) e [maneiras comuns de usar o acesso condicional](conditional-access-intune-common-ways-use.md) são bons recursos introdutórios.
- **Políticas de registro de dispositivo corporativo**: para obter informações sobre as políticas de registro de dispositivo corporativo, confira [registrar dispositivos iOS](ios-enroll.md).

## <a name="frequently-asked-questions-about-intune-policies"></a>Perguntas frequentes sobre as políticas do Intune

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-being-deployed"></a>Quanto tempo leva para os dispositivos móveis obterem uma política ou aplicativos após a implantação?
Quando uma política ou um aplicativo é implantado, o Intune começa imediatamente a notificar o dispositivo para fazer o check-in no serviço do Intune. Essa etapa geralmente leva menos de cinco minutos.

Se um dispositivo não fizer o check-in para obter a política após a primeira notificação ser enviada, o Intune fará mais três tentativas.  Se o dispositivo estiver offline (por exemplo, desligado ou não conectado a uma rede), ele poderá não receber as notificações. Nesse caso, o dispositivo obterá a política em seu próximo check-in agendado no serviço do Intune, da seguinte maneira:

| Plataforma | Frequência de check-in |
| --- | --- |
| iOS | A cada 6 horas | 
| Mac OS X | A cada 6 horas |
| Android | A cada 8 horas | 
| Windows Phone | A cada 8 horas | 
| Windows 8.1  | A cada 8 horas |  
| Computadores Windows 10 registrados como dispositivos | A cada 8 horas | 

Se o dispositivo for recém-registrado, a frequência do check-in será maior, desta forma:

| Plataforma | Frequência |
| --- | --- |
| iOS | A cada 15 minutos por 6 horas e, então, a cada 6 horas |  
| Mac OS X | A cada 15 minutos por 6 horas e, então, a cada 6 horas | 
| Android | A cada 3 minutos por 15 minutos e, então, a cada 15 minutos por 2 horas e, então, a cada 8 horas | 
| Windows Phone | A cada 5 minutos por 15 minutos e, então, a cada 15 minutos por 2 horas e, então, a cada 8 horas | 
| PCs Windows registrados como dispositivos | A cada 3 minutos por 30 minutos e, então, a cada 8 horas | 

Os usuários também podem iniciar o aplicativo Portal da Empresa e sincronizar o dispositivo para verificar imediatamente a política a qualquer momento.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Que ações fazem com que o Intune envie imediatamente uma notificação para um dispositivo?
Os dispositivos fazem check-in no Intune quando recebem uma notificação que solicita o check-in ou durante o check-in agendado regularmente.  Quando você seleciona um dispositivo ou usuário com uma ação, como apagamento, bloqueio, redefinição de senha, implantação de aplicativo, implantação do perfil (Wi-Fi, VPN, email) ou implantação de política, o Intune tenta notificar imediatamente o dispositivo para fazer check-in no serviço Intune.

Outras alterações, como revisar as informações de contato no portal da empresa, não causam uma notificação imediata para os dispositivos.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-are-applied"></a>Se várias políticas estiverem implantadas para o mesmo usuário ou dispositivo, como saber quais configurações serão aplicadas?
Quando duas ou mais políticas estiverem implantadas para o mesmo usuário ou dispositivo, a avaliação de qual configuração será aplicada ocorrerá no nível da configuração individual:

- Configurações de política de conformidade sempre têm precedência sobre configurações da política.

- A configuração da política de conformidade mais restritiva será aplicada se for avaliada em relação à mesma configuração em uma política de conformidade diferente.

- Se a definição de uma política de configuração estiver em conflito com uma configuração em uma política de configuração diferente, esse conflito será exibido no Intune. Resolva esses conflitos manualmente.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-applies-to-the-app"></a>O que acontece quando as políticas de gerenciamento de aplicativo móvel entram em conflito entre si? Qual delas se aplica ao aplicativo?
Os valores em conflito são as configurações mais restritivas disponíveis em uma política de MAM, com exceção dos campos de entrada de número (como as tentativas de PIN antes de redefinir).  Os campos de entrada de número serão definidos com valores iguais aos de uma política de MAM criada no console usando a opção de configurações recomendadas.

Os conflitos ocorrem quando duas configurações de política são iguais.  Por exemplo, você configurou duas políticas MAM idênticas, exceto pela configuração de copiar/colar.  Nesse cenário, a configuração de copiar/colar é definida para o valor mais restritivo, mas o restante das configurações é aplicado conforme a definição.

Se uma política for implantada no aplicativo e entrar em vigor e, em seguida, uma segunda for implantada, o primeiro aplicativo terá precedência e permanecerá aplicado. A segunda política será mostrada como em conflito. Se as duas forem aplicadas ao mesmo tempo, o que significa que não há uma política anterior, as duas estarão em conflito. As configurações conflitantes são definidas para os valores mais restritivos.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>O que acontece quando há conflito de políticas personalizadas de iOS?
O Intune não avalia o conteúdo dos arquivos de Configuração da Apple nem uma política personalizada de OMA-URI (Uniform Resource Identifier da Open Mobile Alliance). Ele simplesmente serve como o mecanismo de entrega.

Quando você implantar uma política personalizada, confirme se as configurações definidas não estão em conflito com as políticas de conformidade e de configuração ou com outras políticas personalizadas. Se uma política personalizada estiver em conflito com as configurações, a ordem em que as configurações serão aplicadas será aleatória.

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
    - Permitir apagamento
    - Permitir Bluetooth
    - Permitir NFC
    - Permitir Wi-Fi

  - **iOS**: todas as configurações são removidas, exceto:
    - Permitir roaming de Voz
    - Permitir roaming de Dados
    - Permitir sincronização automática durante roaming

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Onde posso encontrar ajuda para solucionar problemas de políticas?

Confira [Solucionar problemas de políticas](troubleshoot-policies-in-microsoft-intune.md).
