---
# required metadata

title: Implantar aplicativos | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Implantar aplicativos com o Microsoft Intune

Este tópico explica alguns dos conceitos que você precisará compreender antes de iniciar a implantação de aplicativos com o Microsoft Intune.

## O Intune Software Publisher
O **Microsoft Intune Software Publisher** inicia quando você adiciona ou modifica aplicativos do console de administrador do Microsoft Intune. No editor, selecione um tipo de instalação de software que carregará aplicativos (programas para computadores ou aplicativos para dispositivos móveis) para serem armazenados na nuvem do Intune, ou estabeleça um link com uma loja online ou aplicativo Web.

### Requisitos
Antes de começar a usar o Microsoft Intune Software Publisher, é preciso instalar a versão completa do [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851). Após a instalação, pode ser necessário reiniciar seu computador para que o Software Publisher abra corretamente.

## Espaço de armazenamento em nuvem
Todos os aplicativos que você implanta usando o tipo de instalação do instalador de software devem ser empacotados e carregados no armazenamento em nuvem do Microsoft Intune. Uma assinatura de avaliação do Intune inclui 2 GB de armazenamento baseado em nuvem que é usado para armazenar aplicativos gerenciados e atualizações. Uma assinatura paga inclui 20 GB, com a opção de adquirir mais armazenamento.

Você pode ver quanto espaço está usando e adquirir mais armazenamento no nó **uso de Armazenamento** do espaço de trabalho **Admin**.

As regras a seguir aplicam-se à aquisição de armazenamento baseado em nuvem adicional para o Intune:

-   Você deve ter uma assinatura paga ativa para adquirir armazenamento adicional.

-   Somente administradores de cobrança ou globais do Microsoft Online Service podem adquirir armazenamento adicional no Portal de Gerenciamento do Office 365. Para adicionar, excluir ou gerenciar esses administradores, você deve ser um administrador global e se conectar ao Portal de Gerenciamento do Office 365.

-   Para clientes de licenciamento por volume que adquiriram o Intune ou o Complemento do Microsoft Intune através de um contrato corporativo, contate seu Gerente de Conta da Microsoft ou seu Parceiro da Microsoft para obter informações de preço e adquirir armazenamento adicional.

#### Requisitos de espaço de armazenamento em nuvem

-   Todos os arquivos associados a um aplicativo devem estar no mesmo local e serem acessíveis pelo Intune.

-   O tamanho máximo do arquivo para qualquer arquivo que você carregar é de 2 GB.

-   Para carregar arquivos, você deve ter uma velocidade mínima de Internet de 768 kbps.

## Ações de implantação de aplicativo
Quando você implanta aplicativos, pode escolher uma das seguintes ações de implantação:

-   **Instalação obrigatória** – O aplicativo está instalado no dispositivo, sem necessidade de intervenção do usuário final.

    > [!TIP] Para dispositivos iOS que não estão no modo supervisionado e para todos os dispositivos Android, o usuário deve aceitar a oferta do aplicativo antes que ele seja instalado.
    >
    > Você não pode mais criar novas implantações de aplicativo para dispositivos iOS executando um sistema operacional anterior ao iOS 7.1. As implantações de aplicativos existentes em dispositivos em execução em um sistema operacional anterior ao iOS 7.1 continuarão funcionando e serão gerenciadas pelo Intune.
    > 
    >  Se um usuário final desinstalar um aplicativo implantado como instalação obrigatória, o Intune reinstalará automaticamente o aplicativo após o próximo ciclo de inventário, que normalmente ocorre a cada 7 dias.

-   **Instalação disponível** – O aplicativo é exibido no portal da empresa e os usuários finais podem instalá-lo sob demanda.

-   **Desinstalar** – O aplicativo é desinstalado do dispositivo.

-   **Não aplicável** – O aplicativo não será exibido no portal da empresa e não está instalado em todos os dispositivos.

#### Entender quais ações de implantação estão disponíveis para cada tipo de instalador

|Tipo de instalador|Instalação requerida|Instalação disponível|Desinstalar|Não aplicável|
|------------------|--------------------|---------------------|-------------|------------------|
|Pacote de aplicativos do Windows (implantado em um grupo de usuários)|Sim|Sim|Sim|Sim|
|Pacote do aplicativo do Windows (implantado em um grupo de dispositivos)|Sim|Não|Sim|Sim|
|Pacote de aplicativos para dispositivos móveis (implantado em um grupo de usuários)|Sim|Sim|Sim|Sim|
|Pacote de aplicativos para dispositivos móveis (implantado em um grupo de dispositivos)|Sim|Não|Sim|Sim|
|Windows Installer (implantado em um grupo de usuários)|Não|Sim|Não|Sim|
|Windows Installer (implantado em um grupo de dispositivos)|Sim|Não|Sim|Sim|
|Link externo (implantado em um grupo de usuários)|Não|Sim|Não|Sim|
|Link externo (implantado em um grupo de dispositivos)|Não|Não|Não|Não|
|Aplicativo iOS gerenciado da loja de aplicativos (implantado em um grupo de usuários)|Sim|Sim|Sim|Sim|
|Aplicativo iOS gerenciado da loja de aplicativos (implantado em um grupo de dispositivos)|Sim|Não|Sim|Sim|
> [!TIP] Ao implantar aplicativos, se você selecionar usuários e grupos de dispositivos, só poderá implantar o aplicativo como uma **Instalação disponível**.

## Conflitos de implantação
Quando duas implantações com a mesma ação de implantação são recebidas por um dispositivo, as seguintes regras se aplicam:

-   Implantações em um grupo de dispositivos têm precedência sobre as implantações para um grupo de usuários. No entanto, se um aplicativo é implantado em um grupo de usuários com a ação de implantação **disponível** e o mesmo aplicativo também é implantado em um grupo de dispositivos com uma ação de implantação de **não aplicável**, o aplicativo será disponibilizado no portal da empresa para os usuários instalarem.

-   A intenção do administrador de TI tem precedência sobre o usuário.

-   Uma ação de instalação tem precedência sobre uma ação de desinstalação.

-   Se uma instalação necessária e uma instalação disponível forem recebidas por um dispositivo, as ações serão combinadas (o aplicativo é necessário e está disponível).


## Próximas etapas

Saiba como [implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md).

<!--HONumber=Jun16_HO2-->


