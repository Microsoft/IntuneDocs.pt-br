---
# required metadata

title: Seu computador já está registrado | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Seu computador já está registrado
Você está vendo esta página porque executou a instalação do software cliente do Intune. No entanto, o software já está instalado em seu computador e a instalação não poderá continuar.

Isto pode ter ocorrido devido a:

-   O software cliente foi instalado anteriormente e o programa de instalação foi executado novamente.

-   A instalação foi executada no computador depois que um administrador de TI desativou seu dispositivo no Intune. Depois que o dispositivo for desativado, pode levar várias horas para o software cliente ser removido do seu computador.

-   A instalação detectou uma instalação ou remoção recente com falha do software cliente.

## O que é instalado no computador
É instalado o cliente do Intune. Após a conclusão da instalação, o software cliente continuará em execução em segundo plano e, dessa forma, ele configurará o computador para uso com o Intune. Esse processo pode levar algum tempo para ser concluído e inclui:

-   Registrar seu computador no Intune

-   Enviar o inventário de hardware do computador e software instalado

-   Configurar a política do Intune, incluindo a instalação do Endpoint Protection (se configurado)

-   Instalar o Intune Center

Após a instalação do Intune Center, será possível usá-lo para acessar o portal da empresa, no qual você poderá vincular seu computador à sua conta corporativa.

## Microsoft Intune Center
O Intune Center é instalado como um aplicativo no seu computador após o software cliente ser instalado com êxito e o computador ser registrado no Intune. Você pode usar o Intune Center para:

-   **Obter aplicativos do portal da empresa** – Localize e instale aplicativos implantados pelo administrador de TI. Quando você entra no portal da empresa pela primeira vez em um computador recém inscrito, você recebe a opção de vincular sua conta do trabalho a este computador.

-   **Verificar se há atualizações de software** – Localize atualizações de software implantadas pelo administrador do Intune.

-   **Iniciar uma verificação do Endpoint Protection no computador** – Você pode iniciar uma verificação em busca de software mal-intencionado no seu computador.

-   **Solicitar assistência remota** – Esta opção estará disponível somente se o sistema operacional dos computadores der suporte à assistência remota.

## Validar que o software cliente está instalado ou foi removido
**Validar a instalação do cliente:**
A instalação do cliente do Intune estará concluída quando os aplicativos a seguir estiverem disponíveis no computador:

-   **Intune Center**

-   **Intune Endpoint Protection** (se o Endpoint Protection for habilitado pelo administrador de TI)

Se você estiver familiarizado com o uso do Gerenciador de Tarefas, poderá pesquisar o serviço do cliente do Intune, o qual deverá estar em execução:

-   **OmcSvc**

**Confirme se o cliente foi removido:**
Após o cliente do Intune ser desinstalado de um computador, os aplicativos instalados junto com o cliente são removidos, incluindo o Intune Center.

O serviço do cliente do Intune **OmcSvc** é removido.

## Como remover o software cliente do computador
Por padrão, o software cliente do Intune será desinstalado várias horas após o administrador de TI desativar seu computador no console de administração do Intune.

Para desinstalar manualmente o software cliente do Intune de um computador, você pode usar as seguintes etapas para forçar a desinstalação:

1.  No computador, abra um prompt de comando no modo de administrador.

2.  Vá para a pasta **%programfiles%\Microsoft\OnlineManagement\Common**

3.  Execute o seguinte comando: **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune**

Isso agendará a remoção do software cliente.



<!--HONumber=May16_HO1-->


