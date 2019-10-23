---
title: Ações e opções do Intune compatíveis com o Registro de usuário da Apple
titleSuffix: Microsoft Intune
description: Saiba quais opções e ações do Intune são compatíveis com o Registro de usuário da Apple
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 96c802e76aab673aa6a9108dc0a14f553c26b96b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505409"
---
# <a name="intune-actions-and-options-supported-with-apple-user-enrollment"></a>Ações e opções do Intune compatíveis com o Registro de usuário da Apple

O Registro de usuário é compatível com um subconjunto de opções de gerenciamento de dispositivo. Se um perfil de configuração pré-existente for aplicado a um dispositivo de Registro de usuário, somente as configurações compatíveis com o Registro de usuário serão aplicadas a esse dispositivo.

## <a name="password-settings"></a>Configurações de senha

Em dispositivos de Registro de usuário, se você definir qualquer configuração de senha, as configurações de **Senhas simples** serão definidas automaticamente como **Bloquear** e será aplicado um PIN de seis dígitos.

Por exemplo, você define a configuração de **Expiração de senha** e envia por push essa política para os dispositivos registrados pelo usuário. Nos dispositivos, acontece o seguinte:
- A configuração de **Expiração de senha** é ignorada.
- Senhas simples, como `1111` ou `1234`, não são permitidas.
- É aplicado um PIN de seis dígitos.

## <a name="administrator-remote-device-actions-and-options"></a>Ações e opções de dispositivo remoto do administrador
Os administradores podem executar as seguintes ações e opções em dispositivos de Registro de usuário:
- Desativar
- Excluir
- Bloqueio remoto
- Sincronização

Não há suporte para nenhuma outra ação.

## <a name="end-user-actions"></a>Ações do usuário final
Em dispositivos de Registro de usuário, os usuários finais podem executar estas ações em seus dispositivos no site e aplicativo do Portal da Empresa:
- Renomear. Essa ação se aplica somente ao nome voltado para o usuário no Portal da Empresa. Ela não renomeará completamente o dispositivo fora desse contexto.
- Remover
- Bloqueio remoto
- Verificar status

## <a name="other-supported-options"></a>Outras opções compatíveis

As opções a seguir são compatíveis no Intune para dispositivos registrados usando o Registro de usuário da Apple:
- VPN por aplicativo. Esse suporte exclui os domínios do Safari, pois o Registro de usuário não é compatível com a definição das configurações do Safari.
- Wi-Fi 
- Remoção do aplicativo corporativo após o cancelamento do registro
- Implantação de aplicativo por meio do VPP (plano de compra por volume) licenciado pelo usuário
- Detecção de jailbreak

As seguintes restrições são compatíveis:
- Exibir documentos corporativos em aplicativos não gerenciados
- Exibir documentos não corporativos em aplicativos corporativos
- Permitir que aplicativos não gerenciados leiam contas de contatos gerenciadas
- AirDrop como um destino não gerenciado
- Backup criptografado necessário
- Sincronização de aplicativos gerenciados com a nuvem
- Acesso ao Centro de Controle quando o dispositivo estiver bloqueado
- Acesso ao Centro de Notificações quando o dispositivo estiver bloqueado
- Exibição Hoje quando o dispositivo está bloqueado
- Bloquear capturas de tela
- Bloquear o Backup do Catálogo da Empresa
- Bloquear a sincronização de metadados do Catálogo da Empresa
- Requer Backup com criptografia
- Exigir relógio com detecção de pulso
- Bloquear Siri
- Bloquear Siri enquanto o dispositivo está bloqueado
- Exigir avisos de fraude do Safari
- Bloquear o envio de diagnóstico para a Apple


## <a name="options-not-supported"></a>Opções não compatíveis
As opções a seguir não são compatíveis em dispositivos registrados com o Registro de usuário. Se você precisar dessas opções, confira Registro de dispositivo para dispositivos de propriedade pessoal ou Registro de dispositivo automatizado para dispositivos corporativos.
- Coletar o inventário de aplicativos para aplicativos fora do volume APFS gerenciado.
- Coletar inventário de certificados e perfis de provisionamento fora do volume APFS gerenciado.
- Coletar UDID e outros identificadores de dispositivos persistentes.
- O Registro de usuário é compatível com a ID de registro exclusiva para cada dispositivo registrado, mas essa ID não persiste após o cancelamento do registro.
- Os seguintes recursos do Intune não são compatíveis devido a essa limitação:
- Perfis de usuário SCEP com formato de nome de entidade do número de série.
- VPN no nível do dispositivo.
- Implantação de aplicativo VPP licenciado para dispositivo.
- Controle de MDM de aplicativos fora do volume APFS gerenciado.
- As políticas de proteção de aplicativo ainda serão aplicadas a esses aplicativos. No entanto, você não poderá assumir o gerenciamento ou implantar uma versão gerenciada desses aplicativos, a menos que o usuário os exclua do dispositivo.
- Ações, configurações, definições e comandos que exigem supervisão. 

## <a name="next-steps"></a>Próximas etapas

[Configurar o Registro de usuário do iOS e iPadOS](ios-user-enrollment.md)