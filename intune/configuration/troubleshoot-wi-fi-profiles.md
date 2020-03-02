---
title: Solucionar problemas e examinar logs de perfil de dispositivos Wi-Fi no Microsoft Intune – Azure | Microsoft Docs
description: Compreenda e solucione problemas de perfil de configuração de dispositivos Wi-Fi nos dispositivos Android, iOS/iPadOS e Windows no Microsoft Intune. Examine os logs e veja alguns problemas comuns e suas possíveis resoluções.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: db663f96f1e4fe84c506395b98c52956069e5426
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512816"
---
# <a name="troubleshoot-wi-fi-device-configuration-profiles-in-microsoft-intune"></a>Solucionar problemas de perfis de configuração de dispositivos Wi-Fi no Microsoft Intune

No Intune, é possível criar perfis de configuração de dispositivo que incluem configurações de conexão para sua rede WiFi. Use essas configurações para conectar os dispositivos Android, iOS/iPadOS e Windows dos usuários à rede da organização.

Este artigo mostra como o perfil Wi-Fi será exibido quando aplicado aos dispositivos. Ele também inclui informações de log, problemas comuns e muito mais. Confira este artigo para saber como solucionar problemas com seus perfis Wi-Fi.

Para obter mais informações sobre perfis Wi-Fi no Intune, confira [Adicionar e usar as configurações de Wi-Fi em seus dispositivos ](wi-fi-settings-configure.md).

## <a name="before-you-begin"></a>Antes de começar

Os exemplos deste artigo usam autenticação de certificado SCEP para os perfis do Intune. Também pressupõe-se que os perfis de raiz confiável e SCEP funcionem corretamente no dispositivo.

## <a name="android"></a>Android

Nesta seção, mostramos a experiência do usuário final ao instalar os perfis de configuração em um dispositivo Android.

### <a name="end-user-experience-example"></a>Exemplo de experiência do usuário final

Neste cenário, usaremos o dispositivo Nokia 6.1. Antes de o perfil Wi-Fi ser instalado no dispositivo, instale os perfis de raiz confiável e SCEP.

1. Os usuários finais recebem uma notificação para instalar o perfil de certificado raiz confiável:

    > [!div class="mx-imgBorder"]
    > ![Exemplo de notificação do aplicativo do Portal da Empresa no Android para instalar o perfil de certificado raiz confiável](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-trusted-root.png)

