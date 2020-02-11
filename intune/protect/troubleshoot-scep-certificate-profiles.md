---
title: Solucionar problemas de uso de perfis de certificado SCEP para provisionar certificados com Microsoft Intune | Microsoft Docs
description: Solucionar problemas com o uso do SCEP por dispositivos para solicitar certificados para uso com o Intune, incluindo a comunicação dos dispositivos com o NDES, NDES para autoridades de certificação e do Intune Certificate Connector para o serviço do Intune.
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
ms.openlocfilehash: ae7ffe5a8c20aa7edd67853ff86ef9e28cf2d175
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915818"
---
# <a name="overview-for-troubleshooting-scep-certificate-profiles-with-microsoft-intune"></a>Visão geral da solução de problemas do perfil de certificado SCEP no Microsoft Intune

O uso de perfis de certificados SCEP (protocolo SCEP) pode ser desafiador ao solucionar problemas no Intune. Este artigo é uma visão geral que pode ajudá-lo a resolver problemas:

- Explicar a arquitetura e o fluxo de comunicação do processo SCEP
- Ajudar você a restringir onde existe um problema no fluxo de comunicação
- Identificar os arquivos de log de chaves que são referenciados nos artigos subsequentes para solucionar problemas de perfis de certificado

As informações contidas neste e nos artigos relacionados de solução de problemas de certificado SCEP se aplicam ao uso de perfis de certificado SCEP com dispositivos Android, iOS/iPad e Windows. As informações relativas ao macOS não estão disponíveis no momento.

Para solucionar problemas do NDES (serviço de registro de dispositivo de rede), confira os seguintes artigos em support.microsoft.com:

