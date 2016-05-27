---
# required metadata

title: Implantar e monitorar política de conformidade no Microsoft Intune | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Implantar e monitorar política de conformidade de dispositivo no Microsoft Intune
## Implantar uma política de conformidade
Implante a política de conformidade [criada](create-a-device-compliance-policy-in-microsoft-intune.md) para um ou mais grupos de usuários ou dispositivos em sua organização.

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.
![Captura de tela da página de política de conformidade, mostrando a opção de menu Gerenciar Implantação na parte superior](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  Na caixa de diálogo **Gerenciar Implantação**, escolha um ou mais grupos para os quais deseja implantar a política, e clique em **Adicionar > OK**.
![Captura de tela da caixa de diálogo gerenciar implantação](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png)
Você pode implantar uma política de conformidade para usuários e/ou dispositivos. Use os grupos do Active Directory que você já criou e sincronizado com o Intune ou crie esses grupos manualmente no console do Intune. Para saber mais sobre como implantar políticas, consulte [implantar uma política de configuração](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Use o resumo de status e alertas na página **Visão geral** do espaço de trabalho **Política** para identificar problemas com a política que exigem atenção. Além disso, um resumo de status aparece no espaço de trabalho **Painel** .

> [!IMPORTANT]Se você habilitar a política de acesso condicional do Exchange sem ter antes implantado uma política de conformidade, todos os dispositivos de destino terão o acesso permitido.

## Como os conflitos de política do Intune são resolvidos
Podem ocorrer conflitos de política quando várias políticas Intune são aplicadas a um dispositivo. Se as configurações de política se sobrepuserem, o Intune resolverá os conflitos usando as seguintes regras:

-   Se as configurações conflitantes são de uma política de configuração do Intune e uma política de conformidade, as configurações na política de conformidade têm precedência sobre as configurações na política de configuração, mesmo que as configurações na política de configuração sejam mais seguras.

-   Se você tiver implantado várias políticas de conformidade, a mais segura dessas políticas será usada.

## Monitorar a política de conformidade

#### Para exibir os dispositivos que não estão de acordo com uma política de conformidade

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), acesse **Grupos > Todos os Dispositivos**.

2.  Clique duas vezes no nome de um dispositivo na lista de dispositivos.

3.  Escolha a guia **Política** para ver uma lista de políticas para esse dispositivo.

4.  Na lista suspensa **Filtros**, selecione **Não está em conformidade com a política de conformidade**.
![Captura de tela mostrando a lista de opções na lista de filtros](./media/intune-sa-3e-view-device-noncompliance.png)

#### Para exibir os Relatórios de Atestado de Integridade

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Relatórios**.

2.  Na página **Relatório de Atestado de Integridade - Criar um Novo Relatório**, você pode exibir um relatório com todos os dados do atestado de integridade do Windows 10 coletados pelo Intune. Você também pode criar um relatório com um subconjunto dos dados usando filtros. Os filtros podem ser baseados no tipo de dispositivo, sistema operacional ou apenas um subconjunto de pontos de dados.


## Próximas etapas
Agora, você pode usar a política de conformidade com políticas de acesso condicional para controlar o acesso a serviços em sua organização.

[Restringir o acesso ao email e aos serviços do O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


### Consulte também
[Introdução a políticas de conformidade de dispositivo no Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->

