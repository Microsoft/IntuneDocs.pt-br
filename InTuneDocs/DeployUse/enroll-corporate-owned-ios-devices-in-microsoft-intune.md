---
title: Registrar dispositivos iOS corporativos | Microsoft Intune
description: Registro de dispositivos iOS corporativos usando o DEP (Programa de Registro de Dispositivo) da Apple ou o Apple Configurator
keywords: 
author: NathBarn
manager: angrobe
ms.date: 09/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bee93334e7b868ef6c827fba9efc3318c8419527
ms.openlocfilehash: b295ee11d566fbfbe84513c045f3a76dfd51cda4


---

# Registrar dispositivos iOS corporativos no Microsoft Intune
O Microsoft Intune dá suporte ao registro de dispositivos iOS corporativos usando o DEP (Programa de Registro do Dispositivo) da Apple ou a ferramenta [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) executada em um computador Mac.

**Pré-requisito:** um[certificado do Apple Push Notification Service](set-up-ios-and-mac-management-with-microsoft-intune.md) é obrigatório.

Você pode registrar dispositivos iOS inscritos na empresa de três maneiras: usando o Apple Configurator, o DEP ou o Portal da Empresa.

## Usar o Apple Configurator

Você pode registrar dispositivos iOS exportando um perfil de Registro Corporativo e, em seguida, conectando esses dispositivos móveis a um Mac que esteja executando o Apple Configurator. O Apple Configurator dá suporte a duas formas de registro:

- **Registro no Assistente de Configuração**: redefine o dispositivo para as configurações de fábrica e o prepara para a configuração do novo usuário do dispositivo. Esse método requer que o administrador conecte o dispositivo iOS a um computador Mac via USB executando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) para pré-configurar o registro. Em seguida, os dispositivos são entregues aos usuários, que executam o processo do Assistente de Configuração. Esse processo configura o dispositivo com suas credenciais corporativas ou de estudante e conclui o processo de registro. Para saber mais, confira [Registrar dispositivos iOS usando o Apple Configurator e o Assistente de Configuração](ios-setup-assistant-enrollment-in-microsoft-intune.md).

- **Registro direto**: cria um arquivo compatível com Apple Configurator para uso durante a preparação do dispositivo. O dispositivo registrado não é redefinido para os padrões de fábrica, mas não fica associado a qualquer usuário. Esse método requer que o administrador de USB conecte via USB o dispositivo iOS a um computador Mac que esteja executando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) para registrar o dispositivo. Para saber mais, confira [Registrar dispositivos iOS usando o Apple Configurator Device Enrollment](ios-direct-enrollment-in-microsoft-intune.md).

## Usar o DEP (Device Enrollment Program)
O DEP implanta um perfil de registro "over the air" em dispositivos que são adquiridos por meio do DEP. Quando o usuário executa o Assistente de Configuração no dispositivo, o dispositivo é registrado no Intune.  O registro dos dispositivos feito pelo DEP não pode ser desfeito pelos usuários. Para saber mais, confira [Registrar dispositivos iOS no Device Enrollment Program](ios-device-enrollment-program-in-microsoft-intune.md).

## Usar o Portal da Empresa em dispositivos registrados por DEP ou no Apple Configurator

Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos. Assim que os usuários receberem seus dispositivos, eles deverão concluir várias etapas adicionais a fim de completar o Assistente de Configuração e instalar o aplicativo Portal da Empresa.

Afinidade de usuário é necessária para dar suporte ao seguinte:
  - Aplicativos MAM (Gerenciamento de aplicativos móveis)
  - Acesso condicional para dados de email e da empresa
  - Aplicativo do Portal da Empresa

**Como os usuários registram dispositivos iOS corporativos com afinidade de usuário**
1. Quando os usuários ligam seus dispositivos, eles recebem uma solicitação para concluir o Assistente de Configuração. Durante a configuração, os usuários receberão uma solicitação por suas credenciais. Eles devem usar as credenciais (ou seja, o nome pessoal exclusivo ou UPN) associadas à assinatura do Intune.

2. Durante a configuração, os usuários receberão uma solicitação por uma ID Apple. Eles precisam fornecer uma ID Apple para permitir que o dispositivo instale o Portal da Empresa. Também podem fornecer a ID pelo menu de ajustes do iOS após a conclusão da instalação.

3. Após a conclusão da configuração, o dispositivo iOS deve instalar o aplicativo Portal da Empresa na App Store.

4. Agora, o usuário pode entrar no Portal da Empresa usando o UPN usado durante a configuração do dispositivo.

5. Após o logon, o usuário recebe uma solicitação para registrar seu dispositivo. A primeira etapa é identificar o dispositivo. O aplicativo apresenta uma lista de dispositivos iOS que já foram registrados pela empresa e atribuídos à conta do Intune do usuário. O usuário deve escolher o dispositivo correspondente.

  Se o dispositivo ainda não tiver sido registrado pela empresa, ele deverá escolher **novo dispositivo** para continuar com o fluxo de registro padrão.

6. Na próxima tela, o usuário deverá confirmar o número de série do novo dispositivo. O usuário pode tocar no link **confirmar o Número de Série** para iniciar o aplicativo de Configurações para verificar o número de série. Em seguida, o usuário deve inserir os quatro últimos caracteres do número de série no aplicativo Portal da Empresa.

  Essa etapa verifica se o dispositivo é o dispositivo corporativo registrado no Intune. Se o número de série no dispositivo não corresponder, o dispositivo incorreto terá sido selecionado. O usuário deve voltar à tela anterior e selecionar um dispositivo diferente.

7. Após a verificação do número de série, o aplicativo Portal da Empresa redirecionará para o site do Portal da Empresa a fim de finalizar o registro. Em seguida, o site solicita que o usuário retorne ao aplicativo.

8. O registro está concluído. Agora o usuário pode usar este dispositivo com o conjunto completo de recursos.

### Sobre dispositivos gerenciados de propriedade da empresa sem afinidade de usuário

Os dispositivos configurados sem a afinidade de usuário não têm suporte no Portal da Empresa e não devem instalar o aplicativo. O Portal da Empresa se destina a usuários com credenciais corporativas e que precisam de acesso aos recursos corporativos personalizados (por exemplo, email). Os dispositivos registrados sem afinidade de usuário não devem ter uma entrada de usuário dedicada. O quiosque, o ponto de venda (PDV) ou os dispositivos de utilitário compartilhados são casos de uso comuns de dispositivos registrados sem afinidade de usuário.

Se a afinidade de usuário for necessária, certifique-se de que o perfil de registro do dispositivo tenha a opção **Afinidade de Usuário** selecionada antes de registrar o dispositivo. Para alterar o status de afinidade em um dispositivo, você deve desativar e registrar novamente o dispositivo.



### Consulte também
[Prepare-se registrar dispositivos no Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Sep16_HO3-->


