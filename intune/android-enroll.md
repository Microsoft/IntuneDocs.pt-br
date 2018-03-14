---
title: Registrar dispositivos Android no Intune
titlesuffix: Microsoft Intune
description: Saiba como registrar dispositivos Android no Intune.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a72199c9e38f4f4d9d7317469eea2e6254efee7
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2018
---
# <a name="enroll-android-devices"></a>Registrar dispositivos Android

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, é possível gerenciar dispositivos Android, incluindo dispositivos Samsung Knox Standard. Também é possível gerenciar o perfil de trabalho em [dispositivos Android for Work](#enable-enrollment-of-android-for-work-devices).

Dispositivos que executam o Samsung Knox Standard são compatíveis para o gerenciamento de vários usuários pelo Intune. Isso significa que os usuários finais podem entrar ou sair de um dispositivo com as credenciais do Azure AD. O dispositivo é gerenciado centralizadamente, independentemente de estar ou não em uso. Quando os usuários entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

## <a name="prerequisite"></a>Pré-requisito

Para se preparar para gerenciar dispositivos móveis, é necessário definir a autoridade MDM (gerenciamento de dispositivo móvel) como **Microsoft Intune**. Consulte [Definir a autoridade MDM](mdm-authority-set.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel.

## <a name="set-up-android-enrollment"></a>Configurar registro do Android

Por padrão, o Intune é configurado para permitir o registro de dispositivos Android e Samsung Knox Standard.

Para bloquear o registro de dispositivos Android ou para bloquear o registro somente de dispositivos Android de propriedade pessoal, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).

Para habilitar o gerenciamento de dispositivos, os usuários devem registrá-los baixando o aplicativo do Portal da Empresa do Intune (disponível na Google Play) e, em seguida, abrindo o aplicativo e seguindo as instruções. Depois que os dispositivos Android forem gerenciados, [atribua políticas de conformidade](compliance-policy-create-android.md), [gerencie aplicativos](app-management.md) e mais.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Habilite o registro de dispositivos Android for Work

Para habilitar o gerenciamento do perfil de trabalho em dispositivos que dão [suporte a Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), você deverá adicionar uma associação do Android for Work no Intune. Se você deseja registrar dispositivos no Android for Work, que já foram registrados anteriormente como dispositivos Android regulares, é necessário cancelar os registros dos dispositivos e registrá-los novamente.

Se você estiver registrando dispositivos Android for Work usando uma conta do [Gerenciador de Registros do Dispositivo](device-enrollment-manager-enroll.md), haverá um limite de 10 dispositivos que podem ser registrados por conta.

## <a name="add-android-for-work-binding-for-intune"></a>Adicionar a associação do Android for Work para o Intune

> [!NOTE]
> Devido à interação entre domínios do Google e da Microsoft, esta etapa pode exigir que você ajuste as configurações do navegador para concluir com êxito.  Verifique se "portal.azure.com" e "play.google.com" estão na mesma zona de segurança em seu navegador.

1. **Configurar o MDM do Intune**<br>
Se você ainda não o fez, prepare-se para o gerenciamento de dispositivo móvel ao [configurar a autoridade de gerenciamento do dispositivo móvel](mdm-authority-set.md) como **Microsoft Intune**.
2. **Configurar a associação do Android for Work**<br>
    Como administrador do Intune, no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

   a. Na folha **Intune**, escolha **Registro de Dispositivo** > **Registro do Android for Work** e escolha **Configurar** para abrir o site do Android for Work no Google Play. O site é aberto em uma nova guia em seu navegador.
   ![Tela de registro do Android for Work](./media/android-work-bind.png)

   b. **Entrar no Google**<br>
   Na página de entrada do Google, entre com a conta do Google que será associada a todas as tarefas de gerenciamento do Android for Work para o locatário. Esta é a conta do Google que os administradores de TI da sua empresa compartilham para gerenciar e publicar aplicativos no console do Play for Work. Você pode usar uma conta do Google existente ou criar uma nova.  A conta escolhida não deve estar associada a um domínio G Suite.

   c. **Forneça os detalhes da organização**<br>
   Forneça o nome da sua empresa para **Nome da organização**. O **Microsoft Intune** deverá ser exibido para o **Provedor EMM (Enterprise Mobility Management)**. Aceite o contrato do Android for Work e escolha **Confirmar**. Sua solicitação será processada.

## <a name="specify-android-for-work-enrollment-settings"></a>Especificar as configurações de registro do Android for Work
O Android for Work é compatível em determinados dispositivos Android. Consulte os [requisitos do Google para o Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Qualquer dispositivo compatível com o Android for Work também é compatível com o gerenciamento de Android convencional. O Intune permite que você especifique como os dispositivos compatíveis com Android for Work devem ser gerenciados nas [Restrições de Registro](enrollment-restrictions-set.md).

- **Bloquear (definido por padrão)**: todos os dispositivos Android, incluindo dispositivos compatíveis com Android for Work, serão registrados como dispositivos Android convencionais.
- **Permitir**: todos os dispositivos compatíveis com Android for Work serão registrados como dispositivos Android for Work. Os dispositivos Android que não dão suporte ao Android for Work são registrados como dispositivos Android convencionais.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Aprovar o aplicativo Portal da Empresa na Google Play Store gerenciada
Você deve aprovar o aplicativo Portal da Empresa para o Android na Google Play Store gerenciada a fim de garantir que ele receba atualizações automáticas de aplicativo. Se você não aprová-lo, o Portal da Empresa acabará ficando desatualizado e não poderá receber a correções de bugs importantes ou novos recursos quando lançados pela Microsoft.

Siga estas etapas para aprovar o Portal da Empresa do Intune:

1.  Navegue para o aplicativo do Portal da Empresa na [Google Play Store gerenciada](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Entre na Google Play Store gerenciada com a mesma conta do Google que você usou para configurar a associação para o Android for Work.
3.  Clique em **Aprovar** e uma nova caixa de diálogo será aberta.
4.  Examine as permissões nessa caixa de diálogo e clique em **Aprovar**. É necessário aceitar essas permissões para que o aplicativo Portal da Empresa gerencie o perfil de trabalho no dispositivo.
5.  Selecione **Manter aprovada quando o aplicativo solicitar novas permissões** e clique em **Salvar.**

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa

Peça aos usuários que acessem o Google Play para baixar o aplicativo do Portal da Empresa do Intune e, em seguida, que abram o aplicativo e sigam os avisos para registrar seus dispositivos. O aplicativo orienta os usuários pelo processo de registro, explicando o que os usuários podem esperar e o que os administradores de TI podem e não podem ver em seus dispositivos.

Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Para obter informações sobre outras tarefas, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md)
- [Usando seu dispositivo Android com o Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Desassociar sua conta administrativa do Android for Work

É possível desligar o registro e o gerenciamento do Android for Work. Escolher **Desassociar** no console de administração do Intune remove todos os dispositivos Android for Work registrados do registro. Ele também remove a relação entre a conta do Android for Work e o Intune.

### <a name="to-unbind-an-android-for-work-account"></a>Para desassociar uma conta do Android for Work

1. **Desassociar a associação do Android for Work**<br>
    Como administrador do Intune, no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.  Na folha **Intune**, escolha **Registro de Dispositivo**, > **Registro do Android for Work** e escolha **Desassociar**.

2. **Aceite a exclusão da associação do Android for Work**<br>
  Escolha **Sim** para excluir a associação e cancelar o registro de todos os dispositivos Android for Work do Intune.
