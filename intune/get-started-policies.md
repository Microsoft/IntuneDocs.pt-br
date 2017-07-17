---
title: "Introdução às políticas"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 232ec25c34df5e71f70737ca5f0f8a2ef12a05f0
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Introdução às políticas
<a id="getting-started-with-policies" class="xliff"></a>

Uma das principais metas do guia de introdução do Intune é registrar dispositivos para verificar se eles estão em conformidade com as políticas corporativas. Políticas de conformidade não apenas ajudam a gerenciar os tipos de dispositivos especializados, como quiosques corporativos, mas também dispositivos pessoais (Traga seu próprio), tablets e dispositivos sem usuário.

![Painel de conformidade com pouquíssimos dados](/intune/media/generic-compliance-dashboard.png)

As políticas de conformidade oferecem os seguintes recursos de gerenciamento para dispositivos móveis:

* Regule os números de dispositivos que cada usuário registra
* Gerenciar configurações de dispositivos (como por exemplo criptografia no nível do dispositivo, tamanho da senha e uso de câmera)
* Entrega de aplicativos, perfis de email, perfis de VPN etc.
* Avaliar critérios no nível do dispositivo para as políticas de conformidade de segurança

Crie políticas de conformidade para cada plataforma separadamente. Para este exercício, continuaremos com o iOS. As seguintes políticas estão disponíveis para dispositivos iOS:

* Configuração de senha ou PIN
* Criptografia de dispositivo
* Dispositivo com jailbreak
* Perfil de email
* Versão mínima do SO
* Versão máxima do SO

__Como crio uma política?__

1. Entre no [Portal do Azure](https://portal.azure.com).
2. **Pesquisar recursos**, pesquise por **Intune**.
3. Selecione **Conformidade do dispositivo**.
4. Na folha **Conformidade do dispositivo**, selecione **Políticas**.
5. Selecione **Criar Política** e preencha os detalhes como **Nome** e **Descrição**. Escolha **iOS** como a **Plataforma**.
6. Em **Configurações**, selecione **Segurança do Sistema** e alterne **Exigir uma senha para desbloquear os dispositivos móveis** para **Exigir**. Também é possível definir outras regras, como **Tamanho mínimo da senha**, **Tipo de senha exigido** e **Número de caracteres não alfanuméricos na senha**. Após terminar de configurar a política, selecione **OK**.
7. Volte para a folha **Criar política** e selecione **Criar**.
8. Depois de criar a política, selecione **Atribuições** para atribuí-la ao seu grupo de teste. Selecione o grupo de teste – que deve conter seu usuário de teste – e atribua a política a esse grupo clicando em **Salvar**.
9. Aguarde alguns minutos e seu dispositivo registrado deverá solicitar uma senha atualizada para permanecer em conformidade com as políticas corporativas. Você pode verificar manualmente isso no **aplicativo de Portal da Empresa para iOS** tocando no nome do dispositivo e no botão **Sincronizar**.
