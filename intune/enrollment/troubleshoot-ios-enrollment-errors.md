---
title: Solucionando problemas de registro de dispositivo iOS no Microsoft Intune
titleSuffix: Microsoft Intune
description: Sugestões para solucionar alguns dos problemas mais comuns ao registrar dispositivos iOS no Intune.
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
ms.openlocfilehash: 9bca046302b221b934d0802c0bf637aced2cec3f
ms.sourcegitcommit: 2506cdbfccefd42587a76f14ee50c3849dad1708
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885928"
---
# <a name="troubleshoot-ios-device-enrollment-problems-in-microsoft-intune"></a>Solucionar problemas de registro de dispositivo iOS no Microsoft Intune

Este artigo ajuda os administradores do Intune a entender e solucionar problemas ao registrar dispositivos iOS no Intune.

## <a name="prerequisites"></a>Pré-requisitos

Antes de iniciar a solução de problemas, é importante coletar algumas informações básicas. Essas informações podem ajudá-lo a entender melhor o problema e reduzir o tempo para encontrar uma resolução.

Colete as seguintes informações sobre o problema:

- Qual é a mensagem de erro exata?
- Onde você vê a mensagem de erro?
- Quando o problema começou? O registro já funcionou?
- Qual plataforma (Android, iOS, Windows) tem o problema?
- Quantos usuários são afetados? Todos os usuários foram afetados ou apenas alguns?
- Quantos dispositivos são afetados? Todos os dispositivos foram afetados ou apenas alguns?
- O que é a autoridade de MDM?
- Como o registro está sendo executado? Ele é "Traga seu próprio dispositivo" (BYOD) ou DEP (Programa de registro de dispositivos da Apple) com perfis de registro?

## <a name="error-messages"></a>Mensagens de erro

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>Falha na instalação do perfil. Ocorreu um erro de rede.

**Causa:** Há um problema não especificado com o iOS no dispositivo.

#### <a name="resolution"></a>Resolução

