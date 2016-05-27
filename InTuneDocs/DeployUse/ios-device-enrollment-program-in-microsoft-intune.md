---
# required metadata

title: Gerenciamento de DEP Apple para dispositivos iOS com o Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos iOS do Programa de Registro de Dispositivos corporativos
O Microsoft Intune pode implantar um perfil de registro que registre os dispositivos iOS comprados por meio do DEP (Programa de Registro de Dispositivo) "pelo ar". O pacote de registro pode incluir opções do assistente de instalação para o dispositivo. Registros de dispositivos feitos pelo DEP não podem ser desfeitos pelos usuários.

## Gerenciamento de DEP da Apple para dispositivos iOS com o Microsoft Intune
Para gerenciar dispositivos iOS corporativos com o Programa de registro de dispositivo (DEP) da Apple, sua organização deve ingressar em Apple DEP e adquirir dispositivos por meio do programa. Mais detalhes desse processo estão disponíveis em:  [https://deploy.apple.com](https://deploy.apple.com). As vantagens do programa incluem instalação não assistida de dispositivos sem conectar cada dispositivo por USB a um computador.

Para poder registrar dispositivos iOS corporativos com o DEP, é necessário um Token de DEP da Apple. Esse token permite que Intune sincronize informações sobre dispositivos participantes no DEP pertencentes a sua empresa. Ele também permite que o Intune realize carregamentos de Perfis de registro para a Apple e atribua dispositivos para esses perfis.

1.  **Começar a gerenciar dispositivos iOS com o Microsoft Intune**
    Antes de poder registrar dispositivos no DEP (Programa de Registro do Dispositivo) iOS, você deve habilitar o gerenciamento de iOS para o Intune.

2.  **Obter uma chave de criptografia**
    Como um usuário administrativo, abra o [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Administrador** &gt; **Gerenciamento de dispositivo móvel** &gt; **iOS** &gt; **Programa de Registro de Dispositivo**e clique em **Baixar a Chave de Criptografia**. Salve o arquivo de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.

      ![Atualizar um token de programa de registro do dispositivo](../media/dev-sa-ios-dep.png)

3.  **Obter um token de programa de registro do dispositivo**
    Vá até o [Portal do Programa de Registro do Dispositivo](https://deploy.apple.com) (https://deploy.apple.com) e entre com sua ID Apple corporativa. Essa ID da Apple deve ser usada no futuro para renovar seu token do DEP.

    1.  No [Portal do Programa de Registro de Dispositivo](https://deploy.apple.com), acesse **Programa de Registro de Dispositivo** &gt; **Gerenciar servidores** e, em seguida, clique em **Adicionar Servidor MDM**.

    2.  Insira o **Nome do servidor MDM** e, em seguida, clique em **Próximo**. O nome do servidor é para sua referência para identificar o servidor MDM. Não é o nome ou URL do servidor Microsoft Intune.

    3.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta. Clique em **Escolher Arquivo…** para carregar o arquivo .pem e, em seguida, clique em **Avançar**.

    4.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** exibe um link **Seu Token do Servidor**. Baixe o arquivo do token (.p7m) do servidor em seu computador e, em seguida, clique em **Concluído**.

    Esse arquivo de certificado (.p7m) é usado para estabelecer uma relação de confiança entre os servidores do Programa de registro de dispositivo da Apple.

4.  **Adicionar o token de DEP ao Intune**
    No [console de administração do Microsoft Intune](http://manage.microsoft.com), vá para **Administrador** &gt; **Gerenciamento de Dispositivos Móveis** &gt; **iOS** &gt; **Programa de Registro de Dispositivo** e clique em **Carregar o Token de DEP**. **Procurar** até o arquivo de certificado (.p7m), insira sua **ID Apple** e clique em **Carregar**.

5.  **Adicionar política de registro de dispositivo corporativo**
    No [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Política** &gt; **Registro do Dispositivo Corporativo** e, em seguida, clique em **Adicionar**. Forneça detalhes **Gerais** , incluindo **Nome** e **Descrição**, especifique se os dispositivos atribuídos ao perfil têm afinidade de usuário ou pertencem a um grupo e, em seguida, habilite **definições de Configurar o Programa de Registro de Dispositivo para esta política** para dar suporte a DEP. Os **painéis do Assistente de instalação** definem as configurações de dispositivo iOS estabelecidas durante a instalação.

      ![Painel do assistente de instalação](../media/pol-sa-corp-enroll.png)

6.  **Atribuir dispositivos DEP para gerenciamento**
    Vá até o [Portal do Programa de Registro do Dispositivo](https://deploy.apple.com) (https://deploy.apple.com) e entre com sua ID Apple corporativa. Acesse **Programa de Implantação** &gt; **Programa de Registro de Dispositivo** &gt; **Gerenciar Dispositivos**. Especifique como você vai **escolher dispositivos**, forneça informações do dispositivo e especifique os detalhes por **número de série**, **número do pedido**do dispositivo ou **carregue o arquivo CSV**. Em seguida, selecione **Atribuir ao Servidor** e selecione o &lt;ServerName&gt; especificado para o Microsoft Intune e, em seguida, clique em **OK**.

7.  **Sincronizar dispositivos gerenciados pelo DEP**
    Como um usuário administrativo, abra o [Console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS** &gt; **Programa de Registro de Dispositivo** e clique em **Sincronizar agora**. Uma solicitação de sincronização é enviada à Apple. Para ver os dispositivos gerenciados pelo DEP após a sincronização, no [console de administração do Microsoft Intune](http://manage.microsoft.com) vá para **Grupos** &gt; **Todos os Dispositivos Corporativos**. No espaço de trabalho **Dispositivos Corporativos**, o **Estado** para dispositivos gerenciados lê "Não contatado" até que o dispositivo esteja ligado e executa o Assistente de Configuração para registrar o dispositivo.

    Para cumprir os termos da Apple para tráfego DEP aceitável, o Intune impõe as seguintes restrições:
     -  Uma sincronização completa do DEP pode executar não mais do que uma vez a cada sete dias. Durante uma sincronização completa, o Intune atualiza cada número de série que a Apple atribuiu ao Intune, tenha o número de série sido sincronizado anteriormente ou não. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
     -  Qualquer solicitação de sincronização tem 10 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de sincronização fica desabilitado.

8.  **Distribuir dispositivos para usuários**
    Seus dispositivos corporativos agora podem ser distribuídos para usuários. Quando um dispositivo iOS for ativado, ele será registrado para gerenciamento pelo Intune.



### Consulte também
[Prepare-se para registrar dispositivos](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