- [Verificar a configuração do NDES local para certificados SCEP no Intune](https://support.microsoft.com/help/4490130/ndes-configuration-on-premises-for-scep-certificates-in-intune)
- [Solucionando problemas na configuração do NDES para uso com perfis de certificado do Microsoft Intune]( https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune)

Antes de continuar, verifique se você atende aos [pré-requisitos para usar perfis de certificado SCEP](certificates-scep-configure.md#prerequisites-for-using-scep-for-certificates), incluindo a implantação de um certificado raiz por meio de um perfil de certificado confiável.

## <a name="scep-communication-flow-overview"></a>Visão geral do fluxo de comunicação do SCEP

O gráfico a seguir demonstra uma visão geral básica do processo de comunicação do SCEP no Intune.

![Fluxo do perfil de certificado SCEP](../protect/media/troubleshoot-scep-certificate-profiles/scep-certificate-profile-flow.png)

1. [Implantar um perfil de certificado SCEP](troubleshoot-scep-certificate-profile-deployment.md). O Intune gera uma cadeia de caracteres de desafio, que exige um usuário específico e a finalidade e o tipo de certificado.

2. [Comunicação do dispositivo para servidor NDES](troubleshoot-scep-certificate-device-to-ndes.md). O dispositivo usa o URI para o NDES do perfil entrar em contato com o servidor NDES para que ele possa apresentar um desafio.

3. [Comunicação do NDES com o módulo de política](troubleshoot-scep-certificate-ndes-policy-module.md). O NDES encaminha o desafio para o módulo de política do Intune Certificate Connector no servidor, que valida a solicitação.

4. [NDES com a autoridade de certificação](troubleshoot-scep-certificate-ndes-policy-module.md). O NDES aprova as solicitações válidas para emitir um certificado para a Autoridade de Certificação (CA).

5. [Entrega de certificado para o dispositivo](troubleshoot-scep-certificate-delivery.md). O certificado é entregue ao dispositivo.

6. [Relatório de implantação no Intune](troubleshoot-scep-certificate-reporting.md). O Intune Certificate Connector informa o evento de emissão de certificado para o Intune.

## <a name="log-files"></a>Arquivos de log

Para identificar problemas no fluxo de trabalho de provisionamento de comunicação e certificado, examine os arquivos de log da infraestrutura do servidor e dos dispositivos. As seções posteriores da solução de problemas de perfis de certificado SCEP referem-se aos arquivos de log comentados nesta seção.

- [Logs de infraestrutura e de servidor](#logs-for-on-premises-infrastructure)

Os logs de dispositivo dependem da plataforma do dispositivo:  

- [iOS e iPadOS](#logs-for-ios-and-ipados-devices)
- [Android](#logs-for-android-devices)
- [Windows](#logs-for-windows-devices)

### <a name="logs-for-on-premises-infrastructure"></a>Logs da infraestrutura local
  
A infraestrutura local que dá suporte ao uso de perfis de certificado SCEP para implantações de certificado inclui o Microsoft Intune Certificate Connector, o NDES que é executado em um Windows Server e a autoridade de certificação.

Os arquivos de log para essas funções incluem o Visualizador de Eventos do Windows, os consoles de certificado e vários arquivos de log específicos do Intune Certificate Connector, NDES ou outras funções e operações que fazem parte da infraestrutura local.

A lista a seguir inclui logs ou consoles que são mencionados nos artigos subsequentes de solução de problemas do SCEP. 

- **NDESConnector_date_time.svclog**:

  Esse log mostra a comunicação do Microsoft Intune Certificate Connector com o serviço de nuvem do Intune. Você pode usar a [Ferramenta Visualizador de Rastreamento de Serviço](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) para visualizar este arquivo de log.

  Chave do Registro relacionada: *HKLM\SW\Microsoft\MicrosoftIntune\NDESConnector\ConnectionStatus*

  Localização: no servidor que hospeda o NDES em *%program_files%\Microsoft intune\ndesconnectorsvc\logs\logs*

- **CertificateRegistrationPoint_date_time.svclog**:

  Esse log mostra o módulo de política NDES que recebe e verifica as solicitações de certificado. Você pode usar a [Ferramenta Visualizador de Rastreamento de Serviço](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) para visualizar este arquivo de log.

  Localização: no servidor que hospeda o NDES em *%program_files%\Microsoft intune\ndesconnectorsvc\logs\logs*

- **NDESPlugin.log**:

  Esse log mostra a passagem de solicitações de certificado para o Ponto de Registro de Certificado, e a verificação resultante dessas solicitações.

  Localização: no servidor que hospeda o NDES em *%program_files%\Microsoft Intune\NDESPolicyModule\logs*

- **Logs do IIS**:

  Os logs do IIS mostram as solicitações de certificado de dispositivos móveis entrando no NDES.

  Localização: no servidor que hospeda o NDES em *c:\inetpub\logs\LogFiles\W3SVC1*

- **Log de aplicativos do Windows**:

  Esse log é útil ao investigar problemas do IIS, como o pool de aplicativos SCEP.

  Localização: no servidor que hospeda o NDES: Execute **eventvwr.msc** para abrir o Visualizador de Eventos do Windows




### <a name="logs-for-android-devices"></a>Logs para dispositivos Android

Para dispositivos que executam o Android, use o arquivo de log do aplicativo **OMADM.log** no **Portal da Empresa Android**. Antes de coletar e examinar os logs, certifique-se de que [Log detalhado](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md) está habilitado e, em seguida, reproduza o problema.

Para coletar os OMADM.logs de um dispositivo, confira [Carregar e enviar logs por email usando um cabo USB](/intune-user-help/send-logs-to-your-it-admin-using-cable-android.md).

Você também pode verificar [Carregar e enviar logs por email](/intune-user-help/send-logs-to-your-it-admin-by-email-android.md#upload-and-email-logs-from-microsoft-intune-app).

### <a name="logs-for-ios-and-ipados-devices"></a>Logs para dispositivos iOS e iPadOS

Para dispositivos que executam o iOS ou iPadOS, use os logs de depuração e **Xcode** executado em um computador Mac:

1. Conecte o dispositivo iOS ao Mac e acesse **Aplicativos** > **Utilitários** para abrir o aplicativo de Console. 

2. Em **Ação**, selecione **Incluir Mensagens Informativas** e **Incluir Mensagens de Depuração**.

   ![Selecionar as opções de log](../protect/media/troubleshoot-scep-certificate-profiles/message-options.png)

3. Reproduza o problema e salve os logs em um arquivo de texto:
   1. Escolha **Editar** > **Selecionar todas** para selecionar todas as mensagens na tela atual e selecione **Editar** > **Copiar** para copiar as mensagens para a área de transferência. 
   2. Abra o aplicativo TextEdit, cole os logs copiados em um novo arquivo de texto e salve o arquivo.


O log de Portal da Empresa para dispositivos iOS e iPadOS não contém informações sobre os perfis de certificado SCEP.

### <a name="logs-for-windows-devices"></a>Logs para dispositivos Windows

Para dispositivos que executam o Windows, use os Logs de eventos do Windows para diagnosticar problemas de gerenciamento de dispositivos ou de registros em dispositivos gerenciados com o Intune.

No dispositivo, abra **Visualizador de Eventos** > **Logs de aplicativos e serviços** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider**

![Logs de eventos do Windows](../protect/media/troubleshoot-scep-certificate-profiles/windows-event-log.png)

## <a name="next-steps"></a>Próximas etapas

Examinar [implantação de perfis de certificado SCEP](troubleshoot-scep-certificate-profile-deployment.md) 
