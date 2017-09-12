---
title: Monitorar a conformidade de acesso condicional para o Exchange local e o Exchange Online
titlesuffix: Azure portal
description: Monitorar a conformidade de acesso condicional para o Exchange local e o Exchange Online por meio do Portal do Azure no Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: be0c1cef0dd6562feb54724edbf8ae22072e3d95
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Monitorar a conformidade de acesso condicional do Exchange Local e do Exchange Online no Intune

A partir da versão 1704 do Intune, os administradores podem ver informações de relatório relacionadas aos registros de dispositivos do Exchange ActiveSync que estão sincronizados com o Intune através do Exchange Connector local ou o Service to Service Connector do Intune (conector do Exchange Online). Os relatórios de conformidade de acesso condicional fornecem um resumo dos dispositivos com estados de sincronização diferentes:

-   **Permitir**

-   **Bloquear**

-   **Quarentena**

## <a name="to-monitor-conditional-access-compliance"></a>Para monitorar a conformidade de acesso condicional

1.  Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.

2.  Quando entrar com êxito, você verá o **Painel do Azure**.

3.  Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

4.  Escolha **Intune** e você verá o **Painel do Intune**.

5.  Escolha **Acesso Condicional**, em seguida, escolha **Visão Geral**.

6.  Escolha uma das três áreas (**Bloqueado**, **Quarentena** ou **Permitido**) no gráfico para exibir o relatório de conformidade de acesso condicional.

    ![Painel de acesso condicional](./media/CA-reporting-intune-1.png)

Depois de escolher uma das três áreas, você poderá ver mais detalhes sobre os dispositivos que estão sendo permitidos, bloqueados ou colocados em quarentena.

Você também poderá analisar em dispositivos específicos para ver mais detalhes. Por exemplo, o dispositivo escolhido na imagem abaixo está bloqueado. O Intune dá a opção de remover dados corporativos da folha de relatórios de conformidade de acesso condicional.

![Relatório de detalhes do dispositivo de acesso condicional](./media/CA-reporting-intune-3.png)

Na folha detalhes do dispositivo, você pode ver mais informações:

-   **Visão geral:** você pode ver as propriedades do dispositivo como: versão do sistema operacional, modelo do dispositivo, propriedade, número de série, fabricante do dispositivo, número de telefone e última vez que o dispositivo fez check-in.

-   **Propriedades:** você pode definir a propriedade do dispositivo (pessoal ou corporativa).

-   **Hardware:** fornece as informações que você vê na Visão Geral e também os detalhes de armazenamento (espaço total e livre), compartimento do sistema, detalhes da rede, serviço de rede e mais detalhes de bloqueio de acesso condicional.

-   **Aplicativos descobertos:** mostra todos os aplicativos instalados no seu dispositivo. Você também pode exportar a lista de aplicativos instalados para o formato .CSV.

-   **Conformidade:** mostra todos os detalhes da política de conformidade do dispositivo.

-   **Configuração do dispositivo:** mostra todos os detalhes de configuração do dispositivo.

-   **Acesso do Exchange:** aqui você pode aprender mais sobre o estado do dispositivo após a aplicação de políticas de acesso condicional.
