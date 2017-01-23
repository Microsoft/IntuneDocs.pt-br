---
title: "Solucionar problemas de integração do Lookout | Microsoft Docs"
description: "Este tópico descreve a solução de problemas que costumam ocorrer com a integração do Lookout"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: ed4d828b19620f421461228e04bda7b7be799444


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Solucionar problemas de integração do Lookout com o Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico descreve alguns problemas comuns que podem ocorrer durante a configuração da Consulta MTP (proteção contra ameaças móveis).

**Erros de logon**

## <a name="403-errors"></a>Erros 403
Ao fazer logon no [console do Lookout MTP](https://aad.lookout.com), você recebe um erro 403: **Você não tem autorização para acessar o serviço.** Isso pode acontecer quando o nome de usuário especificado não é membro do grupo do Azure AD (Active Directory) configurado para acessar o Lookout MTP.

O Lookout MTP permite que apenas usuários de um grupo do Azure AD configurado acessem o serviço. Para determinar qual grupo está configurado com acesso ao Lookout MTP, contate o suporte do Lookout:

* Email: enterprisesupport@lookout.com
* Faça logon no [Console de MTP](http://aad.lookout.com) e navegue até o módulo **Suporte**.
* Vá até:  https://enterprise.support.lookout.com/hc/en-us/requests e faça uma solicitação de suporte.

## <a name="unable-to-sign-in"></a>Não é possível entrar
Você vê o erro a seguir quando o usuário administrador global do Azure AD não aceitou a configuração inicial do Lookout.

![captura de tela da tela de logon do Lookout mostrando erro ao entrar](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Para solucionar esse problema, um usuário administrador global precisa fazer logon em https://aad.lookout.com/les?action=consent e aceitar a solicitação para iniciar a instalação. Informações mais detalhadas podem ser encontradas no tópico [Set up your subscription with Lookout MTP](../deploy-use/set-up-your-subscription-with-lookout-mtp.md) (Configurar sua assinatura com a Consulta MTP)

**Problemas de status do dispositivo**

## <a name="device-missing-from-lookout-device-list"></a>Dispositivo ausente na lista de dispositivos do Lookout

Isso pode acontecer em um dos seguintes cenários:
* O usuário do dispositivo não está no **Grupo de Registro** especificado no **Console do Lookout MTP**.  No [console do Lookout](http://aad.lookout.com), acesse **Sistema** > **Intune Connector** > **Gerenciamento de Registro**.  Examine os grupos do Azure AD configurados para o registro e verifique se o usuário do dispositivo faz parte de um dos grupos do Azure AD.  Depois que um usuário é adicionado ao grupo de registro, pode levar até o intervalo de sondagem configurado, 5 minutos por padrão, para que o dispositivo seja exibido no módulo **Dispositivos** do console do Lookout MTP.
* Se o dispositivo não tiver suporte da Consulta MTP.  Os dispositivos que não têm suporte aparecerão na seção **Dispositivos Gerenciados** das configurações do conector no Console da Consulta MTP.

### <a name="device-reported-as-pending"></a>Dispositivo relatado como **pendente**

Um dispositivo é mostrado como **Pendente** se o usuário final não abriu o aplicativo Lookout for Work nem tocou no botão **Ativar**. Para obter mais detalhes sobre a ativação do dispositivo com o aplicativo Lookout for Work, consulte [Você é solicitado a instalar o Lookout for Work](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android) ou [Você é solicitado a instalar o Lookout for Work em seu dispositivo iOS](https://docs.microsoft.com/en-us/intune/enduser/you-are-prompted-to-install-lookout-for-work-ios)

## <a name="device-whos-active-but-has-no-device-id"></a>Dispositivo ativo, mas sem ID de dispositivo
No console do Lookout MTP, se um dispositivo ativo não tiver nenhuma ID de dispositivo, o usuário do dispositivo não estará no grupo de registro. Um dispositivo poderá entrar nesse estado se o usuário do dispositivo tiver sido removido do grupo de registro ou se o grupo de registro tiver sido removido.

No [console do Lookout](http://aad.lookout.com), acesse **Sistema** > **Intune Connector** > **Registro** e examine as configurações.  Examine os grupos do Azure AD e verifique se o usuário do dispositivo faz parte de um dos grupos do Azure AD.

Enquanto o dispositivo estiver nesse estado, o Lookout continuará notificando o usuário das ameaças detectadas, mas não enviará nenhuma informação sobre a ameaça ao Intune.

## <a name="device-reported-as-disconnected"></a>Dispositivo relatado como **desconectado**

**Desconectado** significa que o dispositivo não foi sincronizado com o Lookout MTP no intervalo configurado, 30 dias por padrão, com um mínimo de 7 dias. O aplicativo Portal da Empresa ou Lookout for Work está ausente do dispositivo. Reinstalar os aplicativos deve solucionar esse problema. Quando o usuário abre o Lookout for Work e ativa o aplicativo, o dispositivo é ressincronizado com a Consulta MTP e o Intune.    

### <a name="forcing-a-device-sync"></a>Forçando uma sincronização de dispositivo
Do módulo **Dispositivos** do console da Consulta MTP, o administrador pode selecionar o dispositivo e optar por excluí-lo.   Na próxima vez em que o proprietário do dispositivo abrir o aplicativo do Lookout for Work e tocar em **Ativar**, o estado do dispositivo fará uma ressincronização completa.

## <a name="device-has-a-new-user"></a>O dispositivo tem um novo usuário
É necessário apagar o dispositivo e solicitar que o novo usuário se registre.  Do [Console do administrador do Intune](https://manage.microsoft.com), selecione o dispositivo, clique com botão direito do mouse e escolha **Desativar/Apagar** para remover o dispositivo do gerenciamento. Depois de desativar o dispositivo, você poderá excluí-lo.

![captura de tela do módulo do dispositivo no console de administração do Intune com a opção desativar/apagar exibida](../media/mtp/mtp-retire-device-intune-console.png)

Também é possível acessar o módulo **Dispositivos** do [console do Lookout](http://aad.lookout.com) e escolher **Excluir**.  

Se o novo usuário estiver em um grupo de registro do Lookout MTP, o dispositivo será exibido depois que o Azure AD associar o dispositivo ao novo usuário.

## <a name="compliance-remediation-workflows"></a>Fluxos de trabalho de correção de conformidade
- [Você é solicitado a instalar o Lookout for Work em seu dispositivo Android]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)
- [Você precisa resolver uma ameaça que o Lookout for Work encontrou em seu dispositivo Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [Você precisa resolver uma ameaça que o Lookout for Work encontrou em seu dispositivo iOS](https://docs.microsoft.com/en-us/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a>Consulte também
[Configurar sua assinatura com a Consulta MTP](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Jan17_HO2-->


