---
title: Atualizações da interface do usuário para aplicativos de usuário final do Intune
titlesuffix: Microsoft Intune
description: Descubra o que mudou na interface do usuário para aplicativos que funcionam em dispositivos de usuários finais com o Microsoft Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8da396e41844c854cd18a9384fe97ac0bee59355
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2018
---
# <a name="ui-updates-for-intune-end-user-apps"></a>Atualizações da interface do usuário para aplicativos de usuário final do Intune
Saiba quais atualizações foram feitas na interface do usuário para os aplicativos que os usuários finais vão encontrar nesta versão do Microsoft Intune. Entender essas atualizações pode ajudá-lo nas comunicações com usuários e na atualização da documentação personalizada que você criou para dar suporte à sua implantação. Isso também pode ajudá-lo a entender como solucionar melhor os problemas enfrentados caso seja necessário ligar para a assistência técnica para obter suporte usando o Portal da Empresa.

<!---End-user messaging for accounts 1573558, 1712; changes to be made for other platforms for 1801 Users of the Company Portal website, will be blocked from taking actions that require write access to your tenant. They will see appropriate error messaging explaining that their account is under maintenance. Similar changes are coming to the Company Portal apps for Android, iOS, macOS, and Windows soon. ![Error message that occurs during account move](./media/account-move-rom-iwp-user-1712.png)--->

## <a name="week-of-april-2-2018"></a>Semana de 2 de abril de 2018

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Atualização de experiência do usuário para o aplicativo Portal da Empresa para iOS <!--1412866 -->
Lançamos uma atualização principal da experiência do usuário para o aplicativo Portal da Empresa para iOS. A atualização apresenta um novo design visual completo que inclui uma aparência modernizada. Mantivemos a funcionalidade do aplicativo, mas aumentamos sua usabilidade e acessibilidade.  

Você também verá:
- Suporte para iPhone X.
- Mais rapidez na inicialização do aplicativo e no carregamento de respostas para economizar tempo para os usuários.
- Barras de progresso adicionais para fornecer aos usuários as informações de status mais atualizadas.
- Melhorias às maneiras como os usuários carregam logs, portanto, se algo der errado, será mais fácil relatar.  

|Antes|Depois|
|---|---|
|![01](/intune/media/cp_iosRedesign_before_1803_01.png)|![01](/intune/media/cp_iosRedesign_after_1803_01.png)|
|*Combinado com a etapa anterior*|![02](/intune/media/cp_iosRedesign_after_1803_02.png)|
|![03](/intune/media/cp_iosRedesign_before_1803_02.png)|![03](/intune/media/cp_iosRedesign_after_1803_03.png)|

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Melhorias à linguagem no aplicativo Portal da Empresa para Windows <!---1683758--->
Melhoramos a linguagem no Portal da Empresa para Windows 10 para ser mais amigável e específica para sua empresa.

|Antes|Depois|
|---|---|
|![01](./media/windows_enroll_before_1803.png)|![01](./media/windows_enroll_after_1803.png)|
|![02](./media/windows_view_policy_issues_before_1803.png)|![02](./media/windows_view_policy_issues_after_1803.png)

## <a name="week-of-march-12-2018"></a>Semana de 12 de março de 2018

#### <a name="company-portal-for-android-visual-updates---976944---"></a>Portal da empresa para atualizações visuais do Android <!--976944 -->

