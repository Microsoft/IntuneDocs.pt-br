---
title: Registrar dispositivos Android no Intune
titleSuffix: Intune on Azure
description: Saiba como registrar dispositivos Android no Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 295315dae52662c386055747862717b85ed4b877
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Registrar dispositivos Android
<a id="enroll-android-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, o Intune permite que você gerencie dispositivos Android, incluindo dispositivos Samsung Knox Standard. Você também pode gerenciar o perfil de trabalho em dispositivos [Android for Work](#enable-enrollment-of-android-for-work-devices).

Há suporte para dispositivos que executam o Samsung KNOX Standard para o gerenciamento de vários usuários pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure AD, o dispositivo é gerenciado centralmente independentemente de estar ou não em uso. Quando os usuários finais entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

## Pré-requisito
<a id="prerequisite" class="xliff"></a>

Você deve definir a autoridade MDM como **Microsoft Intune** para se preparar para gerenciar dispositivos móveis. Consulte [Definir a autoridade MDM](mdm-authority-set.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel.

## Configurar registro do Android
<a id="set-up-android-enrollment" class="xliff"></a>

Por padrão, o Intune é configurado para permitir o registro de dispositivos Android e Samsung Knox Standard.

Para bloquear o registro de dispositivos Android ou para bloquear o registro somente de dispositivos Android de propriedade pessoal, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).

Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos baixando o aplicativo do Portal da Empresa do Intune, que está disponível no Google Play e, em seguida, abrindo o aplicativo e seguindo as instruções de registro. Quando os dispositivos Android são gerenciados, você pode [atribuir políticas de conformidade](compliance-policy-create-android.md), [gerenciar aplicativos](app-management.md)e muito mais.

## Habilite o registro de dispositivos Android for Work
<a id="enable-enrollment-of-android-for-work-devices" class="xliff"></a>

Para habilitar o gerenciamento do perfil de trabalho em dispositivos que dão [suporte a Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), você deverá adicionar uma associação do Android for Work no Intune. Para registrar dispositivos que dão suporte ao Android for Work registrados anteriormente como dispositivos Android regulares, é necessário cancelar os registros antigos e registrar os dispositivos novamente.

## Adicione a Associação do Android for Work para o Intune
<a id="add-android-for-work-binding-for-intune" class="xliff"></a>

1. **Configurar o MDM do Intune**<br>
Se você ainda não o fez, prepare-se para o gerenciamento de dispositivo móvel ao [configurar a autoridade de gerenciamento do dispositivo móvel](mdm-authority-set.md) como **Microsoft Intune**.

2. **Configurar a associação do Android for Work**<br>
    Como administrador do Intune, no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

    1. Na folha do **Intune**, escolha **Registro de dispositivo**, > **Android for Work** e clique em **Configurar** para abrir o site do Android for Work no Google Play. Uma nova guia será aberta no navegador.
  ![Captura de tela mostrando link para configurar a associação do Android for Work](./media/android-work-bind.png)

    2. **Faça logon no Google**<br>
   Na página de entrada do Google, entre com a conta do Google que será associada a todas as tarefas de gerenciamento do Android for Work para o locatário. Essa é a conta do Google compartilhada entre os administradores de TI da sua organização que costumavam gerenciar e publicar aplicativos no console Play for Work.

    3. **Forneça os detalhes da organização**<br>
   Forneça o nome da empresa em **Nome da organização**. O **Microsoft Intune** deverá ser exibido para o *Provedor EMM (Enterprise Mobility Management)*. Aceite o acordo do Android for Work e clique em **Confirmar**. Sua solicitação será processada.

## Especifique as Configurações de Registro do Android for Work
<a id="specify-android-for-work-enrollment-settings" class="xliff"></a>
   Há suporte para o Android for Work apenas em determinados dispositivos Android. Consulte os [requisitos do Google para o Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window"). Qualquer dispositivo que dê suporte ao Android for Work também dará suporte ao gerenciamento de Android convencional.  O Intune lhe permite especificar como devem ser gerenciados os dispositivos com suporte para o Android for Work:

   - **Gerencie todos os dispositivos como Android** – Todos os dispositivos Android, incluindo dispositivos com suporte para o Android for Work, serão registrados como dispositivos Android convencionais.
   - **Gerencie dispositivos com suporte como Android for Work** – Todos os dispositivos com suporte para o Android for Work serão registrados como dispositivos Android for Work. Os dispositivos Android que não dão suporte ao Android for Work são registrados como dispositivos Android convencionais.
   - **Gerencie dispositivos com suporte para usuários somente nos grupos de usuários como Android for Work** – Permite direcionar o gerenciamento do Android for Work para um conjunto limitado de usuários. Somente os membros dos grupos selecionados que registram um dispositivo que dá suporte ao Android for Work são registrados como dispositivos Android for Work. Todos os outros são registrados como dispositivos Android. Isso é útil durante os pilotos do Android for Work.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa
<a id="tell-your-users-how-to-enroll-their-devices-to-access-company-resources" class="xliff"></a>

Você precisará pedir aos usuários finais que entrem no Google Play para baixar o aplicativo Portal da Empresa do Intune e, em seguida, abram o aplicativo e sigam os prompts para registrar seus dispositivos. O aplicativo orienta os usuários pelo processo de registro, explicando o que os usuários podem esperar e o que os administradores de TI podem e não podem ver em seus dispositivos.

Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md)
- [Usando seu dispositivo Android com o Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## Desassociando sua conta administrativa do Android for Work
<a id="unbinding-your-android-for-work-administrative-account" class="xliff"></a>

É possível desligar o registro e o gerenciamento do Android for Work. Ao clicar em **Desassociar** no console de administração do Intune, todos os dispositivos Android para Trabalho registrados são removidos, bem como a relação entre a conta do Android para Trabalho e o Intune.

### Como desassociar uma conta do Android for Work
<a id="how-to-unbind-an-android-for-work-account" class="xliff"></a>

1. **Desassociar a associação do Android for Work**<br>
    Como administrador do Intune, no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.  Na folha **Intune**, escolha **Registro de dispositivo**, > **Registro do Android for Work** e clique em **Desassociar**.

2. **Aceite a exclusão da associação do Android for Work**<br>
  Clique em **Sim** para excluir a associação e cancelar o registro de todos os dispositivos Android for Work do Intune.
