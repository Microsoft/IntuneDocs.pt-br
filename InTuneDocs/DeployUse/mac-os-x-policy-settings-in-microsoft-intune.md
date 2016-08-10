---
title: "Configurações de política Mac OS X | Microsoft Intune"
description: "O Intune fornece uma variedade de configurações gerais internas que você pode definir em dispositivos Mac OS X. Além disso, use a ferramenta Apple Configurator para criar configurações personalizadas que não estão disponíveis no Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 744fc6ecbabdccbfab38f45745505d635fb7e190
ms.openlocfilehash: c6b010e49b4e581dad056aa6e8bb17123030f7b0


---

# Definições de política de configuração do Mac OS X no Microsoft Intune

O Intune fornece uma variedade de configurações gerais internas que você pode definir em dispositivos Mac OS X. Além disso, use a ferramenta Apple Configurator para criar configurações personalizadas que não estão disponíveis no Intune.

## Definições de política de configuração geral

Use a **Política de configuração geral do Mac OS X** do Microsoft Intune para definir configurações para:

-   **Configurações de segurança de dispositivo**. Escolha de uma lista de configurações predefinidas que permitem controlar uma variedade de recursos e funcionalidades no dispositivo.

-   **Aplicativos compatíveis e incompatíveis**. Especifique uma lista de aplicativos que são compatíveis ou não compatíveis em sua empresa. O Relatório de Aplicativos Incompatíveis pode ser usado para exibir a conformidade de aplicativos especificados na lista em relação aos aplicativos que os usuários instalaram (mas não é possível bloquear efetivamente a instalação do aplicativo).

Se a configuração que você está procurando não aparecer nessa lista, você poderá criá-la usando uma política personalizada do Mac OS X que lhe permite importar configurações criadas usando a Ferramenta Apple Configurator. Para obter mais informações, consulte “Configurações de política personalizadas” mais adiante neste tópico.

### Configurações de senha

|Nome da configuração|Detalhes|
|----------------|---------------|
|**Exigir uma senha para desbloquear dispositivos**|Especifique se o usuário deve usar uma senha para acessar o computador Mac. **Importante:** ao contrário de dispositivos iOS, em dispositivos Mac OS X o usuário não é notificado imediatamente para atualizar sua senha de modo a manter a conformidade com essa configuração.|
|**Tipo de senha necessária**|Especifique se a senha usada pode ser apenas **Numérica** ou se deve ser **Alfanumérica** (conter letras e números). **Importante:** essa configuração só tem suporte no Mac OS X versão 10.10.3 e posterior.|
|**Número de caracteres complexos necessários na senha**|Especifica o número de caracteres complexos necessários na senha (de **0** a **4**).<br /><br />Um caractere complexo é um símbolo, como **?**.|
|**Comprimento mínimo da senha**|Especifique o comprimento mínimo da senha (**4** a **14** caracteres).|
|**Permitir senha simples**|Permita o uso de senhas simples como **0000** ou **1234**.|
|**Minutos de inatividade antes de a senha ser necessária**|Especifique por quanto tempo o computador deverá ficar inativo antes que uma senha seja necessária para desbloqueá-lo.|
|**Expiração da senha (dias)**|Especifique o número de dias que precisam transcorrer antes que o usuário precise alterar a senha (de **1** a **255** dias).|
|**Lembrar de histórico de senha**|Impeça que o usuário reutilize uma senha anterior. Quando isso for definido, você também poderá definir **Evitar a reutilização de senhas anteriores** para especificar o número de senhas usadas anteriormente que não podem ser reutilizadas (de **1** a **24**).|
|**Minutos de inatividade antes que o protetor de tela seja ativado**|Especifique o período de tempo pelo qual o computador deve permanecer ocioso antes que o protetor de tela seja ativado.|

### Configurações para aplicativos compatíveis e não compatíveis
Na lista Aplicativos **Compatíveis &amp; Incompatíveis para Mac OS X**, habilite **Configurações gerenciadas para dispositivos** e, em seguida, especifique uma lista de aplicativos compatíveis ou incompatíveis usando as informações a seguir.

> [!NOTE]
> Uma única política só pode conter somente uma lista de aplicativos compatíveis ou de aplicativos incompatíveis. Não é possível especificar ambos na mesma política.
>
> O Intune permite relatar os dispositivos com aplicativos incompatíveis. Ele não bloqueia a instalação nem remove os aplicativos não compatíveis.

