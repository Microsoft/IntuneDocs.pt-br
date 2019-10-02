---
title: Solução de problemas do Microsoft Intune Certificate Connector e de IDs de eventos | Microsoft Docs
description: Solucione problemas do Microsoft Intune Certificate Connector examinando IDs e descrições de eventos e examine os códigos de diagnóstico do serviço Intune Connector.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 682d51269798dff181a3bd8384268da862118a70
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721754"
---
# <a name="intune-certificate-connector-events-and-diagnostic-codes"></a>Eventos e códigos de diagnóstico do Intune Certificate Connector

Da versão 6.1806.x.x em diante, o Serviço do Conector do Intune registra em log os eventos no **Visualizador de Eventos** (**Logs de Aplicativos e Serviços** > **Conector do Microsoft Intune**). Use esses eventos para ajudar a solucionar possíveis problemas na configuração do Intune Connector. Esses eventos registram em log êxitos e falhas de uma operação, e também contêm códigos de diagnósticos com mensagens para ajudar o administrador de TI a solucionar problemas.

> [!TIP]  
> Para solucionar problemas e verificar a instalação do Intune Connector, confira [Amostras de script da autoridade de certificação](https://aka.ms/intuneconnectorverificationscript).

## <a name="event-ids-and-descriptions"></a>IDs e descrições de eventos

| ID do evento      | Nome do Evento    | Descrição do Evento | Códigos de Diagnósticos Relacionados |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Serviço do conector iniciado | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Serviço do conector parado | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Certificado de registro do conector renovado com êxito | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Falha na renovação do certificado de registro do conector. Reinstale o conector. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Falha ao recuperar o certificado de registro do conector do Registro. Examine os detalhes do evento para a impressão digital do certificado relacionada a esse evento. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Verifique as informações de diagnóstico nos detalhes do evento. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | Certificado PKCS emitido com êxito. Examine os detalhes do evento para obter a ID do dispositivo, a ID de usuário, o nome da Autoridade de Certificação, o nome do modelo de certificado e a impressão digital do certificado relacionados a esse evento. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | Falha ao emitir um certificado PKCS. Examine os detalhes do evento para obter a ID do dispositivo, a ID de usuário, o nome da Autoridade de Certificação, o nome do modelo de certificado e a impressão digital do certificado relacionados a esse evento. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Certificado revogado com êxito. Examine os detalhes do evento para obter a ID do dispositivo, a ID de usuário, o nome da Autoridade de Certificação e o número de série do certificado relacionado a esse evento. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Falha ao revogar o certificado. Examine os detalhes do evento para obter a ID do dispositivo, a ID de usuário, o nome da Autoridade de Certificação e o número de série do certificado relacionado a esse evento. Para obter mais informações, consulte os Logs de SVC do NDES.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Dados de revogação ou solicitação do certificado carregados com sucesso. Examine os detalhes do evento para obter os detalhes do upload. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Falha ao carregar os dados de revogação ou solicitação do certificado. Examine os detalhes do evento > Estado de Upload para determinar o ponto de falha.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Solicitação para assinar um certificado, baixar um certificado de cliente ou revogar um certificado baixada com sucesso. Examine os detalhes do evento para obter os detalhes do download.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Falha ao baixar a solicitação para assinar um certificado, baixar certificado de cliente ou revogar um certificado. Examine os detalhes do evento para obter os detalhes do download. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | O Ponto de Registro de Certificado verificou com êxito um desafio do cliente | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | O Ponto de Registro de Certificado foi concluído, mas rejeitou a solicitação. Veja o código e a mensagem de diagnóstico para obter mais detalhes. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | O Ponto de Registro de Certificado falhou ao verificar um desafio de cliente. Veja o código e a mensagem de diagnóstico para obter mais detalhes. Veja os detalhes da mensagem de evento para a ID do Dispositivo correspondente ao desafio. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | O Ponto de Registro de Certificado concluiu com êxito o processo de notificação e enviou o certificado ao dispositivo cliente. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | O Ponto de Registro de Certificado falhou ao concluir o processo de notificação. Veja os detalhes da mensagem de evento para obter informações sobre a solicitação. Verifique a conexão entre o servidor NDES e a autoridade de certificação. | 0x00000000, 0x0FFFFFFF |

## <a name="diagnostic-codes"></a>Códigos de diagnóstico

| Código de Diagnóstico | Nome do Diagnóstico | Mensagem de Diagnóstico |
| -------------   | -------------   | -------------      |
| 0x00000000 | Sucesso  | Sucesso |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | A autoridade de certificação não é válida ou está inacessível. Verifique se que a autoridade de certificação está disponível e se o servidor pode se comunicar com ela. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | O Certificado de Autenticação de Cliente da Symantec não foi encontrado no repositório de certificados local. Veja o artigo [Instalar o certificado autorização de registro da Symantec](certificates-digicert-configure.md#install-the-digicert-ra-certificate) para obter mais informações.  |
| 0x00000402 | RevokeCert_AccessDenied  | A conta especificada não tem permissões para revogar um certificado da autoridade de certificação. Veja o campo Nome da Autoridade de Certificação nos detalhes da mensagem do evento para determinar a autoridade de certificação emissora.  |
| 0x00000403 | CertThumbprint_NotFound  | Não foi possível localizar um certificado correspondente à sua entrada. Registre o conector de certificado e tente novamente. |
| 0x00000404 | Certificate_NotFound  | Não foi possível localizar um certificado correspondente à entrada fornecida. Registre o conector de certificado outra vez e tente novamente. |
| 0x00000405 | Certificate_Expired  | Um certificado expirou. Registre o conector de certificado outra vez para renovar o certificado e tente novamente. |
| 0x00000408 | CRPSCEPCert_NotFound  | Não foi possível localizar o certificado de criptografia de CRP. Verifique se que NDES e o Intune Connector estão configurados corretamente. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Não foi possível recuperar o certificado de assinatura. Verifique se o Serviço do Intune Connector está configurado corretamente e se o Serviço do Intune Connector está em execução. Verifique também se os eventos de download de certificado foram bem-sucedidos. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Falha ao desserializar a solicitação de desafio do protocolo SCEP. Verifique se o NDES e o Intune Connector estão configurados corretamente. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Solicitação negada devido a desafio de certificado expirado. O dispositivo cliente pode tentar novamente depois de obter um novo desafio do servidor de gerenciamento. |
| 0x0FFFFFFFF | Unknown_Error  | Não foi possível concluir sua solicitação porque ocorreu um erro no lado do servidor. Tente novamente. |


## <a name="next-steps"></a>Próximas etapas
Para obter assistência adicional, use a guia [Solucionar problemas na implantação do perfil de certificado SCEP no Microsoft Intune](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune).
