---
title: "Monitorar as políticas de conformidade do dispositivo do Intune"
titlesuffix: Azure portal
description: "Saiba como monitorar políticas de conformidade do dispositivo."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 999cb6a9ec37c42b216cda1f6963bbd61ec8fa66
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorar as políticas de conformidade do Dispositivo do Intune

Os relatórios de conformidade ajudam os administradores a analisarem as condições de conformidade dos dispositivos em sua organização e solucionarem rapidamente os problemas relacionados à conformidade encontrados pelos usuários em sua organização. Você pode exibir informações sobre o estado de conformidade geral dos dispositivos, estado de conformidade de uma configuração individual, estado de conformidade de uma política individual e fazer uma busca detalhada nos dispositivos individuais para exibir as configurações específicas e políticas que afetam o dispositivo.

## <a name="before-you-begin"></a>Antes de começar

Siga as etapas abaixo para encontrar o **painel de conformidade do Dispositivo do Intune** no portal do Azure:

1.  Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune.

2.  Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3.  Escolha **Intune** &gt; **Conformidade do dispositivo** &gt; **Visão Geral**,então, o **Painel de conformidade do dispositivo** será aberto.

> [!IMPORTANT] 
> Os dispositivos devem ser registrados no Intune para receber as políticas de conformidade do dispositivo.

## <a name="device-compliance-dashboard"></a>Painel de conformidade do dispositivo

No **Painel de conformidade do dispositivo**, você pode monitorar os estados da política de conformidade do Dispositivo, que fornecem relatórios diferentes em blocos diferentes que dão a condição de conformidade dos dispositivos em sua organização. Você pode exibir os seguintes relatórios:

-   Conformidade geral do dispositivo agregada

-   Conformidade do dispositivo por política

-   Conformidade do dispositivo por configuração

![Painel de conformidade do dispositivo](./media/idc-1.png)

Você também pode exibir as políticas específicas de conformidade e as configurações que se aplicam a um dispositivo individual e o estado de conformidade final para cada uma dessas configurações no dispositivo.

### <a name="overall-device-compliance-aggregate-report"></a>Relatório da conformidade geral do dispositivo agregada

É um gráfico de rosca mostrando o estado de conformidade agregada para todos os dispositivos do Intune registrados. Os estados de conformidade do dispositivo são mantidos em dois bancos de dados diferentes, o Intune e o Azure Active Directory. Mais detalhes sobre os estados da política de conformidade do dispositivo:

-   **Compatível**: o dispositivo aplicou com êxito uma ou mais configurações da política de conformidade do dispositivo direcionadas pelo administrador.

-   **Incompatível:** o dispositivo falhou ao aplicar uma ou mais configurações da política de conformidade do dispositivo direcionadas pelo administrador ou o usuário não está em conformidade com as políticas direcionadas pelo administrador.

-   **Período de cortesia:** o dispositivo foi direcionado pelo administrador com uma ou mais configurações da política de conformidade do dispositivo, mas o usuário não aplicou as políticas ainda, significando que o dispositivo é incompatível, mas ele está no período de cortesia definido pelo administrador.

    -   Saiba mais sobre as Ações dos dispositivos incompatíveis.

-   **Dispositivo não sincronizado:** o dispositivo falhou ao relatar seu status da política de conformidade do dispositivo por um dos seguintes motivos:

    -   **Desconhecido**: o dispositivo está offline ou falhou ao se comunicar com o Intune ou o Azure AD por outras razões.

    -   **Erro**: o dispositivo falhou ao se comunicar com o Intune e o Azure AD, e recebeu uma mensagem de erro com o motivo.

> [!IMPORTANT] 
> Os dispositivos registrados no Intune, mas não direcionados por quaisquer políticas de conformidade do dispositivo, serão incluídos neste relatório no bloco **Compatível**.

#### <a name="drill-down-option"></a>Opção de detalhamento

