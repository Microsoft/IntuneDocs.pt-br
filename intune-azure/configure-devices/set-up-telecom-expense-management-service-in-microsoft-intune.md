---
title: "Configurar um serviço de gerenciamento de despesas de telecomunicações | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: configurar o serviço de gerenciamento de despesas de telecomunicações da Saaswedo para integração com o Intune."
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 915d61344a3c1d388305dd51b1e2463bd2e32770
ms.openlocfilehash: 8d94fec099e1dc8918077062fb73b94a5973ea96

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Configurar um serviço de gerenciamento de despesas de telecomunicações na versão prévia do Intune Azure
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

O Intune integrou-se à solução de gerenciamento de despesas de telecomunicações Datalert da desenvolvedora de software Saaswedo. O Datalert é um software de gerenciamento de despesas de telecomunicações em tempo real que permite que você gerencie o uso de dados de telecomunicações e evitar excedentes de dados móveis e roaming inesperados e dispendiosos para os dispositivos gerenciados pelo Intune. A integração do Intune com o Datalert permite definir, monitorar centralmente e impor limites de uso de dados de roaming e doméstico usando alertas automatizados quando excederem os limites definidos. Você pode configurar o serviço para aplicar diferentes ações a indivíduos ou grupos de usuários finais, incluindo desabilitar roaming quando os usuários excederem o limite. Relatórios que fornecem o uso de dados e informações de monitoramento estão disponíveis no console de gerenciamento Datalert.

Antes de usar o serviço de Datalert com o Intune, você precisa definir as configurações no console de Datalert e no Intune. A conexão deve estar ativada para o serviço Datalert e para o Intune. Se o lado do Datalert da conexão estiver habilitado, mas não o lado do Intune, o Intune receberá a comunicação, mas a ignorará.

>[!NOTE]
>Para habilitar esse recurso em seu locatário de teste, consulte [Contatar o Suporte da Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) para ativação e suporte do Datalert para as licenças de software necessárias.

## <a name="supported-platforms"></a>Plataformas com suporte

- Samsung Knox
- iOS 8.0 e posterior

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura do Microsoft Intune
- Uma assinatura para o serviço de gerenciamento de despesas de telecomunicações do Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Lista de provedores de gerenciamento de despesas de telecomunicações

O Intune atualmente se integra com os seguintes provedores de gerenciamento de despesas de telecomunicações:

[Serviço de gerenciamento de despesas de telecomunicações do Saaswedo Datalert](http://www.datalert.biz/)

## <a name="configure-intune-to-work-with-the-datalert-service"></a>Configurar o Intune para funcionar com o serviço de Datalert

 

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
2. Na folha **Configuração do Dispositivo**, escolha **Instalação** > **Gerenciamento de Despesas de Telecomunicações**.
2. Em **Gerenciamento de Despesas de Telecomunicações**, selecione **Status da Conexão**.

3. Selecione **Lista dos provedores de TEM** e, em seguida, selecione o provedor na lista abaixo. Abre uma página que é específica ao seu provedor. Para Saaswedo, a página Datalert é aberta. Você precisará entrar em contato com a Saaswedo Datalert para comprar uma assinatura.

4. No console de gerenciamento do **Datalert**:

    a. Visite a guia **Configurações** e acesse a seção **Configuração MDM**.

    b. Selecione **Desbloquear** para permitir que você insira as configurações na página.

    c. Para **Servidor MDM**, escolha **Microsoft Intune**.

    d. Em **ID de Locatário**, insira sua ID de locatário do Intune e selecione o botão **Conexão**. Selecionar **Conexão** faz o serviço do Datalert verificar com o Intune se não existem conexões Datalert já existentes com o Intune. Depois de alguns segundos, uma página de logon do Microsoft aparecerá, seguida da autenticação do Datalert Azure.

    e. Na página de autenticação da Microsoft, selecione **Aceitar**. Você será redirecionado para uma página de agradecimento, que se fecha depois de alguns segundos. O Datalert valida a conexão e exibe marcas de seleção verde ao lado de uma lista de itens validados. Se a validação falhar, você verá uma mensagem vermelha. Nesse caso, contate o suporte de Datalert para obter ajuda.

5. Aguarde alguns minutos e acesse o Portal do Azure para verifique se o status de Conexão aparece como **Ativo**. 

    >[!NOTE]
    >Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

6. Retorne ao console de gerenciamento do Datalert e configure as linhas de dados:

    a. Acesse a guia **Configurações**.

    b. Acesse o assistente de **Instalação** e siga as etapas no assistente.



O serviço Datalert agora estará ativo e começará a monitorar o uso de dados e a desabilitar os dados em roaming em dispositivos que excederam os limites de uso configurados.

## <a name="turning-off-the-datalert-service"></a>Desativar o serviço Datalert

Se você desabilitar o serviço Datalert no Portal do Azure:

- Todas as ações que foram aplicadas aos dispositivos devido a violações passadas dos limites de uso serão desfeitas.
- Os usuários não são impedidos de acessar os dados e roaming.
- O Intune ainda recebe os sinais proveniente do serviço, mas os ignora.

**Para desligar o serviço**

1. Na folha **Gerenciamento de Despesas de Telecomunicações** no Portal do Azure, selecione **Desabilitar**.

2. Selecione **Salvar**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Exibindo o uso de dados e relatórios de roaming

No momento, os relatórios de dados de uso estão disponíveis somente no console de gerenciamento do Saaswedo Datalert.



<!--HONumber=Feb17_HO2-->


