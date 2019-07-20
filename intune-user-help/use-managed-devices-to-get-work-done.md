---
title: Usar dispositivos gerenciados para realizar o trabalho | Microsoft Docs
description: Entenda o que significa registrar seu dispositivo no gerenciamento com o Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f698f03ed3c7523ef1d768d2a1361d6d1a55008
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883867"
---
# <a name="enroll-device-for-access-to-work-or-school-resources"></a>Registrar o dispositivo para acesso a recursos corporativos ou de estudante
Para registrar seu dispositivo e obter acesso a email e aplicativos, você precisará instalar o aplicativo Portal da Empresa do Intune ou Microsoft Intune aplicativo. Quando você se registra, as políticas básicas de gerenciamento que sua organização configurou, como senha, PIN e criptografia, são aplicadas ao seu dispositivo. Depois que as configurações do dispositivo atenderem a todos os requisitos da sua organização, você poderá acessar com segurança suas informações de trabalho de praticamente qualquer lugar.  

Os aplicativos Portal da Empresa e Microsoft Intune mantêm seu dispositivo registrado seguro, garantindo que as configurações do dispositivo correspondam às políticas da organização. 

O aplicativo do Portal da Empresa também:  
* Mantém suas informações pessoais e de trabalho separadas.  
* Torna fácil localizar e instalar aplicativos relevantes de trabalho e escolares.   

## <a name="get-the-apps"></a>Obter os aplicativos
Para obter o Portal da Empresa:

- Instale o aplicativo Portal da Empresa da loja de aplicativos específica da plataforma. Em alguns casos, sua organização instalará o aplicativo Portal da Empresa para você.  
- Acesse o [site Portal da empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para acessar o aplicativo em um navegador.  

Se for necessário usar o aplicativo Microsoft Intune, sua organização irá instalá-lo para você.  


## <a name="what-information-can-my-company-see-when-i-enroll"></a>Quais informações minha empresa poderá ver quando eu fizer o registro?
Depois que o dispositivo for registrado, as pessoas de suporte da sua organização poderão ver apenas as informações relevantes para o trabalho. Ela não poderá ver suas informações pessoais. Se você estiver registrando um dispositivo pessoal para uso no trabalho, [saiba exatamente o que pode ou não ser visto](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).  


## <a name="whats-the-difference-between-the-apps-and-the-website"></a>Qual é a diferença entre os aplicativos e o site?
O aplicativo Portal da Empresa está disponível para dispositivos Windows 10, iOS, macOS e Android. Ele se integra perfeitamente à respectiva plataforma do dispositivo. A versão do site pode ser acessada em qualquer dispositivo e proporciona a mesma experiência universal, independentemente de qual dispositivo você está usando. 

O aplicativo Microsoft Intune é para dispositivos Android de propriedade corporativa.  

## <a name="what-kind-of-devices-can-you-enroll-with-company-portal"></a>Que tipo de dispositivos você pode registrar com Portal da Empresa?
- Dispositivos da Apple usando macOS (como MacBook e iMac) e usando iOS (como iPhone e iPad)
- Dispositivos Android
- Dispositivos Windows
  - Windows 10 Mobile
  - Windows 10 Desktop
  - Windows Phone 8.1
  - Windows 8.1

## <a name="what-kind-of-devices-can-you-enroll-with-the-microsoft-intune-app"></a>Que tipo de dispositivos você pode registrar com o aplicativo Microsoft Intune?  
Você pode registrar dispositivos Android de propriedade corporativa que sua organização configurou para usar com o aplicativo. O aplicativo dá suporte ao Android 6,0 e posterior. 

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>É possível remover um computador ou dispositivo do Portal da Empresa?
Você pode remover ou redefinir um computador ou dispositivo do Portal da Empresa. Existe uma diferença entre **remover** e **redefinir**.

Quando você remove um computador ou dispositivo do Portal da Empresa, está cancelando o registro do dispositivo no Intune. Uma vez que o registro for cancelado, você não poderá acessar o Portal da Empresa por meio desse dispositivo e alguns dados da empresa podem ser removidos do seu dispositivo. Para saber como remover seu dispositivo do Portal da Empresa, consulte os links a seguir:  

- [Cancelando o registro do seu dispositivo Android](unenroll-your-device-from-intune-android.md)
- [Cancelando o registro do dispositivo iOS](unenroll-your-device-from-intune-ios.md)
- [Cancelar o registro do seu dispositivo macOS](unenroll-your-device-from-intune-macos.md)
- [Cancelando o registro do seu dispositivo Windows](unenroll-your-device-from-intune-windows.md)

Quando você redefine um computador ou dispositivo, o Portal da Empresa tenta redefinir seu computador ou dispositivo para as configurações padrão do fabricante. A redefinição do dispositivo remove todos os dados pessoais e corporativos dele. Se você tiver perdido seu dispositivo, poderá redefini-lo remotamente pelo site do Portal da Empresa.  

Para saber como redefinir seu dispositivo, consulte [redefinir seu dispositivo no site Portal da empresa](reset-erase-your-device-cpwebsite.md).  

## <a name="can-you-remove-a-computer-or-device-from-the-microsoft-intune-app"></a>Você pode remover um computador ou dispositivo do aplicativo Microsoft Intune?
Não, não há como remover um dispositivo de propriedade corporativa do aplicativo Microsoft Intune.  

## <a name="what-if-i-cant-see-my-device-in-the-company-portal-or-microsoft-intune-app"></a>E se eu não conseguir ver meu dispositivo no Portal da Empresa ou Microsoft Intune aplicativo?
Para ver um dispositivo, ele deve ser adicionado ao Portal da Empresa. Acesse o Portal da Empresa conforme orientado pelo administrador e siga as etapas para o seu dispositivo. Além disso, você não verá dispositivos que são de propriedade e gerenciados por sua empresa.

Se você estiver usando o aplicativo Microsoft Intune, verá apenas o dispositivo que está usando no momento. Outros dispositivos registrados não serão visíveis para você no aplicativo.  

## <a name="where-else-can-i-go-for-help"></a>Em quais outros lugares posso obter ajuda?  
Para solucionar problemas e perguntas comuns, confira estes documentos específicos da plataforma:  

- [Corrigir problemas comuns com o dispositivo Android](check-compliance-on-your-device-android.md)  
- [Corrigir problemas comuns com o dispositivo iOS](troubleshoot-your-device-ios.md)
- [Corrigir problemas comuns com o dispositivo macOS](troubleshoot-your-device-macos.md)
- [Corrigir problemas comuns com o dispositivo Windows](troubleshoot-your-device-windows.md)

Você também pode entrar em contato com o seu pessoal de suporte. O Portal da Empresa e o aplicativo Microsoft Intune oferecem páginas de ajuda e suporte que listam informações de contato e maneiras de relatar um problema. As informações de contato também estão disponíveis no [site Portal da empresa](https://go.microsoft.com/fwlink/?linkid=2010980)da sua organização.  

## <a name="next-steps"></a>Próximas etapas  

Obtenha a ajuda começando com o registro, que é específico para a plataforma do dispositivo:  

- [Usando seu dispositivo Android](using-your-android-device-with-intune.md)
- [Usar seu dispositivo iOS](using-your-ios-device-with-intune.md)
- [Usar seu dispositivo macOS](using-your-macos-device-with-intune.md)
- [Usando seu dispositivo Windows](using-your-windows-device-with-intune.md)
- [Usando o site do Portal da Empresa](using-the-intune-company-portal-website.md)


