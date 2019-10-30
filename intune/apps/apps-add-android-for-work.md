---
title: Atribuir aplicativos do Google Play Gerenciado a dispositivos Android Enterprise
titleSuffix: Microsoft Intune
description: Entenda como sincronizar e atribuir aplicativos a dispositivos Android Enterprise por meio da Google Play Store Gerenciada.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3137db9d1ab82ebb99686f8f98aa768dae222caf
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72584955"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Adicionar aplicativos do Google Play Gerenciado a dispositivos Android Enterprise com o Intune

O Google Play Gerenciado é a loja empresarial de aplicativos do Google e a única fonte de aplicativos para o Android Enterprise. Você pode usar o Intune para orquestrar a implantação de aplicativos por meio do Google Play Gerenciado em qualquer cenário do Android Enterprise (incluindo o perfil corporativo, registros dedicados e totalmente gerenciados). A maneira como você adiciona aplicativos do Google Play Gerenciado ao Intune é diferente de como os aplicativos para Android são adicionados a dispositivos que não são Android Enterprise. Aplicativos da loja, de linha de negócios e Web são aprovados ou adicionados ao Google Play Gerenciado e, depois, sincronizados no Intune para que apareçam na lista de aplicativos cliente. Depois que eles aparecerem na lista de lista de aplicativos cliente, é possível gerenciar a atribuição de qualquer aplicativo do Google Play Gerenciado, como faria com qualquer outro aplicativo.

