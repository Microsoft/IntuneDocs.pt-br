---
title: Solucionar problemas de acesso condicional | Microsoft Intune
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4f79d2890c450a803bfb84ffa3c12b0de58a158c
ms.openlocfilehash: 373b9bf9794840f999d5e5b21fc411ff621a23e1


---

# Solucionar problemas de acesso condicional

Este tópico descreve o que fazer quando os usuários não obtêm acesso aos recursos por meio de acesso condicional do Intune. 

### Os conceitos básicos para o sucesso no acesso condicional

Para que o acesso condicional funcione, são necessárias as seguintes condições:

-   O dispositivo deve ser gerenciado pelo Intune.
-   O usuário deve ser registrado com o AAD (Azure Active Directory)
-   O dispositivo deve ser compatível com as políticas de conformidade configuradas no Intune. 
-   O EAS deverá ser ativado no dispositivo se o usuário estiver recuperando mensagens por meio do cliente de email nativo do dispositivo em vez de por meio do Outlook.

Essas condições podem ser exibidas para cada dispositivo no Portal de gerenciamento do Azure e no relatório de inventário de dispositivo.





Normalmente, um usuário está tentando acessar o email ou o SharePoint e recebe uma solicitação para registrar. Essa solicitação levará o usuário para o portal da empresa. Veja possíveis explicações para este comportamento e soluções sugeridas:

## Cenários de autenticação moderna

### Problemas de registro

 -  O dispositivo não está registrado, portanto o registro resolverá o problema.
 -  O usuário registrou o dispositivo, mas houve falha no ingresso no local de trabalho. O usuário deve atualizar o registro por meio do portal da empresa. 
 
### Problemas de conformidade

 -  O dispositivo não é compatível com a política do Intune. Problemas comuns são requisitos de senha e criptografia. O usuário será redirecionado para o portal da empresa, em que ele pode configurar seu dispositivo para que seja compatível.
 -  Para dispositivos iOS, um perfil de email existente criado pelo usuário bloqueará a implantação de um perfil compatível (criado pelo administrador do Intune) por meio do Intune. Isso é um problema comum, pois usuários do iOS normalmente vão criar um perfil de email e, depois, se registrar. O portal da empresa informará ao usuário que ele não é compatível devido ao seu perfil de email configurado manualmente e solicitará que o usuário remova esse perfil. O usuário deve remover seu perfil de email para que o perfil do Intune possa ser implantado. Para evitar o problema, instrua os usuários a registrar sem instalar um perfil de email e permitir que o Intune implante o perfil.  
 -  Pode levar algum tempo para que as informações de conformidade sejam registradas para um dispositivo. Aguarde alguns minutos e tente novamente.

### Problemas de política

Quando você cria uma política de conformidade e a vincula a uma política de email, ambas as políticas precisam ser implantadas para o mesmo usuário. Portanto, tenha cuidado ao planejar quais políticas são implantadas em quais grupos. Os usuários que têm apenas uma política aplicada têm uma probabilidade de descobrir que seus dispositivos não são compatíveis.


## Cenários do Exchange ActiveSync


- Um dispositivo Android registrado e compatível ainda pode receber um aviso de quarentena ao tentar acessar recursos corporativos. Antes de escolher o link que diz **Começar**, o usuário deve verificar se o portal da empresa não estava aberto quando ele tentou acessar os recursos. Os usuários devem fechar o portal da empresa, tente novamente para acessar os recursos e, em seguida, escolher o link **Começar**.

- Um dispositivo desativado pode continuar a ter acesso por várias horas após a desativação. Isso ocorre porque o Exchange armazena em cache os direitos de acesso por 6 horas. Considere outros meios de proteção de dados em dispositivos desativados neste cenário.
- Possível problema, não é possível corrigir o EASID ao AAD. Uma causa comum desse problema é a limitação, então, aguarde alguns minutos e tente novamente. 

## Coletando logs de caixa de correio do OWA

Se seus problemas de conectividade do Exchange persistem após você solucionar problemas de sua implantação, colete os logs de caixa de correio do OWA antes de entrar em contato com o Suporte da Microsoft conforme descrito em [Como obter suporte para o Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

1. Faça logon por meio do OWA e escolha o símbolo de configurações (engrenagem) ao lado de seu nome no canto superior direito. 
2. Escolha **Opções**
3. Escolha **Telefone** (talvez seja **Dispositivos Móveis**) na coluna à esquerda.
4. No menu superior, escolha **Dispositivos Móveis**. 
5. Escolha seu dispositivo na lista e, em seguida, escolha **Iniciar Registro**. 
6. Quando solicitado, escolha **Sim** na caixa de diálogo pop-up. 
7. Execute a ação que causou o problema, para que você possa reproduzi-lo. 
8. Aguarde 1 a 2 minutos e, em seguida, volte para a lista de telefone no OWA (verifique se o seu telefone está selecionado na lista) e no menu superior, escolha **Recuperar Log**. 
9. Agora você deve ter recebido um email com um anexo. Quando você abrir um tíquete de suporte, forneça o conteúdo do email ao Suporte da Microsoft.


### Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).



<!--HONumber=Jun16_HO4-->


