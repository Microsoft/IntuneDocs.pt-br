---
title: "Definições de política de configuração do Windows Team | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 42e21b802fb605c98f688485c3b77703b3950e94
ms.openlocfilehash: b08d52289b94429b1328a7470469a7efdf4d46a7


---

# Definições de política de configuração do Windows Team no Microsoft Intune
Use a **Política de configuração geral do Windows 10 Team** do Microsoft Intune para definir configurações para dispositivos Windows 10 Team registrados, como o Microsoft Surface Hub.

|Nome da configuração|Detalhes|
|----------------|-----------|
|**Permitir que a tela seja ativada automaticamente quando houver alguém na sala**|Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.|
|**Exigir PIN para projeção sem fio**|Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.|
|**Configurar uma janela de manutenção para atualizações do dispositivo**|Configura a o intervalo em que atualizações podem ocorrer no dispositivo. Você pode configurar a hora de início do intervalo e sua duração (de 1 a 5 horas).|
|**Habilitar Insights Operacionais do Azure**|Os Insights Operacionais do Azure, parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.<br /><br />Para se conectar aos Insights Operacionais do Azure, você deve especificar uma **ID do Espaço de Trabalho** e uma **Chave do Espaço de Trabalho**.|
|**Habilitar projeção sem fio do Miracast**|Habilite esta opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.<br /><br />Se você habilitar essa opção, em **Escolher Canal do Miracast**, selecione o canal do Miracast usado para o conteúdo do projeto.|
|**Escolha as informações da reunião exibidas na tela de boas-vindas**|Se você habilitar essa opção, você poderá escolher as informações que serão exibidas no bloco **Reuniões** da tela **Bem-vindo**. Você pode:<br /><br />-   **Mostrar apenas organizador e hora**<br />-   **Mostrar organizador, hora e assunto (assunto oculto para reuniões particulares)**|
|**URL de imagem de tela de fundo Lockscreen**|Habilite essa configuração para exibir uma tela de fundo personalizada na tela **Bem-vindo** dos dispositivos Windows 10 Team da URL que você especificar.<br /><br />A imagem deve estar no formato PNG e a URL deve começar com **https://**.|


### Consulte também
[Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jun16_HO4-->


