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
ms.openlocfilehash: 1afdaa1bb21e3a13932202524eed9322d95479bb
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67545645"
---
# <a name="what-information-can-my-organization-see-when-i-enroll-my-device"></a>Quais informações minha organização poderá ver quando eu registrar meu dispositivo?

Sua organização não pode ver suas informações pessoais quando você registra um dispositivo no Microsoft Intune. Quando você registra um dispositivo, você concede sua permissão à organização para exibir determinadas informações em seu dispositivo, como modelo do dispositivo e número de série. Sua organização usa essas informações para ajudar a proteger os dados corporativos no dispositivo.

**O que sua organização nunca pode ver:**

- Histórico de chamadas e de navegação na Web
- Email e mensagens de texto
- Contacts
- Calendário
- Senhas
- Imagens, incluindo o conteúdo do aplicativo de fotos ou as imagens da câmera
- Arquivos

**O que sua organização sempre pode ver:**

- Modelo do dispositivo, como Google Pixel
- Fabricante do dispositivo, como Microsoft
- Sistema operacional e versão, como o iOS 12.0.1
- Inventário de aplicativos e nomes de aplicativo, como Microsoft Word. Em dispositivos pessoais, sua organização poderá ver apenas seu inventário de aplicativos gerenciados. Em dispositivos corporativos, sua organização pode ver todo o seu inventário de aplicativos.
- Proprietário do dispositivo
- Nome do dispositivo
- Número de série do dispositivo
- IMEI

**O que sua organização pode conseguir ver:**

- Número de telefone: para dispositivos de propriedade **corporativa**, o número de telefone completo pode ser visto. Para dispositivos de propriedade **pessoal**, apenas os quatro últimos dígitos de seu número de telefone ficam visíveis para sua organização. Você pode ver o **Tipo de Propriedade** de cada dispositivo individual abrindo a página **Detalhes do Dispositivo** desse dispositivo.
- Espaço de armazenamento do dispositivo: se você não puder instalar um aplicativo necessário, sua organização poderá observar o espaço de armazenamento do seu dispositivo para descobrir se há pouco espaço.  
- Localização: a organização nunca poderá ver a localização do seu dispositivo, a menos que você precise recuperar um dispositivo iOS perdido, supervisionado. Visite a [documentação do Apple iOS](https://go.microsoft.com/fwlink/?linkid=853816) para saber mais sobre dispositivos supervisionados.  
- Detalhes do inventário de aplicativo: se a organização usar a Defesa Contra Ameaças Móveis, ela poderá exibir detalhes sobre os aplicativos que estão em seu dispositivo iOS. Saiba mais sobre [Defesa contra Ameaças Móveis](you-are-prompted-to-install-mtd-ios.md).
- Informações de rede: algumas informações sobre conexões de rede para dispositivos Android podem estar disponíveis ao suporte de sua organização. Por exemplo, se a organização precisar que os dispositivos permaneçam dentro de um determinado edifício, seu dispositivo identificará a rede em que ele está conectado. 
