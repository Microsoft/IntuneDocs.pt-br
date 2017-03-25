---
title: Gerenciar dispositivos com o Intune
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: saiba como exibir os dispositivos gerenciados com o Intune e executar várias operações neles."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: 957192c744bf05cd835dfae60b6bb521b8f8b26b
ms.lasthandoff: 03/15/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>O que é o gerenciamento de dispositivo do Microsoft Intune? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A carga de trabalho **Dispositivos** fornece ideias sobre os dispositivos gerenciados e permite que você execute tarefas remotas neles. Para acessar a carga de trabalho:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.

Agora, escolha uma das seguintes opções:

- **Visão geral** Obtenha informações sobre os dispositivos registrados e os sistemas operacionais que cada dispositivo executado.
- **Gerenciar** – Escolha **Todos os Dispositivos** para ver uma lista de todos os dispositivos gerenciados.
    Selecione um desses dispositivos na lista para abrir a folha <*nome do dispositivo*> **Visão geral** na qual você pode selecionar um destes:
    - **Visão geral** – Veja informações gerais sobre o dispositivo, incluindo informações sobre seu nome, proprietário, se ele é um dispositivo BYOD, quando foi seu último check-in e muito mais. 
                
    - **Hardware** – Consulte informações mais detalhadas sobre o dispositivo, inclusive do espaço de armazenamento livre, modelo e fabricante e muito mais.
    ![Inventário de hardware de dispositivo gerenciado](./media/hardware-inventory.png)
    - **Aplicativos detectados** – Exibe uma lista de todos os aplicativos que o Intune encontrou instalados no dispositivo.
    ![Nó de aplicativos detectado](./media/detected-applications.png)
- **Monitorar** Escolha **Ações de Dispositivo** para ver uma lista de ações de dispositivo que foram realizadas em dispositivos gerenciados e o estado atual dessas ações.
![Monitorar ações do dispositivo](./media/monitor-device-actions.png)
- **Ajuda e Suporte** - exibe links para a documentação da solução de problemas e suporte.

## <a name="available-device-actions"></a>Ações do dispositivo disponíveis

Além disso, você pode executar as seguintes ações remotas no dispositivo (nem todas as ações têm suporte em todas as plataformas de dispositivo):

### <a name="remove-company-data"></a>**Remover os dados da empresa**
Remove somente os dados da empresa gerenciados pelo Intune. Não remove dados pessoais do dispositivo. O dispositivo não será mais gerenciado pelo Intune e não será capaz de acessar recursos corporativos (sem suporte para dispositivos Windows que fazem parte do Azure Active Directory).

### <a name="factory-reset"></a>**Redefinição de fábrica**
Retorna o dispositivo para suas configurações padrão. O dispositivo não será gerenciado pelo Intune e dados pessoais e da empresa serão removidos. Você não pode desfazer essa ação.

### <a name="remote-lock"></a>**Bloqueio remoto**
Bloqueia o dispositivo. O proprietário do dispositivo deve usar a senha para desbloqueá-lo. Você pode bloquear remotamente apenas um dispositivo que tenha um PIN ou senha definida.

### <a name="reset-passcode"></a>**Redefinir senha**
Gera uma nova senha para o dispositivo que será exibido na folha *nome do dispositivo*> **Visão Geral**.

### <a name="bypass-activation-lock"></a>**Bypass de Bloqueio de Ativação**
Isso removerá o bloqueio de ativação de um dispositivo iOS sem a ID da Apple e a senha do usuário. Depois de fazer o bypass do bloqueio de ativação, o dispositivo ativa-o novamente quando inicia o aplicativo o Localizar Meu iPhone. Faça bypass do bloqueio de ativação apenas se você tiver acesso físico ao dispositivo.

### <a name="lost-mode"></a>**Modo perdido**
Se um dispositivo iOS foi roubado ou perdido, você poderá habilitar o modo perdido. Ele permite especificar uma mensagem e um número de telefone que serão exibidos na tela de bloqueio do dispositivo. Para fazer isto:
1.    Na folha de propriedades de um dispositivo iOS, escolha **Mais** > **Modo perdido**.
2.    Na folha **Modo perdido**, ative o modo perdido, digite a mensagem que será exibida e, opcionalmente, um número de telefone de contato.
3.    Clique em **OK**.
Quando você ativa o modo perdido, bloqueia todo o uso do dispositivo. O usuário final não poderá acessar o dispositivo até que você desative o modo perdido. Enquanto o modo perdido estiver habilitado, você poderá usar a ação **Localizar dispositivo** para descobrir onde está o dispositivo.

### <a name="locate-device"></a>**Localizar dispositivo**
Use esta ação remota para exibir a localização de um dispositivo iOS perdido ou roubado em um mapa. O dispositivo deve ser um dispositivo iOS corporativo no modo supervisionado. Antes de usar essa ação, o dispositivo deve ser colocado no modo perdido.
1.    Na folha de propriedades de um dispositivo iOS, escolha **Mais** > **Localizar dispositivo**.
2.    Depois do dispositivo ser localizado, o local será exibido na folha **Localizar dispositivo**. 
    ![Folha Localizar dispositivo](./media/locate-device.png)

### <a name="restart"></a>**Reiniciar**
Faz com que o dispositivo seja reiniciado. O proprietário do dispositivo não será notificado automaticamente sobre a reinicialização, portanto ele pode perder trabalho.


## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informações sobre segurança e privacidade para o modo perdido e ações para localizar o dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que você ative esta ação.
- Quando você usa a ação para localizar o dispositivo, as coordenadas da latitude e longitude do dispositivo são enviadas para o Intune e exibidas no portal do Azure.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Ao configurar o modo perdido, recomendamos que a mensagem inserida, que é exibida na tela de bloqueio, inclua informações para que o local do dispositivo possa ser determinado.

