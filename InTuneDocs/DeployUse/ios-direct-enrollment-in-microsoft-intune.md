---
title: Registro direto para dispositivos iOS | Microsoft Intune
description: "Use a Apple Configurator Tool para registrar diretamente dispositivos iOS corporativos com uma política predefinida conectando-os por USB a um computador Mac."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e0d05a4f229e2a8e72d1d60021b159f12dfa0d1
ms.openlocfilehash: 2d2db078bbbce5945bf536a845cd8e4fa8f62c7e


---

# Registrar dispositivos iOS diretamente usando o Apple Configurator
O Intune dá suporte ao registro de dispositivos iOS corporativos usando a ferramenta [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) em execução em um computador Mac. Esse processo não redefine de fábrica o dispositivo e registra o dispositivo com uma política predefinida. Esse método é para dispositivos **Sem afinidade de usuário** e requer que você conecte por USB o dispositivo iOS a um computador Mac para configurar o registro corporativo. Ao registrar dispositivos iOS diretamente, você pode registrar um dispositivo sem adquirir o número de série do dispositivo. Você também pode nomear o dispositivo para fins de identificação antes de o Intune capturar o nome do dispositivo durante o registro. Não há suporte para o aplicativo Portal da empresa em dispositivos com registro direto. Esta diretriz presume que você está usando o Apple Configurator 2.0 em um computador Mac.

1.  **Criar um perfil para dispositivos** Um perfil de registro do dispositivo define as configurações aplicadas a dispositivos. Se você ainda não tiver, crie um perfil de registro para dispositivos iOS registrados usando o Apple Configurator.

    1.  No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Política** &gt; **Registro do Dispositivo Corporativo** e, em seguida, selecione **Adicionar...**.

        ![Criar página de perfil de registro do dispositivo](../media/pol-sa-corp-enroll.png)

    2.  Insira os detalhes para os perfis de dispositivo:

        -   **Nome** – Nome do perfil de registro do dispositivo. Não é visível para os usuários.

        -   **Descrição** - descrição do perfil de registro do dispositivo. Não é visível para os usuários.

        -   **Afiliação do usuário** – Especifica como os dispositivos são registrados. Para o registro direto, selecione **Sem afinidade de usuário**.

        -   **Pré-atribuição de grupo de dispositivos** – todos os dispositivos implantados nesse perfil pertencerão inicialmente a esse grupo. Você pode reatribuir dispositivos após o registro.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  Clique em **Salvar Perfil** para adicionar o perfil.

5.  **Exportar um perfil como .mobileconfig para implantar dispositivos iOS** Selecione o perfil de dispositivo que você criou. Selecione **Exportar...** na barra de tarefas. Selecione **Baixar perfil** e salve o arquivo .mobileconfig baixado.

6.  **Transferir o arquivo** Copie o arquivo .mobileconfig baixado para um computador Mac.
    > [!NOTE]
    > A URL do perfil de registro é válida por duas semanas a partir de quando for exportada. Depois de duas semanas, você deve exportar uma nova URL de perfil de registro para registrar dispositivos iOS com o Assistente de Configuração.
7.  **Preparar o dispositivo com Apple Configurator** Dispositivos iOS são conectados ao computador Mac e registrados para o gerenciamento de dispositivo móvel.

    1.  Em um computador Mac, inicie o **Apple Configurator 2.0**.

    2.  Conecte o dispositivo iOS ao computador Mac com um cabo USB. Feche as **Fotos**, **iTunes**, e outros aplicativos que são abertos com o dispositivo quando ele é detectado.

    3.  No Apple Configurator, clique uma vez no dispositivo iOS conectado e, em seguida, selecione o botão **Adicionar**. As opções que podem ser adicionadas ao dispositivo aparecem na lista suspensa. Selecione **Perfis**.

    4.  Use o seletor de arquivos para selecionar o arquivo .mobileconfig exportado do Intune e, em seguida, selecione **Adicionar**. O perfil é adicionado ao dispositivo.  Se o dispositivo for **Sem supervisão**, a instalação necessitará da aceitação no dispositivo.

8.  **Instalar o perfil** Você está pronto para instalar o perfil no dispositivo iOS. O dispositivo já deve ter concluído o Assistente de Configuração e está pronto para uso.  Se o registro envolve as implantações de aplicativo, o dispositivo deve ter uma ID Apple configurada, pois as implantações de aplicativo exigirão que você tenha uma ID Apple conectada na Windows Store.

    1.  Desbloquear o dispositivo iOS.

    2.  Na caixa de diálogo **Instalar Perfil** para **Perfil de Gerenciamento**, toque em **Instalar**.

    3.  Forneça a **Senha do Dispositivo** ou **ID Apple**, se necessário.

    4.  Aceite o **Aviso**, e toque em **Instalar**.

    5.  Aceite o **Aviso Remoto**, e toque em **Confiar**.

    6.  Quando a caixa **Perfil Instalado** confirmar que o perfil foi **Instalado**, selecione **Concluído**.

9. **Verificar perfil**
    No dispositivo iOS, inicie **Configurações** e vá para **Geral** &gt; **Gerenciamento de Dispositivo** &gt; **Perfil de Gerenciamento** &gt; e confirme se a instalação do perfil está listada, verifique as restrições de política de iOS e os aplicativos instalados. Aplicativos e restrições de política podem levar até 10 minutos para serem exibidos no dispositivo.

10. **Distribuir dispositivos** O dispositivo iOS agora está registrado com o Intune e é gerenciado.



<!--HONumber=Jul16_HO3-->


