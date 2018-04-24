---
title: Entender a experiência de registro de dispositivo iOS
titlesuffix: Microsoft Intune
description: Aprenda a experiência de registro passando por uma experiência completa de registro de um dispositivo iOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a31722bbaf43b099c42673e4a807a8e896bf1fd2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="understand-the-users-experience-enrolling-an-ios-device"></a>Entender a experiência do usuário ao registrar um dispositivo iOS

O Microsoft Intune ajuda você a capacitar sua força de trabalho com dispositivos móveis, ao mesmo tempo que mantém seus dados corporativos protegidos. Como os usuários finais interagem com o Intune em seus dispositivos, em vez de no console do administrador, você deve estar familiarizado com a experiência de registro. Dessa forma, você pode combinar as políticas de conformidade bem elaboradas com sua experiência para demonstrar empatia pelos usuários. Isso é especialmente importante porque os usuários saberão exatamente quais informações que você pode ver como um administrador:

| O que a equipe de TI não pode ver | O que a equipe de TI pode ver |
|---|---|
| Histórico de chamadas e de navegação na Web | Modelo |
| Local | Número de série |
| Email pessoal | Versão do sistema operacional |
| Mensagens de texto | Nomes de aplicativo |
| Contacts | Proprietário |
| Senhas de suas contas pessoais | Nome do dispositivo |
| Eventos do calendário | Fabricante (para dispositivos não fabricados pela Apple) |
| Imagens, incluindo o conteúdo do aplicativo de fotos ou as imagens da câmera | Número de telefone (para dispositivos corporativos, o número completo. Para dispositivos pessoais, apenas os últimos quatro dígitos.) |

## <a name="how-do-i-enroll-a-device"></a>Como registro um dispositivo?

Registrar um dispositivo é a primeira experiência que muitos usuários finais terão ao acessar recursos corporativos. [Entender essa experiência](end-user-educate.md) pode ajudar a tornar uma experiência possivelmente desagradável em uma melhor.

1. Abra a **Loja de Aplicativos** e pesquise por **Portal da Empresa do Intune**.
2. Baixe o aplicativo **Portal da Empresa do Microsoft Intune**.
3. Abra o aplicativo **Portal da Empresa**, digite seu endereço de email e a senha do usuário de teste e toque em **Entrar**.
4. Atualize a senha temporária para uma nova.
5. Na página **Configuração de Acesso da Empresa**, toque em **Registro de Dispositivo**.
6. Na página **Por que registrar seu dispositivo?** leia sobre o que um usuário pode fazer ao registrar o dispositivo e, em seguida, toque em **Continuar**.
7. Examine uma lista de qual acesso um usuário recebe ao registrar-se e toque em **Continuar**.
8. Examine o que os administradores de TI podem ou não podem ver em um dispositivo e toque em **Continuar**.
9. Na página **O que vem em seguida**, leia sobre o que acontece durante o registro e, em seguida, toque em **Registrar**.
10. Na página **Instalar Perfil**, toque em **Instalar** e insira a senha do dispositivo se solicitado.
11. Toque em **Instalar**.
12. Toque em **Instalar** novamente para indicar que você leu o aviso.
13. No pop-up **Aviso**, toque em **Confiar**.
14. Quando a tela for alterada para mostrar que o perfil terminou de instalar, toque em **Concluído**.
15. Uma mensagem de “Registrando dispositivo” é mostrada na tela e, em seguida, mostra que o dispositivo foi registrado com êxito. Um pop-up será exibido perguntando se a página deve ser aberta no Portal da Empresa. Toque em **Abrir**.
16. Você voltará para a tela **Configuração de Acesso da Empresa**. Se você não tiver nenhuma política de teste configurada, então o dispositivo deverá aparecer em conformidade. Se você tiver alguma política de teste, tocar em **Conformidade do Dispositivo** mostrará que há coisas que precisam ser feitas para proteger o dispositivo.

## <a name="next-steps"></a>Próximas etapas

[Introdução à adição de aplicativos](get-started-apps.md) – localize e adicione aplicativos em dispositivos para permitir que os funcionários realizem seus trabalhos.

## <a name="learn-more"></a>Saiba mais

* [Opções de registro para o Intune](enrollment-options.md)
* [Habilitar “Traga seu próprio dispositivo” com o Intune](byod-enable.md)
* [Ensinando os usuários finais sobre registro e gerenciamento de dispositivo](end-user-educate.md)
