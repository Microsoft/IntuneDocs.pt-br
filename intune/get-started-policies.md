---
title: Introdução a políticas no Microsoft Intune
titlesuffix: ''
description: Crie políticas para ajudar a proteger dados corporativos e gerenciar os dispositivos que os usuários finais usam para acessar os recursos da empresa.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b8bffd0435988cc59c5c0e4d754b861729d466ae
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-with-creating-policies"></a>Introdução à criação de políticas

Uma das principais metas ao começar a usar o Intune é registrar dispositivos para garantir que eles estejam em conformidade com as políticas corporativas. Políticas de conformidade não apenas ajudam a gerenciar os tipos de dispositivos especializados, como quiosques corporativos, mas também dispositivos pessoais (Traga seu próprio), tablets e dispositivos sem usuário.

![Painel de conformidade com poucos dados](/intune/media/generic-compliance-dashboard.png)

Gerencie dispositivos móveis nas áreas a seguir usando as políticas de conformidade:

* Regule os números de dispositivos que cada usuário registra
* Gerenciar configurações de dispositivos (por exemplo, criptografia no nível do dispositivo, tamanho da senha e uso de câmera)
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

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione **Conformidade do dispositivo**.
4. No painel **Conformidade do dispositivo**, selecione **Políticas**.
5. Selecione **Criar Política** e preencha os detalhes como **Nome** e **Descrição**. 
6. Escolha **iOS** como a **Plataforma**.
6. Em **Configurações**, selecione **Segurança do Sistema** e alterne **Exigir uma senha para desbloquear os dispositivos móveis** para **Exigir**. Também é possível definir outras regras, como **Tamanho mínimo da senha**, **Tipo de senha exigido** e **Número de caracteres não alfanuméricos na senha**. Após terminar de configurar a política, selecione **OK**.
7. Volte para o painel **Criar política** e selecione **Criar**.
8. Depois de criar a política, selecione **Atribuições** para atribuí-la ao seu grupo de teste. Selecione o grupo de teste – que deve conter seu usuário de teste – e atribua a política a esse grupo clicando em **Salvar**.
9. Aguarde alguns minutos e seu dispositivo registrado deverá solicitar uma senha atualizada para permanecer em conformidade com as políticas corporativas. Você pode verificar manualmente isso no **aplicativo de Portal da Empresa para iOS** tocando no nome do dispositivo e no botão **Sincronizar**.

## <a name="next-steps"></a>Próximas etapas

[Introdução ao registro de dispositivos](get-started-enroll.md) – aprenda a experiência de registro passando por uma experiência completa de registro de um dispositivo iOS.

## <a name="learn-more"></a>Saiba mais

* [Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md)
* [Maneiras comuns de usar as políticas de acesso condicional com o Intune](conditional-access-intune-common-ways-use.md)
