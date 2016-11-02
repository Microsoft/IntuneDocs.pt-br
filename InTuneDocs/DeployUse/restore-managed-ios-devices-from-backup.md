---
title: Restaurar dispositivos iOS gerenciados pelo Intune por meio do backup | Microsoft Intune
description: "Orientar usuários finais sobre como registrar novamente seus dispositivos após a restauração por meio do backup."
keywords: restaurar, gerenciado, iOS
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6bb539c87c4a13a490ba98c016d814bea5c7bbc
ms.openlocfilehash: 6395e50b3e4c06e7363acc136b5ed9eb2ef75abd


---

# Restaurar dispositivos iOS gerenciados pelo Intune por meio do backup

Haverá casos em que você ou seus usuários precisarão restaurar um dispositivo iOS por meio do backup, por exemplo, quando um usuário compra um novo dispositivo. Este tópico explica as etapas adicionais que você precisará executar para configurar o gerenciamento do Intune depois de restaurar o dispositivo.

## Restaurar backups no mesmo dispositivo

Se o backup está sendo restaurado no mesmo dispositivo, o estado do registro nesse dispositivo também será restaurado. Não é preciso fazer mais nada.

## Restaurar backups em dispositivos diferentes

Se o backup está sendo restaurado em um dispositivo diferente, o estado do registro não será automaticamente restaurado no novo dispositivo. É necessário que os usuários sigam as etapas de registro padrão no aplicativo do Portal da Empresa na versão 2.1.22 ou posterior do aplicativo para [registrar seu dispositivo iOS no Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

> [!NOTE]
> Se você estiver direcionando os usuários finais com políticas de acesso condicional, eles não poderão acessar o email corporativo até concluírem o novo registro.

> [!TIP]
> Um exemplo de comunicação para os usuários pode ser a seguinte: para se registrar no novo dispositivo, verifique se a versão do aplicativo do Portal da Empresa é a 2.1.22 ou posterior. Para verificar a versão, abra o aplicativo do Portal da Empresa, toque no botão de Menu no canto superior direito e, em seguida, toque em Sobre. Se você tiver uma versão anterior, saia do aplicativo do Portal da Empresa e abra a App Store. Toque no botão Atualizações no canto inferior direito; em seguida, toque no botão Atualizar ao lado do item do Portal da Empresa na lista. Quando a atualização for concluída, inicie o aplicativo do Portal da Empresa e [registre seu dispositivo iOS no Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

## Resolvendo problemas conhecidos com restaurações

Os usuários podem enfrentar algumas dificuldades se tiverem restaurado seu dispositivo e iniciado o aplicativo de Portal da Empresa quando ainda tinham o Portal da Empresa na versão 2.1.21 ou anteriores. Esses problemas podem ser solucionados executando as etapas adequadas à situação do usuário.

### Para usuários que usarão somente seu novo dispositivo
Inicie o aplicativo de Portal da Empresa e cancele o registro selecionando o bloco do dispositivo atual e tocando no botão __Remover__. Depois de remover, siga as etapas de registro padrão para [registrar um dispositivo iOS no Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

### Para usuários que usarão tanto seus dispositivos novos quanto os antigos
Limpe os cookies do Safari tocando em __Ajustes__ > __Safari__ > __Limpar Histórico e Dados do Site__. Após a limpar, desinstalar e reinstalar o aplicativo de Portal da Empresa, siga as etapas de registro padrão para [registrar um dispositivo iOS no Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).



<!--HONumber=Oct16_HO3-->


