---
# required metadata

title: Configurações de política de conformidade para dispositivos iOS | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Configurações de política de conformidade para dispositivos iOS no Microsoft Intune

As configurações de política descritas neste tópico se aplicam a dispositivos que executam o iOS 6 e posterior.

Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:
> [!div class="op_single_selector"]
- [Configurações da política de conformidade para dispositivos Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações da política de conformidade para dispositivos Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Configurações de segurança do sistema
### Senha
- **Exigir uma senha para desbloquear dispositivos móveis:** defina esta opção como **Sim** para exigir que os usuários insiram uma senha para
  poderem acessar seus dispositivos. Dispositivos iOS que usam a senha são criptografados.

- **Permitir senha simples:** defina esta opção
   como **Sim** para permitir que os usuários criem senhas simples
   como “**1234**” ou “**1111**”.

-  **Comprimento mínimo da senha:**
  Especifique o número mínimo de dígitos ou caracteres que
  a senha do usuário deve conter.
- **Tipo de senha necessária:** especifique se os usuários devem criar
uma senha **Alfanumérica** ou **Numérica**.

- **Número mínimo de conjuntos de caracteres:** se **Tipo de senha necessária** estiver definido como
**Alfanumérico**, use essa configuração para especificar o número mínimo de
conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
  -   Letras minúsculas
  -   Letras maiúsculas
  -   Símbolos
  -   Números

  Definir um número mais alto para essa configuração exigirá que os usuários criem senhas mais complexas.

  Para dispositivos iOS, essa configuração se refere ao número de caracteres especiais (por exemplo, **!**, **#**, **&amp;**) que devem ser incluídos na senha.
- **Minutos de inatividade antes que a senha seja exigida:** especifica o tempo ocioso antes que o usuário precise digitar novamente sua senha.

- **Expiração da senha (dias):** selecione o número de dias antes de a senha do usuário expirar
e ser necessário criar uma nova.

- **Lembrar histórico de senha:** use essa configuração junto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário
crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores:** se **Lembrar histórico de senha** for selecionado, especifique o
número de senhas usadas anteriormente que não podem ser reutilizadas.

- **Exigir senha quando o dispositivo retorna de um estado ocioso:**
Essa configuração deve ser usada junto com a configuração **Minutos de Inatividade Antes da Senha ser Necessária**. Os usuários finais serão solicitados a inserir uma senha para acessar um dispositivo que esteve inativo durante o tempo especificado na configuração
**Minutos de inatividade antes da senha ser necessária**.

### Perfil de email
- **Conta de email deve ser gerenciada pelo Intune:** Quando essa opção é definida como **Sim**, o dispositivo deve usar o email incompatível implantado no dispositivo. O dispositivo é considerado incompatível nas seguintes situações:
  - O perfil de email também deve ser implantado no mesmo grupo de usuários que o grupo visado pela política de conformidade; caso contrário, os dispositivos dos usuários serão considerados incompatíveis.
  - O dispositivo será relatado como incompatível se o usuário já tiver configurado uma conta de email no dispositivo que corresponda ao perfil de email do Intune implantado para o dispositivo. O Intune não pode substituir o perfil de usuário provisionado e, portanto
  , não é capaz de gerenciá-lo. Para garantir a conformidade, o usuário deve remover as
  configurações de email existentes, então, o Intune poderá instalar o
  perfil de email gerenciado.


- **Selecione o perfil de email que deve ser gerenciado pelo Intune:**
     Se a configuração **Conta de Email deve ser gerenciada pelo Intune** for selecionada,
     escolha **Selecionar** para especificar o perfil de email do Intune. O perfil de email deve estar presente no dispositivo.

     Para obter detalhes sobre perfis de email, consulte [Configurar o acesso ao
     email corporativo usando perfis de email com o Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## Configurações de integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz:** se você habilitar essa configuração,
dispositivos com jailbreak não serão compatíveis.

##  Propriedades do dispositivo
- **Sistema operacional mínimo necessário:** quando um dispositivo não atende o requisito mínimo de versão de sistema operacional,
ele é relatado como não compatível.
É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos, após o que eles serão capazes de acessar os recursos da empresa.

- **Versão máxima do sistema operacional permitida:** quando um dispositivo estiver usando uma
versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.


<!--HONumber=May16_HO1-->


