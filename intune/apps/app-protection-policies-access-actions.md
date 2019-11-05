---
title: Apagar dados usando ações de inicialização condicional da política de proteção de aplicativos
titleSuffix: Microsoft Intune
description: Saiba como apagar dados seletivamente usando ações de inicialização condicional da política de proteção de aplicativos no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 882c542d6a1d981b9924bb33eee40f03b41689f7
ms.sourcegitcommit: 4bf23327af734a9811d555fbd566c31239e2acd6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999486"
---
# <a name="selectively-wipe-data-using-app-protection-policy-conditional-launch-actions-in-intune"></a>Apagar dados seletivamente usando ações de inicialização condicional da política de proteção de aplicativos no Intune

Usando as políticas de proteção de aplicativo do Intune, você pode definir configurações para impedir que usuários finais acessem uma conta ou um aplicativo corporativo. Essas configurações são direcionadas aos requisitos de realocação de dados e acesso definidos pela sua organização para assuntos como dispositivos com jailbreak e versões mínimas de sistema operacional.
 
Você pode escolher explicitamente apagar os dados corporativos da empresa do dispositivo do usuário final como uma ação a ser executada em caso de não conformidade usando essas configurações. Para algumas configurações, você poderá configurar várias ações, como bloquear o acesso e apagar os dados com base em diferentes valores especificados.

## <a name="create-an-app-protection-policy-using-conditional-launch-actions"></a>Criar política de proteção de aplicativos usando ações de inicialização condicional

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, selecione **Aplicativos clientes** > **Políticas de proteção de aplicativo**.
4. Clique em **Adicionar uma política** (você também pode editar uma política existente). 
5. Clique em **Definir as configurações necessárias** para ver a lista de configurações disponíveis a serem configuradas para a política. 
6. Rolando para baixo no painel Configurações, você verá uma seção intitulada **Inicialização condicional** com uma tabela editável.

    ![Captura de tela das ações de acesso de proteção de aplicativo do Intune](./media/app-protection-policies-access-actions/apps-selective-wipe-access-actions01.png)

7. Selecione uma **Configuração** e insira o **Valor** que os usuários precisam cumprir para entrar no aplicativo da empresa. 
8. Selecione a **Ação** a ser executada se os usuários não atenderem aos seus requisitos. Em alguns casos, várias ações podem ser definidas para uma única configuração. Para obter mais informações, confira [Como criar e atribuir políticas de proteção de aplicativo](app-protection-policies.md).

>[!NOTE]
> Para usar a configuração **Modelos de dispositivo ou fabricantes de dispositivo**, insira uma lista separada por ponto e vírgula com os identificadores de modelos de dispositivos (iOS) ou fabricantes de dispositivos (Android). Evite usar espaços em listas de vários valores. Esses valores não diferenciam maiúsculas de minúsculas. 

## <a name="policy-settings"></a>Configurações de política 

A tabela de configurações da política de proteção do aplicativo tem colunas para **Configuração**, **Valor** e **Ação**.

### <a name="ios-policy-settings"></a>Configurações de política do iOS
Para iOS, você poderá configurar ações para as seguintes configurações usando a lista suspensa **Configuração**:
- Máximo de tentativas de PIN
- Período de cortesia offline
- Dispositivos com jailbreak ou com root
- Versão mínima do sistema operacional
- Versão mínima do aplicativo
- Versão mínima do SDK
- Modelos de dispositivo
- Nível máximo permitido de ameaça ao dispositivo

Para usar a configuração **Modelos de dispositivo**, insira uma lista separada por ponto e vírgula de identificadores de modelo iOS. Você pode encontrar um identificador de modelo iOS na coluna Tipo de Dispositivo na [documentação de suporte do HockeyApp](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/ios-device-types).<br>
Exemplo de entrada: *iPhone5,2;iPhone5,3*

