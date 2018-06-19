---
title: Dados enviados pelo Intune à Google
titleSuffix: Microsoft Intune
description: Lista de dados que o Intune envia para o Google.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ed713e63b63b4eb4a2696e9fd53b39cb139b4115
ms.sourcegitcommit: 2162ed46d939b4a9b85fa4e7e9943f2fb5948f1e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2018
ms.locfileid: "31617253"
---
# <a name="data-intune-sends-to-google"></a>Dados enviados pelo Intune à Google

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Quando o gerenciamento de dispositivo Android enterprise está habilitado em um dispositivo, o Microsoft Intune estabelece uma conexão com o Google e compartilha informações do usuário e do dispositivo com o Google. Antes que o Microsoft Intune estabeleça uma conexão, você deve criar uma conta do Google.

A tabela a seguir lista os dados que o Microsoft Intune envia ao Google quando o gerenciamento de dispositivo está habilitado em um dispositivo:


| Dados enviados ao Google | Detalhes | Usada para | Exemplo |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Com origem no Google, após a associação da sua conta do Gmail com o Intune. | Identificador primário usado para comunicação entre o Intune e o Google.  Essa comunicação inclui configuração de políticas, gerenciamento de dispositivos e associação/desassociação do Android Empresa com o Intune. | Identificador exclusivo; formato de exemplo: LC04eik8a6 |
| Corpo da política | Com origem no Intune ao salvar uma nova política de aplicativo ou de configuração. | Aplicação de políticas a dispositivos. | Esta é uma coleção de todas as configurações definidas para uma política de aplicativo ou de configuração. Ela pode conter informações do cliente, se fornecidas como parte de uma política, como: nomes de rede, nomes de aplicativos e configurações específicas de aplicativo. |
| Dados do dispositivo | Dispositivos para cenários de perfil corporativo começam com o registro no Intune. Dispositivos para cenários de dispositivo gerenciado começam com o registro no Google. | As informações de dados do dispositivo são enviadas entre o Intune e o Google para várias ações como a aplicação de políticas, o gerenciamento do dispositivo e relatórios em geral. | **Identificador exclusivo para representar o Nome do dispositivo.** Examplo: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Identificador exclusivo para representar o Nome de usuário.** Examplo: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Estado do dispositivo.** Exemplos: Ativo, Desabilitado, Em Provisionamento.<br>**Estados de conformidade.** Exemplos: configuração não compatível, aplicativos necessários ausentes<br>**Informações de software.** Exemplos: versões de software e o nível de patch.<br>**Informações de rede.** Exemplos: IMEI, MEID, WifiMacAddress<br>**Configurações do dispositivo.** Exemplos: informações sobre níveis de criptografia e se o dispositivo permite aplicativos desconhecidos.<br> Veja abaixo um exemplo de uma mensagem JSON. |
| newPassword | Com origem no Intune. | Redefinição da senha do dispositivo. | Cadeia de caracteres que representa a nova senha. |
| Usuário Google | Google | Gerenciamento do perfil corporativo para cenários de Perfil Corporativo (BYOD). | Identificador exclusivo para representar a conta do Gmail vinculada. Exemplo: 114223373813435875042 |
| Dados de Aplicativos | Com origem no Intune, ao salvar a política de aplicativo. |  | Cadeia de caracteres de Nome do aplicativo. Exemplo: app:com.microsoft.windowsintune.companyportal |
| Conta de serviço da empresa | Com origem no Google mediante solicitação do Intune. | Usada para autenticação entre o Intune e o Google para transações que envolvem este cliente. | Há várias partes:<br> **ID da empresa**: documentada anteriormente.<br>**UPN**: UPN gerado, usado na autenticação em nome do cliente.<br>Exemplo: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Chave**: blob codificado em Base64, usado em solicitações de autenticação, armazenado criptografado no serviço, mas esta é a aparência do blob:<br> Identificador exclusivo para representar a chave do cliente<br>Exemplo: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |


Para parar de usar o gerenciamento de dispositivos Android enterprise com o Microsoft Intune e excluir os dados, você deve desabilitar o gerenciamento de dispositivos Android enterprise do Microsoft Intune e também excluir a sua conta do Google. Consulte a conta do Google para saber como executar o gerenciamento de contas.


