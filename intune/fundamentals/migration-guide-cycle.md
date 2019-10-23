---
title: Como funciona um ciclo de migração típico do Intune
titleSuffix: Microsoft Intune
description: Este artigo explica como funciona um ciclo de migração do Microsoft Intune e dá exemplos de como você pode lidar com os ciclos de migração.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: e771c7f061d32748898846f9391758c02f7499c9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505295"
---
# <a name="typical-migration-cycle"></a>Ciclo de migração típico

Normalmente, as organizações começam sua migração no Intune com um pequeno projeto piloto, visando um subconjunto de seus usuários no departamento de TI. Além disso, talvez sua organização precise discutir fatores como a disposição do grupo em mudar, o número de usuários, a complexidade, os requisitos, o local e os riscos comerciais, a fim de ajudar a determinar o cronograma da migração.

Veja um exemplo de como os grupos-alvo poderão ser agendados:

  | **Grupos-alvo da migração** | **Período 1** | **Período 2** | **Período 3** | **Período 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Organização de TI piloto limitada (50 usuários) | Anunciar plano | Instruir para o registro | Definir prazo | Impor acesso condicional |  |                                                        
| Organização de TI piloto expandida (200 usuários) |  | Anunciar plano | Instruir para o registro | Definir prazo | Impor acesso condicional |
| Usuários com conhecimentos técnicos da fase 1 de migração (2000) |  |  | Anunciar plano | Instruir para o registro | Definir prazo |
| Fase 2 da migração, Leste dos EUA |  |  |  | Anunciar plano | Instruir para o registro |
| Todas as regiões |  |  |  |  | Anunciar plano |

## <a name="customer-migration-case-study"></a>Estudo de caso de migração do cliente

### <a name="adatum-corporation"></a>Adatum Corporation

Confira como a [Adatum Corporation passou pelo processo de migração de um provedor de MDM de terceiros para o Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Monitorando a migração

O Intune fornece várias maneiras de monitorar a migração:

* Exibições de grupo de usuários do Intune

* Conjunto de relatórios internos

* Alertas no console

Controle quantos usuários registraram dispositivos após cada fase para que você possa:

- Avaliar a eficiência de seu plano de comunicação.

- Estimar o impacto da aplicação do acesso condicional.


## <a name="post-migration"></a>Pós-migração

Desativar o provedor de MDM anterior e cancelar a assinatura do serviço após a migração para o Intune. Além disso, remover quaisquer requisitos de infraestrutura desnecessários seguindo as instruções do provedor de MDM.
