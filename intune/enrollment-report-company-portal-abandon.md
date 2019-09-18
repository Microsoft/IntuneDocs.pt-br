---
title: Relatório de registros de usuário incompletos no Intune
titleSuffix: Microsoft Intune
description: Conheça o Relatório de registros de usuário incompletos.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9b67adeac619e26de785addbab4c6312915a58f0
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071737"
---
# <a name="incomplete-user-enrollments-report"></a>Relatório de registros de usuário incompletos

Esse relatório informa o local, no Portal da Empresa, em que os usuários não estão concluindo o processo de registro.

Para ver o relatório, escolha **Intune** > **Registro de dispositivos** > **Registros de usuário incompletos**.

Usando essas informações, é possível atualizar seus documentos de integração para ajudar os usuários a concluírem o registro. Por exemplo, se vários usuários estiverem desistindo nos Termos de uso, você poderá investigar essa área e torná-la mais intuitiva para os usuários.

## <a name="what-is-an-incomplete-enrollment"></a>O que é um registro incompleto?

Um registro incompleto é quando um usuário faz o seguinte:

- Explicitamente escolhe uma ação para interromper o registro
- Fecha o Portal da Empresa durante o registro
- Gasta mais de 30 minutos entre seções do registro

Se um usuário optar por interromper o registro e reiniciar várias vezes, ele será exibido como várias tentativas e vários registros incompletos. Se um usuário aguardar 30 minutos entre diferentes telas de registro, isso será considerado vários registros incompletos.

## <a name="what-does-the-report-show"></a>O que o relatório mostra?

Os relatórios incluem dados para dispositivos iOS e Android.

Os relatórios mostram dados das últimas duas semanas, mas você pode filtrar o relatório para mostrar qualquer período de 30 dias no passado.

Você pode filtrar o intervalo de datas, o sistema operacional e a seção do registro escolhendo **Filtrar**.

### <a name="number-and-percentage-tiles"></a>Blocos de números e de percentuais

Na parte superior do relatório, é possível ver o número e o percentual de registros incompletos em relação a todos os registros.

- Registros iniciados: o número de tentativas de registros.
- Registros incompletos: o número de tentativas de registros que não resultaram em um dispositivo totalmente registrado e em conformidade.
- Taxa incompleta: o percentual de tentativas de registro que foram abandonadas (registros abandonados/registros iniciados).

### <a name="line-graph"></a>Gráfico de linhas

O gráfico de linhas mostra os registros incompletos diários para cada uma das quatro seções de registro básicas:

- Lista de verificação de configuração
- Telas de plataforma
- Termos de uso
- Conformidade/Ativação

### <a name="user-abandonment-actions"></a>Ações de abandono de usuário

As tabelas a seguir mostram a lista de ações de usuário que se qualificam como aviso de um registro incompleto. Para ver exemplos de telas de registro, assista aos vídeos de registro do [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) e do [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment). 


#### <a name="setup-checklist-section"></a>Seção de lista de verificação de configuração

| Nome da ação | Tela ou fluxo | Plataforma | Ação |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Prompt para abrir a página no Portal da Empresa | iOS/Android | **Cancelar** |
| EnrollmentWrapUp | Tela de registro do dispositivo até o término do **Carregamento de recursos da empresa** | iOS/Android | Levou >30 minutos |
| DeviceCategory | Seleção de Categoria de Dispositivo (se configurada pelo administrador) até clicar em **Concluído** | iOS/Android | Levou >30 minutos |
| PreEnrollmentWizard | Configurar a tela de acesso quando tiver iniciado o registro, mas retornado para Configurar acesso | iOS/Android| **Adiar** |
| PreEnrollmentWizard | Configurar a tela de acesso até clicar em **Avançar** na tela **Próximas Etapas** | iOS/Android | Levou >30 minutos |

#### <a name="platform-screens-section"></a>Seção de telas de plataforma

| Nome da ação | Tela ou fluxo | Plataforma | Ação |
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

| Nome da ação | Tela ou fluxo | Plataforma | Ação |
| ---- |---- |---- |---- |
| TermsofUse | Termos de uso (se configurados pelo administrador) | iOS/Android | **Recusar Tudo** |
| TermsofUse | Termos de uso até **Aceitar Tudo** | iOS/Android | Levou >30 minutos |

#### <a name="complianceactivation-section"></a>Seção de Conformidade/Ativação

| Nome da ação | Tela ou fluxo | Plataforma | Ação |
| ---- |---- |---- |---- |
| Conformidade | A conformidade do dispositivo (se configurada pelo administrador) é mostrada como não verde na configuração de acesso após o registro| iOS/Android | **Adiar** |
| Conformidade | A conformidade do dispositivo é mostrada como não verde até ser atualizada para ser mostrada em verde | iOS/Android | Levou >30 minutos |
| Ativação | A ativação do registro (se configurada pelo administrador) é mostrada como não verde na configuração de acesso | iOS/Android | **Adiar** |
| Conformidade | A ativação do dispositivo é mostrada como não verde até ser atualizada para ser mostrada como verde | iOS/Android | Levou >30 minutos |

## <a name="next-steps"></a>Próximas etapas

Após verificar as taxas de registros incompletos, será possível examinar as [opções de registro](enrollment-options.md) para ver se você pode fazer alterações para melhorar o registro.
