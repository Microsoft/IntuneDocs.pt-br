---
title: "Solução de problemas com políticas | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: ac3417781df0a5b092a70620aa7343849b1e8c82
ms.openlocfilehash: 3ac6b06b7eb85503786b4d8b0b9bd2a30d2a15e6


---

# Solução de problemas com políticas no Microsoft Intune

Aqui estão relacionados alguns problemas que podem surgir da sua configuração de políticas do Microsoft Intune e as recomendações de solução para esses problemas.

Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.


## A política é aplicada a um usuário?
**Problema:** não está claro se uma determinada política está sendo aplicada a um dispositivo ou se um dispositivo se comporta de forma contrária a ela.

Verifique as informações de política disponíveis para cada dispositivo para entender como uma política afeta um determinado dispositivo.

No console de administração do Intune, cada dispositivo tem uma guia de política em **Propriedades do Dispositivo**. Se não, o dispositivo ainda pode estar no processo de registro ou pode não ter políticas aplicadas. Cada política tem um **Valor Pretendido** e um **Status**. O valor pretendido é o que você quis realizar ao atribuir a política. O status é o que realmente é realizado quando todas as politicas que se aplicam ao dispositivo, bem como as restrições e requisitos de hardware e sistema operacional, são consideradas em conjunto. Os status possíveis são:

-   **Conformidade**: o dispositivo recebeu a política e relatórios do serviço de que está de acordo com a configuração.

-   **Não aplicável**: a configuração de política não é aplicável. Por exemplo, configurações de email para dispositivos iOS não se aplicariam a um dispositivo Android.

-   **Pendente**: a política foi enviada para o dispositivo, mas não relatou seu status para o serviço. Por exemplo, a criptografia no Android exige que o usuário habilite a criptografia e, portanto, pode estar pendente.

Na captura de tela abaixo, você pode ver dois exemplos claros:

-   **Permitir senhas simples** é definido como **Sim**, conforme mostrado na coluna **Valor Pretendido** , mas o **Status** é **Não aplicável**. Isso ocorre porque senhas simples não têm suporte para dispositivos Android.

-   Da mesma forma, o item de política expandido **Configurações de email para dispositivos iOS** não é aplicado a esse dispositivo, pois se trata de um dispositivo Android.

