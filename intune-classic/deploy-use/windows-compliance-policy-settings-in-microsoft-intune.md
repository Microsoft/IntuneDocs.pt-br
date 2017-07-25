---
title: "Configurações da política de conformidade para dispositivos Windows"
description: "Este tópico descreve as regras e configurações que você pode definir para uma política de conformidade para dispositivos Windows."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 67810c51c7a7b2ec1e1ff33c11a27a8757b2bcbd
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="compliance-policy-settings-for-windows-devices-in-microsoft-intune"></a>Configurações de política de conformidade para dispositivos Windows no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As configurações de política descritas neste tópico se aplicam a dispositivos que executam o sistema operacional Windows. As seções a seguir descrevem as versões do Windows com suporte.

Se estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:
> [!div class="op_single_selector"]
- [Configurações da política de conformidade para dispositivos iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações da política de conformidade para dispositivos Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações da política de conformidade para o Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="compliance-policy-settings-for-windows-phone-devices"></a>Configurações da política de conformidade para dispositivos Windows Phone
As configurações listadas nesta seção têm suporte no Windows Phone 8.1 e posterior.

### <a name="system-security-settings"></a>Configurações de segurança do sistema
#### <a name="password"></a>Senha
- **Exigir senha para desbloquear dispositivos móveis**: defina esta opção como **Sim** para exigir que o usuário insira uma senha antes que possa acessar o dispositivo.

- **Permitir senhas simples**: defina como **Sim** para permitir que o usuário crie uma senha simples, como **1234** ou **1111**.

-  **Comprimento mínimo da senha**: especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.
- **Tipo de senha necessária:** especifique se o usuário deve criar uma senha **Alfanumérica** ou **Numérica**.

  Para dispositivos que executam o Windows e são acessados com uma conta da Microsoft, a política de conformidade não será avaliada corretamente se o comprimento mínimo da senha tiver mais de oito caracteres ou se o número mínimo de conjuntos de caracteres for maior que dois.

- **Número mínimo de conjuntos de caracteres:** se **Tipo de senha necessária** estiver definido como **Alfanumérico**, essa configuração especificará o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
  -   Letras minúsculas
  -   Letras maiúsculas
  -   Símbolos
  -   Números

  Definir um número mais alto para essa configuração exigirá que o usuário crie uma senha mais complexa. Para dispositivos que executam o Windows e são acessados com uma conta da Microsoft, a política de conformidade não será avaliada corretamente se o comprimento mínimo da senha tiver mais de oito caracteres ou se o número mínimo de conjuntos de caracteres for maior que dois.

- **Minutos de inatividade antes que a senha seja exigida:** especifica o tempo ocioso antes que o usuário precise digitar novamente a senha.

- **Expiração da senha (dias)**: selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.

- **Lembrar histórico de senha:** use essa configuração em conjunto com **Evitar reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores:** se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.
- **Exigir uma senha quando o dispositivo retorna do estado ocioso:** use essa configuração em conjunto com **Minutos de inatividade antes da senha ser necessária**. O usuário é solicitado a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

  > [!NOTE]
  > Essa configuração só se aplica a dispositivos Windows 10 Mobile.

#### <a name="encryption"></a>Criptografia
- **Exigir criptografia no dispositivo móvel:** defina esta opção como **Sim** para exigir que o dispositivo seja criptografado para se conectar aos recursos.

### <a name="device-health-settings"></a>Configurações de integridade do dispositivo
- **Exigir que os dispositivos sejam reportados como íntegros:** você pode definir uma regra para exigir que os dispositivos **Windows 10 Mobile** sejam relatados como íntegros nas políticas de conformidade novas ou existentes.  Se essa configuração estiver habilitada, dispositivos Windows 10 serão avaliados por meio do HAS (Serviço de Atestado de Integridade) para os seguintes pontos de dados:
  -  **BitLocker habilitado**: quando o BitLocker está ativado, o dispositivo é capaz de proteger os dados armazenados na unidade contra acesso não autorizado quando o sistema é desligado ou entra no modo de hibernação. A Criptografia de Unidade de Disco Windows BitLocker criptografa todos os dados armazenados no volume do sistema operacional Windows. O BitLocker usa o TPM para ajudar a proteger o sistema operacional Windows e os dados do usuário. O BitLocker também ajuda a garantir que o computador não seja adulterado, mesmo que seja autônomo ou seja perdido ou roubado. Se o computador estiver equipado com um TPM compatível, o BitLocker usará o TPM para bloquear as chaves de criptografia que ajudam a proteger os dados. Como resultado, as chaves não podem ser acessadas até que o TPM tenha verificado o estado do computador.
  -  **Integridade de código habilitada:** a integridade de código é um recurso que valida a integridade de um arquivo de sistema ou driver cada vez que ele é carregado na memória. A integridade de código detecta quando um arquivo de sistema ou driver não assinado está sendo carregado no kernel. Ela também detecta se um arquivo de sistema foi modificado por software mal-intencionado que está sendo executado por uma conta de usuário com privilégios de administrador.
  - **Inicialização Segura habilitada:** quando a Inicialização Segura está habilitada, o sistema é forçado a inicializar para um estado confiável de fábrica. Além disso, quando a Inicialização Segura é habilitada, os principais componentes usados para inicializar o computador devem ter assinaturas criptográficas corretas que são confiáveis para a organização que fabricou o dispositivo. O firmware UEFI confirma isso antes de permitir que o computador seja iniciado. Se todos os arquivos foram violados, interrompendo sua assinatura, o sistema não inicializará.

  > [!IMPORTANT]
  > Os dispositivos Windows não dão suporte a software **ELAM** (Antimalware de Início Antecipado) de terceiros instalados como parte do Atestado de integridade do dispositivo.

  Para obter informações sobre como funciona o serviço HAS, consulte [CSP do Estado de Integridade](https://msdn.microsoft.com/library/dn934876.aspx).
###  <a name="device-property-settings"></a>Configurações de propriedade do dispositivo
- **SO mínimo exigido**: quando um dispositivo não atender ao requisito mínimo de versão do SO, ele será relatado como não compatível.
    É exibido um link com informações sobre como atualizar. O usuário pode optar por atualizar seu dispositivo e, depois disso, poderá acessar os recursos da empresa.

- **Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.


## <a name="compliance-policy-settings-for-windows-pcs"></a>Configurações da política de conformidade para computadores Windows
As configurações listadas nesta seção têm suporte em computadores Windows.
### <a name="system-security-settings"></a>Configurações de segurança do sistema
#### <a name="password"></a>Senha
- **Comprimento mínimo da senha**: com suporte no Windows 8.1.

  Especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.

  Para dispositivos acessados com uma conta da Microsoft, a política de conformidade não será avaliada corretamente se o **Comprimento mínimo da senha** tiver mais de oito caracteres ou se o **Número mínimo de conjuntos de caracteres** for maior do que dois.

- **Tipo de senha necessária** com suporte no Windows RT, Windows RT 8.1 e Windows 8.1.

  Especifique se o usuário deve criar uma senha **Alfanumérica** ou **Numérica**.

- **Número mínimo de conjuntos de caracteres**: com suporte no Windows RT, Windows RT 8.1 e Windows 8.1.

  Se **Tipo de senha necessária** for definido como **Alfanumérico**, essa configuração especificará o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
  -   Letras minúsculas
  -   Letras maiúsculas
  -   Símbolos
  -   Números     

  Definir um número mais alto para essa configuração exigirá que o usuário crie uma senha mais complexa. Para dispositivos acessados com uma conta da Microsoft, a política de conformidade não será avaliada corretamente se o **Comprimento mínimo da senha** tiver mais de oito caracteres ou se o **Número mínimo de conjuntos de caracteres** for maior do que dois.

- **Minutos de inatividade antes que a senha seja exigida**: com suporte no Windows RT, Windows RT 8.1 e Windows 8.1.

  Especifique o tempo ocioso antes que o usuário precise inserir novamente sua senha.

- **Expiração de senha (dias)**: com suporte no Windows RT, Windows RT 8.1 e Windows 8.1.

  Selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.

- **Lembrar histórico de senha**: com suporte no Windows RT, Windows RT e Windows 8.1.

  Use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores**: com suporte no Windows RT, Windows RT 8.1 e Windows 8.1.

  Se a opção **Lembrar histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.

### <a name="device-health-settings"></a>Configurações de integridade do dispositivo
- **Exigir que os dispositivos sejam reportados como íntegros**: com suporte em dispositivos Windows 10.
Você pode definir uma regra para exigir que os dispositivos Windows 10 sejam relatados como íntegros em políticas de conformidade novas ou existentes. Se essa configuração estiver habilitada, dispositivos Windows 10 serão avaliados por meio do HAS (Serviço de Atestado de Integridade) para os seguintes pontos de dados:
  -  **BitLocker habilitado**: quando o BitLocker está ativado, o dispositivo é capaz de proteger os dados armazenados na unidade contra acesso não autorizado quando o sistema é desligado ou entra no modo de hibernação. A Criptografia de Unidade de Disco Windows BitLocker criptografa todos os dados armazenados no volume do sistema operacional Windows. O BitLocker usa o TPM para ajudar a proteger o sistema operacional Windows e os dados do usuário. O BitLocker também ajuda a garantir que o computador não seja adulterado, mesmo que seja autônomo ou seja perdido ou roubado. Se o computador estiver equipado com um TPM compatível, o BitLocker usará o TPM para bloquear as chaves de criptografia que ajudam a proteger os dados. Como resultado, as chaves não podem ser acessadas até que o TPM tenha verificado o estado do computador.
  -  **Integridade de código habilitada:** a integridade de código é um recurso que valida a integridade de um arquivo de sistema ou driver cada vez que ele é carregado na memória. A integridade de código detecta quando um arquivo de sistema ou driver não assinado está sendo carregado no kernel. Ela também detecta se um arquivo de sistema foi modificado por software mal-intencionado que está sendo executado por uma conta de usuário com privilégios de administrador.
  - **Inicialização Segura habilitada:** quando a Inicialização Segura está habilitada, o sistema é forçado a inicializar para um estado confiável de fábrica. Além disso, quando a Inicialização Segura é habilitada, os principais componentes usados para inicializar o computador devem ter assinaturas criptográficas corretas que são confiáveis para a organização que fabricou o dispositivo. O firmware UEFI confirma isso antes de permitir que o computador seja iniciado. Se todos os arquivos foram violados, interrompendo sua assinatura, o sistema não inicializará.
  - **Antimalware de Início Antecipado habilitado:** o ELAM (Antimalware de Início Antecipado) fornece proteção para os computadores na sua rede quando eles são iniciados e antes de inicializar drivers de terceiros.

  Para obter informações sobre como funciona o serviço HAS, consulte [CSP do Estado de Integridade](https://msdn.microsoft.com/library/dn934876.aspx).

### <a name="device-property-settings"></a>Configurações de propriedade do dispositivo
- **SO mínimo necessário**: com suporte no Windows 8.1 e no Windows 10.

  Especifique o número de major.minor.build aqui. O número de versão deve corresponder à versão retornada pelo comando **winver**.

  Quando um dispositivo tiver uma versão mais antiga que a versão de sistema operacional especificada, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário pode optar por atualizar seu dispositivo e, depois disso, poderá acessar os recursos da empresa.

- **Versão máxima do SO permitida**: com suporte no Windows 8.1 e no Windows 10.

  Quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

Para localizar a versão do SO que deve ser usada para as configurações **SO mínimo necessário** e **Versão máxima do SO permitida**, execute o comando **winver** no prompt de comando. O comando **winver** retorna a versão relatada do sistema operacional.

- Computadores com Windows 8.1 retornam a versão **6.3**. Se a regra de versão do sistema operacional for definida como Windows 8.1 para Windows, então o dispositivo será relatado como não compatível mesmo que o dispositivo tenha o Windows 8.1.

- Para computadores que executam o Windows 10, a versão deve ser definida como **10.0** mais o número de build do sistema operacional retornado pelo comando **winver**. Por exemplo, poderia ser algo como 10.0.10586.
> ![Versão do build do SO realçada na caixa de diálogo "Sobre o Windows"](./media/ca_win10-os-version.png)
