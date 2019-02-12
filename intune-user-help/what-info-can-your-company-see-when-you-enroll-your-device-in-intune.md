---
title: Quais informações sua empresa poderá ver quando você registrar seu dispositivo?
description: Explica o que a TI pode e não pode ver no seu dispositivo gerenciado.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 12655728-a1af-4d89-97bc-925fe36c0dc4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.collection: M365-identity-device-management
ms.openlocfilehash: 91ea3aab5cd04624bfa036615b8d7710573bcae1
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846971"
---
# <a name="what-information-can-my-organization-see-when-i-enroll-my-device"></a>Quais informações minha organização poderá ver quando eu registrar meu dispositivo?

Sua organização não pode ver suas informações pessoais quando você registra um dispositivo no Microsoft Intune. Quando você registra um dispositivo, você concede sua permissão à organização para exibir determinadas informações em seu dispositivo, como modelo do dispositivo e número de série. Sua organização usa essas informações para ajudar a proteger os dados corporativos no dispositivo.

**O que sua organização nunca pode ver:**

- Histórico de chamadas e de navegação na Web
- Email e mensagens de texto
- Contacts
- Calendário
-   Senhas
- Imagens, incluindo o conteúdo do aplicativo de fotos ou as imagens da câmera
- Arquivos

**O que sua organização sempre pode ver:**

- Modelo do dispositivo, como Google Pixel
- Fabricante do dispositivo, como Microsoft
- Sistema operacional e versão, como o iOS 12.0.1
- Nomes de aplicativo, como Microsoft Word: Em dispositivos pessoais, sua organização poderá ver apenas seu inventário de aplicativos gerenciados. Em dispositivos corporativos, sua organização pode ver todo o seu inventário de aplicativos.
- Proprietário do dispositivo
- Nome do dispositivo
- Número de série do dispositivo
- IMEI

**O que sua organização pode conseguir ver:**

-  Número de telefone: Para dispositivos de propriedade **corporativa**, o número de telefone completo pode ser visto. Para dispositivos de propriedade **pessoal**, apenas os quatro últimos dígitos de seu número de telefone ficam visíveis para sua organização. Você pode ver o **Tipo de Propriedade** de cada dispositivo individual abrindo a página **Detalhes do Dispositivo** desse dispositivo.
- Espaço de armazenamento do dispositivo: Se você não puder instalar um aplicativo necessário, sua organização poderá observar o espaço de armazenamento do seu dispositivo para descobrir se há pouco espaço.  
-  Local: Sua organização nunca poderá ver o local do seu dispositivo, a menos que você precise recuperar um dispositivo iOS perdido, supervisionado. Visite a [documentação do Apple iOS](https://go.microsoft.com/fwlink/?linkid=853816) para saber mais sobre dispositivos supervisionados.  
- Inventário de aplicativos: Se a organização usar a Defesa contra Ameaças Móveis, ela poderá exibir mais detalhes sobre os aplicativos que estão em seu dispositivo iOS. Saiba mais sobre [Defesa contra Ameaças Móveis](you-are-prompted-to-install-mtd-ios.md).
- Informação de rede: Algumas informações sobre conexões de rede para dispositivos Android podem estar disponíveis ao suporte de sua organização. Por exemplo, se a organização precisar que os dispositivos permaneçam dentro de um determinado edifício, seu dispositivo identificará a rede em que ele está conectado. 
