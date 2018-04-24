---
title: Monitorar as políticas de conformidade de dispositivo do Microsoft Intune
titlesuffix: ''
description: Use o painel de conformidade de dispositivos para monitorar a conformidade geral dos dispositivos, exibir relatórios e exibir a conformidade dos dispositivos por política e por configuração.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 2/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 557018264da5c21459e47e3e139ddd327a4a5ea6
ms.sourcegitcommit: c3ae3c3dc46b62d9191813d25a196874ba4927be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorar as políticas de conformidade do Dispositivo do Intune

Os relatórios de conformidade ajudam os administradores a analisar as condições de conformidade dos dispositivos na organização e solucionar rapidamente os problemas relacionados à conformidade encontrados pelos usuários da organização. Você pode exibir informações sobre o estado de conformidade geral dos dispositivos, estado de conformidade de uma configuração individual, estado de conformidade de uma política individual e fazer uma busca detalhada nos dispositivos individuais para exibir as configurações específicas e políticas que afetam o dispositivo.

> [!NOTE]
> Em março, incluímos alguns aprimoramentos de segurança no serviço do Intune com base em seus comentários. Dependendo de como as políticas de conformidade estão configuradas, talvez seja necessário tomar medidas para evitar a perda de acesso ao email para os usuários finais. Para obter detalhes, veja [Futuros aprimoramentos de segurança](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

## <a name="before-you-begin"></a>Antes de começar

Siga estas etapas para encontrar o **Painel de conformidade de dispositivos do Intune** no portal do Azure:

1.  Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune.

2.  Escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3.  Escolha **Intune** &gt; **Conformidade do dispositivo** &gt; **Visão Geral**,então, o **Painel de conformidade do dispositivo** será aberto.

> [!IMPORTANT]
> Os dispositivos devem ser registrados no Intune para receber as políticas de conformidade do dispositivo.

## <a name="device-compliance-dashboard"></a>Painel de conformidade do dispositivo

No **Painel de conformidade de dispositivo**, você pode monitorar os estados da política de Conformidade do dispositivo, que fornecem vários relatórios em blocos diferentes, demonstrando a condição de conformidade dos dispositivos em sua organização. Você pode exibir os seguintes relatórios:

-   Conformidade geral do dispositivo agregada

-   Conformidade do dispositivo por política

-   Conformidade do dispositivo por configuração

![Imagem mostrando o Painel de conformidade de dispositivos](./media/idc-1.png)

Você também pode exibir as políticas específicas de conformidade e as configurações que se aplicam a um dispositivo individual e o estado de conformidade final para cada uma dessas configurações no dispositivo.

### <a name="overall-device-compliance-aggregate-report"></a>Relatório da conformidade geral do dispositivo agregada

É um gráfico de rosca mostrando o estado de conformidade agregada para todos os dispositivos do Intune registrados. Os estados de conformidade do dispositivo são mantidos em dois bancos de dados diferentes, o Intune e o Azure Active Directory. Mais detalhes sobre os estados da política de conformidade do dispositivo:

-   **Compatível**: o dispositivo aplicou com êxito uma ou mais configurações da política de conformidade do dispositivo direcionadas pelo administrador.

-   **Incompatível:** o dispositivo falhou ao aplicar uma ou mais configurações da política de conformidade do dispositivo direcionadas pelo administrador ou o usuário não está em conformidade com as políticas direcionadas pelo administrador.

-   **Período de cortesia:** o dispositivo foi direcionado pelo administrador com uma ou mais configurações da política de conformidade do dispositivo, mas o usuário não aplicou as políticas ainda, significando que o dispositivo é incompatível, mas ele está no período de cortesia definido pelo administrador.

    -   Saiba mais sobre Ações para dispositivos incompatíveis.

-   **Dispositivo não sincronizado:** o dispositivo não conseguiu relatar seu status da política de conformidade de dispositivo por um dos seguintes motivos:

    -   **Desconhecido**: o dispositivo está offline ou falhou ao se comunicar com o Intune ou o Azure AD por outras razões.

    -   **Erro**: o dispositivo falhou ao se comunicar com o Intune e o Azure AD, e recebeu uma mensagem de erro com o motivo.

> [!IMPORTANT]
> Os dispositivos que são registrados no Intune, mas não recebem nenhuma política de conformidade de dispositivo, são incluídos neste relatório no bucket **Compatível**.

#### <a name="drill-down-option"></a>Opção de detalhamento

No **Painel de conformidade do dispositivo**, se você clicar no bloco Conformidade do dispositivo, poderá fazer uma busca detalhada em um determinado **status de conformidade**, **alias de email do usuário**, **modelo de dispositivo** e **local** para cada dispositivo que foi direcionado pelas políticas de conformidade do dispositivo.

![Imagem mostrando a busca detalhada do Painel de conformidade de dispositivos](./media/idc-2.png)

Se você precisar de mais detalhes sobre um usuário específico, poderá filtrar o relatório do Gráfico de conformidade do dispositivo digitando o alias de email do usuário.

![Imagem mostrando o usuário específico do Painel de conformidade de dispositivos](./media/idc-3.png)

Você também pode clicar no status de conformidade diferente no Gráfico de conformidade do dispositivo para ver mais detalhes sobre os status da política de conformidade dos dispositivos do usuário.

![Imagem mostrando diferentes status do Painel de conformidade de dispositivos](./media/idc-4.png)

#### <a name="filter"></a>Filter

Se você clicar no **botão Filtrar**, o filtro suspenso será aberto com as seguintes opções:

-   Modelo

    -   Caixa de texto que aceita uma cadeia de caracteres de pesquisa livre
<br></br>
-   Plataforma

    -   Android

    -   iOS

    -   macOS

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

Clicar em um dispositivo abre o **Painel de Dispositivos** com o dispositivo selecionado, que fornece mais detalhes sobre a configuração da política de conformidade de dispositivo aplicada a esse dispositivo.

Quando você clica na própria configuração da política do dispositivo, pode ver que o nome da política de conformidade do dispositivo originou essa configuração de conformidade do dispositivo direcionada pelo administrador.

### <a name="devices-without-compliance-policy"></a>Dispositivos sem política de conformidade
Esse relatório identifica dispositivos que não têm políticas de conformidade atribuídas a eles. Com a introdução da configuração de segurança que marca todos os dispositivos sem políticas de conformidade, como "não está em conformidade", é importante poder identificar esses dispositivos. Em seguida, poderá atribuir pelo menos uma política de conformidade a eles.

> [!NOTE]
> A nova configuração de segurança pode ser definida no portal do Intune. Selecione **Conformidade do dispositivo** e, em **Instalação**, escolha **Configurações da política de conformidade**. Então use a alternância para definir **Marcar dispositivos sem política de conformidade atribuída como** como **Em conformidade** ou **Não em conformidade**. Leia mais sobre esse [aprimoramento de segurança no serviço do Intune](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

![Imagem mostrando Dispositivos sem relatório de política de conformidade](./media/idc-12.png)

O bloco **Dispositivos sem política de conformidade** está disponível no painel de Conformidade do dispositivo, e mostra todos os dispositivos sem uma política de conformidade, o usuário do dispositivo, o status de conformidade e o modelo do dispositivo.

> [!NOTE]
> Os usuários que recebem uma política de conformidade de qualquer tipo não aparecerão no relatório, independentemente da plataforma do dispositivo. Por exemplo, se você acidentalmente atribuir uma política de conformidade do Windows para um usuário com um dispositivo Android, o dispositivo não aparecerá no relatório. No entanto, o Intune considerará que o dispositivo Android não está em conformidade. Para evitar problemas, recomendamos criar políticas para cada plataforma de dispositivo e implantá-las para todos os usuários.

### <a name="per-policy-device-compliance-report"></a>Relatório de conformidade do dispositivo por política

Este relatório fornece uma exibição da política por conformidade e o número total de dispositivos em cada estado de conformidade. O título **Conformidade da política** está disponível no **Painel de conformidade do dispositivo** e mostra todas as políticas criadas anteriormente pelo administrador, as plataformas nas quais a política é aplicada e o número de dispositivos compatíveis e incompatíveis.

![Imagem mostrando o relatório de conformidade de dispositivo por política](./media/idc-8.png)

Ao clicar no bloco de Conformidade da política e, em seguida, clicar em uma das políticas de conformidade do dispositivo, você poderá ver o **status de conformidade**, o **alias de email do usuário**, o **modelo do dispositivo** e o **local** de cada dispositivo que foi direcionado por essa política de conformidade do dispositivo.

## <a name="setting-compliance-report"></a>Relatório de conformidade de configuração

Este relatório permite exibir - a configuração por conformidade - o número total de dispositivos em cada estado de conformidade. O título **Conformidade de configurações** está disponível no **Painel de conformidade de dispositivos** e mostra todas as configurações da política de conformidade de dispositivo de todas as políticas de conformidade de dispositivo criadas pelo administrador, as plataformas às quais as configurações da política foram aplicadas e o número de dispositivos que não estão em conformidade.

![Imagem mostrando o relatório de conformidade de dispositivo por configuração](./media/idc-10.png)

Ao clicar no bloco de Conformidade da configuração e, em seguida, clicar em uma das configurações da política de conformidade do dispositivo, você poderá ver o **status de conformidade**, o **alias de email do usuário**, o **modelo do dispositivo** e o **local** de cada dispositivo que foi direcionado por essa configuração de política de conformidade do dispositivo.
