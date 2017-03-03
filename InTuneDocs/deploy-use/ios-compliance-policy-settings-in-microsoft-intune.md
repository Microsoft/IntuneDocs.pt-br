---
title: "Configurações da política de conformidade para dispositivos iOS | Microsoft Docs"
description: "Este tópico descreve as regras e configurações que você pode definir em uma política de conformidade para dispositivos iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: f4867d18634add8cb6ffc61a4413618b1bea5a4b


---


# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a>Configurações de política de conformidade para dispositivos iOS no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As configurações de política descritas neste tópico se aplicam a dispositivos que executam o iOS 8.0 e posterior.

Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:
> [!div class="op_single_selector"]
- [Configurações da política de conformidade para dispositivos Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações da política de conformidade para o Android for work](afw-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações de política de conformidade para dispositivos Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Configurações de segurança do sistema
### <a name="password"></a>Senha
- **Exigir senha para desbloquear dispositivos móveis**: defina esta opção como **Sim** para exigir que o usuário insira uma senha antes que possa acessar o dispositivo. Dispositivos iOS que usam uma senha são criptografados.

- **Permitir senhas simples**: defina como **Sim** para permitir que o usuário crie uma senha simples, como **1234** ou **1111**.

-  **Comprimento mínimo da senha**: especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.

- **Tipo de senha necessária:** especifique se o usuário deve criar uma senha **Alfanumérica** ou **Numérica**.

- **Número mínimo de conjuntos de caracteres:** se você definir **Tipo de senha necessária** como **Alfanumérica**, use essa configuração para especificar o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
  -   Letras minúsculas
  -   Letras maiúsculas
  -   Símbolos
  -   Números

  Definir um número mais alto exige que o usuário crie uma senha mais complexa.

  Para dispositivos iOS, essa configuração se refere ao número de caracteres especiais (por exemplo, **!**, **#**, **&amp;**) que devem ser incluídos na senha.

- **Minutos de inatividade antes que a senha seja exigida**: especifique o tempo ocioso antes que o usuário precise digitar novamente sua senha.

- **Expiração da senha (dias)**: selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.

- **Lembrar histórico de senha:** use essa configuração em conjunto com **Evitar reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores**: se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.

- **Exigir uma senha quando o dispositivo volta do estado ocioso**: use essa configuração em conjunto com **Minutos de inatividade antes que a senha seja exigida**. O usuário é solicitado a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

### <a name="email-profile"></a>Perfil de email
- **A conta de email deve ser gerenciada pelo Intune **: quando essa opção é definida como **Sim**, o dispositivo deve usar o perfil de email implantado no dispositivo. O dispositivo é considerado incompatível nas seguintes situações:
  - O perfil de email é implantado em um grupo de usuários diferente do grupo de usuários que é destino da política de conformidade.
  - O usuário já configurou uma conta de email no dispositivo que corresponde ao perfil de email do Intune implantado no dispositivo. Intune não pode substituir o perfil de usuário provisionado e, portanto, não é capaz de gerenciá-lo. Para garantir a conformidade, o usuário deve remover as configurações de email existentes. Depois, o Intune pode instalar o perfil de email gerenciado.

- **Selecione o perfil de email que deve ser gerenciado pelo Intune**: se a configuração **A conta de email deve ser gerenciada pelo Intune** for selecionada, escolha **Selecionar** para especificar o perfil de email do Intune. O perfil de email deve estar presente no dispositivo.

     Para obter detalhes sobre os perfis de email, consulte [Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="device-health-settings"></a>Configurações de integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz**: se você habilitar essa configuração, os dispositivos com jailbreak não serão compatíveis.

##  <a name="device-properties"></a>Propriedades do dispositivo
- **SO mínimo exigido**: quando um dispositivo não atender ao requisito mínimo de versão do SO, ele será relatado como não compatível.
É exibido um link com informações sobre como atualizar. O usuário pode optar por atualizar o dispositivo. Depois disso, ele pode acessar recursos da empresa.

- **Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.



<!--HONumber=Jan17_HO4-->


