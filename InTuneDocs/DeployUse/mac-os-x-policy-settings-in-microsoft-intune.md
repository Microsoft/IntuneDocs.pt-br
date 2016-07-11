---
title: "Configurações de política Mac OS X | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 8c1f4f209c5ec704290882b8f6f71e0b1b01d21c
ms.openlocfilehash: bbbb666fdc34a82d247d760d156d48c5ac72374c


---

# Definições de política de configuração do Mac OS X no Microsoft Intune

## Definições de política de configuração geral

Use a **Política de configuração geral do Mac OS X** do Microsoft Intune para definir configurações para:

-   **Configurações de segurança de dispositivo** - escolha de uma lista de configurações predefinidas que permitem controlar uma variedade de recursos e funcionalidades no dispositivo.

-   **Aplicativos compatíveis e não compatíveis** - especifique uma lista de aplicativos que são compatíveis ou não com sua empresa. O Relatório de Aplicativos Incompatíveis pode ser usado para exibir a conformidade de aplicativos especificados na lista em relação aos aplicativos que os usuários instalaram (mas não é possível bloquear efetivamente a instalação do aplicativo).

Se a configuração que você está procurando não aparecer nessa lista, você poderá criá-la usando uma política personalizada do Mac OS X que lhe permite importar configurações criadas usando a ferramenta Apple Configurator. Para obter mais informações, consulte **Configurações de política personalizadas** mais adiante neste tópico.

### Configurações de senha

|Nome da configuração|Detalhes|
|----------------|---------------|
|**Exigir uma senha para desbloquear dispositivos**|Especifica se o usuário deve usar uma senha para acessar o computador Mac. **Importante:** ao contrário de dispositivos iOS, em dispositivos Mac OS X o usuário não é notificado imediatamente para atualizar sua senha de modo a manter a conformidade com essa configuração.|
|**Tipo de senha necessária**|Especifica se a senha usada pode ser apenas numérica ou se deve ser **alfanumérica** (conter letras e números). **Importante:** essa configuração só tem suporte no Mac OS X versão 10.10.3 e posterior.|
|**Número de caracteres complexos necessários na senha**|Especifica o número de caracteres complexos necessários na senha (de **0** - **4**).<br /><br />Um caractere complexo é um símbolo, como "**?**"|
|**Comprimento mínimo da senha**|Especifica o comprimento mínimo para a senha (entre **4** e **14** caracteres).|
|**Permitir senha simples**|Permite que os usuários criem senhas simples como "**0000**" ou "**1234**".|
|**Minutos de inatividade antes de a senha ser necessária**|Especifica por quanto tempo o computador deverá ficar inativo antes que uma senha seja necessária para desbloqueá-lo.|
|**Expiração da senha (dias)**|Especifica o número de dias que precisam transcorrer antes que o usuário precise alterar a senha (de **1** - **255** dias).|
|**Lembrar de histórico de senha**|Essa configuração é usada para impedir que o usuário reutilize uma senha anterior. Quando ela estiver definida, você também poderá definir **Evitar a reutilização de senhas anteriores** para especificar o número de senhas usadas anteriormente que não podem ser reutilizadas (de **1** - **24**).|
|**Minutos de inatividade antes que o protetor de tela seja ativado**|Especifica o período de tempo pelo qual o computador deve permanecer ocioso antes que o protetor de tela seja ativado.|

### Configurações para aplicativos compatíveis e não compatíveis
Na lista Aplicativos **Compatíveis &amp; Incompatíveis para Mac OS X**, habilite **Configurações gerenciadas para dispositivos** e, em seguida, especifique uma lista de aplicativos compatíveis ou incompatíveis usando as seguintes informações:

> [!NOTE]
> Uma única política só pode conter uma lista de compatibilidade ou de incompatibilidade. Não é possível especificar ambos na mesma política.
> 
> O Intune permite relatar os dispositivos com aplicativos incompatíveis. Ele não bloqueia a instalação nem remove os aplicativos não compatíveis.

