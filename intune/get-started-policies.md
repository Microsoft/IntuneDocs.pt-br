---
title: "Introdução às políticas"
titlesuffix: Azure portal
description: "Crie políticas para impedir que os usuários executem ações não autorizadas com seus dispositivos."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eaac36810f8df524fa795a0fef2cf9a368984658
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2017
---
# <a name="get-started-with-policies"></a>Introdução às políticas

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

## <a name="next-steps"></a>Próximas etapas

[Introdução ao registro de dispositivos](get-started-enroll.md) – aprenda a experiência de registro passando por uma experiência completa de registro de um dispositivo iOS.

## <a name="learn-more"></a>Saiba mais

* [Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md)
* [Maneiras comuns de usar as políticas de acesso condicional com o Intune](conditional-access-intune-common-ways-use.md)
