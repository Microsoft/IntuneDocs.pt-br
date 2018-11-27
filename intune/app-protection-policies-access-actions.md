---
title: Apagar dados seletivamente usando ações de acesso da política de proteção de aplicativo
titleSuffix: Microsoft Intune
description: Saiba como apagar dados seletivamente usando ações de acesso da política de proteção de aplicativo no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/3/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f8173b409eb82a3bb98ef0a30570e489fac1fc49
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189683"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Apagar dados seletivamente usando ações de acesso da política de proteção de aplicativo no Intune

Usando as políticas de proteção de aplicativo do Intune, você pode definir configurações para impedir que usuários finais acessem uma conta ou um aplicativo corporativo. Essas configurações são direcionadas aos requisitos de realocação de dados e acesso definidos pela sua organização para assuntos como dispositivos com jailbreak e versões mínimas de sistema operacional.
 
Você pode escolher explicitamente apagar os dados corporativos da empresa do dispositivo do usuário final como uma ação a ser executada em caso de não conformidade usando essas configurações. Para algumas configurações, você poderá configurar várias ações, como bloquear o acesso e apagar os dados com base em diferentes valores especificados.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Criar uma política de proteção de aplicativo usando ações de acesso

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**.  
    O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos clientes** > **Políticas de proteção de aplicativo**.
4. Clique em **Adicionar uma política** (você também pode editar uma política existente). 
5. Clique em **Definir as configurações necessárias** para ver a lista de configurações disponíveis a serem configuradas para a política. 
6. Rolando para baixo no painel Configurações, você verá uma seção intitulada **Ações de Acesso** com uma tabela editável.

    ![Captura de tela das ações de acesso de proteção de aplicativo do Intune](./media/apps-selective-wipe-access-actions01.png)

7. Selecione uma **Configuração** e insira o **Valor** que os usuários precisam cumprir para entrar no aplicativo da empresa. 
8. Selecione a **Ação** a ser executada se os usuários não atenderem aos seus requisitos. Em alguns casos, várias ações podem ser definidas para uma única configuração. Para obter mais informações, confira [Como criar e atribuir políticas de proteção de aplicativo](app-protection-policies.md).

>[!NOTE]
> Para usar a configuração **Modelos de dispositivo ou fabricantes de dispositivo**, insira uma lista separada por ponto e vírgula de identificadores de modelo. Evite usar espaços em listas de vários valores. Esses valores não diferenciam maiúsculas de minúsculas. 

## <a name="policy-settings"></a>Configurações de política 

A tabela de configurações da política de proteção do aplicativo tem colunas para **Configuração**, **Valor** e **Ação**.

### <a name="ios-policy-settings"></a>Configurações de política do iOS
Para iOS, você poderá configurar ações para as seguintes configurações usando a lista suspensa **Configuração**:
-  Máximo de tentativas de PIN
-  Período de cortesia offline
-  Dispositivos com jailbreak ou com root
-  Versão mínima do sistema operacional
-  Versão mínima do aplicativo
-  Versão mínima do SDK
-  Modelos de dispositivo

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
-  Máximo de tentativas de PIN
-  Período de cortesia offline
-  Dispositivos com jailbreak ou com root
-  Versão mínima do sistema operacional
-  Versão mínima do aplicativo
-  Versão mínima de patch
-  Fabricantes de dispositivo

Para usar a configuração **Fabricantes de dispositivo**, insira uma lista separada por ponto e vírgula de fabricantes Android. Você pode encontrar o fabricante Android de um dispositivo nas configurações do dispositivo.<br>
Entrada de exemplo: *Fabricante A; Fabricante B* 

>[!NOTE]
> Estes são alguns fabricantes comuns relatados por meio de dispositivos que usam o Intune e que podem ser usados como entrada: Asus;Blackberry;Bq;Gionee;Google;Hmd global;Htc;Huawei;Infinix;Kyocera;Lemobile;Lenovo;Lge;Motorola;Oneplus;Oppo;Samsung;Sharp;Sony;Tecno;Vivo;Vodafone;Xiaomi;Zte;Zuk

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
-  **Bloquear acesso** – impedir que o usuário final acesse o aplicativo corporativo.
-  **Apagar dados** – apagar os dados corporativos do dispositivo do usuário final.
-  **Avisar** – fornecer uma caixa de diálogo ao usuário final como uma mensagem de aviso.

Em alguns casos, como a configuração **Versão mínima do sistema operacional**, você pode definir a configuração para executar todas as ações aplicáveis, com base em números de versão diferentes. 

![Captura de tela das ações de acesso da proteção de aplicativo do Intune – versão mínima do sistema operacional](./media/apps-selective-wipe-access-actions05.png)

Depois que uma configuração estiver totalmente configurada, a linha aparecerá em uma exibição somente leitura e estará disponível para ser editada a qualquer momento. Além disso, a linha terá uma lista suspensa disponível para seleção na coluna **Configuração**. As configurações que já foram definidas e que não permitem várias ações não estarão disponíveis para seleção na lista suspensa.

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre as políticas de proteção de aplicativo do Intune, confira:
- [Como criar e atribuir as políticas de proteção de aplicativo](app-protection-policies.md)
- [Configurações da política de proteção de aplicativo do iOS](app-protection-policy-settings-ios.md)
- [Configurações da política de proteção de aplicativo do Android no Microsoft Intune](app-protection-policy-settings-android.md) 