![Política de dispositivo Intune](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> [!NOTE] Lembre-se de que, quando duas políticas com diferentes níveis de restrição aplicam-se ao mesmo dispositivo ou usuário, a política mais restritiva se aplica na prática.

## Atualização de política e intervalos de atualização
Lembre-se de que as políticas são atualizadas em intervalos regulares. Em geral, as políticas devem ser registradas em dispositivos dentro de 15 minutos depois de fazer uma alteração. Aqui estão mais detalhes sobre os intervalos regulares para atualização de política:

-   **Dispositivo Windows registrado para o MDM**: a política é atualizada a cada 8 horas para dispositivos Windows 8.1 e Windows 10 e a cada 24 horas para dispositivos Windows RT.

-   **Windows Phone**: a política é atualizada a cada 8 horas. Isso pode ser forçado por uma atualização no Portal da Empresa, em **Configurações**.

-   **iOS**: a política é atualizada uma vez por dia em um intervalo de tempo aleatório. Isso também pode ser forçado abrindo o Portal da Empresa, selecionando o dispositivo e escolhendo **Sincronização**.

-   **Android**: a política é atualizada uma vez por dia em um intervalo de tempo aleatório. Isso também pode ser forçado abrindo o Portal da Empresa, selecionando o dispositivo e escolhendo **Sincronização**.

## Erros relacionados à política do Microsoft Intune em policyplatform.log
Para dispositivos do Windows não MDM, erros de política no arquivo policyplatform.log podem ser o resultado de configurações não padrão no UAC (Controle de Conta de Usuário) do Windows no dispositivo. Algumas configurações de UAC não padrão podem afetar as instalações de cliente do Microsoft Intune e a execução da política.

### Para resolver problemas do UAC

1.  Desative o computador, conforme descrito em [Retire devices from Microsoft Intune management](/intune/deploy-use/retire-devices-from-microsoft-intune-management) (Desativar dispositivos do gerenciamento do Microsoft Intune).

2.  Espere 20 minutos para o software cliente ser removido.

    > [!NOTE]
    > [!NOTE] Não tente remover o cliente em Programas e Recursos.

3.  No menu Iniciar, digite **UAC** para abrir as configurações de Controle de Conta de Usuário.

4.  Mova o controle deslizante de notificação para a configuração padrão.

## Erro 0x87D1FDE8 para dispositivo KNOX
**Problema**: depois de criar e implantar um perfil de email do Exchange Active Sync para Samsung KNOX para vários dispositivos Android, eles reportam o erro **0x87D1FDE8** ou **falha na correção** na guia Política das &gt; propriedades do dispositivo.

Examine a configuração do seu perfil de EAS para Samsung KNOX e a política de origem. Não há suporte para a opção de sincronização das Samsung Notes e essa opção não deve estar selecionada em seu perfil. Certifique-se de que os dispositivos tiveram tempo suficiente, se até 24 horas, para processar a política.

## Alerta: falha ao salvar regras de acesso ao Exchange
**Problema**: você recebe o alerta **Falha ao salvar as regras de acesso ao Exchange**  no console do administrador.

Se você criou as políticas no espaço de trabalho de Políticas do Exchange local, no Console de administração, mas estiver usando o O365, as configurações definidas para a política não serão impostas pelo Intune. Observe a origem da política no alerta.  No espaço de trabalho de Política do Exchange local, exclua as regras herdadas, pois elas são regras globais do Exchange no Intune para o Exchange local e não são relevantes para o O365. Em seguida, crie uma nova política para o O365.

## ERRO: Não é possível obter o valor do computador, 0x80041013
Isso poderá ocorrer se a hora do sistema local estiver fora de sincronia por cinco minutos ou mais. Se a hora no computador local estiver fora de sincronia, transações seguras falharão porque os carimbos de data/hora serão inválidos.

Para resolver esse problema, defina a hora do sistema local o mais próximo possível do horário da Internet ou do horário definido nos controladores de domínio na rede.

## Não é possível alterar a política de segurança para vários dispositivos MDM
Dispositivos Windows Phone e Windows RT não permitem que políticas de segurança definidas por meio do MDM ou EAS sejam reduzidas em termos de segurança após terem sido configuradas. Por exemplo, você define um **Número mínimo de caracteres de senha** para 8 e tenta reduzi-lo a 4. A política mais restritiva já foi aplicada ao dispositivo.

Dependendo da plataforma do dispositivo, se você quiser alterar a política para um valor menos seguro, pode ser necessário redefinir as políticas de segurança.
Por exemplo, no Windows RT, na área de trabalho, passe o dedo da direita para a esquerda para abrir a barra **Botões** e escolha **Configurações** &gt; **Painel de Controle**.  Selecione o miniaplicativo **Contas de Usuário** .
No menu de navegação à esquerda, há um link **Redefinir Políticas de Segurança** na parte inferior. Escolha-o e clique no botão **Redefinir Políticas**.
Outros dispositivos MDM, como Android, Windows Phone 8.1 e posterior e iOS, precisarão ser desativados e registrados novamente no serviço para que você possa aplicar uma política menos restritiva.

## Dispositivos Android não forçam alterações de política de segurança sem aceitação do usuário final
O MDM para Android não permite que o serviço force alterações de política iniciais nos dispositivos como as outras plataformas permitem. Isso se deve à funcionalidade do Android e não está relacionado ao serviço do Intune. Dispositivos com Android solicitarão ao usuário final por meio da janela de notificação de alteração da política relacionada (ou seja, senha, criptografia etc.)  O usuário final deve responder à solicitação e, uma vez aceita, a política deve ser aplicada.

## Não é possível criar a política ou registrar os clientes se o nome da empresa contiver caracteres especiais
**Problema:** não é possível criar a política ou registrar os clientes.

**Resolução:** no [Centro de administração do Office 365](https://portal.office.com/), remova os caracteres especiais do nome da empresa e salve as informações da empresa.

### Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).



<!--HONumber=Jul16_HO2-->


