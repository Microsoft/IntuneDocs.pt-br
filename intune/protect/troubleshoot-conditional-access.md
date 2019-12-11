---
title: Solucionar problemas de acesso condicional
titleSuffix: Microsoft Intune
description: O que fazer quando os usuários não obtêm acesso aos recursos por meio de Acesso Condicional do Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/23/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5fa59501-5f33-46b7-a5f5-75eeae9f1209
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c662de98ffa497c5fbc89ac1b78ed8537ff0d80c
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71732692"
---
# <a name="troubleshoot-conditional-access"></a>Solucionar problemas de acesso condicional
Este artigo descreve o que fazer quando os usuários não obtêm acesso aos recursos protegidos com Acesso Condicional, ou quando os usuários podem acessar os recursos protegidos que deveriam estar bloqueados.

Com o Intune e o acesso condicional, você pode proteger o acesso a serviços como:
- Serviços do Office 365, como o Exchange Online, o SharePoint Online e o Skype for Business Online
- Exchange local
- Vários outros serviços

Essa funcionalidade permite que você garanta que somente os dispositivos que estão registrados no Intune e em conformidade com as regras de Acesso Condicional definidas no console de administração do Intune ou no Azure Active Directory tenham acesso aos recursos da empresa. 

## <a name="requirements-for-conditional-access"></a>Requisitos para Acesso Condicional

Os seguintes requisitos precisam ser cumpridos para que o Acesso Condicional funcione:

- O dispositivo precisa ser registrado no MDM e gerenciado pelo Intune.

- Tanto o usuário quanto o dispositivo precisam estar em conformidade com as políticas de conformidade atribuídas no Intune.

- Por padrão, o usuário precisa receber uma política de conformidade de dispositivo. Isso pode depender da configuração da definição de **Marcar dispositivos sem política de conformidade atribuída como**, que está em **Conformidade do dispositivo** > **Configurações de política de conformidade** no portal de administração do Intune.

- O Exchange ActiveSync precisará ser ativado no dispositivo se o usuário estiver usando o cliente de email nativo do dispositivo em vez do Outlook. Isso ocorre automaticamente para dispositivos Android/Knox, iOS e Windows Phone.

- Para o Exchange local, seu Exchange Connector do Intune deve ser configurado corretamente. Para saber mais, confira [Solução de problemas do Exchange Connector no Microsoft Intune](troubleshoot-exchange-connector.md).

- Para o Skype local, você deve configurar a autenticação moderna híbrida. Consulte [visão geral da autenticação moderna híbrida](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview).

Exiba essas condições para cada dispositivo no portal do Azure e no relatório de inventário de dispositivo.

## <a name="devices-appear-compliant-but-users-are-still-blocked"></a>Os dispositivos aparecem em conformidade, mas os usuários ainda estão bloqueados

- Verifique se o usuário tem uma licença do Intune atribuída para a avaliação de conformidade adequada.

- Dispositivos Android que não são Knox não terão acesso até que o usuário clique no link **Comece agora mesmo** no email de quarentena que eles receberam. Isso se aplicará mesmo se o usuário já estiver registrado no Intune. Se o usuário não receber o email com o link no smartphone dele, ele poderá usar um computador para acessar o email e encaminhá-lo para uma conta de email no dispositivo.

- Quando um dispositivo é registrado pela primeira vez, pode levar algum tempo para que as informações de conformidade sejam registradas para um dispositivo. Aguarde alguns minutos e tente novamente.

- Para dispositivos iOS, um perfil de email existente pode bloquear a implantação de um perfil de email criado pelo administrador do Intune atribuído a esse usuário, tornando o dispositivo não compatível. Nesse cenário, o aplicativo do Portal da Empresa informará o usuário de que ele não está em conformidade devido ao perfil de email configurado manualmente, e solicita que o usuário remova esse perfil. Depois que o usuário remover o perfil de email existente, o perfil de email do Intune pode ser implantado com êxito. Para evitar esse problema, instrua os usuários a removerem quaisquer perfis de email existentes no dispositivo antes de se registrarem.

- Um dispositivo pode ficar parado em um estado de verificação de conformidade, impedindo que o usuário inicie outro check-in. Se você tiver um dispositivo neste estado:
  - Verifique se o dispositivo está usando a versão mais recente do aplicativo do Portal da empresa.
  - Reinicie o dispositivo.
  - Veja se o problema persiste em redes diferentes (por exemplo, celular, Wi-Fi, etc.).

  Se o problema continuar, entre em contato com o Suporte da Microsoft, conforme descrito em [obter suporte para o Microsoft Intune](../fundamentals/get-support.md).

- Certos dispositivos Android podem parecer criptografados, mas o aplicativo do Portal da Empresa os reconhece como não criptografados e os marca como não compatíveis. Nesse cenário, o usuário verá uma notificação no aplicativo do Portal da Empresa solicitando a definição de uma senha de inicialização para o dispositivo. Depois de tocar na notificação e confirmar o PIN ou a senha atual, escolha a opção **Exigir PIN para iniciar o dispositivo** na tela **Proteger inicialização** e, em seguida, toque no botão **Verificar conformidade** para o dispositivo no aplicativo do Portal da Empresa. Agora o dispositivo deve ser detectado como criptografado. 

  > [!NOTE]
  > Alguns fabricantes criptografam seus dispositivos usando um PIN padrão em vez daquele definido pelo usuário. A criptografia de exibições do Intune que usa um PIN padrão é insegura e marca tais dispositivos como incompatíveis até que o usuário crie uma nova senha, um PIN não padrão.

