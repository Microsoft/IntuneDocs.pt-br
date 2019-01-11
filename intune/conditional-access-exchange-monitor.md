---
title: Monitorar o acesso condicional do Exchange no Microsoft Intune | Microsoft Intune
description: Monitorar a conformidade de acesso condicional para o Exchange local e o Exchange Online por meio do Portal do Azure no Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 8c9602dbe183501cc779fcb9b5d5a1e6e4bf6154
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816763"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Monitorar a conformidade de acesso condicional do Exchange Local e do Exchange Online no Intune

A partir da versão 1704 do Intune, os administradores podem ver informações de relatório relacionadas aos registros de dispositivos do Exchange ActiveSync que estão sincronizados com o Intune através do Exchange Connector local ou o Service to Service Connector do Intune (conector do Exchange Online). Os relatórios de conformidade de acesso condicional fornecem um resumo dos dispositivos com estados de sincronização diferentes:

-   **Permitir**

-   **Bloquear**

-   **Quarentena**

## <a name="to-monitor-conditional-access-compliance"></a>Para monitorar a conformidade de acesso condicional

1.  Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.

2.  Depois de entrar com êxito, você verá o **Painel do Azure**.

3.  Escolha  **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

4.  Escolha **Intune** e você verá o **Painel do Intune**.

5.  Escolha **Acesso condicional** e, em seguida, escolha **Visão Geral**.

6.  Escolha uma das três áreas (**Permitido**, **Bloqueado** ou **Quarentena**) no gráfico para exibir o relatório de conformidade de acesso condicional.

    ![Imagem do Painel de acesso condicional](./media/CA-reporting-intune-1.png)

Depois de escolher uma das três áreas, você poderá ver mais detalhes sobre os dispositivos que foram permitidos, bloqueados ou colocados em quarentena.

Você também poderá fazer uma busca detalhada em dispositivos específicos para ver mais detalhes. Por exemplo, o dispositivo escolhido na imagem a seguir está bloqueado. O Intune dá a opção de remover dados corporativos do painel de relatórios de conformidade de acesso condicional.

![Imagem do Relatório de detalhes do dispositivo de acesso condicional](./media/CA-reporting-intune-3.png)

No painel de detalhes do dispositivo, é possível ver mais informações:

-   **Visão geral:** É possível pode ver as propriedades do dispositivo como: Versão do sistema operacional, modelo do dispositivo, propriedade, número de série, fabricante do dispositivo, número de telefone e última vez que o dispositivo fez check-in.

-   **Propriedades:** É possível definir a propriedade do dispositivo (Pessoal ou Corporativa).

-   **Hardware:** Fornece as informações exibidas na Visão Geral e também os detalhes de armazenamento (espaço total e livre), compartimento do sistema, detalhes da rede, serviço de rede e mais detalhes sobre o bloqueio de acesso condicional.

-   **Aplicativos Descobertos:** Mostra todos os aplicativos instalados no dispositivo. Você também pode exportar a lista de aplicativos instalados para o formato .CSV.

-   **Conformidade:** Mostra todos os detalhes da política de conformidade do dispositivo.

-   **Configuração do Dispositivo:** Mostra todos os detalhes da configuração do dispositivo.

-   **Acesso do Exchange:** Aqui você poderá saber mais sobre o estado do dispositivo após a aplicação de políticas de acesso condicional.
