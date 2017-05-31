---
title: "Solucionar problemas de políticas | Microsoft Docs"
description: "Solucione problemas de configuração de política."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 91aaf9fb442ecdc43eb7e6ec5ed71a8ead72350c
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="troubleshoot-policies-in-microsoft-intune"></a>Solução de problemas com políticas no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Se você estiver tendo problemas ao implantar e gerenciar políticas do Intune, comece aqui. Este tópico contém alguns problemas comuns que podem ocorrer, juntamente com as soluções.

## <a name="general-issues"></a>Problemas gerais

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Uma política implantada foi aplicada ao dispositivo?
**Problema:** você não tem certeza se uma política foi aplicada corretamente.

No console de administração do Intune, cada dispositivo tem uma guia de política em **Propriedades do Dispositivo**. Cada política tem um **Valor Pretendido** e um **Status**. O valor pretendido é o que você quis realizar ao atribuir a política. O status é o que realmente é aplicado quando todas as politicas que se aplicam ao dispositivo, bem como as restrições e requisitos de hardware e sistema operacional, são consideradas em conjunto. Os status possíveis são:

-   **Conformidade**: o dispositivo recebeu a política e relatórios do serviço de que está de acordo com a configuração.

-   **Não aplicável**: a configuração de política não é aplicável. Por exemplo, configurações de email para dispositivos iOS não se aplicariam a um dispositivo Android.

-   **Pendente**: a política foi enviada para o dispositivo, mas não relatou seu status para o serviço. Por exemplo, a criptografia no Android exige que o usuário habilite a criptografia e, portanto, pode estar pendente.

Na captura de tela abaixo, você pode ver dois exemplos claros:

-   **Permitir senhas simples** é definido como **Sim**, conforme mostrado na coluna **Valor Pretendido**, mas o **Status** é **Não aplicável**. Isso ocorre porque senhas simples não têm suporte para dispositivos Android.

-   Da mesma forma, o item de política expandido **Configurações de email para dispositivos iOS** não é aplicado a esse dispositivo, pois se trata de um dispositivo Android.

![Política de dispositivo Intune](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Lembre-se de que, quando duas políticas com diferentes níveis de restrição aplicam-se ao mesmo dispositivo ou usuário, a política mais restritiva se aplica na prática.


## <a name="issues-with-enrolled-devices"></a>Problemas com dispositivos registrados

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Alerta: falha ao salvar regras de acesso ao Exchange
**Problema**: você recebe o alerta **Falha ao salvar as regras de acesso ao Exchange** no console do administrador.

Se você criou as políticas no espaço de trabalho de Políticas do Exchange local, no Console de administração, mas estiver usando o O365, as configurações definidas para a política não serão impostas pelo Intune. Observe a origem da política no alerta.  No espaço de trabalho de Política do Exchange local, exclua as regras herdadas, pois elas são regras globais do Exchange no Intune para o Exchange local e não são relevantes para o O365. Em seguida, crie uma nova política para o O365.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Não é possível alterar a política de segurança para vários dispositivos registrados
Dispositivos Windows Phone não permitem que políticas de segurança definidas por meio do MDM ou EAS sejam reduzidas em termos de segurança após terem sido configuradas. Por exemplo, você define um **Número mínimo de caracteres de senha** para 8 e tenta reduzi-lo a 4. A política mais restritiva já foi aplicada ao dispositivo.

Dependendo da plataforma do dispositivo, se você quiser alterar a política para um valor menos seguro, pode ser necessário redefinir as políticas de segurança.
Por exemplo, no Windows, na área de trabalho, passe o dedo da direita para a esquerda para abrir a barra **Botões** e escolha **Configurações** &gt; **Painel de Controle**.  Selecione o miniaplicativo **Contas de Usuário**.
No menu de navegação à esquerda, há um link **Redefinir Políticas de Segurança** na parte inferior. Escolha-o e clique no botão **Redefinir Políticas**.
Outros dispositivos MDM, como Android, Windows Phone 8.1 e posterior e iOS, precisarão ser desativados e registrados novamente no serviço para que você possa aplicar uma política menos restritiva.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Problemas com computadores que executam o cliente de software do Intune

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Erros relacionados à política do Microsoft Intune em policyplatform.log
Para computadores com Windows gerenciados com o cliente de software do Intune, erros de política no arquivo policyplatform.log podem ser o resultado de configurações não padrão no UAC (Controle de Conta de Usuário) do Windows no dispositivo. Algumas configurações de UAC não padrão podem afetar as instalações de cliente do Microsoft Intune e a execução da política.

#### <a name="to-resolve-uac-issues"></a>Para resolver problemas do UAC

1.  Desative o computador, conforme descrito em [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management) (Desativar dispositivos do gerenciamento do Microsoft Intune).

2.  Espere 20 minutos para o software cliente ser removido.

    > [!NOTE]
    > Não tente remover o cliente em Programas e Recursos.

3.  No menu Iniciar, digite **UAC** para abrir as configurações de Controle de Conta de Usuário.

4.  Mova o controle deslizante de notificação para a configuração padrão.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>ERRO: Não é possível obter o valor do computador, 0x80041013
Isso poderá ocorrer se a hora do sistema local estiver fora de sincronia por cinco minutos ou mais. Se a hora no computador local estiver fora de sincronia, transações seguras falharão porque os carimbos de data/hora serão inválidos.

Para resolver esse problema, defina a hora do sistema local o mais próximo possível do horário da Internet ou do horário definido nos controladores de domínio na rede.








### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).

