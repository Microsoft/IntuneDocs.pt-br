---
title: Solução de problemas com o registro de dispositivos iOS/iPadOS no Microsoft Intune
titleSuffix: Microsoft Intune
description: Sugestões para solucionar alguns dos problemas mais comuns ao registrar dispositivos iOS/iPadOS no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a29fab4be6e2046b2c6757505001a7ba3455b8d6
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514312"
---
# <a name="troubleshoot-iosipados-device-enrollment-problems-in-microsoft-intune"></a>Solucionar problemas com o registro de dispositivos iOS/iPadOS no Microsoft Intune

Este artigo ajuda os Administradores do Intune a entender e solucionar problemas ao registrar dispositivos iOS/iPadOS no Intune.

## <a name="prerequisites"></a>Pré-requisitos

Antes de dar início à solução de problemas, é importante reunir algumas informações básicas. Essas informações podem ajudar você a entender melhor o problema e reduzir o tempo necessário para encontrar uma resolução.

Colete as seguintes informações sobre o problema:

- Qual é a mensagem de erro exata?
- Onde você vê a mensagem de erro?
- Quando o problema começou? O registro funcionou em algum momento?
- Qual plataforma (Android, iOS/iPadOS, Windows) apresenta o problema?
- Quantos usuários são afetados? Todos os usuários foram afetados ou apenas alguns deles?
- Quantos dispositivos foram afetados? Todos os dispositivos foram afetados ou apenas alguns deles?
- Qual é a autoridade de MDM?
- Como o registro está sendo realizado? Você está usando BYOD ("Traga seu próprio dispositivo") ou o DEP (Programa de registro de dispositivos) da Apple com perfis de registro?

## <a name="error-messages"></a>Mensagens de erro

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>Falha na instalação do perfil. Ocorreu um erro de rede.

**Causa:** há um problema não especificado com o iOS/iPadOS no dispositivo.

#### <a name="resolution"></a>Resolução