- Um dispositivo Android registrado e em conformidade ainda pode ser bloqueado e receber um aviso de quarentena ao tentar acessar recursos corporativos pela primeira vez. Se isso ocorrer, verifique se o aplicativo do Portal da Empresa não está em execução e selecione o link **Comece a usar agora mesmo** no email de quarentena para disparar a avaliação. Só será necessário fazer isso quando o acesso condicional é habilitado pela primeira vez.

- Um dispositivo Android registrado pode solicitar ao usuário "nenhum certificado encontrado" e não receber acesso aos recursos do O365. O usuário deve habilitar a opção *Habilitar Acesso do Navegador* no dispositivo registrado da seguinte maneira:
  1. Abra o aplicativo do Portal da Empresa.
  2. Vá para a página Configurações por meio dos três pontos (...) ou do botão de menu do hardware.
  3. Selecione o botão *Habilitar Acesso do Navegador*.
  4. No navegador Chrome, saia do Office 365 e reinicie o Chrome.  


## <a name="devices-are-blocked-and-no-quarantine-email-is-received"></a>Os dispositivos estão bloqueados e nenhum email de quarentena foi recebido

- Verifique se o dispositivo existe no console de administração do Intune como um dispositivo do Exchange ActiveSync. Se não, é provável que a descoberta de dispositivos esteja falhando, provavelmente devido a um problema do Exchange Connector. Para saber mais, confira [Solucionar problemas do Intune Exchange Connector no Local](troubleshoot-exchange-connector.md).

- Antes do Exchange Connector bloquear um dispositivo, ele envia um email de ativação (quarentena). Se o dispositivo estiver offline, ele poderá não receber o email de ativação. 

- Verifique se o cliente de email no dispositivo está configurado para recuperar emails usando **Push** em vez de **Pull**. Nesse caso, isso poderia fazer com que o usuário perca o email. Mude para **Pull** e veja se o dispositivo recebe o email.

## <a name="devices-are-noncompliant-but-users-are-not-blocked"></a>Os dispositivos são incompatíveis, mas os usuários não estão bloqueados

- Para computadores Windows, o Acesso Condicional bloqueia somente o aplicativo de email nativo, o Office 2013 com autenticação moderna ou o Office 2016. O bloqueio de versões anteriores do Outlook ou de todos os aplicativos de email em computadores Windows exige o Registro de Dispositivo do Azure Active Directory e as configurações do AD FS (Serviços de Federação do Active Directory) de acordo com o artigo [Configurar o SharePoint Online e o Exchange Online para Acesso Condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication).

- Se o dispositivo for seletivamente desativado ou apagado do Intune, ele poderá continuar a ter acesso por várias horas após a desativação. Isso ocorre porque o Exchange armazena em cache os direitos de acesso por seis horas. Considere outros meios de proteção de dados em dispositivos desativados neste cenário.

- Surface Hub, os dispositivos Windows registrados em massa e o DEM inscrito podem dar suporte ao acesso condicional quando um usuário ao qual é atribuída uma licença para o Intune está conectado. No entanto, você deve implantar a política de conformidade em grupos de dispositivos (não grupos de usuários) para obter a avaliação correta.

- Verifique as atribuições das suas políticas de conformidade e as políticas de acesso condicional. Se um usuário não estiver no grupo que tem as políticas atribuídas ou estiver em um grupo que foi excluído, o usuário não será bloqueado. Somente a conformidade dos dispositivos de usuários em um grupo atribuído é verificada.

## <a name="noncompliant-device-is-not-blocked"></a>Dispositivo incompatível não bloqueado

Se um dispositivo não estiver em conformidade, mas continuar tendo acesso, execute as seguintes ações.

- Analise os grupos de Destino e Exclusão. Se um usuário não estiver no grupo de destino correto ou estiver no grupo de exclusão, ele não será bloqueado. Somente os dispositivos de usuários em um grupo de Destino são verificados quanto à conformidade.

- Certifique-se de que o dispositivo esteja sendo descoberto. O Exchange Connector está apontando para uma CAS do Exchange 2010 enquanto o usuário está em um servidor Exchange 2013? Nesse caso, se a regra padrão do Exchange for Permitir, mesmo se o usuário estiver no grupo de Destino, o Intune não poderá estar ciente da conexão do dispositivo com o Exchange.

- Verifique a existência/estado de acesso do dispositivo no Exchange:
  - Use este cmdlet do PowerShell para obter uma lista de todos os dispositivos móveis para uma caixa de correio: "Get-ActiveSyncDeviceStatistics -mailbox mbx". Caso o dispositivo não esteja listado, isso indicará que ele não está acessando o Exchange.
  
  - Se o dispositivo estiver listado, use cmdlet "Get-CASmailbox -identity:’upn’ | fl" para obter informações detalhadas sobre seu estado de acesso e fornecer essas informações ao Suporte da Microsoft.

## <a name="next-steps"></a>Próximas etapas
Caso essas informações não ajudem você, [obtenha também o suporte para o Microsoft Intune](../fundamentals/get-support.md).