Em dispositivos de usuário final, o cliente do Intune executaria uma ação com base em uma correspondência simples de cadeias de caracteres de modelo de dispositivo especificadas no Intune para Políticas de Proteção de Aplicativo. A correspondência depende totalmente do que é relatado pelo dispositivo. Você (o administrador de TI) é incentivado a garantir que o comportamento pretendido ocorra testando essa configuração com base em uma variedade de fabricantes e modelos de dispositivos e direcionando-o a um grupo de usuários pequeno. O valor padrão é **Não configurado**.<br>
Defina uma das seguintes ações: 
- Permitir especificado (Bloquear não especificado)
- Permitir especificado (Apagar não especificado)

**O que acontece se o administrador de TI insere uma lista diferente de identificadores de modelo iOS entre políticas direcionadas aos mesmos aplicativos para o mesmo usuário do Intune?**<br>
Quando ocorrem conflitos entre duas políticas de proteção de aplicativo para os valores configurados, o Intune normalmente usa a abordagem mais restritiva. Dessa forma, a política resultante enviada para o aplicativo de destino que está sendo aberto pelo usuário do Intune direcionado seria uma interseção dos identificadores de modelo iOS listados na *Política A* e *Política B* voltadas para o mesma combinação de usuário/aplicativo. Por exemplo, a *Política A* especifica "iPhone5,2; iPhone5,3", enquanto a *Política B* especifica"iPhone5,3", a política resultante direcionada pelo usuário do Intune com ambas *Política A* e *Política B* será "iPhone5,3". 

### <a name="android-policy-settings"></a>Configurações da política do Android

Para o Android, você poderá configurar ações para as seguintes configurações usando a lista suspensa **Configuração**:
- Máximo de tentativas de PIN
- Período de cortesia offline
- Dispositivos com jailbreak ou com root
- Versão mínima do sistema operacional
- Versão mínima do aplicativo
- Versão mínima de patch
- Fabricantes de dispositivo
- Atestado de dispositivo SafetyNet
- Exigir verificação de ameaças em aplicativos
- Versão mínima do Portal da Empresa
- Nível máximo permitido de ameaça ao dispositivo

Com a **Versão mínima do Portal da Empresa**, você pode determinar uma versão mínima definida específica do Portal da Empresa que é imposta em um dispositivo de usuário final. Essa configuração de inicialização condicional permite que você defina valores para **Bloquear acesso**, **Apagar dados** e **Avisar** como possíveis ações quando cada valor não for atendido. Os formatos possíveis para esse valor seguem o padrão *[Major].[Minor]* , *[Major].[Minor].[Build]* ou *[Major].[Minor].[Build].[Revision]* . Considerando que alguns usuários finais podem preferir não receber uma atualização forçada de aplicativos no local, a opção "Avisar" pode ser ideal ao definir essa configuração. O Google Play Store faz um bom trabalho ao enviar apenas os bytes delta para atualizações do aplicativo, mas isso ainda pode ser uma grande quantidade de dados que o usuário talvez não queira utilizar caso esteja com dados no momento da atualização. Forçar uma atualização e, portanto, baixar um aplicativo atualizado pode resultar em encargos de dados inesperados no momento da atualização. A configuração **Versão mínima do Portal da Empresa**, se configurada, afetará todos os usuários finais que receberem a versão 5.0.4560.0 do Portal da Empresa e todas as versões futuras do Portal da Empresa. Essa configuração não terá nenhum efeito nos usuários que usam uma versão do Portal da Empresa mais antiga do que a versão na qual esse recurso é lançado. Os usuários finais que usam as atualizações automáticas do aplicativo nos dispositivos provavelmente não verão nenhuma caixa de diálogo desse recurso, considerando que eles provavelmente estarão na versão mais recente do Portal da Empresa. Essa configuração é apenas para Android, com proteção de aplicativo para dispositivos registrados e não registrados.

Para usar a configuração **Fabricantes de dispositivo**, insira uma lista separada por ponto e vírgula de fabricantes Android. Você pode encontrar o fabricante Android de um dispositivo nas configurações do dispositivo.<br>
Entrada de exemplo: *Fabricante A;Fabricante B* 

