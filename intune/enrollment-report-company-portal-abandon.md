---
title: Abandono de registro do portal da empresa no Intune
titlesuffix: Microsoft Intune
description: Saiba mais sobre o relatório de abandono de portal da empresa.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: ba1ee5a6811457b8c6e7343de7355261a2fcecdb
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236740"
---
# <a name="company-portal-abandonment-report"></a>Relatório de abandono de portal da empresa

Esse relatório informa em que ponto os usuários de registro do Portal da Empresa estão abandonando o processo de registro.

Para ver o relatório, escolha **Intune** > **Registro de dispositivo** > **Abandono do portal da empresa**.

Usando essas informações de abandono, você pode atualizar seus documentos de integração para ajudar os usuários a concluírem o registro. Por exemplo, se vários usuários estiverem desistindo nos Termos de uso, você poderá investigar essa área e torná-la mais intuitiva para os usuários.

## <a name="what-is-abandonment"></a>O que é o abandono?

Abandono é quando um usuário faz o seguinte:

-   Explicitamente escolhe uma ação para interromper o registro
-   Fecha o Portal da Empresa durante o registro
-   Gasta mais de 30 minutos entre seções do registro

Se um usuário optar por parar o registro e reiniciar várias vezes, isso aparecerá como várias tentativas e vários abandonos. Se um usuário aguardar 30 minutos entre as telas de registro diferente, isso será considerado como vários abandonos.

## <a name="what-does-the-report-show"></a>O que o relatório mostra?

Os relatórios de registro incluem dados de dispositivos iOS e Android.

Os relatórios mostram dados das últimas duas semanas, mas você pode filtrar o relatório para mostrar qualquer período de 30 dias no passado.

Você pode filtrar o intervalo de datas, o sistema operacional e a seção do registro escolhendo **Filtrar**.

### <a name="number-and-percentage-tiles"></a>Blocos de números e de percentuais

Na parte superior do relatório, você pode ver o número e o percentual de relatórios abandonados em relação a todos os registros.

-   Registros iniciados: o número de tentativas de registros.
-   Registros abandonados: O número de tentativas registros que não resultam em um dispositivo totalmente registrado e em conformidade.
-   Taxa de abandono: o percentual de tentativas de registro que foram abandonadas (registros abandonados/registros iniciados).

### <a name="line-graph"></a>Gráfico de linhas

O gráfico de linhas mostra os abandonos diários para cada uma das seções de registro de quatro núcleos:

-   Lista de verificação de configuração
-   Telas de plataforma
-   Termos de uso
-   Conformidade/Ativação

### <a name="user-abandonment-actions"></a>Ações de abandono de usuário

As tabelas a seguir mostram a lista de ações do usuário que se qualificam como Abandono. Para ver exemplos de telas de registro, assista aos vídeos de registro do [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) e do [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment). 


#### <a name="setup-checklist-section"></a>Seção de lista de verificação de configuração

| Nome do abandono | Tela ou fluxo | Plataforma | Ação |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Prompt para abrir a página no Portal da Empresa | iOS/Android | **Cancelar** |
| EnrollmentWrapUp | Tela de registro do dispositivo até o término do **Carregamento de recursos da empresa** | iOS/Android | Levou >30 minutos |
| DeviceCategory | Seleção de Categoria de Dispositivo (se configurada pelo administrador) até clicar em **Concluído** | iOS/Android | Levou >30 minutos |
| PreEnrollmentWizard | Configurar a tela de acesso quando tiver iniciado o registro, mas retornado para Configurar acesso | iOS/Android| **Adiar** |
| PreEnrollmentWizard | Configurar a tela de acesso até clicar em **Avançar** na tela **Próximas Etapas** | iOS/Android | Levou >30 minutos |

#### <a name="platform-screens-section"></a>Seção de telas de plataforma

| Nome do abandono | Tela ou fluxo | Plataforma | Ação |
| ---- |---- |---- |---- |
| iOSProfileLaunch | Prompt para mostrar um perfil de configuração | iOS | **Ignorar** |
| iOSProfileLaunch | Tela de instalação do perfil | iOS | **Cancelar** |
| iOSProfileLaunch | Prompt para confiar na origem do perfil para registrar o dispositivo | iOS | **Cancelar** |
| iOSProfileLaunch | Tela de instalar o perfil até o perfil ser instalado | iOS | Levou >30 minutos |
| AndroidPermissions | Tela de ativação de administrador do dispositivo | Android | **Cancelar** |
| AndroidPermissions | Do prompt para aprovação para fazer e gerenciar chamadas telefônicas até o administrador do dispositivo **Ativar** | Android | Levou >30 minutos |
| KnoxActivation | Ativação de agente KLMS (somente Samsung) | Android| **Cancelar** |
| KnoxActivation | Ativação de agente KLMS até **Confirmar** | Android | Levou >30 minutos|

#### <a name="terms-of-use-section"></a>Seção de Termos de uso

| Nome do abandono | Tela ou fluxo | Plataforma | Ação |
| ---- |---- |---- |---- |
| TermsofUse | Termos de uso (se configurados pelo administrador) | iOS/Android | **Recusar Tudo** |
| TermsofUse | Termos de uso até **Aceitar Tudo** | iOS/Android | Levou >30 minutos |

#### <a name="complianceactivation-section"></a>Seção de Conformidade/Ativação

| Nome do abandono | Tela ou fluxo | Plataforma | Ação |
| ---- |---- |---- |---- |
| Conformidade | A conformidade do dispositivo (se configurada pelo administrador) é mostrada como não verde na configuração de acesso após o registro| iOS/Android | **Adiar** |
| Conformidade | A conformidade do dispositivo é mostrada como não verde até ser atualizada para ser mostrada em verde | iOS/Android | Levou >30 minutos |
| Ativação | A ativação do registro (se configurada pelo administrador) é mostrada como não verde na configuração de acesso | iOS/Android | **Adiar** |
| Conformidade | A ativação do dispositivo é mostrada como não verde até ser atualizada para ser mostrada como verde | iOS/Android | Levou >30 minutos |

## <a name="next-steps"></a>Próximas etapas

Depois de verificar em suas taxas de abandono, você pode examinar as [opções de registro](enrollment-options.md) para ver se pode fazer alterações para melhorar o registro.