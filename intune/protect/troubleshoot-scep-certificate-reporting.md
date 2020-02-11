---
title: Solucionar problemas de relatórios de implantação de certificado com êxito em dispositivos ao usar o SCEP com Microsoft Intune | Microsoft Docs
description: Solucione problemas de relatórios pelo NDES e pelo conector do Intune sobre uma implantação bem-sucedida de certificados que foram provisionados com perfis de certificado SCEP.
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
ms.openlocfilehash: 2ccc738626efc140efca46d1b997164ed36dd37f
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76916013"
---
# <a name="troubleshoot-ndes-reporting-of-certificate-deployments-in-microsoft-intune"></a>Solucionar problemas de relatórios de NDES de implantações de certificado no Microsoft Intune

Use as informações a seguir para confirmar se o NDES e o Microsoft Intune Certificate Connector reportam com êxito ao Intune que o certificado foi entregue a um dispositivo. O relatório para o Intune é a última fase para usar perfis de certificado SCEP para provisionar dispositivos Windows com um certificado.

Este artigo se aplica à etapa 6 do [fluxo de trabalho de comunicação do SCEP](troubleshoot-scep-certificate-profiles.md).

## <a name="review-for-signs-of-successful-reporting"></a>Examinar os sinais de relatórios bem-sucedidos

Se o relatório foi bem-sucedido, você encontrará entradas que se assemelham aos seguintes exemplos no servidor de NDES:

- **Logs do IIS**:

  `fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/Notify - 443 - fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 204 0 0 277 62`

- **NDESPlugin.log**:

  ```
  Calling Notifyrequest ...
  Sending request to certificate registration point.
  Exiting Notify with 0x0
  ```

- **CertificateRegistrationPoint.svclog**:

  ![Log do Intune Certificate Connector](../protect/media/troubleshoot-scep-certificate-reporting/certificate-registration-point-log.png)

- **NDESConnector.svclog**:

  ![Log do Intune Certificate Connector](../protect/media/troubleshoot-scep-certificate-reporting/ndesconnector-log.png)

- **CertificateRequestStatus**:

  Vá para a pasta *%ProgramFiles%\Microsoft Intune\CertificateRequestStatus* na qual você verá as pastas **Falhou**, **Processando** e **Êxito** que contêm os arquivos de status de solicitação de certificado.

  Se a solicitação de certificado for processada com êxito, você verá novos arquivos na pasta **Êxito**. Você pode usar o *Notepad.exe* para abrir os arquivos e exibir os dados que são carregados no serviço do Intune pelo Intune Certificate Connector. Os dados carregados incluem detalhes como **CertificateSerialNumber**, **UserID**, **DeviceID** e **Thumbprint**.

### <a name="troubleshoot-stuck-files"></a>Solucionar problemas de arquivos travados

Se você não vir os novos arquivos sendo criados na pasta *Êxito*, verifique se há arquivos presos na pasta *Processando*.

Verifique se o Intune Connector Service foi iniciado no servidor NDES e se não há erros em Ndesconnector.svclog.

## <a name="next-steps"></a>Próximas etapas

[Como obter suporte para o Microsoft Intune](../fundamentals/get-support.md)
