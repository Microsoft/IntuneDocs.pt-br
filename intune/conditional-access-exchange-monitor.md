---
title: Monitorar o acesso condicional do Exchange no Microsoft Intune
titlesuffix: 
description: Monitorar a conformidade de acesso condicional para o Exchange local e o Exchange Online por meio do Portal do Azure no Intune.
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 932dfe32c6df5741615d9db9f303aaee7785d3a3
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Monitorar a conformidade de acesso condicional do Exchange Local e do Exchange Online no Intune

A partir da versão 1704 do Intune, os administradores podem ver informações de relatório relacionadas aos registros de dispositivos do Exchange ActiveSync que estão sincronizados com o Intune através do Exchange Connector local ou o Service to Service Connector do Intune (conector do Exchange Online). Os relatórios de conformidade de acesso condicional fornecem um resumo dos dispositivos com estados de sincronização diferentes:

-   **Permitir**

-   **Bloquear**

-   **Quarentena**

## <a name="to-monitor-conditional-access-compliance"></a>Para monitorar a conformidade de acesso condicional

1.  Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.

2.  Quando entrar com êxito, você verá o **Painel do Azure**.

3.  Escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

4.  Escolha **Intune** e você verá o **Painel do Intune**.

5.  Escolha **Acesso condicional** e, em seguida, escolha **Visão Geral**.

6.  Escolha uma das três áreas (**Permitido**, **Bloqueado** ou **Quarentena**) no gráfico para exibir o relatório de conformidade de acesso condicional.

    ![Imagem do Painel de acesso condicional](./media/CA-reporting-intune-1.png)

Depois de escolher uma das três áreas, você poderá ver mais detalhes sobre os dispositivos que foram permitidos, bloqueados ou colocados em quarentena.

Você também poderá analisar em dispositivos específicos para ver mais detalhes. Por exemplo, o dispositivo escolhido na imagem a seguir está bloqueado. O Intune dá a opção de remover dados corporativos do painel de relatórios de conformidade de acesso condicional.

![Imagem do Relatório de detalhes do dispositivo de acesso condicional](./media/CA-reporting-intune-3.png)

No painel de detalhes do dispositivo, é possível ver mais informações:

-   **Visão geral:** é possível ver as propriedades do dispositivo como: versão do sistema operacional, modelo do dispositivo, propriedade, número de série, fabricante do dispositivo, número de telefone e última vez que o dispositivo fez check-in.

-   **Propriedades:** você pode definir a propriedade do dispositivo (pessoal ou corporativa).

-   **Hardware:** fornece as informações que você vê na Visão Geral e também os detalhes de armazenamento (espaço total e livre), compartimento do sistema, detalhes da rede, serviço de rede e mais detalhes de bloqueio de acesso condicional.

-   **Aplicativos descobertos:** mostra todos os aplicativos instalados no seu dispositivo. Você também pode exportar a lista de aplicativos instalados para o formato .CSV.

-   **Conformidade:** mostra todos os detalhes da política de conformidade do dispositivo.

-   **Configuração do dispositivo:** mostra todos os detalhes de configuração do dispositivo.

-   **Acesso do Exchange:** aqui você pode aprender mais sobre o estado do dispositivo após a aplicação de políticas de acesso condicional.
