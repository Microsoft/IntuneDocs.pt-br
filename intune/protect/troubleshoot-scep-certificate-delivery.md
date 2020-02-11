---
title: Solucionar problemas de entrega de certificados para dispositivos ao usar o SCEP com o Microsoft Intune | Microsoft Docs
description: Solucione problemas de entrega de um certificado para um dispositivo da AC ao usar perfis de certificado SCEP com o Intune para implantar certificados.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77be59d126dc7e73bee468ca938938c6bb1b2e1a
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915870"
---
# <a name="troubleshoot-the-delivery-of-certificates-provisioned-by-scep-to-devices-in-microsoft-intune"></a>Solucione problemas de entrega de certificados provisionados pelo SCEP para dispositivos no Microsoft Intune

Use as informações neste artigo para ajudar a investigar a entrega de certificados para dispositivos ao usar o protocolo SCEP para provisionar certificados no Intune. Depois que o servidor NDES (Serviço de Registro de Dispositivo de Rede) recebe da Autoridade de Certificação (CA) o certificado solicitado para um dispositivo, ele passa esse certificado de volta para o dispositivo.

Este artigo se aplica à etapa 5 do [fluxo de trabalho de comunicação do SCEP](troubleshoot-scep-certificate-profiles.md); a entrega do certificado para o dispositivo que enviou a solicitação de certificado.

## <a name="review-the-certification-authority"></a>Examinar a autoridade de certificação

Quando a autoridade de certificação emitir o certificado, você verá uma entrada semelhante ao exemplo a seguir na autoridade de certificação:

![Exemplo de certificados emitidos](../protect/media/troubleshoot-scep-certificate-delivery/certificate-authority.png)

## <a name="review-the-device"></a>Examinar o dispositivo

### <a name="android"></a>Android

Em dispositivos registrados no administrador do dispositivo, você verá uma notificação semelhante à imagem a seguir, que solicita que você instale o certificado:

![Notificação do Android](../protect/media/troubleshoot-scep-certificate-delivery/android-notification.png)

Para o Android Enterprise ou o Samsung Knox, a instalação do certificado é automática e silenciosa.

Para exibir um certificado instalado no Android, use um aplicativo de exibição de certificado de terceiros.

Também é possível examinar o [log do OMADM dos dispositivos](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Procure entradas semelhantes com a seguinte, que são registradas ao instalar o certificados:

**Certificado raiz**:

```
2018-02-27T04:50:52.1890000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        9    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALL_REQUESTED
2018-02-27T04:53:31.1300000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        0    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T04:53:32.0390000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595       14    Root cert '17…' state changed from CERT_INSTALLING to CERT_INSTALL_SUCCESS
```

**Certificado provisionado por meio do SCEP**

```
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    There are 1 requests
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    Trying to enroll certificate request: ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787
2018-02-27T05:16:20.6150000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:20.6530000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:21.7460000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.7890000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:28.0340000    VERB    Event     org.jscep.transaction.EnrollmentTransaction    18327       10    Response: org.jscep.message.CertRep@3150777b[failInfo=<null>,pkiStatus=SUCCESS,recipientNonce=Nonce [GUID],messageData=org.spongycastle.cms.CMSSignedData@27cc8998,messageType=CERT_REP,senderNonce=Nonce [GUID],transId=TRANSID]
2018-02-27T05:16:28.2440000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       10    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ENROLLED to CERT_INSTALL_REQUESTED
2018-02-27T05:18:44.9820000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327        0    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T05:18:45.3460000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       14    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALLING to CERT_ACCESS_REQUESTED
2018-02-27T05:20:15.3520000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       21    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ACCESS_REQUESTED to CERT_ACCESS_GRANTED
```

### <a name="ios-and-ipados"></a>iOS e iPadOS

No dispositivo iOS ou iPadOS, você pode exibir o certificado no Perfil de Gerenciamento de Dispositivo. Faça drill-in para ver os detalhes dos certificados instalados.

![Certificado do iOS](../protect/media/troubleshoot-scep-certificate-delivery/ios-certificate.png)

Você também pode encontrar entradas parecidas com as seguintes no [log de depuração do iOS](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices):

```
Debug 18:30:53.691033 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\  
Debug 18:30:54.640644 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
Debug 18:30:55.487908 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQG 
Debug 18:30:57.285730 -0500 profiled Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295 in domain ManagedProfileToManagingProfile to system\ 
Default 18:30:57.320616 -0500 profiled Profile \'93www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295\'94 installed.\ 
```

### <a name="windows"></a>Windows

No dispositivo Windows, verifique se o certificado foi entregue:

- Execute **eventvwr.msc** para abrir o Visualizador de Eventos. Acesse **Logs do Aplicativo e Serviços** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Admin** e procure pelo **Evento 39**. Esse Evento deve ter uma descrição geral de: **SCEP: Certificado instalado com êxito.**

   ![O Evento 39 no log do Aplicativo do Windows](../protect/media/troubleshoot-scep-certificate-delivery/device-app-log.png)

Para exibir o certificado no dispositivo, execute **certmgr.msc** para abrir os Certificados do MMC e verifique se os certificados raiz e SCEP estão instalados corretamente no repositório pessoal do dispositivo:

   1. Acesse **Certificados (Computador local)**  > **Autoridades de Certificação Raiz Confiáveis** > **Certificados** e verifique se o certificado raiz de sua Autoridade de Certificação está presente. Os valores *Emitido Para* e *Emitido Por* serão os mesmos.
   2. Nos Certificados do MMC, acesse **Certificados – Usuário Atual** > **Pessoal** > **Certificados** e verifique se o certificado solicitado está presente, sendo o nome em *Emitido Por* igual ao nome da autoridade de certificação.

## <a name="troubleshoot-failures"></a>Solucionar problemas de falhas

### <a name="android"></a>Android

Para solucionar problemas dessa etapa, examine os erros registrados no log do OMA DM.

### <a name="ios-and-ipados"></a>iOS e iPadOS

Para solucionar problemas dessa etapa, examine os erros registrados no log de depuração de dispositivos.

### <a name="windows"></a>Windows

Para solucionar problemas caso o certificado não esteja instalado no dispositivo, procure erros que sugiram problemas no log de Eventos do Windows:

- No dispositivo, abra **eventvwr.msc** para abrir o Visualizador de Eventos e acesse **Logs de Aplicativos e Serviços** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider** > **Admin**.

Os erros com entrega e instalação do certificado para o dispositivo normalmente estão relacionados às operações do Windows e não do Intune.

## <a name="next-steps"></a>Próximas etapas

Se o certificado for implantado com êxito no dispositivo, mas o Intune não relatar êxito, confira os [Relatórios do NDES para o Intune](troubleshoot-scep-certificate-reporting.md) para solucionar problemas de relatórios.