|Nome da configuração|Detalhes|
|----------------|---------------|
|**Reportar não conformidade quando os usuários instalam os aplicativos listados**|Lista os aplicativos Mac OS X que os usuários não têm permissão para instalar. Se os usuários instalarem qualquer um desses aplicativos, eles serão informados nos **Relatórios de aplicativos não compatíveis**.|
|**Relatar não conformidade quando os usuários instalam aplicativos não listados**|Lista os aplicativos Mac OS X que os usuários têm permissão para instalar. Se os usuários instalarem quaisquer outros aplicativos, eles serão informados nos **Relatórios de aplicativos não compatíveis**.|
|**Adicionar**|Adiciona um aplicativo à lista selecionada. Especifique um nome de sua preferência, opcionalmente, o fornecedor do aplicativo e a ID do pacote do aplicativo. **Dica:** para localizar a ID do pacote de um aplicativo, use as seguintes etapas em um computador Mac que tem o aplicativo instalado:<ol><li>Abra a pasta na qual o aplicativo está instalado (por exemplo, **/Applications**)</li><li>Selecione o pacote *&lt;Nome do Aplicativo&gt;***.app** e escolha **Mostrar Conteúdo do Pacote**</li><li>Abra o arquivo **Info.plist** </li><li>Verifique o valor associado à chave **CFBundleIdentifier**</li></ol>O formato para a ID do pacote é **com.contoso.nomedoaplicativo**|
|**Importar aplicativos**|Importa uma lista dos aplicativos que você especificou em um arquivo de valores separados por vírgulas. Use o formato, nome do aplicativo, editor e ID do pacote do aplicativo encontrados no arquivo.|
|**Editar**|Permite editar o nome, editor e ID do pacote do aplicativo para o aplicativo selecionado.|
|**Excluir**|Exclui o aplicativo selecionado da lista.|
> [!TIP]
> Para obter mais informações sobre relatórios do Intune, consulte [Entender as operações do Microsoft Intune usando relatórios](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Quando um dispositivo Mac OS X está no modo de Suspensão, as políticas e os perfis não podem ser entregues nem inventariados. Assim, o console do Intune pode exibir temporariamente o status **Erro nas configurações de política** até a próxima vez que o dispositivo sair do modo de Suspensão.

### Monitore aplicativos compatíveis e não compatíveis
Use os **Relatórios de aplicativos incompatíveis** para exibir a compatibilidade dos aplicativos especificados por você.

#### Para executar o relatório

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Relatórios** &gt; **Relatórios de Aplicativos Não Compatíveis**.

2.  Selecione os grupos de dispositivos que você deseja verificar, se deseja verificar se há aplicativos compatíveis, aplicativos incompatíveis ou ambos, e clique em **Exibir relatório**.

## Configurações de política personalizada do Mac OS X no Microsoft Intune
Use a **política de configuração personalizada do Mac OS X** do Microsoft Intune para implantar configurações que você criou usando a ferramenta [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) em dispositivos Mac OS X. Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração. Você pode, então, importar este perfil de configuração para uma política personalizada do Mac OS X do Intune e implantar as configurações para usuários e dispositivos na sua organização.

Essa funcionalidade destina-se a permitir que você implante configurações do Mac OS X que não podem ser configuradas com a política de configuração geral do Mac OS X do Intune.

### Pré-requisitos
Antes de começar, você precisa ter instalado o Apple Configurator e criado um arquivo de configuração que contém as configurações que deseja implantar para usuários ou dispositivos. Você pode baixar e aprender sobre o Apple Configurator na [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

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
    |**Nome do perfil de configuração personalizada (exibido aos usuários)**|Forneça um nome para a política, como ela será exibida no dispositivo e em relatórios da política do Intune.|
    |**Arquivo de configuração de perfil**|Clique em **Importar**e navegue até o perfil de configuração que você criou usando o Apple Configurador. **Dica:** consulte **How to create a configuration profile file (Como criar um arquivo de perfil de configuração)** neste tópico para obter ajuda na criação do perfil de configuração.|
    |**Detalhes da configuração do perfil**|Exibe o código xml para o perfil de configuração que você importou.|



### Como criar um arquivo de perfil de configuração
Você pode criar o arquivo de perfil de configuração usado pela política personalizada de duas maneiras:

-   Exportar o arquivo (com a extensão **.mobileconfig**) da ferramenta Apple Configurator.

-   Criar o arquivo você mesmo, usando o esquema apropriado da [Referência de chave de perfil de configuração da Apple](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


> [!IMPORTANT]
> Quando um dispositivo Mac OS X está no modo de Suspensão, as políticas e os perfis não podem ser entregues nem inventariados. Assim, o console do Intune pode exibir temporariamente o status **Erro nas configurações de política** até a próxima vez que o dispositivo sair do modo de Suspensão.

### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jun16_HO4-->


