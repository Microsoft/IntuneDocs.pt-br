---
title: "Configurações de política de conformidade para dispositivos iOS | Microsoft Intune"
description: "Este tópico descreve as regras e configurações que você pode definir em uma política de conformidade para dispositivos iOS."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9a442d9472159757333a9ebe081d86eac9907cdc
ms.openlocfilehash: 4fcfcb5a9a48dd4051c0f2652f3fb589e3ff73a8


---


# Configurações de política de conformidade para dispositivos iOS no Microsoft Intune

As configurações de política descritas neste tópico se aplicam a dispositivos que executam o iOS 8.0 e posterior.

Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:
> [!div class="op_single_selector"]
- [Configurações da política de conformidade para dispositivos Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações da política de conformidade para dispositivos Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Configurações de segurança do sistema
### Senha
- **Exigir uma senha para desbloquear dispositivos móveis:**    defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que eles possam acessar o dispositivo. Dispositivos iOS que usam a senha são criptografados.

- **Permitir senhas simples:**    defina como **Sim** para permitir que os usuários criem senhas simples, como '**1234**' ou '**1111**'.

-  **Comprimento mínimo da senha:** especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve conter.
- **Tipo de senha exigido:** especifique se os usuários devem criar uma senha **Alfanumérica** ou **Numérica**.

- **Número mínimo de conjuntos de caracteres:** se você definir **Tipo de senha necessária** para **Alfanumérica**, use essa configuração para especificar o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
  -   Letras minúsculas
  -   Letras maiúsculas
  -   Símbolos
  -   Números

  Definir um número mais alto para essa configuração exigirá que os usuários criem senhas mais complexas.

  Para dispositivos iOS, essa configuração se refere ao número de caracteres especiais (por exemplo, **!**, **#**, **&amp;**) que devem ser incluídos na senha.
- **Minutos de inatividade antes que a senha seja exigida:** especifica o tempo ocioso antes que o usuário precise digitar novamente sua senha.

- **Expiração da senha (dias):** selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.

- **Lembrar o histórico da senha:** use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores:** se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.

- **Exigir uma senha quando o dispositivo retorna do estado ocioso:** essa configuração deve ser usada junto com a configuração **Minutos de inatividade antes da senha ser necessária**. Os usuários finais serão solicitados a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

### Perfil de email
- **Conta de email deve ser gerenciada pelo Intune:** Quando essa opção é definida como **Sim**, o dispositivo deve usar o email incompatível implantado no dispositivo. O dispositivo é considerado incompatível nas seguintes situações:
  - O perfil de email também deve ser implantado no mesmo grupo de usuários que o grupo visado pela política de conformidade; caso contrário, os dispositivos dos usuários serão considerados incompatíveis.
  - O dispositivo será relatado como incompatível se o usuário já tiver configurado uma conta de email no dispositivo que corresponda ao perfil de email do Intune implantado para o dispositivo. Intune não pode substituir o perfil de usuário provisionado e, portanto, não é capaz de gerenciá-lo. Para garantir a conformidade, o usuário deve remover as configurações de email existentes e, em seguida, o Intune pode instalar o perfil de email gerenciado.


- **Selecionar o perfil de email que deve ser gerenciado pelo Intune:**
     se a configuração **Conta de email deve ser gerenciada pelo Intune** for selecionada, escolha **Selecionar** para especificar o perfil de email do Intune. O perfil de email deve estar presente no dispositivo.

     Para obter detalhes sobre os perfis de email, consulte [Configure access to corporate email using email profiles with Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) (Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune).

## Configurações de integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz:** se você habilitar essa configuração, os dispositivos com jailbreak não serão compatíveis.

##  Propriedades do dispositivo
- **Sistema operacional mínimo exigido:** quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível.
É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos, após o que eles serão capazes de acessar os recursos da empresa.

- **Versão do sistema operacional máxima permitida:** quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.



<!--HONumber=Oct16_HO3-->