|Nome da configuração|Detalhes|
|----------------|---------------|
|**Reportar não conformidade quando os usuários instalam os aplicativos listados**|Exibe os aplicativos Mac OS X que os usuários não têm permissão para instalar. Se os usuários instalarem qualquer um desses aplicativos, eles serão informados em **Relatórios de aplicativos não compatíveis**.|
|**Relatar não conformidade quando os usuários instalam aplicativos não listados**|Exibe os aplicativos Mac OS X que os usuários têm permissão para instalar. Se os usuários instalarem quaisquer outros aplicativos, eles serão informados em **Relatórios de aplicativos não compatíveis**.|
|**Adicionar**|Adicionar um aplicativo à lista selecionada. Especifique um nome de sua preferência, opcionalmente, o fornecedor do aplicativo e a ID do pacote do aplicativo. **Dica:** para localizar a ID do pacote de um aplicativo, use as seguintes etapas em um computador Mac que tem o aplicativo instalado:<ol><li>Abra a pasta na qual o aplicativo está instalado (por exemplo, **/Applications**).</li><li>Selecione o pacote *&lt;Nome do Aplicativo&gt;***.app** e escolha **Mostrar Conteúdo do Pacote**.</li><li>Abra o arquivo **Info.plist**.</li><li>Verifique o valor associado à chave **CFBundleIdentifier**.</li></ol>O formato para a ID do pacote é **com.contoso.nomedoaplicativo**.|
|**Importar aplicativos**|Importar uma lista dos aplicativos que você especificou em um arquivo de valores separados por vírgulas. No arquivo, use este formato: nome do aplicativo, editor e ID do pacote do aplicativo.|
|**Editar**|Editar o nome, editor e ID do pacote do aplicativo para o aplicativo selecionado.|
|**Excluir**|Excluir o aplicativo selecionado da lista.|
> [!TIP]
> Para obter mais informações sobre relatórios do Intune, consulte [Entender as operações do Microsoft Intune usando relatórios](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Quando um dispositivo Mac OS X está no modo de suspensão, as políticas e os perfis não podem ser entregues nem inventariados. Assim, o console do Intune pode exibir temporariamente o status **Erro nas configurações de política** até a próxima vez que o dispositivo sair do modo de suspensão.

### Monitore aplicativos compatíveis e não compatíveis
Use os **Relatórios de aplicativos incompatíveis** para exibir a conformidade dos aplicativos especificados por você.

#### Para executar um relatório

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Relatórios** &gt; **Relatórios de Aplicativos Incompatíveis**.

2.  Selecione os grupos de dispositivos que você deseja verificar, se deseja verificar se há aplicativos compatíveis, aplicativos incompatíveis ou ambos e então escolha **Exibir Relatório**.

## Configurações de política personalizada do Mac OS X no Microsoft Intune
Use a **Política de configuração personalizada do Mac OS X** do Microsoft Intune para implantar configurações que você criou usando a [ferramenta Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) em dispositivos Mac OS X. Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração. Você pode, então, importar este perfil de configuração para uma política personalizada do Mac OS X do Intune e implantar as configurações para usuários e dispositivos na sua organização.

Essa funcionalidade permite que você implante configurações do Mac OS X que não podem ser configuradas com a política de configuração geral do Mac OS X do Intune.

### Pré-requisitos
Antes de começar, você precisa ter instalado o Apple Configurator e criado um arquivo de configuração que contém as configurações que deseja implantar para usuários ou dispositivos. Você pode baixar o Apple Configurator e aprender sobre ele na [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

> [!NOTE]
> O Intune não relata a conformidade de configurações individuais em uma política personalizada do Mac OS X. No entanto, a conformidade geral da política é informada.

### Configurações gerais

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para a política personalizada do Mac OS X para ajudar a identificá-la no console do Intune.|
    |**Descrição**|Forneça uma descrição que dê uma visão geral da política personalizada do Mac OS X e outras informações relevantes que o ajudarão a localizá-la.|


### Configurações Personalizadas

|Nome da configuração|Detalhes|
    |----------------|--------------------|
    |**Nome do perfil de configuração personalizada (exibido aos usuários)**|Forneça um nome para a política, já que ela será exibida no dispositivo e em relatórios da política do Intune.|
    |**Arquivo de configuração de perfil**|Clique em **Importar** e então navegue até o perfil de configuração criado usando o Apple Configurador. **Dica:** consulte “How to create a configuration profile file” (Como criar um arquivo de perfil de configuração) neste tópico para obter ajuda na criação do perfil de configuração.|
    |**Detalhes da configuração do perfil**|Exibir o código XML para o perfil de configuração que você importou.|



### Como criar um arquivo de perfil de configuração
Você pode criar o arquivo de perfil de configuração usado pela política personalizada de duas maneiras:

-   Exportar o arquivo (com a extensão **.mobileconfig**) da ferramenta Apple Configurator.

-   Crie o arquivo você mesmo, usando o esquema apropriado da [Referência de chave de perfil de configuração da Apple](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO1-->