No **Painel de conformidade do dispositivo**, se você clicar no bloco Conformidade do dispositivo, poderá fazer uma busca detalhada em um determinado **status de conformidade**, **alias de email do usuário**, **modelo de dispositivo** e **local** para cada dispositivo que foi direcionado pelas políticas de conformidade do dispositivo.

![Busca detalhada do painel de conformidade do dispositivo](./media/idc-2.png)

Se você precisar de mais detalhes sobre um usuário específico, poderá filtrar o relatório do Gráfico de conformidade do dispositivo digitando o alias de email do usuário.

![Usuário específico do painel de conformidade do dispositivo](./media/idc-3.png)

Você também pode clicar no status de conformidade diferente no Gráfico de conformidade do dispositivo para ver mais detalhes sobre os status da política de conformidade dos dispositivos do usuário.

![Status diferentes do painel de conformidade do dispositivo](./media/idc-4.png)

#### <a name="filter"></a>Filter

Se você clicar no **botão Filtrar**, o filtro suspenso será aberto com as seguintes opções:

-   Modelo

    -   Caixa de texto que aceita uma cadeia de caracteres de pesquisa livre
<br></br>
-   Plataforma

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   Status

    -   Compatível

    -   Incompatível

    -   Período de cortesia

    -   Unknown

    -   Erro do

Se você clicar no **botão Atualizar**, o menu suspenso deverá fechar e os resultados deverão ser atualizados de acordo com os critérios do filtro selecionados.

##### <a name="device-details"></a>Detalhes do dispositivo

Clicar em um dispositivo abre o **Folha de Dispositivos** com o dispositivo selecionado. Isso fornece mais detalhes sobre a configuração da política de conformidade do dispositivo aplicada nesse dispositivo.

![Painel de conformidade do dispositivo](./media/idc-6.png)

Quando você clica na própria configuração da política do dispositivo, pode ver que o nome da política de conformidade do dispositivo originou essa configuração de conformidade do dispositivo direcionada pelo administrador.

![Nome da configuração da conformidade do dispositivo](./media/idc-7.png)

### <a name="per-policy-device-compliance-report"></a>Relatório de conformidade do dispositivo por política

Este relatório fornece uma exibição da política por conformidade e o número total de dispositivos em cada estado de conformidade. O título **Conformidade da política** está disponível no **Painel de conformidade do dispositivo** e mostra todas as políticas criadas anteriormente pelo administrador, as plataformas nas quais a política é aplicada e o número de dispositivos compatíveis e incompatíveis.

![Relatório de conformidade do dispositivo por política](./media/idc-8.png)

Quando você clicar no bloco de Conformidade da política, então, clicar em uma das políticas de conformidade do dispositivo, poderá ver o **status de conformidade**, **alias de email do usuário**, **modelo do dispositivo** e **local** de cada dispositivo que foi direcionado por essa política de conformidade do dispositivo.

![Bloco de conformidade da política](./media/idc-9.png)

### <a name="per-setting-device-compliance-report"></a>Relatório de conformidade do dispositivo por configuração

Este relatório permite exibir - a configuração por conformidade - o número total de dispositivos em cada estado de conformidade. O título **Conformidade das configurações** está disponível no **painel de Conformidade do dispositivo** e mostra todas as configurações da política de conformidade do dispositivo a partir de todas as políticas de conformidade do dispositivo criadas pelo administrador, as plataformas nas quais as configurações da política foram aplicadas e o número de dispositivos incompatíveis.

![Relatório de conformidade do dispositivo por configuração](./media/idc-10.png)

Quando você clicar no bloco de Conformidade da configuração, então, clicar em uma das configurações da política de conformidade do dispositivo, conseguirá ver o **status de conformidade**, **alias de email do usuário**, **modelo do dispositivo** e **local** de cada dispositivo que foi direcionado por essa configuração da política de conformidade do dispositivo.

![Bloco de conformidade da configuração](./media/idc-11.png)