Atualizamos o aplicativo Portal da Empresa para Android para seguir as diretrizes do [Design de Material](https://material.io/) do Android.

|Antes|Depois|
|---|---|
|![01](./media/android_about_before_1803.png)|![01](./media/androidCP_about_after_1803.png)|
|![02](./media/android_contact_it_before_1803.png)|![02](./media/android_contact_it_after_1803.png)|
|![03](./media/android_devices_before_1803.png)|![03](./media/androidCP_devicelist_after_1803.png)|
|![04](./media/android_device_details_before_1803.png)|![05](./media/androidCP_devicedetails_1_after1803.png)|
|![05](./media/android_device_details_update_settings_before_1803.png)|![05](./media/androidCP_devicedetails_red_box_2_after1803.png)|
|![06](./media/android_profile_before_1803.png)|![06](./media/android_profile_after_1803.png)|
|![07](./media/androidCP_Setup01_before_1803.png)|![07](./media/androidCP_Setup01_after_1803.png)|


## <a name="week-of-november-27-2017"></a>Semana de 27 de novembro de 2017

### <a name="new-device-categories-step-in-guided-setup-for-the-company-portal-app-for-windows-10----1335292---"></a>Nova etapa "Categorias de Dispositivo" na configuração interativa do aplicativo Portal da Empresa para Windows 10 <!---1335292--->

Se você tiver habilitado o [mapeamento do grupo de dispositivos](device-group-mapping.md), o aplicativo Portal da Empresa para Windows 10 orientará os usuários pela seleção de uma categoria de dispositivo depois de registrar seu dispositivo.

![Categoria de mapeamento do grupo de dispositivos](./media/w10_cp_category_device_setup_after_1711.png)

## <a name="week-of-november-13-2017"></a>Semana de 13 de novembro de 2017

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Aprimoramentos no fluxo de trabalho de configuração de dispositivo no Portal da Empresa para iOS na versão 2.9.0 <!---1417174--->

Melhoramos o fluxo de trabalho de configuração de dispositivo no aplicativo do Portal da Empresa para iOS. A linguagem é mais fácil de usar e combinamos as telas sempre que possível. Também tornamos a linguagem mais específica à sua empresa usando o nome da empresa em todo o texto de configuração.

> [!NOTE]
> Usamos o nome da empresa que você definiu no Portal do Azure no **Microsoft Intune** > **Aplicativos Móveis** > **Marca do Portal da Empresa** > **Nome da empresa**. Se você não tiver definido esse valor, usaremos o nome do locatário definido em **Azure Active Directory** > **Propriedades** > **Nome**. Se você não tiver definido um nome de empresa na identidade visual do Portal da Empresa e não quiser que seu nome de locatário seja exibido, recomendamos que você defina o nome da empresa na guia de identidade visual do Portal da Empresa. Se você não quiser que essa cadeia de caracteres apareça no cabeçalho no Portal da Empresa, desmarque a caixa de seleção "Mostrar nome da empresa perto do logotipo".

|Antes|Depois|
|---|---|
|![01](./media/ios_cp_enroll_01_before_1711.png)|![01](./media/ios_cp_enroll_01_after_1711.png)|
|![02](./media/ios_cp_enroll_02_before_1711.png)|*Combinado com a etapa anterior*|
|![03](./media/ios_cp_enroll_03_before_1711.png)|![03](./media/ios_cp_enroll_03_after_1711.png)|
|![04](./media/ios_cp_enroll_04_before_1711.png)|![04](./media/ios_cp_enroll_04_after_1711.png)|
|![05](./media/ios_cp_enroll_05_before_1711.png)|![05](./media/ios_cp_enroll_05_after_1711.png)|
|![06](./media/ios_cp_enroll_06_before_1711.png)|![06](./media/ios_cp_enroll_06_after_1711.png)|
|![07](./media/ios_cp_enroll_07_before_1711.png)|![07](./media/ios_cp_enroll_07_after_1711.png)|


## <a name="week-of-november-6-2017"></a>Semana de 6 de novembro de 2017

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Atualizações para o aplicativo Portal da Empresa para Windows 10 <!--1299474-->
A página Configurações no aplicativo Portal da Empresa para Windows 10 foi atualizada para tornar as configurações e as ações de usuário pretendidas mais consistentes em todas as configurações. Ela também foi atualizada para corresponder ao layout de outros aplicativos do Windows.

|Antes|Depois|
|---|---|
|![01](./media/w10-share-logs.png)|![02](./media/w10-share-logs-after-1711.png)|


### <a name="search-improvements-to-the-company-portal-apps-and-website---1418189--"></a>Pesquisar melhorias nos aplicativos e no site do Portal da Empresa <!--1418189-->
Agora os aplicativos do Portal da Empresa pesquisa entre categorias, nomes e descrições de aplicativos. Os resultados são classificados em ordem decrescente de relevância. Essas atualizações também estão disponíveis no [site do Portal da Empresa](https://portal.manage.microsoft.com).

Ainda estamos ajustando maneira como a relevância é controlada, portanto, informe-nos como ele está funcionando usando o link "Comentários" na parte inferior do site do Portal da Empresa.

## <a name="week-of-october-16-2017"></a>Semana de 16 de outubro de 2017

### <a name="search-improvements-to-the-company-portal-website---1331697--"></a>Pesquisar aprimoramentos no site do Portal da Empresa <!--1331697-->
Estamos melhorando os recursos de pesquisa do nosso aplicativo, começando com o [site do Portal da Empresa](https://portal.manage.microsoft.com). As pesquisas agora serão executadas em categorias de aplicativo, além dos campos de Nome e Descrição. Os resultados serão classificados, por padrão, em ordem decrescente de relevância. 

Usuários do iOS também receberão essa alteração, como o Portal da Empresa site também é usado como parte do aplicativo de Portal da Empresa para iOS. Os aplicativos de Portal da Empresa para Android e Windows receberão atualizações semelhantes nos próximos meses.

Ainda estamos ajustando maneira como a relevância é controlada, portanto, informe-nos como ele está funcionando usando o link "Comentários" na parte inferior do site do Portal da Empresa.


### <a name="ios-company-portal-displays-large-icons----1454593---"></a>O Portal da Empresa do iOS exibe ícones grandes <!-- 1454593 -->
Esta versão corrige um problema conhecido que trata de como o Portal da Empresa do iOS exibe ícones no bloco do aplicativo. Se você carregar ícones de aplicativo com 120 x 120 pixels ou maiores, agora eles serão exibidos no [site Portal da Empresa](https://portal.manage.microsoft.com) e nas páginas de aplicativos do Portal da Empresa do iOS com o tamanho total do bloco do aplicativo.


## <a name="week-of-october-2-2017"></a>Semana de 2 de outubro de 2017

#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Melhorias no fluxo de trabalho de configuração de dispositivo no Portal da Empresa <!--1490692-->
Melhoramos o fluxo de trabalho de configuração de dispositivo no aplicativo do Portal da Empresa para Android. A linguagem é mais fácil de usar e mais específica para sua empresa e combinamos as telas sempre que possível. 

|Antes|Depois|
|---|---|
|![01](./media/android_cp_enroll_01_post_1709.png)|![01](./media/android_cp_enroll_01_1709_new.png)|
|![01a](./media/android_cp_enroll_01_before_1710.png)| *Combinado com a etapa anterior* |
|![02](./media/android_cp_enroll_02_before_1710.png)|![02](./media/android_cp_enroll_02_after_1710.png)|
|![03](./media/android_cp_enroll_03_before_1710.png)|![03](./media/android_cp_enroll_03_after_1710.png)|

Etapas adicionais foram aprimoradas para dispositivos Android for Work.

|Antes|Depois|
|---|---|
|![04](./media/android_work_cp_enroll_01_before_1710.png)|![04](./media/android_work_cp_enroll_01_after_1710.png)|
|![05](./media/android_work_cp_enroll_02_before_1710.png)| *Combinado com a etapa anterior* |
|![06](./media/android_work_cp_enroll_03_before_1710.png)|![06](./media/android_work_cp_enroll_03_after_1710.png)|
|![07](./media/android_work_cp_enroll_04_before_1710.png)|![07](./media/android_work_cp_enroll_04_after_1710.png)|
|![08](./media/android_work_cp_enroll_05_before_1710.png)| *Combinado com a etapa anterior* |


Também atualizamos a tela de ativação de email de acesso condicional.

|Antes|Depois|
|---|---|
|![06](./media/android_conditional_access_email_before_1710.png)|![06](./media/android_conditional_access_email_after_1710.png)

## <a name="week-of-september-11-2017"></a>Semana de 11 de setembro de 2017

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Frases mais fáceis de entender para o aplicativo Portal da Empresa para Android <!---1396349--->  

O processo de registro para o aplicativo Portal da Empresa para Android foi simplificado com o novo texto a fim de facilitar o registro dos usuários. Se você tiver a documentação de registro personalizado, você deverá atualizá-la para refletir as novas telas. Imagens de amostra podem ser encontradas abaixo:

|Antes|Depois|
|---|---|
|![01](./media/android_cp_enroll_01_before_1709.png)|![01](./media/android_cp_enroll_01_post_1709.png)|
|![02](./media/android_cp_enroll_02_before_1709.png)|![02](./media/android_cp_enroll_02_post_1709.png)|
|![03](./media/android_cp_enroll_03_before_1709.png)|![03](./media/android_cp_enroll_03_post_1709.png)|
|![04](./media/android_cp_enroll_04_before_1709.png)|![04](./media/android_cp_enroll_04_post_1709.png)|
|![05](./media/android_cp_enroll_05_before_1709.png)|![05](./media/android_cp_enroll_05_post_1709.png)|


## <a name="august-2017"></a>Agosto de 2017

### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>O aplicativo Mail do iOS 11 dará suporte ao OAuth <!---1196951--->

O acesso condicional com o Intune dá suporte a uma autenticação mais segura em dispositivos iOS com o OAuth. Para dar suporte a ela, agora haverá um fluxo diferente no aplicativo Portal da Empresa para iOS, a fim de possibilitar uma autenticação mais segura. Quando os usuários finais tentarem entrar em uma nova conta do Exchange no aplicativo Mail, eles verão um prompt de exibição da Web. Após o registro no Intune, os usuários verão um aviso para permitir que o aplicativo Mail nativo acesse um certificado. A maioria dos usuários finais não verá mais nenhum email em quarentena. As contas de email existentes continuarão usando o protocolo de autenticação básica. Portanto, esses usuários ainda receberão emails em quarentena. Essa experiência de entrada para usuários finais é semelhante à de aplicativos móveis do Office.

![Seleção do tipo de conta no aplicativo de email nativo.](./media/ios-11-ca-email-after-1708-01.png)

![Depois de selecionar o Exchange, um aviso do dispositivo iOS solicita o endereço de email e o nome da conta.](./media/ios-11-ca-email-after-1708-02.png)

![Forneça o endereço de email e o nome da conta.](./media/ios-11-ca-email-after-1708-03.png)

![Enviado para a página externa de logon da Microsoft.](./media/ios-11-ca-email-after-1708-04.png)

![Fornecimento de senha na página de Microsoft.](./media/ios-11-ca-email-after-1708-05.png)

![A Microsoft solicita que o usuário registre o dispositivo no gerenciamento.](./media/ios-11-ca-email-after-1708-06.png)

![Usuário deve se registrar no site do Portal da Empresa.](./media/ios-11-ca-email-after-1708-07.png)



### <a name="intune-mobile-application-management-mam-dialog-boxes-will-have-a-modern-interface----1199015---"></a>As caixas de diálogo de MAM (gerenciamento de aplicativo móvel) do Intune móvel terão uma interface moderna <!-- 1199015 -->

As caixas de diálogo de MAM (gerenciamento de aplicativo móvel) do Intune serão atualizadas com uma aparência moderna. As caixas de diálogo funcionarão da mesma maneira que no estilo anterior.

**Experiência anterior**

![interface antiga](./media/NewUI_Old_AttachFileHandler.jpg)

**Experiência moderna**

![interface moderna](./media/NewUI_Modern_AttachFileHandler.jpg)


### <a name="updates-to-the-device-details-page-on-the-company-portal-app-for-windows-10----1287448---"></a>Atualizações da página "Detalhes do Dispositivo" no aplicativo Portal da Empresa para Windows 10 <!---1287448--->

O aplicativo Portal da Empresa para Windows 10 está movendo a marca __Categoria__, que ficava abaixo do título, para que ela seja exibida como uma propriedade na página __Detalhes do Dispositivo__.

![A tela "Detalhes do Dispositivo" do aplicativo Portal da Empresa para Windows, que agora mostra o campo "Categorias" como uma propriedade em vez de diretamente abaixo do título dessa tela.](./media/cp_win10_category_tag_move_after_1708.png)

## <a name="july-2017"></a>Julho de 2017

### <a name="apps-details-pages-will-display-new-information-for-android-devices---1287476--"></a>As páginas de detalhes de aplicativos exibirão novas informações para dispositivos Android <!--1287476-->

A página de detalhes de aplicativos do aplicativo Portal da Empresa para Android agora exibirá as categorias de aplicativos que o administrador de TI tiver definido para esse aplicativo.

![A nova página de detalhes de aplicativos](./media/cp_android_appdetails_after_1708.png)

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Experiência de início de sessão aprimorada em aplicativos Portal da Empresa para todas as plataformas <!--User Story 1132123-->

Anunciamos uma alteração que entrará em vigor nos próximos meses, que visa melhorar a experiência de entrada para os aplicativos do Portal da Empresa do Intune para Android, iOS e Windows. A nova experiência do usuário será exibida automaticamente em todas as plataformas para o aplicativo Portal da Empresa quando o Azure AD fizer essa alteração. Além disso, agora os usuários poderão entrar no Portal da Empresa através de outro dispositivo, com um código gerado de uso único. Isso é especialmente útil nos casos em que os usuários precisam entrar sem credenciais.  

Abaixo, é possível ver a experiência de conexão anterior, a nova experiência de conexão com as credenciais e a nova experiência de conexão por meio de outro dispositivo.

__Experiência de início de sessão anterior__

![A página de credenciais do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site. O botão "Entrar" está embaixo. Um link na parte inferior leva às informações de Privacidade e Cookies da Microsoft.](./media/cp_ios_aad_signin_before_1704_001.png)

![Depois de tocar em Entrar, o usuário insere as credenciais nesta página, que solicita um email e uma senha de usuário e também oferece meios para resolver falhas de senha.](./media/cp_ios_aad_signin_before_1704_002.png)

![Depois de fornecer a senha, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_before_1704_003.png)

__Nova experiência de início de sessão__

![A página de entrada do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site. Abaixo está o botão "Entrar". Um link na parte inferior leva às informações de Privacidade e Cookies da Microsoft.](./media/cp_ios_aad_signin_after_1704_001.png)

![O usuário é solicitado a fornecer somente o endereço de email em vez do email e da senha na mesma tela.](./media/cp_ios_aad_signin_after_1704_002.png)

![É solicitada a senha do usuário, depois que seu endereço de email é aceito.](./media/cp_ios_aad_signin_after_1704_003.png)

![Depois de concluir o processo de autenticação, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Nova experiência de início de sessão ao entrar em outro dispositivo__

![A página de credenciais do Portal da Empresa, com um ícone de uma pessoa na frente de uma representação gráfica de um site. Abaixo está o botão "Entrar". Um link na parte inferior leva às informações de Privacidade e Cookies da Microsoft.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Toque no link __Entrar de outro dispositivo__.

![São fornecidas instruções para acessar a página aka.ms/devicelogin com uma senha exclusiva do seu computador de trabalho e, em seguida, usar o código para entrar.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Inicie um navegador e vá para [https://aka.ms/devicelogin](https://aka.ms/devicelogin).

![Uma imagem do navegador do usuário em seu computador de trabalho em vez de seu aplicativo Portal da Empresa. A página de "Logon do dispositivo" que é exibida, solicita aos usuários o código que receberam no aplicativo Portal da Empresa.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Insira o código que você viu no aplicativo Portal da Empresa. Ao selecionar __Continuar__, você será capaz de se autenticar usando qualquer método que tenha suporte pela sua empresa, como um cartão inteligente.

![O usuário inseriu o código exclusivo no campo, e o site de "Logon do dispositivo" pediu uma confirmação de que o Portal da Empresa do Intune era o aplicativo correto a receber autorização para entrar.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Uma página de confirmação, informando que o usuário entrou no aplicativo Portal da Empresa em seu dispositivo, e que essa página poderá ser fechada.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

O aplicativo Portal da Empresa começará a entrar.

![Depois de concluir o processo de autenticação, o aplicativo Portal da Empresa inicia a sessão, mostrando isso por meio de uma barra de carregamento.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="june-2017"></a>Junho de 2017

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies"></a>Agora o aplicativo Portal da Empresa para Android tem uma nova experiência de usuário final para as Políticas de Proteção do Aplicativo
Com base nos comentários dos clientes, modificamos o aplicativo de Portal da Empresa para Android mostrar um botão **Acessar Conteúdo da Empresa**. A intenção é impedir que os usuários finais passem pelo processo de registro desnecessariamente quando eles só precisam acessar os aplicativos que dão suporte às Políticas de Proteção de Aplicativo, um recurso de gerenciamento de aplicativos móveis do Intune.

O usuário deverá tocar no botão **Acessar Conteúdo da Empresa** em vez de iniciar o registro do dispositivo.

![Uma imagem do aplicativo de Portal da Empresa Android, que mostra em texto grande “Acessar Conteúdo da Empresa” no meio em vez de oferecer opções de registro imediatamente, como é o caso padrão](./media/and_access_company_content_after_1706.png)

O usuário é levado para o site de Portal da Empresa para autorizar o uso do aplicativo no dispositivo, no qual o site do Portal da Empresa verifica as credenciais.

![Uma imagem do site do Portal da Empresa, confirmando a credencial.](./media/and_iwp_sign_in_auth_page_after_1706.png)

O dispositivo ainda pode ser registrado no gerenciamento completo tocando no menu de **ação**.

![Uma imagem do aplicativo de Portal da Empresa para Android, mostrando o menu no canto superior direito da tela com uma opção para ainda registrar o dispositivo.](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!--676505-->

O aplicativo do Portal da Empresa para Windows 10 agora iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo em dispositivos com a Atualização do Windows 10 para Criadores (versão 1703). Isso reduzirá o problema de atraso das instalações de aplicativos durante o estado de "Sincronização Pendente". Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo.

![Uma imagem do aplicativo de Portal da Empresa do Windows 10, em que o download do Microsoft Word está em um estado pendente na loja de aplicativos do Portal da Empresa.](./media/w10_download_pending_after_1706.png)

![Uma imagem do aplicativo de Portal da Empresa do Windows 10, com o novo estado de sincronização automática mostrando com uma mensagem de status que indica que o dispositivo está sendo sincronizado e tentando baixar o aplicativo.](./media/w10_download_pending_syncing_after_1706.png)

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nova experiência orientada para o Portal da Empresa do Windows 10 <!---1058938--->
O aplicativo do Portal da Empresa para o Windows 10 incluirá uma experiência de passo a passo guiado do Intune para dispositivos que não foram identificados nem registrados. A nova experiência fornece instruções passo a passo que guiam o usuário pelo processo de inscrição no Azure Active Directory (exigido para recursos de Acesso Condicional) e inscrição de MDM (exigido para os recursos de gerenciamento de dispositivo). A experiência guiada estará acessível na home page do Portal da Empresa. Os usuários podem continuar a usar o aplicativo se não concluírem o registro e inscrição, mas enfrentarão uma funcionalidade limitada.

Esta atualização só é visível em dispositivos que executam a Atualização de Aniversário do Windows 10 (build 1607) ou superior.

![Uma imagem da página de aterrissagem do aplicativo de Portal da Empresa do Windows 10, com uma mensagem de status no meio da lista de “dispositivos”, que indica a um usuário que o dispositivo usado ainda não foi configurado para uso corporativo e que o usuário deve selecionar a mensagem para iniciar a configuração.](./media/win10_guided_enroll_select_setup_after_1706.png)

![Uma imagem da página de configuração do aplicativo de Portal da Empresa do Windows 10, que avisa ao usuário que ele precisa adicionar uma conta corporativa ao dispositivo para poder registrá-lo no gerenciamento.](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![Uma imagem do aplicativo Portal da Empresa do Windows 10 adiciona conta corporativa a esta página de dispositivo, que indica ao usuário que ele precisará acessar o aplicativo Configurações e selecionar “Conectar” para concluir o registro. Depois de fazer isso, a tela informa que será necessário retornar para o aplicativo de Portal da Empresa para concluir o registro.](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![Uma imagem da tela Registrar no gerenciamento do aplicativo de Portal da Empresa do Windows 10, que mostra uma mensagem de status concluído dizendo que o dispositivo do usuário agora está registrado e que o botão “Avançar” deve ser tocado para continuar.](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![Uma imagem da tela de conclusão do aplicativo de Portal da Empresa do Windows 10, informando ao usuário que está tudo pronto e que o dispositivo está registrado com uma conta corporativa devidamente adicionada.](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nova ação de menu para remover o Portal da Empresa com facilidade <!--1164569-->
De acordo com os comentários dos usuários, o aplicativo do Portal da Empresa para Android adicionou uma nova ação de menu para iniciar a remoção do Portal da Empresa por meio do dispositivo. Essa ação remove o dispositivo do gerenciamento do Intune, de forma que o aplicativo possa ser removido do dispositivo pelo usuário.

![Uma imagem do aplicativo do Portal da Empresa do Android, com o menu de ação aberto no canto superior direito. A nova opção “Remover o Portal da Empresa” está disponível como a terceira opção, sob “Meu perfil” e “Configurações” e acima de “Termos e condições”, “Ajuda e comentários” e “Sobre”.](./media/android_remove_cp_menu_action_after_1705.png)

![Uma imagem da caixa de diálogo de confirmação, que está disponível após a seleção da nova opção “Remover o Portal da Empresa” no menu de ação. A caixa de diálogo informa o usuário do seguinte: “Ao remover o Portal da Empresa, seu dispositivo não será mais gerenciado pelo administrador de TI e isso poderá remover o acesso a dados, aplicativos e email da empresa”. Em seguida, ela solicita ao usuário que confirme se deseja remover o aplicativo do Portal da Empresa com a seleção de “Sim”.](./media/android_remove_cp_menu_confirmation_after_1705.png)

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios---1230777--"></a>Melhorias nos blocos de aplicativo no aplicativo Portal da Empresa para iOS <!--1230777-->
Atualizamos o design dos blocos do aplicativo na home page para refletir a cor da identidade visual definida para o Portal da Empresa.

**Antes**

![Uma imagem do aplicativo do Portal da Empresa para iOS antes da atualização, que mostrava imagens de preenchimento predefinidas para “Todos os aplicativos”, “Aplicativos em destaque” e “Categorias”.](./media/cp_ios_homepage_before_1705.png)

**Depois**

![Uma imagem do aplicativo do Portal da Empresa para iOS após a atualização, que agora reflete a capacidade de selecionar as cores relevantes para sua organização.](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Seletor de conta agora disponível para o aplicativo do Portal da Empresa para iOS
Se os usuários usavam suas contas corporativas ou de estudante para entrar em outros aplicativos da Microsoft em seus dispositivos iOS, talvez eles vejam nosso novo seletor de conta ao entrar no Portal da Empresa pela primeira vez.

![Uma imagem do seletor de conta, que mostra um usuário de teste “Ricardo Santos” escolhendo entre um de seus dois endereços de email. Há um botão abaixo dos dois endereços que permite ao usuário entrar com outra conta.](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a>Abril de 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Novos ícones para o navegador gerenciado e o Portal da Empresa<!--918433, 918431-->

O navegador gerenciado está recebendo ícones atualizados para versões de Android e iOS do aplicativo. O novo ícone conterá o emblema Intune atualizado para torná-lo mais consistente com outros aplicativos no Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width="200" height="366" align="center">
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width="200" height="366" align="center">
           </td>
      </tr>
   </table>
</body>
</html>

O Portal da Empresa também está recebendo ícones atualizados para as versões do Windows, iOS e Android do aplicativo para aprimorar a consistência com outros aplicativos EM+S. Esses ícones serão liberados gradualmente em plataformas a partir de abril até o fim de maio.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Indicador de progresso de entrada no Portal da Empresa Android <!--953374-->

Uma atualização para o aplicativo de Portal da empresa Android mostra um indicador de progresso de conexão quando o usuário inicia ou reinicia o aplicativo. O indicador avança em novos status, começando com "Conectando …", então, "Entrando..." e "Verificando os requisitos de segurança..." antes de permitir que o usuário acesse o aplicativo.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign-in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width="200" height="366" align="center">
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign-in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width="200" height="366" align="center">
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign-in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width="200" height="366" align="center">
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Status de instalação do aplicativo aprimorado para o aplicativo de Portal da empresa do Windows 10 <!--676495-->
Agora, o aplicativo de Portal da Empresa do Windows 10 fornece uma barra de progresso da instalação na página de detalhes do aplicativo. Isso é compatível para aplicativos modernos em dispositivos que executam a Atualização de Aniversário do Windows 10 e versões posteriores.

__Antes__ ![Uma imagem da versão anterior da tela de carregamento, em que o status simplesmente mostrava “Instalando”.](./media/cp_win10_install_status_before_1704.png)

__Depois__ ![Uma imagem da versão atualizada da tela de carregamento, que agora exibe uma barra de progresso da instalação.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>Fevereiro de 2017

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Nova experiência do usuário para o aplicativo Portal da Empresa para Android <!--621622, announced 1702-->
A partir de março, o aplicativo de Portal da empresa para Android seguirá [as diretrizes de design de material](https://material.io/guidelines/material-design/introduction.html) para criar uma aparência mais moderna. Essa experiência do usuário aprimorada inclui:

* __Cores__: cabeçalhos de guia podem ser coloridos de acordo com sua paleta de cores personalizada.

![À esquerda, uma imagem do aplicativo Portal da Empresa para Android antes da atualização. À direita, uma imagem do aplicativo Portal da Empresa para Android após a atualização. As duas imagens mostram a guia Dispositivos como a guia selecionada entre as três guias disponíveis, Contato com o TI, Dispositivos e Aplicativos.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Interface__: os botões __Aplicativos em Destaque__ e __Todos os Aplicativos__ foram atualizados na guia __Aplicativos__. O botão __Pesquisa__ agora é um botão de ação flutuante.

![À esquerda, uma imagem do aplicativo Portal da Empresa para Android antes da atualização. À direita, uma imagem do aplicativo Portal da Empresa para Android após a atualização. As duas imagens mostram a guia Aplicativos como a guia selecionada entre as três guias disponíveis, Contatar TI, Dispositivos e Aplicativos.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Navegação__: Todos os Aplicativos mostra uma exibição com guias de __Em Destaque__, __Todos__ e __Categorias__ para facilitar a navegação. __Contatar TI__ foi otimizada para melhor legibilidade.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width="200" height="366" align="center">
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Janeiro de 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Modernizando o site Portal da Empresa <!--753980, announced 1701-->
A partir de fevereiro, o site Portal da Empresa oferecerá suporte a aplicativos destinados a usuários que não têm dispositivos gerenciados. O site será alinhado com outros produtos e serviços da Microsoft usando um novo esquema de cores contrastantes, ilustrações dinâmicas e um "menu hambúrguer", ![Imagem pequena do menu hambúrguer que foi adicionado no canto superior esquerdo do site do Portal da Empresa](./media/CP_hamburger_menu.png) que conterá detalhes de contato do suporte técnico e informações sobre dispositivos gerenciados existentes. A página de aterrissagem será reorganizada para enfatizar os aplicativos que estão disponíveis aos usuários, com carrosséis para aplicativos em destaque e atualizados recentemente.

![À esquerda, uma imagem da versão atual do site de Portal da Empresa com a versão anterior da exibição de Aplicativos, Meus Dispositivos e Destacados e Categorias. À direita, uma imagem da versão atualizada do site do Portal da Empresa com um carrossel de aplicativo atualizado, a lista de aplicativos publicados recentemente e uma exibição de Categorias atualizadas.](./media/CP_Website_BeforeAfter_Feb2016.png)

## <a name="coming-soon-in-the-ui"></a>Em breve na interface do usuário
Esses são os planos de aprimoramento da experiência do usuário por meio da atualização de nossa interface do usuário.

> [!Note]
> Observe que as imagens abaixo podem ser visualizações, e o produto anunciado pode ser diferente das versões apresentadas.

### <a name="ui-iwp"></a>Nova atualização de experiência do usuário para o site do Portal da Empresa <!--2000968-->

Estamos introduzindo uma nova experiência de site de Portal da Empresa em abril, com atualizações da interface do usuário, fluxos de trabalho simplificados e aprimoramentos de acessibilidade. Isso incluirá aprimoramentos voltados ao cliente como compartilhamento de aplicativos e melhor desempenho geral para levar a você uma experiência mais simples.

Adicionamos alguns recursos novos com base nos comentários de clientes como você, que aprimorarão significativamente a funcionalidade e a usabilidade existentes:

-   Aprimoramentos da interface do usuário em todo o site
-   Capacidade de compartilhar links diretos para aplicativos
- Melhor desempenho para grandes catálogos de aplicativos

Não é necessário tomar nenhuma medida para se preparar para essa mudança. Informaremos você quando o site atualizado do Portal da Empresa estiver disponível. No entanto, você pode eventualmente precisar atualizar os documentos do usuário final com capturas de tela atualizadas. Observe que talvez seja necessário, também, atualizar a documentação do aplicativo de Portal da Empresa no iOS, uma vez que o site habilita a seção **Aplicativos** do aplicativo iOS.

|Atualizado|Anterior|
|---|---|
|![A página de dispositivos atualizada mostra o dispositivo alinhado corretamente acima das informações do dispositivo, não mais aparecendo em cima da lista completa.](./media/iwp-device-after-1803.png)|![A versão anterior da página de dispositivos.](./media/iwp-device-before-1803.png)|
|![A página de instalação do aplicativo atualizada mostra o aplicativo exatamente em cima de uma descrição e de várias informações de instalação, incluindo data de publicação, versão e tipo de aplicativo.](./media/iwp-app-install-after-1803.png)|![A versão anterior da página de instalação do aplicativo.](./media/iwp-app-install-before-1803.png)|

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Atualizações da interface do usuário do site do Portal da Empresa <!--1313244 part 2-->

__Atualizações para os Aplicativos em Destaque__ Adicionamos uma página dedicada ao site em que os usuários podem procurar os aplicativos que você optou por destacar e fizemos algumas alterações na interface do usuário da seção Em destaque na home page.

![Os blocos coloridos que mostram os aplicativos. Eles são grandes quadrados coloridos abaixo de cada aplicativo, em que a cor é extraída da cor primária dentro do logotipo do aplicativo. A seção "Aplicativos em Destaque" aparece na parte superior do aplicativo do Portal da Empresa.](./media/cp_win10_colorful_tiles_after_1708.png)



### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/cloud-platform/roadmap)
* [Novidades do Intune](https://docs.microsoft.com/intune/whats-new)