>[!NOTE]
> Estes são alguns fabricantes comuns relatados por dispositivos usando o Intune e podem ser usados como entrada: Asus;Blackberry;Bq;Gionee;Google;Hmd global;Htc;Huawei;Infinix;Kyocera;Lemobile;Lenovo;Lge;Motorola;Oneplus;Oppo;Samsung;Sharp;Sony;Tecno;Vivo;Vodafone;Xiaomi;Zte;Zuk

Em dispositivos de usuário final, o cliente do Intune executaria uma ação com base em uma correspondência simples de cadeias de caracteres de modelo de dispositivo especificadas no Intune para Políticas de Proteção de Aplicativo. A correspondência depende totalmente do que é relatado pelo dispositivo. Você (o administrador de TI) é incentivado a garantir que o comportamento pretendido ocorra testando essa configuração com base em uma variedade de fabricantes e modelos de dispositivos e direcionando-o a um grupo de usuários pequeno. O valor padrão é **Não configurado**.<br>
Defina uma das seguintes ações: 
- Permitir especificado (Bloquear não especificado)
- Permitir especificado (Apagar em não especificado)

**O que acontece se o administrador de TI insere uma lista diferente de fabricantes Android entre políticas direcionadas aos mesmos aplicativos para o mesmo usuário do Intune?**<br>
Quando ocorrem conflitos entre duas políticas de proteção de aplicativo para os valores configurados, o Intune normalmente usa a abordagem mais restritiva. Dessa forma, a política resultante enviada para o aplicativo de destino que está sendo aberto pelo usuário do Intune direcionado seria uma interseção dos fabricantes Android listados na *Política A* e *Política B* voltadas para o mesma combinação de usuário/aplicativo. Por exemplo, a *Política A* especifica "Google;Samsung" e a *Política B* especifica "Google"; a política resultante que o usuário do Intune direcionou pela *Política A* e pela *Política B* será "Google". 

### <a name="additional-settings-and-actions"></a>Ações e configurações adicionais 

Por padrão, a tabela terá linhas populadas como as configurações definidas para **Período de carência offline** e **Máximo de tentativas de PIN**, se a configuração **Exigir PIN para acesso** estiver definida como **Sim**.
 
Para definir uma configuração, selecione uma configuração na lista suspensa na coluna **Configuração**. Depois que uma configuração for selecionada, a caixa de texto editável será habilitada na coluna **Valor** na mesma linha, se for necessário definir um valor. Além disso, a lista suspensa ficará habilitada na coluna **Ação** com o conjunto de ações de inicialização condicionais aplicáveis à configuração. 

A lista a seguir fornece a lista de ações comuns:
- **Bloquear acesso** – impedir que o usuário final acesse o aplicativo corporativo.
- **Apagar dados** – apagar os dados corporativos do dispositivo do usuário final.
- **Avisar** – fornecer uma caixa de diálogo ao usuário final como uma mensagem de aviso.

Em alguns casos, como a configuração **Versão mínima do sistema operacional**, você pode definir a configuração para executar todas as ações aplicáveis, com base em números de versão diferentes. 

![Captura de tela das ações de acesso da proteção de aplicativo – versão mínima do sistema operacional](./media/app-protection-policies-access-actions/apps-selective-wipe-access-actions05.png)

Depois que uma configuração estiver totalmente configurada, a linha aparecerá em uma exibição somente leitura e estará disponível para ser editada a qualquer momento. Além disso, a linha terá uma lista suspensa disponível para seleção na coluna **Configuração**. As configurações que já foram definidas e que não permitem várias ações não estarão disponíveis para seleção na lista suspensa.

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre as políticas de proteção de aplicativo do Intune, confira:
- [Como criar e atribuir as políticas de proteção de aplicativo](app-protection-policies.md)
- [Configurações da política de proteção de aplicativo do iOS](app-protection-policy-settings-ios.md)
- [Configurações da política de proteção de aplicativo do Android no Microsoft Intune](app-protection-policy-settings-android.md) 