Para facilitar a configuração e o uso do gerenciamento do Android Enterprise, quando o locatário do Intune se conecta ao Google Play Gerenciado, o Intune adiciona automaticamente ao console do administrador do Intune quatro aplicativos comuns relacionados ao Android Enterprise. Os quatro aplicativos são os seguintes:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**  – usado para cenários totalmente gerenciados pelo Android Enterprise. Esse aplicativo é instalado automaticamente em dispositivos totalmente gerenciados durante o processo de registro do dispositivo.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : ajudará você a entrar em suas contas se usar a verificação de dois fatores. Esse aplicativo é instalado automaticamente em dispositivos totalmente gerenciados durante o processo de registro do dispositivo.
- **[Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – usado para cenários de perfil de trabalho das Políticas de Proteção do Aplicativo (APP) e do Android Enterprise.
- **[Tela inicial gerenciada](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise)** : usada em cenários de quiosques de vários aplicativos dedicados do Android Enterprise. Os administradores de TI devem criar uma atribuição para instalar esse aplicativo em dispositivos dedicados que serão usados em cenários de quiosque de vários aplicativos.

>[!NOTE]
>Quando um usuário final registra seu dispositivo Android Enterprise totalmente gerenciado, o aplicativo Portal da Empresa do Intune é instalado automaticamente e o ícone do aplicativo pode ficar visível para o usuário final. Se tentar iniciar o aplicativo Portal da Empresa do Intune, o usuário final será redirecionado para o aplicativo Microsoft Intune e o ícone do aplicativo Portal da Empresa será subsequentemente ocultado.

## <a name="before-you-start"></a>Antes de começar
- Verifique se você conectou seu locatário do Intune ao Google Play Gerenciado.  Confira mais informações em [Conectar sua conta do Intune à sua conta gerenciada do Google Play](../enrollment/connect-intune-android-enterprise.md).
- Caso pretenda registrar os dispositivos de perfil corporativo, verifique se o Intune e os perfis corporativos Android estão configurados para trabalharem juntos na carga de trabalho **Registro de dispositivo** do portal do Azure. Para obter mais informações, confira [Registrar dispositivos Android](../enrollment/android-work-profile-enroll.md).

>[!NOTE]
>Ao trabalhar com o Microsoft Intune, recomendamos que você use o Microsoft Edge ou o Google Chrome.

## <a name="managed-google-play-app-types"></a>Tipos de aplicativos do Google Play Gerenciado
O Google Play Gerenciado disponibiliza três tipos de aplicativos:

- **Aplicativo da Google Play Store Gerenciada**: aplicativos públicos geralmente disponíveis na Play Store. Para gerenciar esses aplicativos no Intune, navegue até os aplicativos que você deseja gerenciar, aprove-os, depois sincronize-os no Intune.
- **Aplicativos particulares do Google Play Gerenciado**: esses são aplicativos de linha de negócios publicados no Google Play Gerenciado pelos administradores do Intune.  Esses aplicativos são particulares e disponibilizados somente para o seu locatário do Intune. Essa é a forma de gerenciar e implantar os aplicativos de LOB com o Google Play Gerenciado e o Android Enterprise.
- **Link da Web do Google Play Gerenciado**: links com ícones definidos pelo administrador de TI que podem ser implantados nos dispositivos Android Enterprise. Eles aparecem na lista de aplicativos do dispositivo, como os aplicativos regulares.

## <a name="managed-google-play-store-apps"></a>Aplicativos da Google Play Store Gerenciada
Há duas maneiras de procurar e aprovar aplicativos da Google Play Store Gerenciada com o Intune:

1. Diretamente no console do Intune: navegue e aprove aplicativos da loja em uma exibição hospedada no Intune, que abre diretamente no console do Intune e não exige a reautenticação com uma conta diferente.
1. No console do Google Play Gerenciado: opcionalmente você pode abrir o console do Google Play Gerenciado diretamente e aprovar os aplicativos. Confira [Sincronizar um aplicativo do Google Play Gerenciado com o Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune) para saber mais.  Isso requer um logon separado com a conta que você usou para conectar o locatário do Intune ao Google Play Gerenciado.


### <a name="add-a-managed-google-play-store-app-directly-in-the-intune-console"></a>Adicionar um aplicativo da Google Play Store Gerenciada diretamente no console do Intune

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel do **Intune**, selecione **Aplicativos de cliente** > **Aplicativos**.
5. No painel **Aplicativos**, selecione **Adicionar**.
6. Na lista suspensa **Tipo de aplicativo**, selecione **Google Play Gerenciado**.
7. Selecione **Google Play Gerenciado – Abrir** para abrir o catálogo do Google Play Gerenciado.
7. Selecione **Pesquisar Play Store** no catálogo do Google Play.
8. Use a caixa de pesquisa para procurar os aplicativos que você quer gerenciar.
9. Clique em **Aprovar** para aprovar o aplicativo no Google Play gerenciado e clique em **Aprovar** para aceitar as permissões do aplicativo.
10. Selecione **Manter aprovados quando o aplicativo solicitar novas permissões** na janela Configurações de Aprovação e clique em **Salvar**. Se você não escolher essa opção, precisará aprovar manualmente todas as permissões novas, se o desenvolvedor do aplicativo publicar uma atualização. Isso fará com que as instalações e atualizações do aplicativo sejam interrompidas até que as permissões sejam aprovadas. Por esse motivo, recomendamos a seleção da opção para aprovar automaticamente novas permissões. 
11. Clique em **OK** para incluir os aplicativos aprovados.
12. Clique em **Sincronizar** no painel **Aplicativo** para sincronizar com o serviço Google Play Gerenciado.

### <a name="add-a-managed-google-play-store-app-in-the-managed-google-play-console-alternative"></a>Adicionar um aplicativo gerenciado da Google Play Store ao console do Google Play Gerenciado (alternativa)
Se você preferir sincronizar um aplicativo do Google Play Gerenciado com o Intune em vez de adicioná-lo diretamente usando o Intune, use as etapas a seguir.

> [!IMPORTANT]
> As informações fornecidas abaixo são um método alternativo para adicionar um aplicativo do Google Play Gerenciado usando o Intune, conforme descrito acima.

1. Acesse a [Google Play Store gerenciada](https://play.google.com/work). Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android Enterprise.
2. Pesquise na Store e selecione o aplicativo que deseja atribuir usando o Intune.
3. Na página que exibe o aplicativo, selecione **Aprovar**.  
    No exemplo a seguir, o aplicativo do Microsoft Excel foi escolhido.

    ![O botão Aprovar na Google Play Store gerenciada](./media/apps-add-android-for-work/approve.png)

   Uma janela do aplicativo se abrirá solicitando que você conceda permissões para o aplicativo executar várias operações.

4. Selecione **Aprovar** para aceitar as permissões do aplicativo e continuar.

    ![O botão Aprovar para permissões de aplicativo](./media/apps-add-android-for-work/approve-app-permissions.png)

5. Selecione uma opção de gerenciamento das novas solicitações de permissão de aplicativo e, em seguida, selecione **Salvar**.

    ![Opções para gerencia novas solicitações de permissão de aplicativo](./media/apps-add-android-for-work/approve-app-settings.png)

    O aplicativo é aprovado e exibido no console do administrador de TI. Em seguida, será possível [Sincronizar o aplicativo de perfil corporativo Android com o Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).

## <a name="managed-google-play-private-lob-apps"></a>Aplicativos particulares (LOB) do Google Play Gerenciado

Há duas maneiras de adicionar aplicativos de LOB ao Google Play Gerenciado:

1. Diretamente no console do Intune: possibilita que você adicione aplicativos LOB enviando apenas o APK do aplicativo e um título, diretamente no Intune. Esse método não exige que você tenha uma conta de desenvolvedor do Google nem que você pague uma inscrição para registrar-se no Google como desenvolvedor.  É um método mais simples e tem um número significativamente reduzido de etapas, disponibilizando aplicativos de LOB para gerenciamento em até dez minutos.
1. No Console do Desenvolvedor do Google Play: se você tem uma conta de desenvolvedor do Google ou quer configurar recursos de distribuição avançada que só estão disponíveis no Console do Desenvolvedor do Google Play (como adicionar capturas adicionais da tela do aplicativo), use o [Console do Desenvolvedor do Google Play](https://play.google.com/apps/publish). 

### <a name="managed-google-play-private-lob-app-publishing-directly-in-the-intune-console"></a>Aplicativo particular (LOB) do Google Play Gerenciado publicado diretamente no console do Intune

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel do **Intune**, selecione **Aplicativos de cliente** > **Aplicativos**.
5. No painel **Aplicativos**, selecione **Adicionar**.
6. Na lista suspensa **Tipo de aplicativo**, selecione **Google Play Gerenciado**.
7. Selecione **Google Play Gerenciado – Abrir** para abrir o catálogo do Google Play Gerenciado.
7. Selecione **Aplicativos Particulares** no catálogo do Google Play.
7. Clique no botão **"+"** para adicionar um novo aplicativo
8. Envie um título de aplicativo e um pacote APK para o aplicativo
9. Clique em **Criar**
9. Feche o painel do Google Play Gerenciado ao terminar de adicionar aplicativos
12. Clique em **Sincronizar** no painel **Aplicativo** para sincronizar com o serviço Google Play Gerenciado. Os aplicativos particulares podem demorar vários minutos até ficarem disponíveis para sincronização. Se não aparecer na primeira vez em que você executar uma sincronização, aguarde alguns minutos e inicie uma nova sincronização.

Para saber mais sobre aplicativos particulares do Google Play Gerenciado, incluindo as perguntas frequentes, confira o artigo de suporte do Google: https://support.google.com/googleplay/work/answer/9146439

>[!NOTE]
>Aplicativos particulares adicionados com esse método nunca podem se tornar públicos. Use esta opção de publicação somente se tiver certeza de que esse aplicativo sempre será exclusivo de sua organização.
  

### <a name="managed-google-play-private-lob-app-publishing-using-the-google-developer-console"></a>Publicação de aplicativo particular (LOB) no Google Play Gerenciado usando o Console do Desenvolvedor do Google

1. Entre no [Console do Desenvolvedor do Google Play](https://play.google.com/apps/publish) com a mesma conta usada para configurar a conexão entre o Intune e o Android Enterprise.  
    Se você estiver entrando pela primeira vez, será necessário se registrar e pagar uma taxa para se tornar membro do programa de Desenvolvedor do Google.
2. No console, selecione **Adicionar novo aplicativo**.
3. Carregue e forneça informações sobre o aplicativo da mesma maneira que você publica aplicativos na loja do Google Play. No entanto, você deve selecionar **Disponibilizar este aplicativo somente para minha organização (<*nome da organização*>)** .

    ![Disponibilizar o aplicativo apenas para a sua organização](./media/apps-add-android-for-work/restrict.png)

    Essa operação faz com que o aplicativo fique disponível somente para sua organização. Ele não ficará disponível na Google Play Store pública.

    Para saber mais sobre como carregar e publicar aplicativos Android, veja [Ajuda do Console do Desenvolvedor do Google](https://support.google.com/googleplay/android-developer/answer/113469).
4. Após publicar o aplicativo, entre na [Google Play Store Gerenciada](https://play.google.com/work) com a mesma conta usada para configurar a conexão entre o Intune e o Android Enterprise.
5. No nó **Aplicativos** da Store, verifique se o aplicativo que você publicou aparece.  
    A sincronização do aplicativo com o Intune é aprovada automaticamente.

## <a name="managed-google-play-web-links"></a>Links do Google Play Gerenciado

Os links do Google Play Gerenciado podem ser instalados e gerenciados da mesma forma que outros aplicativos Android. Quando instalados em um dispositivo, são exibidos na lista de aplicativos do usuário com os outros aplicativos que ele instalou. Quando se toca neles, são iniciados no navegador do dispositivo.

Os links abrem no Microsoft Edge ou em qualquer outro aplicativo de navegador que você escolher implantar. Implante pelo menos um aplicativo de navegador nos dispositivos para conseguir abrir corretamente os links. No entanto, todas as opções de **Exibição** disponíveis para links (tela inteira, autônoma e interface do usuário mínima) só funcionam com o navegador Chrome. 

> [!IMPORTANT]
> Na publicação deste documento, há um bug conhecido do Google que impede que os links abram em dispositivos com navegadores diferentes do Chrome. A Google se comprometeu em corrigir esse bug.  Esse aviso será removido quando a Microsoft confirmar que a Google publicou uma correção.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel do **Intune**, selecione **Aplicativos de cliente** > **Aplicativos**.
5. No painel **Aplicativos**, selecione **Adicionar**.
6. Na lista suspensa **Tipo de aplicativo**, selecione **Google Play Gerenciado**.
7. Selecione **Google Play Gerenciado – Abrir** para abrir o catálogo do Google Play Gerenciado.
7. Selecione **Aplicativos Web** no catálogo do Google Play.
7. Clique no botão **"+"** para adicionar um novo aplicativo
7. Insira as informações solicitadas e clique em **Criar**
7. Feche o painel do Google Play Gerenciado ao terminar de adicionar aplicativos
12. Clique em **Sincronizar** no painel **Aplicativo** para sincronizar com o serviço Google Play Gerenciado. Os aplicativos particulares podem demorar vários minutos até ficarem disponíveis para sincronização. Se não aparecer na primeira vez em que você executar uma sincronização, aguarde alguns minutos e inicie uma nova sincronização.

## <a name="sync-a-managed-google-play-app-with-intune"></a>Sincronizar um aplicativo do Google Play gerenciado com o Intune

Se você aprovou um aplicativo da loja e ainda não o encontra na carga de trabalho **Aplicativos clientes**, force uma sincronização imediata da seguinte maneira:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, selecione **Aplicativos clientes**.
4. No painel da carga de trabalho **Aplicativos clientes**, em **Instalação**, selecione **Google Play gerenciado**.
5. No painel **Google Play gerenciado**, escolha **Atualizar**.  
    A página atualiza a hora e o status da última sincronização.
6. No painel da carga de trabalho **Aplicativos clientes**, selecione **Aplicativos**.  
    O aplicativo que acabou de ficar disponível no Google Play gerenciado é exibido.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices"></a>Atribuir aplicativos do Google Play Gerenciado a dispositivos de perfil corporativo Android Enterprise

Quando o aplicativo é exibido no nó **Licenças de aplicativo** do painel da carga de trabalho **Aplicativos clientes**, é possível [atribuí-lo como atribuiria qualquer outro aplicativo](/intune-azure/manage-apps/deploy-apps) para os grupos de usuários.

Depois de atribuir o aplicativo, ele é instalado (ou disponibilizado para instalação) nos dispositivos de destino. A aprovação da instalação do dispositivo não é solicitada ao usuário. Para saber mais sobre dispositivos de perfil corporativo Android Enterprise, confira [Configurar o registro de dispositivos de perfil corporativo Android Enterprise](../enrollment/android-work-profile-enroll.md). 

> [!NOTE] 
> Somente os aplicativos atribuídos serão exibidos para um usuário final na Google Play Store Gerenciada. Portanto, essa é uma etapa importante para o administrador realizar ao configurar aplicativos com o Google Play Gerenciado.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-fully-managed-devices"></a>Atribuir aplicativos do Google Play Gerenciado a dispositivos Android Enterprise totalmente gerenciados

Os [dispositivos Android Enterprise totalmente gerenciados](../enrollment/android-fully-managed-enroll.md) são dispositivos de propriedade da empresa associados a um único usuário e usados exclusivamente para trabalho, e não para uso pessoal. Os usuários com dispositivos totalmente gerenciados podem obter os aplicativos corporativos disponibilizados para o dispositivo no Google Play Gerenciado.

Por padrão, um dispositivo Android Enterprise totalmente gerenciado não permite que os funcionários instalem aplicativos que não estejam aprovados pela organização. Além disso, os funcionários não poderão remover aplicativos instalados contrariando as políticas. Se você quer permitir que os usuários acessem toda a Google Play Store para instalar aplicativos, ao invés de ter acesso somente aos aplicativos aprovados na Google Play Store Gerenciada, é possível definir a opção **Permitir o acesso a todos os aplicativos na Google Play Store** como **Permitir**. Com essa configuração, o usuário pode acessar todos os aplicativos na Google Play Store usando a conta corporativa, no entanto, as compras podem ter algum limite. Você pode remover a restrição de compras limitadas ao permitir que os usuários adicionem novas contas ao dispositivo. Assim, os usuários finais poderão comprar aplicativos na Google Play Store usando contas pessoais e também realizar compras no próprio aplicativo. Para saber mais, confira [Configurações do dispositivo Android Enterprise para permitir ou restringir recursos usando o Intune](../configuration/device-restrictions-android-for-work.md). 

> [!NOTE]
> Os aplicativos Microsoft Intune e Microsoft Authenticator serão obrigatoriamente instalados em todos os dispositivos totalmente gerenciados durante a integração. Instalar automaticamente esses aplicativos fornece suporte de acesso condicional e, assim, os usuários do Microsoft Intune podem ver e resolver problemas de conformidade. 

## <a name="manage-android-enterprise-app-permissions"></a>Gerenciar permissões de aplicativo do Android Enterprise
O Android Enterprise exige que você aprove aplicativos no console Web do Google Play Gerenciado antes de sincronizá-los com o Intune e atribuí-los aos usuários. Como o Android Enterprise possibilita que você envie os aplicativos por push de maneira silenciosa e automática aos dispositivos dos usuários, é preciso aceitar as permissões do aplicativo em nome de todos os usuários. Os usuários não veem as permissões dos aplicativos quando os instalam, portanto, é importante que você entenda essas permissões.

Quando um desenvolvedor de aplicativo atualiza as permissões com uma nova versão do aplicativo, as permissões não são aceitas automaticamente, mesmo se você aprovou as permissões anteriores. Os dispositivos que executam a versão antiga do aplicativo ainda podem usá-lo. No entanto, só é feito o upgrade do aplicativo quando as novas permissões são aprovadas. Os dispositivos sem o aplicativo instalado só instalam o aplicativo quando você aprova as novas permissões do aplicativo. 

### <a name="update-app-permissions"></a>Atualizar as permissões do aplicativo

Periodicamente, acesse o console gerenciado do Google Play para verificar se há novas permissões. Você pode configurar o Google Play para enviar um email a você ou a outras pessoas quando novas permissões forem necessárias para um aplicativo aprovado. Se você atribuir um aplicativo e observar que ele não está instalado nos dispositivos, verifique as novas permissões seguindo estas etapas:

1. Vá ao [Google Play](https://play.google.com/work).
2. Entre com a conta do Google usada para publicar e aprovar os aplicativos.
3. Selecione a guia **Atualizações** e verifique se todos os aplicativos precisam de atualização.  
    Os aplicativos listados exigem novas permissões e só são atribuídos quando elas são aplicadas.

Como alternativa, você pode configurar o Google Play para aprovar permissões de aplicativo novamente de forma automática por aplicativo.

## <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices"></a>Relatórios adicionais de aplicativos do Google Play Gerenciado para dispositivos de perfil de trabalho do Android Enterprise

Para aplicativos do Google Play Gerenciado implantados em dispositivos de perfil de trabalho do Android Enterprise, você pode exibir o status e o número de versão do aplicativo instalado em um dispositivo usando o Intune. 

## <a name="delete-managed-google-play-apps"></a>Excluir aplicativos do Google Play Gerenciados
Quando for necessário, você poderá excluir aplicativos do Google Play Gerenciado do Microsoft Intune. Para excluir um aplicativo do Google Play Gerenciado, abra o Microsoft Intune no portal do Azure e selecione **Aplicativos do cliente** > **Aplicativos**. Na lista de aplicativos, selecione as reticências (...) à direita do aplicativo do Google Play Gerenciado e, em seguida, selecione **Excluir** na lista exibida. Quando você exclui um aplicativo do Google Play gerenciado na lista de aplicativos, o aplicativo do Google Play gerenciado torna-se para aprovação automaticamente.

## <a name="android-enterprise-system-apps"></a>Aplicativos do sistema Android Enterprise

Você pode habilitar um aplicativo de sistema do Android Enterprise para [dispositivos Android Enterprise dedicados](../enrollment/android-kiosk-enroll.md) ou para [dispositivos totalmente gerenciados](../enrollment/android-fully-managed-enroll.md). Para saber mais, confira [Adicionar aplicativos do sistema Android Enterprise ao Microsoft Intune](apps-ae-system.md).

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)
