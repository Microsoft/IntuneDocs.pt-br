---
title: Logs de uso StageNow em dispositivos Android Zebra no Microsoft Intune – Azure | Microsoft Docs
description: Consulte os problemas comuns e resoluções ao usar StageNow em dispositivos Android com o Microsoft Intune. Saiba também como obter logs e ver exemplos de como ler os logs para o êxito ou erros.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36476820805c00cefafcd9f64dd2f08a014762c0
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490534"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Solucionar problemas e consulte os problemas potenciais em dispositivos Android Zebra no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

No Microsoft Intune, você pode usar [Zebra mobilidade extensões (MX) para gerenciar dispositivos Android Zebra](android-zebra-mx-overview.md). Ao usar dispositivos Zebra, criar perfis no StageNow para gerenciar as configurações e carregá-los ao Intune. O Intune usa o aplicativo StageNow para aplicar as configurações nos dispositivos. O aplicativo StageNow também cria um arquivo de log detalhado no dispositivo que é usado para solucionar problemas.

Esse recurso aplica-se a:

- Android

Por exemplo, você deve criar um perfil no StageNow para configurar um dispositivo. Quando você cria o perfil de StageNow, a última etapa gera um arquivo para testar o perfil. Você consome este arquivo com o aplicativo StageNow no dispositivo.

Em outro exemplo, você deve cria um perfil no StageNow e testá-lo. No Intune, adicionar o perfil StageNow e, em seguida, atribuí-lo para seus dispositivos Zebra. Ao verificar o status do perfil atribuído, o perfil mostra um status de alto nível.

Em ambos os casos, você pode obter mais detalhes do arquivo de log StageNow, que é salvo no dispositivo, sempre que um perfil de StageNow se aplica.

Alguns problemas não são relacionados ao conteúdo do perfil StageNow e não são refletidos nos logs.

Este artigo mostra como ler os logs de StageNow e lista alguns possíveis problemas com dispositivos de Zebra que podem não ser refletidos nos logs.

[Use e gerencie dispositivos Zebra com extensões de mobilidade Zebra](android-zebra-mx-overview.md) tem mais informações sobre esse recurso.

## <a name="get-the-logs"></a>Obter os logs

### <a name="use-the-stagenow-app-on-the-device"></a>Usar o aplicativo de StageNow no dispositivo
Quando você testa um perfil usando o StageNow diretamente em seu computador, em vez de usar [Intune para implantar o perfil](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), o aplicativo StageNow no dispositivo salva os logs do teste. Para obter o arquivo de log, use o **mais (...)**  opção no aplicativo StageNow no dispositivo.

### <a name="get-logs-using-android-debug-bridge"></a>Obter logs usando o Android Debug Bridge
Para obter os logs depois que o perfil já foi implantado com o Intune, conecte o dispositivo a um computador com [Android Debug Bridge (adb)](https://developer.android.com/studio/command-line/adb) (abre o site de web do Android).

No dispositivo, os logs são salvos em `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Obter os logs do email
Para obter os logs depois que o perfil já foi implantado com o Intune, os usuários finais podem enviar por email logs usando um aplicativo de email no dispositivo. No dispositivo Zebra, abra o aplicativo de Portal da empresa, e [enviar os logs](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). Usando o recurso de logs de envio também cria um PowerLift incidentes ID, que você pode fazer referência se entrar em contato com o suporte da Microsoft.

## <a name="read-the-logs"></a>Ler os logs

Ao examinar os logs, há um erro sempre que você vê o `<characteristic-error>` marca. Detalhes do erro são gravados para o `<parm-error>` marca > `desc` propriedade.

## <a name="error-types"></a>Tipos de erros

Dispositivos zebra incluem diferentes níveis de relatório de erros:

- Não há suporte para o CSP no dispositivo. Por exemplo, o dispositivo não é um dispositivo de rede celular e não tem um Gerenciador de celular.
- A versão MX ou do OSX é incompatível. Cada CSP tem controle de versão. Para obter uma matriz de suporte completo, consulte [documentação da Zebra](http://techdocs.zebra.com/mx/) (abre o site de web da Zebra).
- O dispositivo reporta a outro problema ou erro.

## <a name="examples"></a>Exemplos

Por exemplo, você tem o seguinte perfil de entrada:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

No log, o XML é idêntico à entrada. Essa saída correspondente significa que o perfil aplicado com êxito para o dispositivo sem erros:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock" version="6.0">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

Outro exemplo, você tem a seguinte entrada:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2" >
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic type="AppMgr" version="4.2" >
        <parm name="Action" value="Install"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic>
</wap-provisioningdoc>
```

O log mostra um erro, pois ele contém um `<characteristic-error>` marca. Nesse cenário, o perfil tentou instalar um pacote Android (APK) que não existe no caminho fornecido:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2">
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic-error type="AppMgr" version="5.1" desc="missing">
        <parm-error name="Action" value="Install" desc="apk doesnot exist in the path"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic-error>
</wap-provisioningdoc>
```

## <a name="other-potential-issues-with-zebra-devices"></a>Outros possíveis problemas com dispositivos Zebra

Esta seção lista outros possíveis problemas que você pode ver ao usar dispositivos Zebra com o administrador do dispositivo. Esses problemas não são relatados nos logs de StageNow.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView está desatualizado

Quando dispositivos mais antigos entram usando o aplicativo de Portal da empresa, os usuários poderão ver uma mensagem informando que o componente System WebView está desatualizado e precisa atualizado. Se o dispositivo tiver o Google Play instalado, conecte-se à internet e verifique se há atualizações. Se o dispositivo não tiver instalado do Google Play, obter a versão atualizada do componente e aplicá-lo para os dispositivos. Ou então, atualize para o dispositivo mais recente do sistema operacional emitido pelo Zebra.

### <a name="management-actions-take-a-long-time"></a>Ações de gerenciamento levar muito tempo

Se os serviços do Google Play não estiverem disponíveis, algumas tarefas levar até 8 horas para ser concluída. [Aplicativo de Portal da empresa limitações do Intune para Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (abre outro site da web) pode ser um bom recurso.

### <a name="device-spoofing-suspected-shows-in-intune"></a>"Dispositivo falsificação suspeito" é mostrado no Intune

Esse erro significa que o Intune suspeita de que um dispositivo não - Zebra Android está relatando seu modelo e fabricante como um dispositivo Zebra.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Aplicativo de Portal da empresa é anterior à versão mínima necessária

Intune pode atualizar a versão mínima necessária do aplicativo de Portal da empresa. Se o Google Play não estiver instalado no dispositivo, o aplicativo de Portal da empresa não é atualizado automaticamente. Se a versão mínima necessária é mais recente do que a versão instalada, o aplicativo Portal da empresa para de funcionar. Atualização para o aplicativo Portal da empresa mais recente usando [sideload em dispositivos Zebra](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Próximas etapas

[Quadros de discussão zebra](https://developer.zebra.com/community/home/discussions) (abre o site de web da Zebra)

[Use e gerencie dispositivos Zebra com extensões de mobilidade Zebra no Intune](android-zebra-mx-overview.md)