1. Para evitar a perda de dados nas etapas a seguir (a restauração do iOS exclui todos os dados no dispositivo), certifique-se de fazer backup dos dados.
2. Coloque o dispositivo no modo de recuperação e restaure-o. Certifique-se de configurá-lo como um novo dispositivo. Para obter mais informações sobre como restaurar dispositivos iOS, consulte [https://support.apple.com/HT201263](https://support.apple.com/HT201263).
3. Registrar o dispositivo novamente.

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>Falha na instalação do perfil. Não foi possível estabelecer conexão com o servidor.

**Causa:** Seu locatário do Intune está configurado para permitir somente dispositivos de propriedade corporativa. 

#### <a name="resolution"></a>Resolução
1. Entre no Portal do Azure.
2. Selecione **Mais serviços**, pesquise por Intune e, em seguida, selecione **Intune**.
3. Selecione **Registro de dispositivos** > **Restrições de registro**.
4. Em **restrições de tipo de dispositivo**, selecione a restrição que você deseja definir > **Propriedades** > **Selecionar plataformas** > selecione **permitir** para **Ios**e clique em **OK**.
5. Selecione **Configurar plataformas**, selecione **permitir** dispositivos IOS de propriedade pessoal e clique em **OK**.
6. Registrar o dispositivo novamente.

**Causa:** Os registros CNAME necessários no DNS não existem.

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

**Causa:** Você registra um dispositivo que foi registrado anteriormente com uma conta de usuário diferente e o usuário anterior não foi removido adequadamente do Intune.

#### <a name="resolution"></a>Resolução
1. Cancele qualquer instalação de perfil atual.
2. Abra [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) no Safari.
3. Registrar o dispositivo novamente.

> [!NOTE]
> Se o registro ainda falhar, remova os cookies no Safari (não bloqueie cookies) e registre o dispositivo novamente.

**Causa:** O dispositivo já está registrado com outro provedor de MDM.

#### <a name="resolution"></a>Resolução
1. Abra **configurações** no dispositivo IOS, vá para **geral > gerenciamento de dispositivo**.
2. Remova qualquer perfil de gerenciamento existente.
3. Registrar o dispositivo novamente.

**Causa:** O usuário que está tentando registrar o dispositivo não tem uma licença de Microsoft Intune.

#### <a name="resolution"></a>Resolução
1. Vá para o [centro de administração do Office 365](https://portal.office.com/adminportal/home#/homepage)e escolha **usuários > usuários ativos**.
2. Selecione a conta do usuário à qual você deseja atribuir uma licença de usuário do Intune e, em seguida, selecione **Licenças de produto > Editar**.
3. Alterne a alternância para a posição **ligado** da licença que você deseja atribuir a esse usuário e, em seguida, escolha **salvar**.
4. Registrar o dispositivo novamente.

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Este Serviço não tem suporte. Nenhuma política de registro.

**Causa**: um certificado de push de MDM da Apple não está configurado no Intune ou o certificado é inválido. 

#### <a name="resolution"></a>Resolução

- Se o MDM Push Certificate não estiver configurado, siga as etapas em [obter um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate).
- Se o MDM Push Certificate for inválido, siga as etapas em [renovar Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>Portal da empresa temporariamente indisponível. O aplicativo Portal da Empresa encontrou um problema. Se o problema persistir, contate o administrador do sistema.

**Causa:** O aplicativo Portal da Empresa está desatualizado ou corrompido.

#### <a name="resolution"></a>Resolução
1. Remova o aplicativo de Portal da Empresa do dispositivo.
2. Baixar e instalar o aplicativo **Portal da Empresa do Microsoft Intune** da **Loja de aplicativos**.
3. Registrar o dispositivo novamente.
 > [!NOTE]
    > Esse erro também pode ocorrer se o usuário estiver tentando registrar mais dispositivos do que o registro do dispositivo está configurado para permitir. Siga as etapas de resoluções para o **limite do dispositivo** que foi atingido abaixo se essas etapas não resolverem o problema.

### <a name="device-cap-reached"></a>Limite do dispositivo atingido

**Causa:** O usuário tenta registrar mais dispositivos do que o limite de registro do dispositivo.

#### <a name="resolution"></a>Resolução
1. No [centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **dispositivos** > **todos os dispositivos**e verifique o número de dispositivos que o usuário registrou.
    > [!NOTE]
    > Você também deve ter o logon do usuário afetado no [portal do usuário do Intune](https://portal.manage.microsoft.com/) e verificar os dispositivos que foram registrados. Pode haver dispositivos que aparecem no portal do [usuário do Intune](https://portal.manage.microsoft.com/) , mas não no [portal de administração do Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview), tais dispositivos também contam para o limite de registro do dispositivo.
2. No [centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **dispositivos** > **restrições de registro** > verificar o limite de registro do dispositivo. Por padrão, o limite é definido como 15. 
3. Se o número de dispositivos registrados tiver atingido o limite, remova os dispositivos desnecessários ou aumente o limite de registro do dispositivo. Como cada dispositivo registrado consome uma licença do Intune, recomendamos que você sempre remova dispositivos desnecessários primeiro.
4. Registrar o dispositivo novamente.

### <a name="workplace-join-failed"></a>Falha na Workplace Join

**Causa:** O aplicativo Portal da Empresa está desatualizado ou corrompido.  

#### <a name="resolution"></a>Resolução
1. Remova o aplicativo de Portal da Empresa do dispositivo.
2. Baixar e instalar o aplicativo **Portal da Empresa do Microsoft Intune** da **Loja de aplicativos**.
3. Registrar o dispositivo novamente.

### <a name="user-license-type-invalid"></a>Tipo de licença de usuário inválido

**Causa:** O usuário que está tentando registrar o dispositivo não tem uma licença do Intune válida.

#### <a name="resolution"></a>Resolução
1. Vá para o [centro de administração do Microsoft 365](https://portal.office.com/adminportal/home#/homepage)e, em seguida, escolha **usuários** > **usuários ativos**.
2. Selecione a conta de usuário afetada > **licenças de produto** > **Editar**.
3. Verifique se uma licença válida do Intune está atribuída a este usuário.
4. Registrar o dispositivo novamente.

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>Nome de Usuário Não Reconhecido. Esta conta de usuário não está autorizada a usar Microsoft Intune. Contate o administrador do sistema se você considerar que recebeu esta mensagem por erro.

**Causa:** O usuário que está tentando registrar o dispositivo não tem uma licença do Intune válida.

1. Vá para o [centro de administração do Microsoft 365](https://portal.office.com/adminportal/home#/homepage)e, em seguida, escolha **usuários** > **usuários ativos**.
2. Selecione a conta de usuário afetada e escolha **licenças de produto** > **Editar**.
3. Verifique se uma licença válida do Intune está atribuída a este usuário.
4. Registrar o dispositivo novamente.

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>Falha na instalação do perfil. A nova carga de MDM não corresponde à carga antiga.

**Causa:** Um perfil de gerenciamento já está instalado no dispositivo.

#### <a name="resolution"></a>Resolução

1. Abra **as configurações** no dispositivo IOS > **geral** > **Gerenciamento de dispositivos**.
2. Toque no perfil de gerenciamento existente e toque em **remover gerenciamento**.
3. Registrar o dispositivo novamente.

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Causa:** O certificado do Apple Push Notification Service (APNs) está ausente, inválido ou expirou.

#### <a name="resolution"></a>Resolução
Verifique se um certificado APNs válido foi adicionado ao Intune. Para obter mais informações, consulte [Configurar o registro do IOS](ios-enroll.md).

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Causa:** Há um problema com o certificado APNs (Apple Push Notification Service) configurado no Intune.

#### <a name="resolution"></a>Resolução
Renove o certificado APNs e registre novamente o dispositivo.

> [!IMPORTANT]
> Certifique-se de renovar o certificado APNs. Não substitua o certificado APNs. Se você substituir o certificado, será necessário registrar novamente todos os dispositivos iOS no Intune. 

- Para renovar o certificado APNs no Intune autônomo, consulte [renovar Apple MDM Push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).
- Para renovar o certificado APNs no Office 365, consulte [criar um certificado APNs para dispositivos IOS](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7).

### <a name="xpc_type_error-connection-invalid"></a>XPC_TYPE_ERROR conexão inválida

Quando você ativa um dispositivo gerenciado por DEP que recebe um perfil de registro, o registro falha e você recebe a seguinte mensagem de erro:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Causa:** Há um problema de conexão entre o dispositivo e o serviço de DEP da Apple.

#### <a name="resolution"></a>Resolução
Corrija o problema de conexão ou use uma conexão de rede diferente para registrar o dispositivo. Talvez você também precise entrar em contato com a Apple se o problema persistir.


## <a name="other-issues"></a>Outros problemas

### <a name="dep-enrollment-doesnt-start"></a>O registro de DEP não é iniciado
Quando você ativa um dispositivo gerenciado por DEP que recebe um perfil de registro, o processo de registro do Intune não é iniciado.

**Causa:** O perfil de registro é criado antes do token de DEP ser carregado no Intune.

#### <a name="resolution"></a>Resolução

1. Edite o perfil de registro. Você pode fazer qualquer alteração no perfil. A finalidade é atualizar a hora de modificação do perfil.
2. Sincronizar dispositivos gerenciados por DEP: no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **iOS** > **Registro do iOS** > **Tokens do programa de registro** > escolha um token > **Sincronizar agora**. Uma solicitação de sincronização é enviada à Apple.

### <a name="dep-enrollment-stuck-at-user-login"></a>Registro de DEP travado no logon do usuário
Quando você ativa um dispositivo gerenciado por DEP que recebe um perfil de registro, a instalação inicial se une depois que você insere as credenciais.

**Causa:** A autenticação multifator (MFA) está habilitada. Atualmente, o MFA não funciona durante o registro em dispositivos DEP.

#### <a name="resolution"></a>Resolução
Desabilite o MFA e registre novamente o dispositivo.

## <a name="next-steps"></a>Próximas etapas

- [Solucionar problemas de registro de dispositivo no Intune](../troubleshoot-device-enrollment-in-intune.md)
- [Faça uma pergunta no fórum do Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Confira o blog da equipe de suporte do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Confira o blog de segurança e mobilidade corporativa da Microsoft](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