1. Para evitar a perda de dados nas próximas etapas (restaurar o iOS/iPadOS exclui todos os dados do dispositivo), não deixe de fazer backup dos dados.
2. Coloque o dispositivo no modo de recuperação e restaure-o. Configure-o como um novo dispositivo. Para obter mais informações sobre como restaurar dispositivos iOS/iPadOS, confira [https://support.apple.com/HT201263](https://support.apple.com/HT201263).
3. Registrar o dispositivo novamente.

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>Falha na instalação do perfil. Não foi possível estabelecer conexão com o servidor.

**Causa:** seu locatário do Intune está configurado para permitir somente dispositivos de propriedade corporativa. 

#### <a name="resolution"></a>Resolução
1. Entre no Portal do Azure.
2. Selecione **Mais serviços**, pesquise por Intune e, em seguida, selecione **Intune**.
3. Selecione **Registro de dispositivos** > **Restrições de registro**.
4. Em **Restrições do Tipo de Dispositivo**, selecione a restrição que deseja configurar > **Propriedades** > **Selecionar plataformas** > selecione **Permitir** para **iOS** e, em seguida, clique em **OK**.
5. Selecione **Configurar plataformas**, selecione **Permitir** para dispositivos iOS/iPadOS de propriedade pessoal e, em seguida, clique em **OK**.
6. Registrar o dispositivo novamente.

**Causa:** os registros CNAME necessários no DNS não existem.

#### <a name="resolution"></a>Resolução
Crie registros de recursos DNS CNAME para o domínio de sua empresa. Por exemplo, se o domínio da sua empresa for contoso.com, crie um CNAME no DNS que redirecione EnterpriseEnrollment.contoso.com para EnterpriseEnrollment-s.manage.microsoft.com.

Embora a criação de entradas de DNS de CNAME seja opcional, os registros CNAME facilitam o registro para os usuários. Se não for possível encontrar nenhum registro CNAME no registro, os usuários deverão inserir manualmente o nome do servidor MDM enrollment.manage.microsoft.com.

Se houver mais de um domínio verificado, crie um registro CNAME para cada domínio. Os registros de recursos de CNAME deve conter as seguintes informações:

|TYPE|Nome do host|Aponta para|TTL|
|------|------|------|------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com|1h|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1h|

Se sua empresa usa vários domínios para credenciais de usuário, crie registros CNAME para cada domínio.

> [!NOTE]
> As alterações nos registros DNS podem levar até 72 horas para serem propagadas. Não é possível verificar a alteração do DNS no Intune até que o registro de DNS seja propagado.

**Causa:** você registrou um dispositivo que já foi registrado com uma conta de usuário diferente e o usuário anterior não foi removido adequadamente do Intune.

#### <a name="resolution"></a>Resolução
1. Cancele qualquer instalação do perfil atual.
2. Abra [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) no Safari.
3. Registrar o dispositivo novamente.

> [!NOTE]
> Se o registro continuar falhando, remova os cookies no Safari (não bloqueie-os) e registre o dispositivo novamente.

**Causa:** o dispositivo já está registrado com outro provedor de MDM.

#### <a name="resolution"></a>Resolução
1. Abra as **Configurações** no dispositivo iOS/iPadOS, vá para **Geral > Gerenciamento de Dispositivo**.
2. Remova qualquer perfil de gerenciamento existente.
3. Registrar o dispositivo novamente.

**Causa:** o usuário que está tentando registrar o dispositivo não tem uma licença do Microsoft Intune.

#### <a name="resolution"></a>Resolução
1. Vá para o [Centro de Administração do Office 365](https://portal.office.com/adminportal/home#/homepage) e, em seguida, escolha **Usuários > Usuários Ativos**.
2. Selecione a conta do usuário à qual você deseja atribuir uma licença de usuário do Intune e, em seguida, selecione **Licenças de produto > Editar**.
3. Coloque o botão de alternância na posição **Ativado** para a licença que deseja atribuir ao usuário e, em seguida, escolha **Salvar**.
4. Registrar o dispositivo novamente.

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Este Serviço não tem suporte. Nenhuma política de registro.

**Causa**: não há um Apple MDM Push Certificate configurado no Intune ou o certificado é inválido. 

#### <a name="resolution"></a>Resolução

- Se o MDM Push Certificate não estiver configurado, siga as etapas em [Obter um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate).
- Se o MDM Push Certificate for inválido, siga as etapas em [Renovar um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>Portal da empresa temporariamente indisponível. O aplicativo Portal da Empresa apresentou um problema. Se o problema persistir, contate o administrador do sistema.

**Causa:** o aplicativo Portal da Empresa está desatualizado ou corrompido.

#### <a name="resolution"></a>Resolução
1. Remova o aplicativo de Portal da Empresa do dispositivo.
2. Baixar e instalar o aplicativo **Portal da Empresa do Microsoft Intune** da **Loja de aplicativos**.
3. Registrar o dispositivo novamente.
 > [!NOTE]
    > Esse erro também poderá ocorrer se o usuário estiver tentando registrar mais dispositivos do que o registro do dispositivo está configurado para permitir. Siga as etapas de resolução na seção **Limite do dispositivo atingido** a seguir se essas etapas não resolverem o problema.

### <a name="device-cap-reached"></a>Limite do dispositivo atingido

**Causa:** o usuário tentou registrar mais dispositivos do que o limite de registro do dispositivo.

#### <a name="resolution"></a>Resolução
1. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **Todos os Dispositivos** e verifique o número de dispositivos que o usuário registrou.
    > [!NOTE]
    > Você também precisa ter o logon do usuário afetado no [Portal do usuário do Intune](https://portal.manage.microsoft.com/) para verificar os dispositivos registrados. É possível que alguns dispositivos apareçam no [Portal do usuário do Intune](https://portal.manage.microsoft.com/), mas não no [Portal de administração do Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview), e esses dispositivos também são contabilizados para o limite de registro do dispositivo.
2. No [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **Restrições de registro** e verifique o limite de registro do dispositivo. Por padrão, o limite é definido como 15. 
3. Se o limite de dispositivos registrados tiver sido atingido, remova os dispositivos desnecessários ou aumente o limite. Como cada dispositivo registrado consome uma licença do Intune, recomendamos que você sempre remova os dispositivos desnecessários primeiro.
4. Registrar o dispositivo novamente.

### <a name="workplace-join-failed"></a>Falha no Workplace Join

**Causa:** o aplicativo Portal da Empresa está desatualizado ou corrompido.  

#### <a name="resolution"></a>Resolução
1. Remova o aplicativo de Portal da Empresa do dispositivo.
2. Baixar e instalar o aplicativo **Portal da Empresa do Microsoft Intune** da **Loja de aplicativos**.
3. Registrar o dispositivo novamente.

### <a name="user-license-type-invalid"></a>Tipo de licença de usuário inválido

**Causa:** o usuário que está tentando registrar o dispositivo não tem uma licença válida do Intune.

#### <a name="resolution"></a>Resolução
1. Vá para o [Centro de Administração do Microsoft 365](https://portal.office.com/adminportal/home#/homepage) e, em seguida, escolha **Usuários** > **Usuários Ativos**.
2. Selecione a conta de usuário afetada > **Licenças do produto** > **Editar**.
3. Verifique se uma licença válida do Intune está atribuída ao usuário.
4. Registrar o dispositivo novamente.

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>Nome de Usuário Não Reconhecido. Esta conta de usuário não está autorizada a usar o Microsoft Intune. Entre em contato com o administrador do sistema se você considera que recebeu a mensagem por engano.

**Causa:** o usuário que está tentando registrar o dispositivo não tem uma licença válida do Intune.

1. Vá para o [Centro de Administração do Microsoft 365](https://portal.office.com/adminportal/home#/homepage) e, em seguida, escolha **Usuários** > **Usuários Ativos**.
2. Selecione a conta de usuário afetada e, em seguida, escolha **Licenças do produto** > **Editar**.
3. Verifique se uma licença válida do Intune está atribuída ao usuário.
4. Registrar o dispositivo novamente.

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>Falha na instalação do perfil. O novo conteúdo de MDM não corresponde ao conteúdo antigo.

**Causa:** um perfil de gerenciamento já está instalado no dispositivo.

#### <a name="resolution"></a>Resolução

1. Abra as **Configurações** no dispositivo iOS/iPadOS > **Geral** > **Gerenciamento de Dispositivo**.
2. Toque no perfil de gerenciamento existente e toque em **Remover Gerenciamento**.
3. Registrar o dispositivo novamente.

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Causa:** o certificado do APNs (Apple Push Notification Service) está ausente, é inválido ou expirou.

#### <a name="resolution"></a>Resolução
Verifique se um certificado APNs válido foi adicionado ao Intune. Para obter mais informações, confira [Configurar o registro do iOS/iPadOS](ios-enroll.md).

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Causa:** há um problema com o certificado APNs (Apple Push Notification Service) configurado no Intune.

#### <a name="resolution"></a>Resolução
Renove o certificado APNs e registre o dispositivo novamente.

> [!IMPORTANT]
> Não deixe de renovar o certificado APNs. Não substitua o certificado APNs. Se substituir o certificado, você precisará registrar novamente todos os dispositivos iOS/iPadOS no Intune. 

- Para renovar o certificado APNs no Intune autônomo, confira [Renovar Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).
- Para renovar o certificado APNs no Office 365, confira [Criar um Certificado APNs para dispositivos iOS/iPadOS](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7).

### <a name="xpc_type_error-connection-invalid"></a>XPC_TYPE_ERROR Conexão inválida

Quando você ativa um dispositivo gerenciado pelo DEP ao qual foi atribuído um perfil de registro, o registro falha e você recebe a seguinte mensagem de erro:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Causa:** há um problema de conexão entre o dispositivo e o serviço do DEP da Apple.

#### <a name="resolution"></a>Resolução
Corrija o problema de conexão ou use outra conexão de rede para registrar o dispositivo. Talvez você também precise entrar em contato com a Apple se o problema persistir.


## <a name="other-issues"></a>Outros problemas

### <a name="dep-enrollment-doesnt-start"></a>O registro do DEP não é iniciado
Quando você ativa um dispositivo gerenciado pelo DEP ao qual foi atribuído um perfil de registro, o processo de registro do Intune não é iniciado.

**Causa:** o perfil de registro foi criado antes que o token do DEP fosse carregado no Intune.

#### <a name="resolution"></a>Resolução

1. Edite o perfil de registro. Você pode fazer qualquer alteração no perfil. A finalidade é atualizar a hora de modificação do perfil.
2. Sincronizar dispositivos gerenciados por DEP: no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **iOS** > **Registro do iOS** > **Tokens do programa de registro** > escolha um token > **Sincronizar agora**. Uma solicitação de sincronização é enviada à Apple.

### <a name="dep-enrollment-stuck-at-user-login"></a>Registro do DEP paralisado no logon do usuário
Quando você ativa um dispositivo gerenciado pelo DEP ao qual foi atribuído um perfil de registro, a configuração inicial fica paralisada após você inserir as credenciais.

**Causa:** a MFA (autenticação multifator) está habilitada. Atualmente, a MFA não funciona durante o registro em dispositivos do DEP.

#### <a name="resolution"></a>Resolução
Desabilite a MFA e registre o dispositivo novamente.


## <a name="next-steps"></a>Próximas etapas

- [Solucionar problemas de registro de dispositivo no Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Faça uma pergunta no fórum do Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Confira o blog da equipe de suporte do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Confira o blog de segurança e mobilidade corporativa da Microsoft](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
