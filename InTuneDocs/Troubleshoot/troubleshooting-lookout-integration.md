---
title: "Solucionar problemas de integração do Lookout | Microsoft Intune"
description: "Este tópico descreve a solução de problemas que costumam ocorrer com a integração do Lookout"
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: 66242455279c20bac2aa2e17dda6c2739e9204c7


---

# Solucionar problemas de integração do Lookout com o Intune
Este tópico descreve alguns problemas comuns que podem ocorrer durante a configuração da Consulta MTP (proteção contra ameaças móveis).
## Solucionar problemas de erros de logon
### Erros 403
Você poderá ver um erro 403 quando fizer logon no [Console da Consulta MTP](https://aad.lookout.com):  **Você não tem autorização para acessar o serviço.**  Isso pode acontecer quando o nome de usuário especificado não for membro do grupo do Azure AD (Azure Active Directory) que está configurado para acessar a Consulta MTP.

a Consulta MTP está configurado para permitir o acesso apenas a usuários de um grupo configurado do Azure AD. Se não tiver certeza de qual grupo está configurado com acesso à Consulta MTP, contate o Suporte do Lookout.

Você pode contatar o Suporte do Lookout por meio de um dos métodos a seguir:

* Email: enterprisesupport@lookout.com
* Faça logon no [Console de MTP](http://aad.lookout.com) e navegue até o módulo **Suporte**.
* Vá até:  https://enterprise.support.lookout.com/hc/en-us/requests e faça uma solicitação de suporte.

### Não é possível entrar
Você pode ver o seguinte erro quando o usuário administrador global do Azure AD não tiver aceitado a configuração inicial do Lookout.

![captura de tela da tela de logon do Lookout mostrando erro ao entrar](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Para solucionar esse problema, um usuário administrador global precisa fazer logon em https://aad.lookout.com/les?action=consent e aceitar a solicitação para iniciar a instalação. Informações mais detalhadas podem ser encontradas no tópico [Set up your subscription with Lookout MTP](set-up-your-subscription-with-lookout-mtp.md) (Configurar sua assinatura com a Consulta MTP)

## Solucionar problemas de status do dispositivo

### O dispositivo não aparece na lista de dispositivos do console da Consulta MTP

Isso pode acontecer em um dos seguintes cenários:
* Quando o usuário que possui o dispositivo não está no **Grupo de Registro** especificado no **Console da Consulta MTP**.  Do módulo **Sistema**, vá até a guia **Conector do Intune** e examine as configurações de **Gerenciamento de Registro**.  Você deve ver um ou mais grupos do Azure AD configurados para o registro.  Confirme se o usuário que possui o dispositivo ausente faz parte de um dos grupos especificados no Azure AD.  Após um novo usuário ser adicionado ao grupo de registro, demorará o intervalo de sondagem configurado (o padrão é 5 minutos) para ver o dispositivo no módulo **Dispositivos** do Console da Consulta MTP.

* Se o dispositivo não tiver suporte da Consulta MTP.  Os dispositivos que não têm suporte aparecerão na seção **Dispositivos Gerenciados** das configurações do conector no Console da Consulta MTP.

### O dispositivo continua sendo relatado como **pendente**

Quando o dispositivo mostra **Pendente**, significa que o usuário final não abriu o aplicativo do Lookout for work e tocou no botão **Ativar**. Para obter mais detalhes sobre a ativação do dispositivo com o aplicativo do Lookout for Work, leia o tópico a seguir:

[Você é solicitado a instalar o Lookout for Work em seu dispositivo Android ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### No console da Consulta MTP, um dispositivo está aparecendo como ativo, mas não tem uma ID do dispositivo.  
Isso significa que o usuário que possui o dispositivo não está no grupo de registro especificado no Console da Consulta MTP.   Um dispositivo pode ficar nesse estado se o usuário que o possui tiver sido removido do grupo de registro ou se o grupo de registro a que o usuário pertence tiver sido removido.

Do módulo **Sistema** no console da Consulta MTP, vá até a guia **Conector do Intune** e examine as configurações de **Registro**.  Você deve ver um ou mais grupos do Azure AD configurados para o registro.  Confirme se o usuário que possui o dispositivo faz parte de um dos grupos especificados no Azure AD.  

Enquanto o dispositivo estiver nesse estado, o Lookout continuará notificando o usuário das ameaças detectadas, mas não enviará nenhuma informação sobre a ameaça ao Intune.

### Dispositivo exibe estado desconectado

Desconectado significa que a Consulta MTP não recebeu informações do dispositivo no intervalo pré-configurado (o padrão é de 30 dias, com um mínimo de 7). Isso significa que o aplicativo do Portal da Empresa ou o aplicativo do Lookout for Work não está instalado no dispositivo ou foi desinstalado. Reinstalar os aplicativos deve solucionar esse problema. Quando o usuário abre o Lookout for Work e ativa o aplicativo, o dispositivo é ressincronizado com a Consulta MTP e o Intune.    

### Forçar uma ressincronização do dispositivo
Do módulo **Dispositivos** do console da Consulta MTP, o administrador pode selecionar o dispositivo e optar por excluí-lo.   Na próxima vez em que o proprietário do dispositivo abrir o aplicativo do Lookout for Work e tocar em **Ativar**, o estado do dispositivo fará uma ressincronização completa.

### O proprietário do dispositivo não está mais usando o dispositivo
Você deve apagar o dispositivo e solicitar que o novo usuário faça o registro.  Do [Console do administrador do Intune](https://manage.microsoft.com), selecione o dispositivo, clique com botão direito do mouse e escolha **Desativar/Apagar** para remover o dispositivo do gerenciamento. Depois de desativar o dispositivo, você poderá excluí-lo.

![captura de tela do módulo do dispositivo no console de administração do Intune com a opção desativar/apagar exibida](../media/mtp/mtp-retire-device-intune-console.png)

Você também pode ir até o módulo **Dispositivos** do console da Consulta MTP e escolher **Excluir**.  

Se o novo usuário estiver em um dos grupos de registro especificados no console da Consulta MTP, o dispositivo será exibido depois que o Azure AD o associar ao novo usuário.

## Fluxos de trabalho de correção de conformidade
[Você é solicitado a instalar o Lookout for Work em seu dispositivo Android]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[Você precisa resolver uma ameaça que o Lookout for Work encontrou em seu dispositivo Android ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### Consulte também
[Set up you subscription with Lookout MTP (Configurar sua assinatura com a Consulta MTP)](set-up-your-subscription-with-lookout-mtp.md)



<!--HONumber=Sep16_HO2-->


