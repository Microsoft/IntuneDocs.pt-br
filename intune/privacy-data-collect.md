---
title: Coleta de dados no Intune
description: Saiba como os dados pessoais são coletados no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1171740-936d-46a5-af37-f418bd6fa63e
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08066c0742ad4ad02f907e55cc84eb65068c9b99
ms.sourcegitcommit: c9725ddae6c0f82a491de27c87f240254d32716b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2019
ms.locfileid: "70986416"
---
# <a name="data-collection-in-intune"></a>Coleta de dados no Intune

Quando os usuários registram seus dispositivos corporativos ou pessoais usando o Intune, o Intune coleta e compartilha alguns dados pessoais. O Intune coleta dados pessoais das seguintes fontes:

- Uso do administrador do Intune no portal do Azure.
- Dispositivos do usuário final (quando ele se registra no gerenciamento do Intune e durante o uso).
- Contas de clientes em serviços de terceiros (de acordo com as instruções do administrador).
- Informações de diagnóstico, desempenho e uso.

Dessas fontes, o Intune coleta informações que se enquadram nas três seguintes categorias: [identificadas](#identified-data), [pseudoanonimizadas](#pseudonymized-data) e [agregadas](#aggregated-data).

> [!NOTE]
> Não vendemos os dados coletados por nossos serviços para terceiros por nenhum motivo.

## <a name="identified-data"></a>Dados identificados

A maioria dos dados pessoais coletados pelo Intune são dados identificados. Esses dados estão vinculados a um usuário, um dispositivo ou um aplicativo e são essenciais para a natureza do gerenciamento. Os dados identificados são usados para gerenciar o dispositivo e os aplicativos de um usuário e para provisionar o serviço Intune.

Os dados identificados coletados pelo Intune podem incluir, entre outros: 

- Informações do usuário
  - Exibição do nome do proprietário/usuário (o nome registrado pelo Azure do usuário, conforme identificado pela theAzureUserID)
  - Nome UPN ou endereço de email
  - Identificações do usuário de terceiros (como a AppleID)
- Informações de inventário de hardware
  - Nome do dispositivo
  - Fabricante
  - Sistema operacional
  - Número de série
  - Número IMEI
  - Endereço IP
  - MacAddress de Wi-Fi
  - ICCID
  - Número do telefone
- Informações do log de auditoria, incluindo dados sobre as seguintes atividades
  - assinaturas
  - Criar
  - Atualizar (editar)
  - Excluir
  - Atribuir
  - Tarefas remotas
- Informações de suporte
  - Informações de contato (nome, número de telefone, endereço de email)
  - Conversas por email com membros da equipe de suporte, de produto e/ou de experiência do cliente da Microsoft
- Informações de controle de acesso (o Intune usa esses dados para gerenciar o acesso a funções administrativas por meio de recursos, como o [Controle de Acesso Baseado em Função](role-based-access-control.md)).
  - Autenticadores estáticos (senha do cliente)
  - Chaves de privacidade para certificados 
- Dados da conta e do administrador
  - Nome e sobrenome do usuário administrador
  - Nome de usuário administrador
  - UPN (email)
  - Número do telefone
  - Endereço de email do proprietário da conta
  - ID do Active Directory de cada administrador de TI do cliente
  - Dados de pagamento para cobrança do cliente
  - Chave de assinatura
- Inventário de aplicativos, como
  - nome do aplicativo
  - Versão do
  - ID do aplicativo
  - tamanho
  - local de instalação
  - Os dados de inventário de aplicativo são coletados apenas quando são marcados pelo Administrador como um dispositivo corporativo ou se o recurso de aplicativo em conformidade está ativado.  
- IDs de locatário de terceiros do cliente, como a ID da Apple. 

## <a name="pseudonymized-data"></a>Dados pseudoanonimizados

Os dados pseudoanonimizados estão associados a um identificador exclusivo, normalmente, um número gerado pelo sistema que não pode, por conta própria, identificar uma pessoa, mas que é usado para fornecer os serviços empresariais para os usuários. 

Os dados pseudoanonimizados coletados pelo Intune podem incluir, entre outros: 

- Dados de diagnóstico, de desempenho e de uso vinculados a um usuário e/ou um dispositivo
  - O número de vezes que um recurso é usado
  - Os comandos fornecidos para o recurso
  - Tempo de resposta de um serviço
  - Taxas de sucesso de instalações e outros processos
  - Erros do aplicativo do Portal da Empresa do Intune
  - Identificadores de usuário e de dispositivo
  - Identificadores para fins de referência, correlação e gerenciamento 
- Dados do dispositivo não vinculados a um dispositivo ou um usuário (se esses dados estão vinculados a um dispositivo ou um usuário, o Intune trata-os como dados identificados)
  - ID do dispositivo Intune
  - ID do dispositivo do Azure Active Directory
  - ID de gerenciamento de dispositivo do Intune
  - ID do locatário
  - ID da Conta
  - ID do dispositivo EAS
  - IDs específicas à plataforma
  - AppleID para dispositivos iOS
  - Endereço Mac para dispositivos Mac
  - ID do Windows para dispositivos Windows
- Informações de aplicativo gerenciado
  - ID de aplicativo gerenciado
  - Marcação de dispositivo de aplicativo gerenciado
  - ID de gerenciamento de dispositivo do Intune
  - ID do dispositivo do Azure Active Directory
  - Chaves de criptografia

## <a name="aggregated-data"></a>Dados agregados

Os dados agregados são usados para provisionar e aprimorar o serviço Intune. 

Os dados agregados coletados pelo Intune podem incluir, entre outros: 

- Dados de uso do administrador em todos os locatários do Intune (por exemplo, controles do administrador selecionados ao interagir com o Console de administrador)
- Dados da conta de locatário (esses dados estão disponíveis na folha do Intune)
  - Número de dispositivos ou usuários registrados
  - Número de plataformas de dispositivo identificadas  
  - Número de dispositivos instalados
  - installedDeviceCount: o número de dispositivos nos quais o aplicativo está instalado.
  - notApplicableDeviceCount: o número de dispositivos aos quais o aplicativo não é aplicável.
  - notInstalledDeviceCount: o número de dispositivos aos quais o aplicativo é aplicável, mas não está instalado.
  - pendingInstallDeviceCount: o número de dispositivos aos quais o aplicativo é aplicável e a instalação está pendente.

## <a name="next-steps"></a>Próximas etapas

Saiba mais sobre como o Intune [armazena e processa](privacy-data-store-process.md) e [compartilha](privacy-data-secure-share.md) os dados pessoais. 
