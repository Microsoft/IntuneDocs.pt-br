---
title: "Habilitar o conector do Defesa contra Ameaças Móveis no Microsoft Intune"
titleSuffix: 
description: "Habilite o conector entre o parceiro de MTD (Defesa contra Ameaças Móveis) e o Microsoft Intune."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ca0b8082e0fccc5ee4c97e281d546ba4a75d813
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Habilitar o conector do Defesa contra Ameaças Móveis no Intune

> [!NOTE] 
> Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

Durante a instalação do MTD (Defesa contra Ameaças Móveis), você configurou uma política para classificar ameaças em seu console de parceiro do MTD e criou a política de conformidade de dispositivo no Intune. Se já tiver configurado o conector do Intune no console do parceiro de MTD, agora você poderá habilitar a conexão do MTD no Intune.

## <a name="to-enable-the-mtd-connector"></a>Para habilitar o conector MTD

1. Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune. Quando entrar com êxito, você verá o **Painel do Azure**.

2. No **Painel do Azure**, escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune** e o **Painel do Intune** se abrirá.

4. No **Painel do Intune**, escolha **Conformidade do dispositivo** e, depois, **Defesa contra Ameaças Móveis** na seção **Configuração**.

5. No painel **Defesa contra Ameaças Móveis**, escolha **Adicionar**.

6. Escolha sua solução MTD como o **conector de Defesa contra Ameaças Móveis para configuração** na lista suspensa.

    ![Configuração do MTD no Portal do Azure no Intune](./media/enable-mtd-connector-1.png)

7. Habilite as opções de alternância de acordo com os requisitos de sua organização.

## <a name="mtd-toggle-options"></a>Opções de alternância de MTD

Decida quais opções de alternância do MTD você precisa habilitar de acordo com os requisitos da sua organização. Veja mais detalhes abaixo:

- **Conectar dispositivos Android 4.1 ou superior ao [nome do parceiro de MTD] for Work MTD**: ao habilitar essa opção, você pode fazer com que os dispositivos Android 4.1 ou superior relatem os riscos de segurança para o Intune.
    - **Marcar como fora de conformidade se nenhum dado for recebido**: se o Intune não receber dados do parceiro de MTD sobre um dispositivo nesta plataforma, considerar o dispositivo não compatível.
<br></br>
- **Conectar dispositivos iOS 8.0 ou superior ao [nome do parceiro de MTD] for Work MTD**: ao habilitar essa opção, você pode fazer com que os dispositivos Android 4.1 ou superior relatem os riscos de segurança para o Intune.
    - **Marcar como fora de conformidade se nenhum dado for recebido**: se o Intune não receber dados do parceiro de MTD sobre um dispositivo nesta plataforma, considerar o dispositivo não compatível.
<br></br>
- **Bloquear versões do sistema operacional sem suporte**: bloqueie se o dispositivo estiver executando um sistema operacional inferior à versão mínima com suporte.

- **Número de dias até que o parceiro seja considerado sem resposta**: número de dias de inatividade antes que o Intune considere o parceiro sem resposta devido à perda da conexão. O Intune ignora o estado de conformidade de parceiros de MTD sem resposta.

> [!IMPORTANT] 
> Você deve adicionar e atribuir os aplicativos MTD antes de criar a conformidade do dispositivo e as regras de política de acesso condicional. Isso garante que o aplicativo MTD esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

> [!TIP]
> Veja o **Status da conexão** e o tempo da **Última sincronização** entre o Intune e o parceiro de MTD no painel de Defesa contra Ameaças Móveis.
