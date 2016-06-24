---
# required metadata

title: Solucionar problemas de perfis de email | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Solucionar problemas de perfis de email no Microsoft Intune
Aqui estão relacionados alguns problemas com o perfil de email e como resolvê-los.

Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.


## Não é possível enviar imagens da conta de email
Os usuários que têm contas de email configuradas automaticamente não podem enviar imagens de seus dispositivos.
Isso ocorre quando a opção **Permitir que o email seja enviado de aplicativos de terceiros** não está habilitada.

### Solução do Intune

1.  Abra o Console de administração do Microsoft Intune, selecione **Política** Carga de trabalho &gt;**Política de configuração**.

2.  Selecione o perfil de email e clique em **Editar**.

3.  Selecione a opção **Permitir que o email seja enviado de aplicativos de terceiros.**

### Configuration Manager integrado à solução Intune

1.  Abra o console do Configuration Manager &gt; **Ativos e Conformidade**.

2.  Expanda **Visão geral** -&gt; **Configurações de Conformidade** -&gt; **Acesso aos Recursos da Empresa** e selecione **Perfis de Email**.

3.  Clique com o botão direito do mouse no perfil de email e abra as **Propriedades**.

4.  Na guia **Configurações de Sincronização**, selecione **Permitir que o email seja enviado de aplicativos de terceiros**.

## Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).


<!--HONumber=Jun16_HO1-->


