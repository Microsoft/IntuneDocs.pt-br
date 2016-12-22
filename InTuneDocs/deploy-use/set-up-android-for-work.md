---
title: Configurar o gerenciamento do Android for Work | Microsoft Intune
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para dispositivos Android for Work com o Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: cfb1ba8ad3d737538fe1e54167121552571d7a1b


---

# <a name="enable-enrollment-of-android-for-work-devices"></a>Habilite o registro de dispositivos Android for Work

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Para habilitar o gerenciamento de dispositivos Android for Work, você deve adicionar uma associação do Android for Work no Intune. Para registrar dispositivos que dão suporte ao Android for Work registrados anteriormente como dispositivos Android regulares, é necessário cancelar os registros antigos e registrar os dispositivos novamente.

## <a name="add-android-for-work-binding-for-intune"></a>Adicione a Associação do Android for Work para o Intune

1. **Configurar Intune**<br>
Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) como **Microsoft Intune** e configure o MDM.

2. **Configurar a associação do Android for Work**<br>
    Como administrador do Intune, abra o [console de administração do Microsoft Intune](http://manage.microsoft.com), vá para **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Android for Work** e clique em **Configurar** para abrir o site do Android for Work no Google Play. Uma nova guia será aberta no navegador.

3. **Faça logon no Google**<br>
   Na página de credenciais do Google, entre com a conta do Google que será associada a todas as tarefas de gerenciamento do Android for Work para o locatário. A conta do Google compartilhada entre os administradores que gerenciam o Intune pode ser usada. Esta é a conta do Google que a organização usa para gerenciar e publicar aplicativos no console do Play for Work.

4. **Forneça os detalhes da Organização**<br>
   Forneça o nome da empresa em **Nome da organização**. O **Microsoft Intune** deverá ser exibido para o *Provedor EMM (Enterprise Mobility Management)*. Aceite o acordo do Android for Work e clique em **Confirmar**. Sua solicitação será processada.

## <a name="specify-android-for-work-enrollment-settings"></a>Especifique as Configurações de Registro do Android for Work
   Há suporte para o Android for Work apenas em determinados dispositivos Android. Consulte os [requisitos do Google para o Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").  Qualquer dispositivo que dê suporte ao Android for Work também dará suporte ao gerenciamento de Android convencional.  O Intune permite que você especifique como o suporte a dispositivos Android for Work deve ser gerenciado:

   - **Gerenciar todos os dispositivos com o Android** – (Desabilitado) Todos os dispositivos Android, incluindo dispositivos com suporte para o Android for Work, serão registrados como dispositivos Android convencionais.
   - **Gerenciar dispositivos com suporte com o Android for Work** – (Habilitado) Todos os dispositivos com suporte para o Android for Work serão registrados como dispositivos Android for Work. Os dispositivos Android que não dão suporte ao Android for Work são registrados como dispositivos Android convencionais.
   - **Gerenciar dispositivos com suporte para usuários somente em grupos desse usuário com o Android for Work** – (Em teste) Permite direcionar o gerenciamento do Android for Work para um conjunto limitado de usuários. Somente os membros dos grupos selecionados que registram um dispositivo que dá suporte ao Android for Work são registrados como dispositivos Android for Work. Todos os outros são registrados como dispositivos Android.

## <a name="next-steps-for-android-for-work"></a>Próximas etapas para o Android for Work
Após a configuração da associação e das preferências do Android for Work, faça o seguinte:
- [Implante os aplicativos Android for Work](android-for-work-apps.md)
- [Adicione as políticas de configuração do Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Desassociando sua conta administrativa do Android for Work

É possível desligar o registro e o gerenciamento do Android for Work. Ao clicar em **Desassociar**, todos os dispositivos Android for Work registrados são removidos, bem como a relação entre a conta do Android for Work e o Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Como desassociar uma conta do Android for Work

1. **Desassociar a associação do Android for Work**<br>
    Como usuário administrativo, abra o [console de administração do Microsoft Intune](http://manage.microsoft.com), vá para **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Android for Work** e clique em **Desassociar**.

2. **Aceite a exclusão da associação do Android for Work**<br>
  Clique em **Sim** para excluir a associação e cancelar o registro de todos os dispositivos Android for Work do Intune.



<!--HONumber=Dec16_HO2-->


