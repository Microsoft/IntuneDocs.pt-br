---
title: Registro direto para dispositivos iOS
description: Use a Apple Configurator Tool para registrar diretamente dispositivos iOS corporativos com uma política predefinida conectando-os por USB a um computador Mac.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c4c98c6b279ecc99d2220a7e5071a1f92af1ea8b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="directly-enroll-ios-devices-by-using-apple-configurator"></a>Registrar dispositivos iOS diretamente usando o Apple Configurator

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

O Intune dá suporte ao registro de dispositivos iOS corporativos usando a ferramenta [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) em execução em um computador Mac. Esse processo não restaura as configurações de fábrica do dispositivo e registra o dispositivo com uma política predefinida. Esse método é para dispositivos **Sem afinidade de usuário** e requer que você conecte por USB o dispositivo iOS a um computador Mac para configurar o registro corporativo.

Ao registrar dispositivos iOS diretamente, você pode registrar um dispositivo sem adquirir o número de série do dispositivo. Você também pode nomear o dispositivo para fins de identificação antes de o Intune capturar o nome do dispositivo durante o registro. Não há suporte para o aplicativo de Portal da Empresa para dispositivos registrados diretamente. Esta diretriz presume que você está usando o Apple Configurator 2.0 em um computador Mac.

>[!NOTE]
>Esse método de registro não pode ser usado com o método de [gerenciador de registro de dispositivos](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

1. Se ainda não tiver feito isso, crie um perfil de registro para dispositivos iOS registrados usando o Apple Configurator. Um perfil de registro do dispositivo define as configurações aplicadas a dispositivos.

   1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), acesse **Política** &gt; **Registro do Dispositivo Corporativo** e escolha **Adicionar**.

      ![Criar página de perfil de registro do dispositivo](../media/pol-sa-corp-enroll.png)

   2. Insira os detalhes para os perfis de dispositivo:

      - **Nome**: nome do perfil de registro do dispositivo. Não é visível para os usuários.

      - **Descrição**: descrição do perfil de registro do dispositivo. Não é visível para os usuários.

      - **Afiliação do usuário**: especifica como os dispositivos são registrados. Para o registro direto, escolha **Sem afinidade de usuário**.

      - **Pré-atribuição de grupo de dispositivos**: todos os dispositivos que têm esse perfil pertencerão inicialmente a esse grupo. Você pode reatribuir dispositivos após o registro.

        [!INCLUDE [groups deprecated](../includes/group-deprecation.md)]


   3. Clique em **Salvar Perfil** para adicionar o perfil.

2. Exporte um perfil como .mobileconfig para implantar em dispositivos iOS:

   1.   Selecione o perfil de dispositivo que você criou.

   2.   Escolha **Exportar** na barra de tarefas.

   3.   Selecione **Baixar perfil** e salve o arquivo .mobileconfig baixado.

3. Transfira o arquivo copiando o arquivo .mobileconfig baixado para um computador Mac.
   > [!NOTE]
   > A URL do perfil de registro é válida por duas semanas a partir de quando for exportada. Depois de duas semanas, você deve exportar uma nova URL de perfil de registro para registrar dispositivos iOS com o Assistente de Configuração.

4. Preparar o dispositivo com o Apple Configurator. Dispositivos iOS são conectados ao computador Mac e registrados para o gerenciamento de dispositivo móvel.

   1.  Em um computador Mac, abra o **Apple Configurator 2.0**.

   2.  Conecte o dispositivo iOS ao computador Mac com um cabo USB. Feche as **Fotos**, **iTunes**, e outros aplicativos que são abertos com o dispositivo quando ele é detectado.

   3.  No Apple Configurator, escolha o dispositivo iOS conectado e selecione o botão **Adicionar**. As opções que podem ser adicionadas ao dispositivo aparecem na lista suspensa. Escolha **Perfis**.

   4.  Use o seletor de arquivos para selecionar o arquivo .mobileconfig exportado do Intune e escolha **Adicionar**. O perfil é adicionado ao dispositivo.  Se o dispositivo for **Sem supervisão**, a instalação necessitará da aceitação no dispositivo.

5. Você está pronto para instalar o perfil no dispositivo iOS. O dispositivo já deve ter concluído o Assistente de Configuração e está pronto para uso. Se o registro envolve as implantações de aplicativo, o dispositivo deve ter uma ID Apple configurada, pois as implantações de aplicativo exigirão que você tenha uma ID Apple conectada na Windows Store.

   1.  Desbloquear o dispositivo iOS.

   2.  Na caixa de diálogo **Instalar perfil** para o **Perfil de gerenciamento**, escolha **Instalar**.

   3.  Forneça a **Senha do Dispositivo** ou **ID Apple**, se necessário.

   4.  Aceite o **Aviso** e escolha **Instalar**.

   5.  Aceite o **Aviso Remoto** e escolha **Confiar**.

   6.  Quando a caixa **Perfil Instalado** confirmar que o perfil foi **Instalado**, selecione **Concluído**.

6. No dispositivo iOS, abra **Configurações** e vá para **Geral** &gt; **Gerenciamento de Dispositivos** &gt; **Perfil de Gerenciamento**. Confirme que o perfil de instalação está listado, verifique as restrições de política do iOS e os aplicativos instalados. Aplicativos e restrições de política podem levar até 10 minutos para serem exibidos no dispositivo.

7. Distribuir dispositivos. O dispositivo iOS agora está registrado com o Intune e é gerenciado.
