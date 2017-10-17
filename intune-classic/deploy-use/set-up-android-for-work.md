---
title: Configurar o Android for Work
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para dispositivos Android for Work com o Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: b3a961bdf754100f1a48258290a635add8e03053
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="enable-enrollment-of-android-for-work-devices"></a>Habilite o registro de dispositivos Android for Work

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Para habilitar o gerenciamento de dispositivos Android for Work, você deve adicionar uma associação do Android for Work no Intune. Para registrar dispositivos que dão suporte ao Android for Work registrados anteriormente como dispositivos Android regulares, é necessário cancelar os registros antigos e registrar os dispositivos novamente.

## <a name="add-android-for-work-binding-for-intune"></a>Adicione a Associação do Android for Work para o Intune

1. **Configurar Intune**<br>
Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) como **Microsoft Intune** e configure o MDM.

2. **Configurar a associação do Android for Work**<br>
    Como administrador do Intune, abra o [Console de Administração do Microsoft Intune](https://manage.microsoft.com), acesse **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Android for Work** e clique em **Configurar** para abrir o site do Android for Work no Google Play. Uma nova guia será aberta no navegador.

3. **Faça logon no Google**<br>
   Na página de entrada do Google, entre com a conta do Google que será associada a todas as tarefas de gerenciamento do Android for Work para o locatário. Essa é a conta do Google compartilhada entre os administradores de TI da sua organização que costumavam gerenciar e publicar aplicativos no console Play for Work.

4. **Forneça os detalhes da organização**<br>
   Forneça o nome da empresa em **Nome da organização**. O **Microsoft Intune** deverá ser exibido para o *Provedor EMM (Enterprise Mobility Management)*. Aceite o acordo do Android for Work e clique em **Confirmar**. Sua solicitação será processada.

## <a name="specify-android-for-work-enrollment-settings"></a>Especifique as Configurações de Registro do Android for Work
   Há suporte para o Android for Work apenas em determinados dispositivos Android. Consulte os [requisitos do Google para o Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").  Qualquer dispositivo que dê suporte ao Android for Work também dará suporte ao gerenciamento de Android convencional.  O Intune lhe permite especificar como devem ser gerenciados os dispositivos com suporte para o Android for Work:

   - **Gerencie todos os dispositivos como Android** – Todos os dispositivos Android, incluindo dispositivos com suporte para o Android for Work, serão registrados como dispositivos Android convencionais.
   - **Gerencie dispositivos com suporte como Android for Work** – Todos os dispositivos com suporte para o Android for Work serão registrados como dispositivos Android for Work. Os dispositivos Android que não dão suporte ao Android for Work são registrados como dispositivos Android convencionais.
   - **Gerencie dispositivos com suporte para usuários somente nos grupos de usuários como Android for Work** – Permite direcionar o gerenciamento do Android for Work para um conjunto limitado de usuários. Somente os membros dos grupos selecionados que registram um dispositivo que dá suporte ao Android for Work são registrados como dispositivos Android for Work. Todos os outros são registrados como dispositivos Android. Isso é útil durante os pilotos do Android for Work.

## <a name="next-steps-for-android-for-work"></a>Próximas etapas para o Android for Work
Após a configuração da associação e das preferências do Android for Work, você pode fazer o seguinte:
- [Implante os aplicativos Android for Work](android-for-work-apps.md)
- [Adicione as políticas de configuração do Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Desassociando sua conta administrativa do Android for Work

É possível desligar o registro e o gerenciamento do Android for Work. Ao clicar em **Desassociar** no console de administração do Intune, todos os dispositivos Android para Trabalho registrados são removidos, bem como a relação entre a conta do Android para Trabalho e o Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Como desassociar uma conta do Android for Work

1. **Desassociar a associação do Android for Work**<br>
    Como usuário administrativo, abra o [console de administração do Microsoft Intune](https://manage.microsoft.com), vá para **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Android for Work** e clique em **Desassociar**.

2. **Aceite a exclusão da associação do Android for Work**<br>
  Clique em **Sim** para excluir a associação e cancelar o registro de todos os dispositivos Android for Work do Intune.
