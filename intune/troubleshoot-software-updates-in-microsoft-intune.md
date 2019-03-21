---
title: Solução de problemas de atualizações de software no Microsoft Intune – Azure | Microsoft Docs
description: Solucione problemas de atualização de software no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e7ec762e7e7299e400fefedbf7a8810e1da929f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461338"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Solucionar problemas de atualização de software no Microsoft Intune

Ajude a solucionar problemas de atualização de software no Microsoft Intune.

Caso essas informações não ajudem, [obtenha também o suporte para o Microsoft Intune](get-support.md).

## <a name="update-agent-error-codes"></a>Atualizar códigos de erro do agente

A tabela a seguir relaciona os códigos de erro do **Agente de Atualização** do Intune. Se você não encontrar um código de erro específico nessa tabela, consulte [Lista de códigos de erro do Windows Update](https://support.microsoft.com/help/938205/windows-update-error-code-list).

|Código do erro|Nome simbólico|Mais informações|
|--------------|-----------------|--------------------|
|**0x00cf0001**|OM_S_SERVICE_STOP|O agente foi interrompido com êxito.|
|**0x00cf0003**|OM_S_UPDATE_ERROR|A operação foi concluída com êxito, mas ocorreram erros durante a aplicação das atualizações.|
|**0x00cf0004**|OM_S_MARKED_FOR_DISCONNECT|Um retorno de chamada foi marcado para ser desconectado mais tarde porque a solicitação para desconectar a operação ocorreu enquanto um retorno de chamada estava em execução.|
|**0x00cf0005**|OM_S_REBOOT_REQUIRED|O sistema deve ser reiniciado para concluir a instalação da atualização.|
|**0x00cf0006**|OM_S_ALREADY_INSTALLED|A atualização a ser instalada já está instalada no sistema.|
|**0x00cf0007**|OM_S_ALREADY_UNINSTALLED|A atualização a ser removida não está instalada no sistema.|
|**0x00cf2015**|OM_S_UH_INSTALLSTILLPENDING|A instalação da atualização está em andamento.|
|**0x80cf0001**|OM_E_NO_SERVICE|O agente não pôde fornecer o serviço.|
|**0x80cf0002**|OM_E_MAX_CAPACITY_REACHED|A capacidade máxima do serviço foi excedida.|
|**0x80cf0003**|OM_E_UNKNOWN_ID|Uma ID não foi encontrada.|
|**0x80cf0004**|OM_E_NOT_INITIALIZED|Não foi possível inicializar o objeto.|
|**0x80cf0007**|OM_E_INVALIDINDEX|O índice para uma coleção não é válido.|
|**0x80cf0008**|OM_E_ITEMNOTFOUND|A chave para o item consultado não foi encontrada.|
|**0x80cf0009**|OM_E_OPERATIONINPROGRESS|Uma operação conflitante estava em andamento. Algumas operações, como várias instalações, não podem ser realizadas simultaneamente.|
|**0x80cf000B**|OM_E_CALL_CANCELLED|A operação foi cancelada.|
|**0x80cf000C**|OM_E_NOOP|Nenhuma operação foi necessária.|
|**0x80cf000D**|OM_E_XML_MISSINGDATA|O agente não pôde encontrar as informações necessárias nos dados XML da atualização.|
|**0x80cf000E**|OM_E_XML_INVALID|O agente encontrou informações em dados XML da atualização que não são válidas.|
|**0x80cf000F**|OM_E_CYCLE_DETECTED|Relações circulares de atualização foram detectadas nos metadados.|
|**0x80cf0010**|OM_E_TOO_DEEP_RELATION|As relações de atualização estavam aninhadas muito profundamente para serem avaliadas.|
|**0x80cf0011**|OM_E_INVALID_RELATIONSHIP|Foi encontrada uma relação de atualização que não é válida.|
|**0x80cf0012**|OM_E_REG_VALUE_INVALID|Foi lido um valor do Registro que não é válido.|
|**0x80cf0013**|OM_E_DUPLICATE_ITEM|A operação tentou adicionar um item duplicado a uma lista.|
|**0x80cf0014**|OM_E_INVALID_INSTALL_REQUESTED|O chamador não pode instalar atualizações que foram solicitadas para instalação.|
|**0x80cf0016**|OM_E_INSTALL_NOT_ALLOWED|A operação tentou instalar enquanto outra instalação estava em andamento, ou o sistema possuía uma reinicialização obrigatória pendente.|
|**0x80cf0017**|OM_E_NOT_APPLICABLE|A operação não foi executada porque não existem atualizações aplicáveis.|
|**0x80cf0018**|OM_E_NO_USERTOKEN|A operação falhou porque um token de usuário necessário está ausente.|
|**0x80cf0019**|OM_E_EXCLUSIVE_INSTALL_CONFLICT|Uma atualização exclusiva não pode ser instalada simultaneamente com outras atualizações.|
|**0x80cf001A**|OM_E_POLICY_NOT_SET|Não foi definido um valor de política.|
|**0x80cf001D**|OM_E_INVALID_UPDATE|Uma atualização contém metadados que não são válidos.|
|**0x80cf001E**|OM_E_SERVICE_STOP|A operação não pôde ser concluída porque o serviço ou o sistema estava sendo desligado.|
|**0x80cf001F**|OM_E_NO_CONNECTION|A operação não pôde ser concluída porque a conexão de rede não estava disponível.|
|**0x80cf0020**|OM_E_NO_INTERACTIVE_USER|A operação não pôde ser concluída porque não há nenhum usuário interativo conectado.|
|**0x80cf0021**|OM_E_TIME_OUT|A operação não pôde ser concluída porque atingiu o tempo limite.|
|**0x80cf0022**|OM_E_ALL_UPDATES_FAILED|A operação falhou para todas as atualizações.|
|**0x80cf0024**|OM_E_NO_UPDATE|Não existem atualizações.|
|**0x80cf0025**|OM_E_USER_ACCESS_DISABLED|As configurações de Política de Grupo impediram o acesso ao Windows Update.|
|**0x80cf0026**|OM_E_INVALID_UPDATE_TYPE|O tipo de atualização não é válido.|
|**0x80cf0028**|OM_E_UNINSTALL_NOT_ALLOWED|Não foi possível desinstalar a atualização porque a solicitação não é proveniente de um servidor WSUS.|
|**0x80cf0029**|OM_E_INVALID_PRODUCT_LICENSE|A pesquisa talvez tenha perdido algumas atualizações, ou pode haver um aplicativo sem licença no sistema.|
|**0x80cf002C**|OM_E_BIN_SOURCE_ABSENT|Uma atualização compactada em delta não pôde ser instalada porque exigia a origem.|
|**0x80cf002D**|OM_E_SOURCE_ABSENT|Uma atualização de arquivos completos não pôde ser instalada porque exigia a origem.|
|**0x80cf002E**|OM_E_WU_DISABLED|Não é permitido o acesso a um servidor não gerenciado.|
|**0x80cf002F**|OM_E_CALL_CANCELLED_BY_POLICY|Não foi possível concluir a operação porque a política **DisableWindowsUpdateAccess** foi definida.|
|**0x80cf0030**|OM_E_INVALID_PROXY_SERVER|O formato da lista de proxy não é válido.|
|**0x80cf0031**|OM_E_INVALID_FILE|O arquivo está no formato incorreto.|
|**0x80cf0032**|OM_E_INVALID_CRITERIA|A cadeia de caracteres de critérios de pesquisa não é válida.|
|**0x80cf0034**|OM_E_DOWNLOAD_FAILED|Falha no download da atualização.|
|**0x80cf0035**|OM_E_UPDATE_NOT_PROCESSED|A atualização não foi processada.|
|**0x80cf0036**|OM_E_INVALID_OPERATION|O estado atual do objeto não permitiu a operação.|
|**0x80cf0037**|OM_E_NOT_SUPPORTED|Não há suporte para a operação.|
|**0x80cf0038**|OM_E_WINHTTP_INVALID_FILE|O arquivo baixado tem um tipo de conteúdo inesperado.|
|**0x80cf0039**|OM_E_TOO_MANY_RESYNC|O servidor solicitou que o agente fosse ressincronizado muitas vezes.|
|**0x80cf0043**|OM_E_NO_UI_SUPPORT|Não existe suporte para a interface de usuário do WUA.|
|**0x80cf0044**|OM_E_PER_MACHINE_UPDATE_ACCESS_DENIED|Somente administradores podem executar esta operação em atualizações por computador.|
|**0x80cf0045**|OM_E_UNSUPPORTED_SEARCHSCOPE|Foi tentada uma pesquisa com um escopo sem suporte.|
|**0x80cf0046**|OM_E_BAD_FILE_URL|A URL não aponta para um arquivo.|
|**0x80cf0047**|OM_E_NOTSUPPORTED|Não há suporte para a operação solicitada.|
|**0x80cf0049**|OM_E_OUTOFRANGE|Os dados estão fora do intervalo.|
|**0x80cf004A**|OM_E_INVALIDWUAVERSION|Os dados contêm uma versão que não é válida.|
|**0x80cf004B**|OM_E_SEARCH_COMPLETED_WITH_SOME_FAILURES|A chamada de pesquisa foi concluída, mas não pôde detectar algumas das atualizações.|
|**0x80cf004C**|OM_E_DOWNLOAD_COMPLETED_WITH_SOME_FAILURES|A chamada de download foi concluída, mas falhou ao baixar algumas das atualizações.|
|**0x80cf004D**|OM_E_INSTALL_COMPLETED_WITH_SOME_FAILURES|A chamada de instalação foi concluída, mas falhou ao instalar algumas das atualizações.|
|**0x80cf004E**|OM_E_WINUPDATE_CACHE_UNINITIALIZED|O cache do Windows Update está vazio porque não foi inicializado.|
|**0x80cf0436**|OM_E_PT_CATALOG_SYNC_REQUIRED|O servidor não oferece suporte a pesquisas específicas de categoria. Em vez disso, a pesquisa de catálogo completo deve ser emitida.|
|**0x80cf0437**|OM_E_PT_SECURITY_VERIFICATION_FAILURE|Houve um problema durante a autorização no serviço.|
|**0x80cf0438**|OM_E_PT_ENDPOINT_UNREACHABLE|Não há conectividade de rede ou rota para o ponto de extremidade.|
|**0x80cf0439**|OM_E_PT_INVALID_FORMAT|Os dados recebidos não atendem às expectativas do contrato de dados.|
|**0x80cf043A**|OM_E_PT_INVALID_URL|A URL não é válida.|
|**0x80cf043B**|OM_E_PT_NWS_NOT_LOADED|O tempo de execução do NWS não pode ser carregado.|
|**0x80cf043C**|OM_E_PT_PROXY_AUTH_SCHEME_NOT_SUPPORTED|Não há suporte para o esquema de autenticação do proxy.|
|**0x80cf043D**|OM_E_SERVICEPROP_NOTAVAIL|A propriedade de serviço solicitada não está disponível.|
|**0x80cf043E**|OM_E_PT_ENDPOINT_REFRESH_REQUIRED|O plug-in do provedor de ponto de extremidade requer uma atualização online.|
|**0x80cf043F**|OM_E_PT_ENDPOINTURL_NOTAVAIL|Uma URL para o ponto de extremidade do serviço solicitado não está disponível.|
|**0x80cf0440**|OM_E_PT_ENDPOINT_DISCONNECTED|A conexão com o ponto de extremidade do serviço foi encerrada.|
|**0x80cf0441**|OM_E_PT_INVALID_OPERATION|A operação não é válida porque o agente de conversação do protocolo está em um estado inadequado.|
|**0x80cf0FFF**|OM_E_UNEXPECTED|Uma operação falhou por motivos não explicados por outro código de erro.|
|**0x80cf1001**|OM_E_MSI_WRONG_VERSION|A pesquisa pode ter perdido algumas atualizações porque o Windows Installer está em uma versão anterior à versão 3.1.|
|**0x80cf1002**|OM_E_MSI_NOT_CONFIGURED|A pesquisa pode ter perdido algumas atualizações porque o Windows Installer não está configurado.|
|**0x80cf1003**|OM_E_MSP_DISABLED|A pesquisa pode ter perdido algumas atualizações porque a política desabilitou a aplicação de patchs do Windows Installer.|
|**0x80cf1004**|OM_E_MSI_WRONG_APP_CONTEXT|Não foi possível aplicar uma atualização porque o aplicativo é instalado por usuário.|
|**0x80cf2000**|OM_E_UH_REMOTEUNAVAILABLE|Uma solicitação para um manipulador de atualizações remotas não pôde ser concluída porque nenhum processo remoto está disponível.|
|**0x80cf2001**|OM_E_UH_LOCALONLY|Uma solicitação para um manipulador de atualizações remotas não pôde ser concluída porque o manipulador é local apenas.|
|**0x80cf2003**|OM_E_UH_REMOTEALREADYACTIVE|Não foi possível criar um manipulador de atualizações remotas porque já existe um.|
|**0x80cf2004**|OM_E_UH_DOESNOTSUPPORTACTION|Uma solicitação para o manipulador instalar (desinstalar) uma atualização não pôde ser concluída porque a atualização não oferece suporte para instalação (desinstalação).|
|**0x80cf2005**|OM_E_UH_WRONGHANDLER|Uma operação não pôde ser concluída porque o manipulador incorreto foi especificado.|
|**0x80cf2006**|OM_E_UH_INVALIDMETADATA|Uma operação do manipulador não pôde ser concluída porque a atualização contém metadados que não são válidos.|
|**0x80cf2007**|OM_E_UH_INSTALLERHUNG|Uma operação não pôde ser concluída porque o instalador excedeu o limite de tempo. Verifique se uma atualização que requer interação do usuário foi aprovada para implantação. Nesse caso, você deve revisar os parâmetros de instalação da atualização para que ela possa ser instalada silenciosamente.|
|**0x80cf2008**|OM_E_UH_OPERATIONCANCELLED|Uma operação que estava sendo realizada pelo manipulador de atualizações foi cancelada.|
|**0x80cf2009**|OM_E_UH_BADHANDLERXML|Uma operação não pôde ser concluída porque os metadados específicos do manipulador não são válidos.|
|**0x80cf200B**|OM_E_UH_INSTALLERFAILURE|Falha no instalador ao instalar (desinstalar) uma ou mais atualizações.|
|**0x80cf200D**|OM_E_UH_NEEDANOTHERDOWNLOAD|O manipulador de atualizações não instalou a atualização porque ela deve ser baixada novamente.|
|**0x80cf200E**|OM_E_UH_NOTIFYFAILURE|O manipulador de atualizações falhou ao enviar a notificação do status da operação de instalação (desinstalação).|
|**0x80cf2014**|OM_E_UH_POSTREBOOTSTILLPENDING|A operação pós-reinicialização para a atualização ainda está em andamento.|
|**0x80cf2015**|OM_E_UH_POSTREBOOTRESULTUNKNOWN|O resultado da operação pós-reinicialização para a atualização não pôde ser determinado.|
|**0x80cf2016**|OM_E_UH_POSTREBOOTUNEXPECTEDSTATE|O estado da atualização após a conclusão da sua operação pós-reinicialização é inesperado.|
|**0x80cf2017**|OM_E_UH_NEW_SERVICING_STACK_REQUIRED|A pilha de atendimento do sistema operacional deve ser atualizada antes que essa atualização possa ser baixada ou instalada.|
|**0x80cf2018**|OM_E_UH_CALLED_BACK_FAILURE|Um instalador de retorno de chamada retornou a chamada com um erro.|
|**0x80cf2019**|OM_E_UH_CUSTOMINSTALLER_INVALID_SIGNATURE|A assinatura do instalador personalizado não correspondeu à assinatura que requer a atualização.|
|**0x80cf201A**|OM_E_UH_UNSUPPORTED_INSTALLCONTEXT|O instalador não oferece suporte para a configuração da instalação.|
|**0x80cf201B**|OM_E_UH_INVALID_TARGETSESSION|A sessão definida como destino para a instalação não é válida.|
|**0x80cf2FFF**|OM_E_UH_UNEXPECTED|Um erro do manipulador de atualizações não é coberto por outro código OM_E_UH_&#42;.|
|**0x80cf3FFD**|OM_E_NON_UI_MODE|Não é possível mostrar a interface do usuário quando no modo sem interface do usuário. Módulos de interface do usuário de cliente do Windows Update podem não estar instalados.|
|**0x80cf3FFE**|OM_E_WUCLTUI_UNSUPPORTED_VERSION|Não há suporte para funções exportadas da Interface do Usuário do cliente WU desta versão.|
|**0x80cf3FFF**|OM_E_AUCLIENT_UNEXPECTED|Ocorreu um erro de interface do usuário que não é coberto por outro código de erro OM_E_AUCLIENT_&#42;.|
|**0x80cf4007**|OM_E_PT_SOAPCLIENT_SOAPFAULT|Mesmo que **SOAPCLIENT_SOAPFAULT**. O cliente SOAP falhou porque uma falha SOAP do tipo de código de erro **OM_E_PT_SOAP_&#42;** ocorreu.|
|**0x80cf4008**|OM_E_PT_SOAPCLIENT_PARSEFAULT|Mesmo que **SOAPCLIENT_PARSEFAULT_ERROR**.  O cliente SOAP falhou ao analisar um erro de falha SOAP.|
|**0x80cf400A**|OM_E_PT_SOAPCLIENT_PARSE|Mesmo que **SOAPCLIENT_PARSE_ERROR**.  O cliente SOAP falhou ao analisar a resposta do servidor.|
|**0x80cf400B**|OM_E_PT_SOAP_VERSION|Mesmo que **SOAP_E_VERSION_MISMATCH**. O cliente SOAP encontrou um namespace não reconhecido para o envelope SOAP.|
|**0x80cf400C**|OM_E_PT_SOAP_MUST_UNDERSTAND|Mesmo que **SOAP_E_MUST_UNDERSTAND**. O cliente SOAP não pôde interpretar um cabeçalho.|
|**0x80cf400D**|OM_E_PT_SOAP_CLIENT|Mesmo que **SOAP_E_CLIENT**. O cliente SOAP descobriu que a mensagem estava malformada. Corrija antes de reenviar.|
|**0x80cf400E**|OM_E_PT_SOAP_SERVER|Mesmo que **SOAP_E_SERVER**. A mensagem SOAP não pôde ser processada por causa de um erro no servidor. Reenvie mais tarde.|
|**0x80cf4010**|OM_E_PT_EXCEEDED_MAX_SERVER_TRIPS|O número de idas e voltas para o servidor excedeu o limite máximo.|
|**0x80cf4012**|OM_E_PT_DOUBLE_INITIALIZATION|A inicialização falhou porque o objeto já estava inicializado.|
|**0x80cf4013**|OM_E_PT_INVALID_COMPUTER_NAME|Não foi possível determinar o nome do computador.|
|**0x80cf4015**|OM_E_PT_REFRESH_CACHE_REQUIRED|A resposta do servidor indica que ele foi alterado ou que o cookie era inválido. Atualize o cache interno e tente novamente.|
|**0x80cf4016**|OM_E_PT_HTTP_STATUS_BAD_REQUEST|Mesmo que **status HTTP 400**. O servidor não pôde processar a solicitação porque a sintaxe não é válida.|
|**0x80cf4017**|OM_E_PT_HTTP_STATUS_DENIED|Mesmo que **status HTTP 401**. O recurso solicitado requer a autenticação do usuário.|
|**0x80cf4018**|OM_E_PT_HTTP_STATUS_FORBIDDEN|Mesmo que **status HTTP 403**. O servidor compreendeu a solicitação, mas se recusou a atendê-la.|
|**0x80cf4019**|OM_E_PT_HTTP_STATUS_NOT_FOUND|Mesmo que **status HTTP 404**. O servidor não consegue localizar o URI (Uniform Resource Identifier) solicitado.|
|**0x80cf401A**|OM_E_PT_HTTP_STATUS_BAD_METHOD|Mesmo que **status HTTP 405**. O método HTTP não é permitido.|
|**0x80cf401B**|OM_E_PT_HTTP_STATUS_PROXY_AUTH_REQ|Mesmo que **status HTTP 407**. A autenticação de proxy é necessária.|
|**0x80cf401C**|OM_E_PT_HTTP_STATUS_REQUEST_TIMEOUT|Mesmo que **status HTTP 408**. O servidor atingiu o tempo limite ao aguardar a solicitação.|
|**0x80cf401D**|OM_E_PT_HTTP_STATUS_CONFLICT|Mesmo que **status HTTP 409**. A solicitação não foi concluída por causa de um conflito com o estado atual do recurso.|
|**0x80cf401E**|OM_E_PT_HTTP_STATUS_GONE|Mesmo que **status HTTP 410**. O recurso solicitado não está mais disponível no servidor.|
|**0x80cf401F**|OM_E_PT_HTTP_STATUS_SERVER_ERROR|Mesmo que **status HTTP 500**. Um erro interno no servidor impediu que a solicitação fosse atendida.|
|**0x80cf4020**|OM_E_PT_HTTP_STATUS_NOT_SUPPORTED|Mesmo que **status HTTP 500**. O servidor não oferece suporte à funcionalidade necessária para atender à solicitação.|
|**0x80cf4021**|OM_E_PT_HTTP_STATUS_BAD_GATEWAY|Mesmo que **status HTTP 502**. O servidor, ao atuar como gateway ou proxy, recebeu uma resposta inválida do servidor ascendente que ele acessou ao tentar atender à solicitação.|
|**0x80cf4022**|OM_E_PT_HTTP_STATUS_SERVICE_UNAVAIL|Mesmo que **status HTTP 503**. O serviço está temporariamente sobrecarregado.|
|**0x80cf4023**|OM_E_PT_HTTP_STATUS_GATEWAY_TIMEOUT|Mesmo que **status HTTP 503**. A solicitação atingiu o tempo limite ao aguardar um gateway.|
|**0x80cf4024**|OM_E_PT_HTTP_STATUS_VERSION_NOT_SUP|Mesmo que **status HTTP 505**. O servidor não oferece suporte para a versão do protocolo HTTP usada para a solicitação.|
|**0x80cf4025**|OM_E_PT_FILE_LOCATIONS_CHANGED|A operação falhou devido um local de arquivo alterado. Atualize o estado interno e envie novamente.|
|**0x80cf4027**|OM_E_PT_NO_AUTH_PLUGINS_REQUESTED|O servidor retornou uma lista de informações de autenticação vazia.|
|**0x80cf4028**|OM_E_PT_NO_AUTH_COOKIES_CREATED|O agente não pôde criar cookies de autenticação válidos.|
|**0x80cf4029**|OM_E_PT_INVALID_CONFIG_PROP|Um valor de propriedade de configuração estava errado.|
|**0x80cf402A**|OM_E_PT_CONFIG_PROP_MISSING|Um valor de propriedade de configuração estava ausente.|
|**0x80cf402B**|OM_E_PT_HTTP_STATUS_NOT_MAPPED|Não foi possível concluir a solicitação HTTP e o motivo não correspondeu a nenhum dos códigos de erro **OM_E_PT_HTTP_&#42;**.|
|**0x80cf402C**|OM_E_PT_WINHTTP_NAME_NOT_RESOLVED|Mesmo que **ERROR_WINHTTP_NAME_NOT_RESOLVED**. O nome do servidor proxy ou do servidor de destino não pode ser resolvido.|
|**0x80cf402F**|OM_E_PT_ECP_SUCCEEDED_WITH_ERRORS|O processamento do arquivo .cab externo foi concluído com alguns erros.|
|**0x80cf4030**|OM_E_PT_ECP_INIT_FAILED|A inicialização do processador .cab externo não foi concluída.|
|**0x80cf4031**|OM_E_PT_ECP_INVALID_FILE_FORMAT|O formato de um arquivo de metadados não é válido.|
|**0x80cf4032**|OM_E_PT_ECP_INVALID_METADATA|O processador .cab externo encontrou metadados que não são válidos.|
|**0x80cf4033**|OM_E_PT_ECP_FAILURE_TO_EXTRACT_DIGEST|Não foi possível extrair o resumo de arquivos de um arquivo. cab externo.|
|**0x80cf4034**|OM_E_PT_ECP_FAILURE_TO_DECOMPRESS_CAB_FILE|Um arquivo .cab externo não pôde ser descompactado.|
|**0x80cf4035**|OM_E_PT_ECP_FILE_LOCATION_ERROR|O processador .cab externo não pôde obter os locais dos arquivos.|
|**0x80cf4FFF**|OM_E_PT_UNEXPECTED|Ocorreu um erro de comunicação que não é coberto por outro código de erro do **OM_E_PT_&#42;**.|
|**0x80cf6001**|OM_E_DM_URLNOTAVAILABLE|Uma operação do gerenciador de download não pôde ser concluída porque o arquivo solicitado não tem uma URL.|
|**0x80cf6002**|OM_E_DM_INCORRECTFILEHASH|Uma operação do gerenciador de download não pôde ser concluída porque o resumo de arquivos não foi reconhecido.|
|**0x80cf6003**|OM_E_DM_UNKNOWNALGORITHM|Uma operação do gerenciador de download não pôde ser concluída porque os metadados de arquivo solicitaram um algoritmo de hash não reconhecido.|
|**0x80cf6005**|OM_E_DM_NONETWORK|Uma operação do gerenciador de download não pôde ser concluída porque a conexão de rede não estava disponível.|
|**0x80cf6007**|OM_E_DM_NOTDOWNLOADED|A atualização não foi baixada.|
|**0x80cf6008**|OM_E_DM_FAILTOCONNECTTOBITS|Uma operação do gerenciador de download falhou porque houve o gerenciador de download não conseguiu se conectar com o BITS (Serviço de Transferência Inteligente em Segundo Plano).|
|**0x80cf6009**|OM_E_DM_BITSTRANSFERERROR|Uma operação do gerenciador de download falhou porque houve um erro de transferência não especificado do BITS (Serviço de Transferência Inteligente em Segundo Plano).|
|**0x80cf600a**|OM_E_DM_DOWNLOADLOCATIONCHANGED|Um download deve ser reiniciado porque o local de origem do download foi alterado.|
|**0x80cf600B**|OM_E_DM_CONTENTCHANGED|Um download deve ser reiniciado porque o conteúdo de atualização foi alterado em uma nova revisão.|
|**0x80cf6FFF**|OM_E_DM_UNEXPECTED|Ocorreu um erro do gerenciador de download que não é coberto por outro código de erro do **OM_E_DM_&#42;**.|
|**0x80cf7003**|OM_E_INVALID_EVENT_PAYLOAD|Uma carga de evento especificada não é válida.|
|**0x80cf7004**|OM_E_INVALID_EVENT_PAYLOADSIZE|O tamanho da carga do evento enviada não é válido.|
|**0x80cf7005**|OM_E_SERVICE_NOT_REGISTERED|O serviço não está registrado.|
|**0x80cf8000**|OM_E_DS_SHUTDOWN|Uma operação falhou porque o agente está sendo desligado.|
|**0x80cf8001**|OM_E_DS_INUSE|Uma operação falhou porque o repositório de dados estava em uso.|
|**0x80cf8002**|OM_E_DS_INVALID|O estado atual e o estado esperado do repositório de dados não coincidem.|
|**0x80cf8003**|OM_E_DS_TABLEMISSING|O repositório de dados não possui uma tabela.|
|**0x80cf8004**|OM_E_DS_TABLEINCORRECT|O repositório de dados contém uma tabela que possui colunas inesperadas.|
|**0x80cf8005**|OM_E_DS_INVALIDTABLENAME|Não foi possível abrir uma tabela porque essa tabela não está no repositório de dados.|
|**0x80cf8006**|OM_E_DS_BADVERSION|A versão atual e a versão esperada do repositório de dados não coincidem.|
|**0x80cf8007**|OM_E_DS_NODATA|As informações solicitadas não estão no repositório de dados.|
|**0x80cf8008**|OM_E_DS_MISSINGDATA|O repositório de dados não possui informações necessárias ou possui um valor nulo em uma coluna de tabela que exige um valor não nulo.|
|**0x80cf8009**|OM_E_DS_MISSINGREF|O repositório de dados não possui informações necessárias ou possui uma referência para termos de licença ausentes, arquivo, propriedade localizada ou linha vinculada.|
|**0x80cf800A**|OM_E_DS_UNKNOWNHANDLER|A atualização não foi processada porque o manipulador de atualizações não foi reconhecido.|
|**0x80cf800B**|OM_E_DS_CANTDELETE|A atualização não foi excluída porque ainda é referenciada por um ou mais serviços.|
|**0x80cf800C**|OM_E_DS_LOCKTIMEOUTEXPIRED|A seção do repositório de dados não pôde ser bloqueada no tempo alocado.|
|**0x80cf800E**|OM_E_DS_ROWEXISTS|A linha não foi adicionada como uma linha existente tem a mesma chave primária.|
|**0x80cf800F**|OM_E_DS_STOREFILELOCKED|Não foi possível inicializar o repositório de dados porque ele foi bloqueado por outro processo.|
|**0x80cf8010**|OM_E_DS_CANNOTREGISTER|O repositório de dados não pode ser registrado em COM no processo atual.|
|**0x80cf8011**|OM_E_DS_UNABLETOSTART|Uma operação não pôde criar um objeto de repositório de dados em outro processo.|
|**0x80cf8013**|OM_E_DS_DUPLICATEUPDATEID|O servidor enviou a mesma atualização para o cliente com duas IDs de revisão diferentes.|
|**0x80cf8014**|OM_E_DS_UNKNOWNSERVICE|Uma operação não pôde ser concluída porque o serviço não está no repositório de dados.|
|**0x80cf8015**|OM_E_DS_SERVICEEXPIRED|Uma operação não pôde ser concluída porque o registro do serviço expirou.|
|**0x80cf8016**|OM_E_DS_DECLINENOTALLOWED|Uma solicitação para ocultar uma atualização foi recusada porque é uma atualização obrigatória ou porque foi implantada com um prazo final.|
|**0x80cf8017**|OM_E_DS_TABLESESSIONMISMATCH|Uma tabela não foi fechada porque não está associada à sessão.|
|**0x80cf8018**|OM_E_DS_SESSIONLOCKMISMATCH|Uma tabela não foi fechada porque não está associada à sessão.|
|**0x80cf8019**|OM_E_DS_NEEDWINDOWSSERVICE|A solicitação para remover o serviço ou cancelar seu registro foi recusada porque esse serviço é interno ou porque o recurso de Atualizações Automáticas não pode efetuar fallback para outro serviço.|
|**0x80cf801A**|OM_E_DS_INVALIDOPERATION|A solicitação foi recusada porque a operação não é permitida.|
|**0x80cf801B**|OM_E_DS_SCHEMAMISMATCH|O esquema do repositório de dados atual e o esquema de uma tabela em um documento XML de backup não coincidem.|
|**0x80cf801C**|OM_E_DS_RESETREQUIRED|O repositório de dados requer uma redefinição da sessão. Libere a sessão e tente novamente com uma nova sessão.|
|**0x80cf801D**|OM_E_DS_IMPERSONATED|Uma operação do repositório de dados não pôde ser concluída porque foi solicitada com uma identidade representada.|
|**0x80cf8FFF**|OM_E_DS_UNEXPECTED|Ocorreu um erro no armazenamento de dados que não é coberto por outro código do **OM_E_DS_&#42;**.|
|**0x80cfA000**|OM_E_AU_NOSERVICE|Atualizações Automáticas não puderam atender a solicitações de entrada.|
|**0x80cfA004**|OM_E_AU_PAUSED|Atualizações Automáticas não puderam processar solicitações de entrada porque foram pausadas.|
|**0x80cfA005**|OM_E_AU_NO_REGISTERED_SERVICE|Nenhum serviço não gerenciado está registrado em Atualizações Automáticas.|
|**0x80cfA006**|OM_E_AU_DETECT_SVCID_MISMATCH|O serviço padrão registrado em Atualizações Automáticas foi alterado durante a pesquisa.|
|**0x80cfA007**|OM_E_AU_ALREADY_PROMPTING_FOR_REBOOT|Atualizações Automáticas já estão solicitando uma reinicialização ao usuário.|
|**0x80cfAFFF**|OM_E_AU_UNEXPECTED|Ocorreu um erro de Atualizações Automáticas que não é coberto por outro código do **OM_E_AU &#42;**.|
|**0x80cfE001**|OM_E_EE_UNKNOWN_EXPRESSION|Uma operação do avaliador de expressão não pôde ser concluída porque uma expressão não foi reconhecida.|
|**0x80cfE002**|OM_E_EE_INVALID_EXPRESSION|Uma operação do avaliador de expressão não pôde ser concluída porque uma expressão não era válida.|
|**0x80cfE003**|OM_E_EE_MISSING_METADATA|Uma operação do avaliador de expressão não pôde ser concluída porque uma expressão contém um número incorreto de nós de metadados.|
|**0x80cfE004**|OM_E_EE_INVALID_VERSION|Uma operação do avaliador de expressão não pôde ser concluída porque a versão dos dados de expressão serializados não é válida.|
|**0x80cfE005**|OM_E_EE_NOT_INITIALIZED|O avaliador de expressão não pôde ser inicializado.|
|**0x80cfE006**|OM_E_EE_INVALID_ATTRIBUTEDATA|Uma operação do avaliador de expressão não pôde ser concluída porque um atributo não é válido.|
|**0x80cfE007**|OM_E_EE_CLUSTER_ERROR|Uma operação do avaliador de expressão não pôde ser concluída porque o estado do cluster do computador não pode ser determinado.|
|**0x80cfEFFF**|OM_E_EE_UNEXPECTED|Ocorreu um erro do avaliador de expressão que não é coberto por outro código de erro do **OM_E_EE_&#42;**.|
|**0x80cfF001**|OM_E_REPORTER_EVENTCACHECORRUPT|O arquivo de cache de eventos estava defeituoso.|
|**0x80cfF002**|OM_E_REPORTER_EVENTNAMESPACEPARSEFAILED|O XML no descritor do namespace de eventos não pôde ser analisado.|
|**0x80cfF003**|OM_E_INVALID_EVENT|O XML no descritor do namespace de eventos não é válido.|
|**0x80cfF004**|OM_E_SERVER_BUSY|O servidor rejeitou um evento porque o servidor estava muito ocupado.|
|**0x80cfFFFF**|OM_E_REPORTER_UNEXPECTED|Ocorreu um erro no menismo de geração de relatórios que não é coberto por outro código de erro.|
|**0x80af0005**|OMC_E_INSTALL_NOT_ALLOWED_REBOOT_REQUIRED|A instalação falhou porque uma reinicialização obrigatória está pendente.|
|**0x80af0006**|OMC_E_DOWNLOAD_CANCELLED|O download foi cancelado.|

## <a name="windows-7-based-computers-with-lots-of-superseded-updates-stop-reporting-to-the-microsoft-intune-console"></a>Os computadores baseados no Windows 7, com muitas atualizações substituídas, param de reportar ao console do Microsoft Intune
**Problema**: você pode encontrar uma situação na qual os clientes do Microsoft Intune observam um ou mais dos seguintes sintomas:
- Eles repentinamente param de reportar ao console de administração do Microsoft.  
- Eles observam alta utilização da CPU.
- Os aplicativos são instalados lentamente quando a instalação ocorre por meio do portal do Intune.
- O Microsoft Intune Center dispara o seguinte erro: *Ocorreu um erro ao atualizar seu computador. Erro encontrado: código 0x800705b4*.
- O campo de status no Console de administração do Intune > Grupos > Todos os Dispositivos exibe: *Um ou mais agentes que estão instalados neste computador têm erros. As informações deste computador podem estar imprecisas ou desatualizadas*.

Esse problema poderá ocorrer se as atualizações substituídas (que foram trocadas por outra atualização) não forem recusadas por um longo período. Durante determinados processos, como a instalação de um aplicativo, o Windows verifica todas as atualizações substituídas em sequência, para que as atualizações e suas sucessoras possam ser mapeadas corretamente. Se a lista de atualizações substituídas ficar muito grande, essa tarefa de verificação poderá causar alta utilização da CPU devido à carga de processamento e ao tempo necessário. Esse problema afeta principalmente os clientes que estão executando o Windows 7 devido ao grande número de atualizações substituídas que estão disponíveis para o Windows 7. O Windows 8 e os sistemas operacionais posteriores não têm tantas atualizações substituídas disponíveis e, portanto, não são tão suscetíveis a esse problema.

**Resolução**:  
1. Entre no [portal do Azure](https://portal.azure.com) e abra o **Microsoft Intune**. 
2. Selecione **Atualizações de Software**.
3. Recuse todas as atualizações substituídas que podem ser aplicáveis ao Windows 7 ou aos aplicativos (por exemplo, o Microsoft Office) que foram instalados nos clientes afetados.
4. Reinicie os clientes afetados.

Além disso, se você estiver executando o Windows 7, certifique-se de que você tenha a seguinte atualização instalada:[3050265 Windows Update Client para Windows 7: junho de 2015](https://support.microsoft.com/kb/3050265).

### <a name="next-steps"></a>Próximas etapas
Caso essas informações não ajudem, [obtenha também o suporte para o Microsoft Intune](get-support.md).
