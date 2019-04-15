---
title: Habilitar o conector do Defesa contra Ameaças Móveis no Microsoft Intune
titleSuffix: Microsoft Intune
description: Habilite o conector entre o parceiro de MTD (Defesa contra Ameaças Móveis) e o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ab9fef5a577783ebbdd512de6d00ab98483e754c
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59569617"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Habilitar o conector do Defesa contra Ameaças Móveis no Intune

> [!NOTE] 
> Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

Durante a instalação do MTD (Defesa contra Ameaças Móveis), você configurou uma política para classificar ameaças em seu console de parceiro do MTD e criou a política de conformidade de dispositivo no Intune. Se já tiver configurado o conector do Intune no console do parceiro de MTD, agora você poderá habilitar a conexão do MTD no Intune.

## <a name="to-enable-the-mtd-connector"></a>Para habilitar o conector MTD

1. Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune. Depois que você entrar com êxito, o **Painel do Azure** será exibido.

2. No **Painel do Azure**, escolha **Todos os serviços** no menu à esquerda, em seguida, digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune**. O **Painel do Intune** será aberto.

4. No **Painel do Intune**, escolha **Conformidade do dispositivo** e selecione **Defesa Contra Ameaças Móveis** na seção **Instalação**.

5. No painel **Defesa contra Ameaças Móveis**, escolha **Adicionar**.

6. Escolha sua solução MTD como o **conector de Defesa contra Ameaças Móveis para configuração** na lista suspensa.

    ![Configuração do MTD no Portal do Azure no Intune](./media/enable-mtd-connector-1.png)

7. Habilite as opções de alternância de acordo com os requisitos de sua organização. A alternância da visibilidade das opções varia dependendo do parceiro de MTD.

## <a name="mtd-toggle-options"></a>Opções de alternância de MTD

Você pode decidir quais opções de alternância de MTD você precisa habilitar de acordo com os requisitos da sua organização. Veja mais detalhes abaixo:

- **Conectar dispositivos Android 4.1 e posterior ao [nome do parceiro de MTD] para o Work MTD**: Ao habilitar essa opção, você poderá fazer com que os dispositivos Android 4.1 e posterior relatem os riscos de segurança novamente ao Intune.
    - **Marcar como fora de conformidade se nenhum dado for recebido**: Se o Intune não receber dados sobre um dispositivo nessa plataforma do parceiro de MTD, considere o dispositivo fora de conformidade.
<br></br>
- **Conectar dispositivos iOS 8.0 e posterior ao [nome do parceiro de MTD] para o Work MTD**: Ao habilitar essa opção, você poderá fazer com que dispositivos iOS 8.0 e posterior relatem os riscos de segurança novamente ao Intune.
    - **Marcar como fora de conformidade se nenhum dado for recebido**: Se o Intune não receber dados sobre um dispositivo nessa plataforma do parceiro de MTD, considere o dispositivo fora de conformidade.
<br></br>
- **Habilitar a Sincronização de Aplicativos para Dispositivos iOS**: Permite que esse parceiro de Defesa Contra Ameaças Móveis solicite metadados de aplicativos do iOS do Intune para uso para fins de análise de ameaças.

- **Bloquear versões de sistema operacional sem suporte**: Bloqueie se o dispositivo estiver executando um sistema operacional inferior à versão mínima com suporte.

- **Número de dias até que o parceiro seja considerado sem resposta**: Número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão. O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.

> [!IMPORTANT] 
> Você deve adicionar e atribuir os aplicativos MTD antes de criar a conformidade do dispositivo e as regras de política de acesso condicional. Isso garante que o aplicativo MTD esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

> [!TIP]
> Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD no painel de Defesa contra Ameaças Móveis.