2. A próxima notificação solicita a instalação do perfil de certificado SCEP:

    > [!div class="mx-imgBorder"]
    > ![Exemplo de notificação do aplicativo do Portal da Empresa no Android para instalar o perfil de certificado SCEP](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-scep-certificate.png)

    > [!TIP]
    > Ao usar um dispositivo Android gerenciado pelo administrador do dispositivo, é possível que existam vários certificados listados. Quando um perfil de certificado é revogado ou removido, o certificado permanece no dispositivo. Nesse cenário, selecione o certificado mais recente. Em geral, ele é o último certificado exibido na lista.
    >
    > Essa situação não ocorre nos dispositivos Android Enterprise e Samsung Knox. Para obter mais informações, confira [Gerenciar dispositivos de perfil de trabalho Android](../enrollment/android-enterprise-overview.md) e [Remover os certificados SCEP e PKCS ](../protect/remove-certificates.md#android-knox-devices).

3. Em seguida, os usuários recebem uma notificação para instalar o perfil Wi-Fi:

    > [!div class="mx-imgBorder"]
    > ![Exemplo de notificação do aplicativo do Portal da Empresa no Android para instalar o perfil de certificado SCEP](./media/troubleshoot-wi-fi-profiles/android-end-user-install-wifi-profile.png)

4. Quando concluída, a conexão Wi-Fi é mostrada como uma rede salva:

    > [!div class="mx-imgBorder"]
    > ![A conexão Wi-Fi é exibida como uma rede salva](./media/troubleshoot-wi-fi-profiles/android-end-user-saved-networks.png)

### <a name="review-company-portal-app-logs"></a>Examine os logs do aplicativo no Portal da Empresa

No Android, o arquivo **Omadmlog.log** detalha as atividades do perfil Wi-Fi quando ele é instalado no dispositivo. Você pode ter até cinco arquivos de log do Omadmlog. Lembre-se de obter o registro de data e hora da última sincronização porque isso ajudará você a encontrar as entradas de log relacionadas.

No exemplo a seguir, use o [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace) para ler os logs e procure por "wifimgr":

> [!div class="mx-imgBorder"]
> ![A conexão Wi-Fi é exibida como uma rede salva](./media/troubleshoot-wi-fi-profiles/android-cmtrace-filter-wifimgr.png)

O registro a seguir mostra os resultados da pesquisa e o perfil Wi-Fi aplicado com sucesso:

```log
2019-08-01T19:22:46.7340000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.7490000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:46.8100000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:46.8209999    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.8240000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected ca certificate with alias: 'user:205xxxxx.0' and thumbprint '<thumbprint>'.
2019-08-01T19:22:47.0990000    VERB    com.microsoft.omadm.platforms.android.certmgr.CertificateChainBuilder    15118    04142    Complete certificate chain built with Complete certs.
2019-08-01T19:22:47.1010000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    1 cert(s) matched criteria: User<ID>[i:<ID>,17CECEA1D337FAA7D167AD83A8CC7A8FCBF9xxxx;eku:1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2]
2019-08-01T19:22:47.1090000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    0 cert(s) excluded by criteria:
2019-08-01T19:22:47.1110000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected client cert with alias 'User<ID>' and requestId 'ModelName=<ModelName>%2FLogicalName_<LogicalName>;Hash=-912418295'.
2019-08-01T19:22:47.4120000    VERB    com.microsoft.omadm.Services    15118    04142    Successfully applied, enabled and saved wifi profile '<profile ID>'
2019-08-01T19:22:47.4240000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.4910000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.4970000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5080000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.5820000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.5900000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5910000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04142    Applied profile <profile ID>

```

## <a name="iosipados"></a>iOS/iPadOS

Depois que o perfil Wi-Fi é instalado no dispositivo, ele é mostrado no **Perfil de Gerenciamento**:

> [!div class="mx-imgBorder"]
> ![Perfil de gerenciamento no dispositivo iOS/iPadOS no Intune](./media/troubleshoot-wi-fi-profiles/ios-management-profile.png)

> [!div class="mx-imgBorder"]
> ![A conexão Wi-Fi é exibida como uma rede Wi-Fi no dispositivo iOS/iPadOS no Intune](./media/troubleshoot-wi-fi-profiles/ios-wifi-connection-in-management-profile.png)

### <a name="review-the-iosipados-console-and-device-logs"></a>Examinar os logs do console e do dispositivo iOS/iPadOS

Em dispositivos iOS/iPadOS, o log do aplicativo do Portal da Empresa não inclui informações sobre perfis Wi-Fi. Para ver os detalhes da instalação dos seus perfis Wi-Fi, use os registros do console/dispositivo:

1. Conecte o dispositivo iOS/iPadOS ao Mac. Vá para **Aplicativos** > **Utilitários** e abra o aplicativo do Console.
2. Em **Ação**, selecione **Incluir Mensagens Informativas** e **Incluir Mensagens de Depuração**:

    > [!div class="mx-imgBorder"]
    > ![Incluir Mensagens Informativas e Incluir Mensagens de Depuração no aplicativo de console do iOS/iPadOS](./media/troubleshoot-wi-fi-profiles/ios-console-app-include-info-messages-debug-messages.png)

3. Reproduza o cenário e salve os logs em um arquivo de texto:

    1. Selecione todas as mensagens na tela atual: **Editar** > **Selecionar Tudo**.
    2. Copie as mensagens: **Editar** > **Copiar**.
    3. Cole os dados do log em um editor de texto e salve o arquivo.

4. Pesquise o arquivo de log salvo para ver informações detalhadas. Quando o perfil tiver sido instalado, sua saída será semelhante ao seguinte log:

    ```log
    Line 390870: debug    11:19:58.994815 -0400    profiled    Adding dependent www.windowsintune.com.wifi.Contoso to parent Microsoft.Profiles.MDM in domain ManagingProfileToManagedProfile to system\
    Line 390872: debug    11:19:58.995210 -0400    profiled    Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.wifi.Contoso in domain ManagedProfileToManagingProfile to system\
    Line 392346: default    11:19:59.360460 -0400    profiled    Profile \'93www.windowsintune.com.wifi.Contoso\'94 installed.\
    ```

## <a name="windows"></a>Windows

Depois que o perfil Wi-Fi estiver instalado no dispositivo, vá para **Configurações** > **Contas** > **Acessar conta corporativa ou de estudante**. Selecione sua conta> **Informações**:

> [!div class="mx-imgBorder"]
> ![Acesse sua conta corporativa e de estudante e selecione Informações no dispositivo Windows](./media/troubleshoot-wi-fi-profiles/windows-access-work-school-info.png)

Em **Áreas gerenciadas pela Microsoft**, o **Wi-Fi** é mostrado:

> [!div class="mx-imgBorder"]
> ![Nas áreas gerenciadas pela Microsoft. Verifique se o Wi-Fi está listado no Windows](./media/troubleshoot-wi-fi-profiles/windows-wifi-areas-managed-by-microsoft.png)

Para ver a conexão Wi-Fi, vá para **Configurações** > **Rede e Internet**  > **Wi-Fi**:

> [!div class="mx-imgBorder"]
> ![No Windows, veja a conexão Wi-Fi como uma rede conhecida nas configurações](./media/troubleshoot-wi-fi-profiles/windows-wifi-connection-known-networks.png)

### <a name="review-event-viewer-logs"></a>Examine os logs do visualizador de eventos

Nos dispositivos Windows, os detalhes sobre os perfis Wi-Fi são registrados no Visualizador de Eventos:

1. Abra o aplicativo **Visualizador de Eventos**.
2. No menu de **Exibir**, selecione **Mostrar Logs Analíticos e de Depuração**.
3. Expanda os menus de **Logs de Aplicativos e Serviços** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Administrador**

Sua saída deve se assemelhar aos seguintes logs:

```log
Log Name:      Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
Source:        Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider
Date:          8/7/2019 8:01:41 PM
Event ID:      1506
Task Category: (1)
Level:         Information
Keywords:      (2)
User:          SYSTEM
Computer:      <Computer Name>
Description:
WiFiConfigurationServiceProvider: Node set value, type: (0x4), Result: (The operation completed successfully.).
```

## <a name="common-issues"></a>Problemas comuns

### <a name="issue-1-the-wi-fi-profile-isnt-deployed-to-the-device"></a>Problema 1: O perfil Wi-Fi não está implantado no dispositivo

- Confirme se o perfil Wi-Fi foi atribuído ao grupo correto:

    1. No [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **Perfis de configuração**.
    2. Selecione seu perfil > **Atribuições**. Verifique se os grupos selecionados estão corretos.
    3. No Gerenciador de Ponto de Extremidade, selecione **Solução de problemas + Suporte**. Revise as informações das **Atribuições**.

- No Gerenciador de Ponto de Extremidade, selecione **Solução de problemas + Suporte**. Confirme se o dispositivo pode sincronizar com o Intune verificando o campo **Última verificação em**.

- Se o perfil Wi-Fi estiver vinculado aos perfis raiz confiável e SCEP, confirme se ambos estão implantados no dispositivo. O perfil Wi-Fi depende desses perfis.

- No Windows 10 e dispositivos mais recentes, revise o log de Informações de diagnóstico do MDM:

  1. Acesse **Configurações** > **Contas** > **Acessar conta corporativa ou de estudante**.
  2. Selecione sua conta corporativa ou de estudante > **Informações**.
  3. Na parte inferior da página de **Configurações**, selecione **Criar relatório**.
  4. Uma janela é exibida, mostrando o caminho para os arquivos de log. Selecione **Exportar**.
  5. Acesse o caminho `\Users\Public\Documents\MDMDiagnostics` e analise o relatório:

      > [!div class="mx-imgBorder"]
      > ![Amostra de informações de diagnóstico do MDM que mostra a configuração do perfil WiFi nos dispositivos Windows 10](./media/troubleshoot-wi-fi-profiles/windows-mdm-diagnostic-info.png)

  > [!TIP]
  > Para obter mais informações, confira [Diagnosticar falhas do MDM no Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).

- Nos dispositivos Android, se os perfis raiz confiável e SCEP não estiverem instalados no dispositivo, você verá a seguinte entrada no arquivo Omadmlog do aplicativo do Portal da Empresa:

  ``` log
  2019-08-01T19:18:13.5120000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04105    Skipping Wifi profile <profile ID> because it is pending certificates.
  ```

  - se os perfis raiz confiável e SCEP estiverem no dispositivo Android e forem compatíveis, o perfil Wi-Fi poderá não estar no dispositivo. Esse problema ocorre quando o provedor **CertificateSelector** do aplicativo do Portal da Empresa não encontra um certificado que corresponda aos critérios especificados. Os critérios específicos podem estar no modelo de certificado ou no perfil do SCEP.

    Se o certificado correspondente não for encontrado, os certificados no dispositivo não serão instalados. O perfil Wi-Fi não será aplicado por não possuir o certificado correto. Nesse cenário, você verá a seguinte entrada no arquivo Omadmlog do aplicativo do Portal da Empresa:

    ` Skipping Wifi profile <profile ID> because it is pending certificates.`

    O exemplo de log a seguir mostra certificados sendo excluídos porque os critérios de EKU (uso avançado de chave) **Qualquer finalidade** foram especificados. Mas os certificados atribuídos ao dispositivo não possuem esse EKU:

    ```log
    2018-11-27T21:10:37.6390000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID1> and requestId <requestID1> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID2> and requestId <requestID2> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    0 cert(s) matched criteria:
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    2 cert(s) excluded by criteria:
    2018-11-27T21:10:37.6400000    INFO       com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager       14210                00948     Skipping Wifi profile <profile ID> because it is pending certificates.
    ```

    A amostra a seguir mostra o perfil do SCEP inserido no EKU **Qualquer Finalidade**. No entanto, ele não é inserido no modelo de certificado na autoridade de certificação (CA). Para corrigir o problema, adicione a opção **Qualquer Finalidade** ao modelo de certificado. Ou remova a opção **Qualquer Finalidade** do perfil SCEP.

    > [!div class="mx-imgBorder"]
    > ![No Android, adicione Qualquer Finalidade ao modelo de certificado na autoridade de certificação](./media/troubleshoot-wi-fi-profiles/android-add-any-purpose-eku.png)

    > [!div class="mx-imgBorder"]
    > ![No Android, adicione Qualquer Finalidade ao perfil de configuração do certificado SCEP no Intune](./media/troubleshoot-wi-fi-profiles/android-any-purpose-scep-device-config-profile.png)

  - Confirme se todos os certificados necessários na cadeia de certificados completa estão no dispositivo Android. Caso contrário, o perfil Wi-Fi não pode ser instalado no dispositivo. Para obter mais informações, confira [Autoridade de certificação intermediária ausente](https://developer.android.com/training/articles/security-ssl#MissingCa) (abre o site do Android).
  - Filtre o Omadmlog com palavras-chave para procurar informações, como qual certificado é usado no perfil Wi-Fi e se o perfil foi aplicado.

    Por exemplo, use [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace) para ler os logs. Use a cadeia de caracteres de pesquisa para filtrar “wifimgr”:

    > [!div class="mx-imgBorder"]
    > ![Filtre o CMTrace para procurar perfis de configuração WiFiMgr em dispositivos Android](./media/troubleshoot-wi-fi-profiles/cmtrace-filter-wifimgr.png)

    O resultado é semelhante ao log a seguir:

    > [!div class="mx-imgBorder"]
    > ![Exemplo de saída de log do CMTrace que mostra o perfil de configuração de Wi-Fi do Intune aplicado nos dispositivos](./media/troubleshoot-wi-fi-profiles/cmtrace-sample-log-output.png)

    Se você vir um erro no log, copie o registro de data e hora do erro e filtre o log. Em seguida, use a opção "localizar" com o carimbo de data e hora para ver o que aconteceu logo antes do erro.

### <a name="issue-2-the-wi-fi-profile-is-deployed-to-the-device-but-the-device-cant-connect-to-the-network"></a>Problema 2: O perfil Wi-Fi será implantado no dispositivo, mas o dispositivo não poderá se conectar à rede

Normalmente, esse problema é causado por algo fora do Intune. As tarefas a seguir podem ajudá-lo a entender e solucionar problemas de conectividade:

- Conecte-se manualmente à rede, usando um certificado com os mesmos critérios do perfil Wi-Fi.

  Se não conseguir se conectar, abra as propriedades do certificado na conexão manual. Em seguida, atualize o perfil Wi-Fi do Intune com as mesmas propriedades de certificado.
- Os erros de conectividade geralmente são registrados no log do servidor Radius. Por exemplo, ele deve mostrar se o dispositivo tentou se conectar ao perfil Wi-Fi.

## <a name="need-more-help"></a>Precisa de mais ajuda?

- Use os [Fóruns de usuários do Intune](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc) ou [receba suporte da Microsoft](../fundamentals/get-support.md).

- Para obter mais informações sobre perfis Wi-Fi no Microsoft Intune, confira os seguintes artigos:

  - Adicione configurações Wi-Fi a dispositivos com [Android](wi-fi-settings-android.md), [iOS/iPadOS](wi-fi-settings-ios.md) e [Windows 10 e posterior](wi-fi-settings-windows.md).
  - [Dica de suporte: como configurar implantações de certificado NDES para SCEP no Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-How-to-configure-NDES-for-SCEP-certificate/ba-p/455125)
  - Solucione problemas com a [Implantação do perfil de certificado SCEP](https://support.microsoft.com/help/4526725/troubleshooting-scep-profile-deployment-to-android-devices-in-intune) e a [Configuração do NDES](https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune).

- Para obter as últimas notícias, informações e dicas técnicas, confira os blogs oficiais:
  - [Blog da equipe de suporte do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
  - [Blog de segurança e mobilidade corporativa da Microsoft](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/bg-p/enterprisemobilityandsecurity)

## <a name="next-steps"></a>Próximas etapas

[Monitore seus perfis](device-profile-monitor.md).
