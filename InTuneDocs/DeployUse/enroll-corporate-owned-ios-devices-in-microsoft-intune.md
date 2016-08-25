---
title: Registrar dispositivos iOS corporativos | Microsoft Intune
description: Registro de dispositivos iOS corporativos usando o DEP (Programa de Registro de Dispositivo) da Apple ou o Apple Configurator
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9b7b8f6e5182e228458f5ea75e804a638f1e2a2b
ms.openlocfilehash: ca05e94e72269c11db24b667f1d113c794cd8b23


---

# Registrar dispositivos iOS corporativos no Microsoft Intune
O Microsoft Intune dá suporte ao registro de dispositivos iOS corporativos usando o DEP (Programa de Registro do Dispositivo) da Apple ou a ferramenta [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) executada em um computador Mac.

**Pré-requisito:**  [Certificado do Apple Push Notification Service](set-up-ios-and-mac-management-with-microsoft-intune.md)

Você pode registrar dispositivos iOS com registro corporativo de três maneiras:

-   **Apple Configurator** – os dispositivos iOS podem ser registrados exportando um perfil de Registro Corporativo e, em seguida, conectando esses dispositivos móveis a um Mac executando o Apple Configurator. O Apple Configurator dá suporte a duas formas de registro:

    - **Configurar o assistente de registro** – Redefine o dispositivo para os padrões de fábrica e o prepara para a instalação do novo usuário do dispositivo. Esse método requer que o administrador de USB conecte o dispositivo iOS a um computador Mac executando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) para pré-configurar o registro. Os dispositivos são, então, entregues aos usuários que executam o processo do Assistente de configuração, configurando o dispositivo com suas credenciais corporativas ou de estudante e concluindo o processo de registro. [Registrar dispositivos iOS usando o Apple Configurator e Assistente de configuração](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Registro direto** – Cria um arquivo compatível com Apple Configurator para uso durante a preparação do dispositivo. O dispositivo registrado não recebe redefinição de fábrica, mas não fica associado a nenhum usuário. Esse método requer que o administrador de USB conecte o dispositivo iOS a um computador Mac executando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) para registrar o dispositivo. [Registrar dispositivos iOS usando o registro direto do Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **DEP(Programa de Registro do Dispositivo)** – Implanta um perfil de registro sem fio em dispositivos comprados através do Programa de Registro de Dispositivo da Apple. Quando o usuário executa o Assistente de configuração do dispositivo, o dispositivo é registrado no Intune.  Registros de dispositivos feitos pelo DEP não podem ser desfeitos pelos usuários. [Registrar dispositivos iOS no Programa de Registro de Dispositivos](ios-device-enrollment-program-in-microsoft-intune.md)

## Usando o Portal da empresa em DEP ou dispositivos registrados no Apple Configurator

Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos. Assim que os usuários receberem seus dispositivos, eles deverão concluir várias etapas adicionais a fim de completar o Assistente de Configuração e instalar o aplicativo Portal da Empresa.

Como registrar dispositivos iOS corporativos com afinidade de usuário
1. Quando os usuários ligarem seus dispositivos, receberão uma solicitação para concluir o Assistente de Configuração. Durante a configuração, os usuários receberão uma solicitação por suas credenciais. Eles devem usar as credenciais (ou seja, o nome pessoal exclusivo ou UPN) associadas à assinatura do Intune.

2. Durante a configuração, os usuários receberão uma solicitação por uma ID Apple. É necessário fornecer uma ID Apple para permitir que o dispositivo instale o Portal da Empresa. Também é possível fornecer uma ID Apple após a configuração no menu de ajustes do iOS.

3. Após a conclusão da configuração, o dispositivo iOS deve instalar o aplicativo Portal da Empresa na App Store, por exemplo, aplicativo Portal da Empresa.

4. Agora, o usuário pode fazer logon no Portal da Empresa usando o UPN usado durante a configuração do dispositivo.

5. Após o logon, o usuário recebe uma solicitação para registrar seu dispositivo. A primeira etapa é Identificar o dispositivo. O aplicativo apresenta uma lista de dispositivos iOS que já foram registrados pela empresa e atribuídos à conta do Intune do usuário final. Escolha o dispositivo correspondente.

  Se o dispositivo ainda não tiver sido registrado pela empresa, selecione "novo dispositivo" para continuar com o fluxo de registro padrão.

6. Na próxima tela, o usuário deverá confirmar o número de série do novo dispositivo. O usuário pode tocar no link "confirmar o Número de Série" para iniciar o aplicativo de Configurações para verificar o número de série. Em seguida, o usuário deve inserir os quatro últimos caracteres do número de série no aplicativo Portal da Empresa.

  Essa etapa verifica se o dispositivo é o dispositivo corporativo registrado no Intune. Se o número de série no dispositivo não corresponder, o dispositivo incorreto terá sido selecionado. Volte para a tela anterior e selecione um dispositivo diferente.

7. Após a verificação do número de série, o aplicativo Portal da Empresa redirecionará para o site do Portal da Empresa a fim de finalizar o registro e solicitará que o usuário retorne ao aplicativo.

8. O registro está concluído. Agora você pode usar este dispositivo com o conjunto completo de recursos.

### Sobre dispositivos gerenciados de propriedade da empresa sem afinidade de usuário

Os dispositivos configurados sem a afinidade de usuário não têm suporte no Portal da Empresa e não devem instalar o aplicativo. O Portal da Empresa se destina a usuários com credenciais corporativas e que precisam de acesso aos recursos corporativos personalizados (por exemplo, email). O dispositivo registrado sem afinidade de usuário não deve ter uma entrada de usuário dedicada. Quiosque, ponto de venda (PDV) ou dispositivos de utilitário compartilhados são casos de uso comuns de dispositivos registrados sem afinidade de usuário. Se a afinidade de usuário for necessária, certifique-se de que o perfil de registro do dispositivo tenha a opção Afinidade de Usuário selecionada antes de registrar o dispositivo. Para alterar o status de afinidade em um dispositivo, você deve desativar e registrar novamente o dispositivo.



### Consulte também
[Prepare-se registrar dispositivos no Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


