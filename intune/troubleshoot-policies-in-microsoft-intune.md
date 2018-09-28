---
title: Solução de problemas com políticas no Microsoft Intune – Azure | Microsoft Docs
description: Problemas comuns e resoluções ao usar políticas no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d656dcc8c3abcf3a4b0a9c6aacbc42eb896289f
ms.sourcegitcommit: 7c70c3e0fcae7c4fa8c9e108aafb1cebb366332d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44096482"
---
# <a name="troubleshoot-policies-in-intune"></a>Solucionar problemas de políticas no Intune

Se você estiver com problemas ao implantar e gerenciar políticas do Intune, comece aqui. Este artigo descreve alguns problemas comuns que você pode enfrentar e possíveis soluções.

## <a name="general-issues"></a>Problemas gerais

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Uma política implantada foi aplicada ao dispositivo?
**Problema:** você não tem certeza se uma política foi aplicada corretamente.

Em Intune > **Dispositivos** > **Todos os dispositivos** > selecione o dispositivo > **Configuração do dispositivo**, todos os dispositivos listam suas políticas. Cada política tem um **Status**. O status é aplicado quando todas as politicas que se aplicam ao dispositivo, incluindo as restrições e requisitos de hardware e sistema operacional, são consideradas em conjunto. Os status possíveis são:

- **Conformidade**: o dispositivo recebeu a política e relatórios do serviço de que está de acordo com a configuração.

- **Não aplicável**: a configuração de política não é aplicável. Por exemplo, configurações de email para dispositivos iOS não se aplicariam a um dispositivo Android.

- **Pendente**: a política foi enviada para o dispositivo, mas não relatou o status para o serviço. Por exemplo, a criptografia no Android exige que o usuário habilite a criptografia e, portanto, pode ser mostrada como pendente.

> [!NOTE]
> Quando duas políticas com diferentes níveis de restrição aplicam-se ao mesmo dispositivo ou usuário, a política mais restritiva é aplicada.

## <a name="issues-with-enrolled-devices"></a>Problemas com dispositivos registrados

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Alerta: falha ao salvar regras de acesso ao Exchange
**Problema**: você recebe o alerta **Falha ao salvar as regras de acesso ao Exchange** no console do administrador.

Se você tiver criado as políticas no espaço de trabalho de Políticas do Exchange local, no Console de Administração, mas estiver usando o O365, as configurações definidas para a política não serão impostas pelo Intune. Observe a origem da política no alerta.  No espaço de trabalho de Políticas do Exchange local, exclua as regras herdadas. Elas são regras globais do Exchange no Intune para o Exchange local e não são relevantes para o O365. Em seguida, crie uma nova política para o O365.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Não é possível alterar a política de segurança para vários dispositivos registrados
Os dispositivos Windows Phone não permitem que políticas de segurança definidas por meio do MDM ou EAS sejam reduzidas em termos de segurança após terem sido configuradas. Por exemplo, você define um **Número mínimo de caracteres de senha** para 8 e tenta reduzi-lo a 4. A política mais restritiva já foi aplicada ao dispositivo.

Dependendo da plataforma do dispositivo, se você quiser alterar a política para um valor menos seguro, pode ser necessário redefinir as políticas de segurança.

Por exemplo, no Windows, na área de trabalho, passe o dedo da direita para a esquerda para abrir a barra **Botões**. Escolha **Configurações** > **Painel de Controle** e selecione **Contas de Usuário**. À esquerda, selecione o link **Redefinir Políticas de Segurança** e, em seguida, escolha **Redefinir Políticas**.

Outros dispositivos MDM, como Android, Windows Phone 8.1 e posterior e iOS, precisarão ser desativados e registrados novamente no serviço para aplicar uma política menos restritiva.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Problemas com computadores que executam o cliente de software do Intune

Aplica-se ao portal clássico.

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Erros relacionados à política do Microsoft Intune em policyplatform.log
Para computadores com Windows gerenciados com o cliente de software do Intune, erros de política no arquivo policyplatform.log podem ser o resultado de configurações não padrão no UAC (Controle de Conta de Usuário) do Windows no dispositivo. Algumas configurações de UAC não padrão podem afetar as instalações de cliente do Microsoft Intune e a execução da política.

#### <a name="resolve-uac-issues"></a>Resolver problemas do UAC

1. Desative o computador. Veja [Remover dispositivos](devices-wipe.md).

2. Espere 20 minutos para o software cliente ser removido.

    > [!NOTE]
    > Não tente remover o cliente em Programas e Recursos.

3. No menu Iniciar, digite **UAC** para abrir as configurações de Controle de Conta de Usuário.

4. Mova o controle deslizante de notificação para a configuração padrão.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>ERRO: Não é possível obter o valor do computador, 0x80041013
Ocorrerá se a hora do sistema local estiver fora de sincronia por cinco minutos ou mais. Se a hora no computador local estiver fora de sincronia, transações seguras falharão porque os carimbos de data/hora serão inválidos.

Para resolver esse problema, defina a hora do sistema local o mais próximo possível do horário da Internet ou do horário definido nos controladores de domínio na rede.

### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [obter suporte para o Microsoft Intune](get-support.md).
