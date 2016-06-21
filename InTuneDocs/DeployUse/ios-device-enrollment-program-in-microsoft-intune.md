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
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos iOS do Programa de Registro de Dispositivos corporativos
O Microsoft Intune pode implantar um perfil de registro que registre os dispositivos iOS comprados por meio do DEP (Programa de Registro de Dispositivo) "pelo ar". O pacote de registro pode incluir opções do assistente de instalação para o dispositivo. Registros de dispositivos feitos pelo DEP não podem ser desfeitos pelos usuários.

## Gerenciamento de DEP da Apple para dispositivos iOS com o Microsoft Intune
Para gerenciar dispositivos iOS corporativos com o Programa de registro de dispositivo (DEP) da Apple, sua organização deve ingressar em Apple DEP e adquirir dispositivos por meio do programa. Mais detalhes desse processo estão disponíveis em:  [https://deploy.apple.com](https://deploy.apple.com). As vantagens do programa incluem instalação não assistida de dispositivos sem conectar cada dispositivo por USB a um computador.

Para poder registrar dispositivos iOS corporativos com o DEP, é necessário um Token de DEP da Apple. Esse token permite que Intune sincronize informações sobre dispositivos participantes no DEP pertencentes a sua empresa. Ele também permite que o Intune realize carregamentos de Perfis de registro para a Apple e atribua dispositivos para esses perfis.

1.  **Começar a gerenciar dispositivos iOS com o Microsoft Intune** Antes de poder registrar dispositivos no DEP (Programa de Registro de Dispositivo) iOS, você concluir a habilitação de gerenciamento de iOS para o Intune.

2.  **Obter uma Chave de Criptografia** Como usuário administrativo, abra o [console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS** &gt; **Programa de Registro de Dispositivo** e clique em **Baixar a Chave de Criptografia**. Salve o arquivo de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.

      ![Atualizar um token de programa de registro do dispositivo](../media/dev-sa-ios-dep.png)

3.  **Obtenha um token do Programa de Registro de Dispositivo** Vá até o [Portal do Programa de Registro de Dispositivo](https://deploy.apple.com) (https://deploy.apple.com) e entre com sua ID da Apple corporativa. Essa ID da Apple deve ser usada no futuro para renovar seu token do DEP.

    1.  No [Portal do Programa de Registro de Dispositivo](https://deploy.apple.com), acesse **Programa de Registro de Dispositivo** &gt; **Gerenciar servidores** e, em seguida, clique em **Adicionar Servidor MDM**.

    2.  Insira o **Nome do servidor MDM** e, em seguida, clique em **Próximo**. O nome do servidor é para sua referência para identificar o servidor MDM. Não é o nome ou URL do servidor Microsoft Intune.

    3.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta. Clique em **Escolher Arquivo…** para carregar o arquivo .pem e, em seguida, clique em **Avançar**.

    4.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** exibe um link **Seu Token do Servidor**. Baixe o arquivo do token (.p7m) do servidor em seu computador e, em seguida, clique em **Concluído**.

    Esse arquivo de certificado (.p7m) é usado para estabelecer uma relação de confiança entre os servidores do Programa de registro de dispositivo da Apple.

4.  **Adicionar o token de DEP ao Intune** No [console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS** &gt; **Programa de Registro de Dispositivo** e clique em **Carregar Token de DEP**. **Vá** até o arquivo de certificado (.p7m), insira sua **ID Apple**e clique em **Carregar**.

5.  **Adicionar Política de Registro de Dispositivo Corporativo** No [console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Política** &gt; **Registro de Dispositivo Corporativo** e, em seguida, clique em **Adicionar**.

    Forneça detalhes **Gerais**, incluindo **Nome** e **Descrição**, especifique se os dispositivos atribuídos ao perfil têm afinidade de usuário ou pertencem a um grupo.
      - **Solicitar afinidade de usuário**: o dispositivo deve ser afiliado a um usuário durante a configuração inicial e depois receber permissão para acessar dados e email da empresa como esse usuário.  A **afinidade do usuário** deve ser configurada para dispositivos gerenciados por DEP que pertencem aos usuários e que precisam usar o portal da empresa (por exemplo, para instalar aplicativos).
      - **Sem afinidade de usuário**: o dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem a afiliação do usuário, incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios, não funcionarão.

    Em seguida, habilite **Configurar definições do Programa de Registro do Dispositivo para esta política** para dar suporte ao DEP.

      ![Painel do assistente de instalação](../media/pol-sa-corp-enroll.png)

     As seguintes configurações estão disponíveis para dispositivos gerenciados por DEP:

     - **Departamento** - Aparece quando os usuários tocam em "Sobre a Configuração" durante a ativação
     - **Número de telefone de suporte** -Exibido quando o usuário clica no botão **Precisa de Ajuda** durante a ativação
     - **Modo de preparação** - Esse estado é definido durante a ativação e não pode ser alterado sem redefinir o dispositivo de fábrica:
        - **Sem supervisão** -Recursos de gerenciamento limitados
        - **Supervisionado** - Permite mais opções de gerenciamento e desabilita o Bloqueio de Ativação por padrão
     - **Bloquear o registro do perfil o dispositivo** - Esse estado é definido durante a ativação e não pode ser alterado sem uma redefinição de fábrica
        - **Desabilitar** - Permite que o perfil de gerenciamento seja removido do menu **Configurações**
        - **Habilitar** - (requer o **Modo de Preparação** = **Supervisionado**) Desabilita as configurações do iOS que podem permitir a remoção do perfil de gerenciamento
     - **Opções do Assistente de Instalação** -Essas configurações são opcionais e pode ser configuradas mais tarde no menu **Configurações** do iOS
        - **Senha** - Solicitar senha durante a ativação. Sempre exigir uma senha, a menos que o dispositivo esteja protegido ou tenha acesso controlado de alguma outra maneira (por exemplo, modo de quiosque que restringe o dispositivo a um aplicativo).
        - **Serviços de Localização** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Restaurar** - Se habilitado, o Assistente de Instalação solicitará o backup do iCloud durante a ativação
        - **ID da Apple** - Uma ID da Apple é exigida para baixar aplicativos na App Store do iOS, incluindo aqueles instalados pelo Intune. Se habilitado, o iOS solicitará aos usuários uma ID da Apple quando o Intune tentar instalar um aplicativo sem uma ID.
        - **Termos e Condições** - Se habilitado, o Assistente de Instalação solicitará que usuários aceitem os termos e condições da Apple durante a ativação do - **ID de Toque** - Se habilitado, o Assistente de Instalação solicitará esse serviço durante a ativação do - **Pagamento de Apple** - Se habilitado, o Assistente de Instalação solicitará esse serviço durante a ativação do - **Zoom** - Se habilitado, o Assistente de Instalação solicitará esse serviço durante a ativação da - **Siri** - Se habilitado, o Assistente de Instalação solicitará esse serviço durante a ativação de - **Enviar dados de diagnóstico à Apple** - Se habilitado, o Assistente de Instalação solicitará este serviço durante a ativação de -  **Permitir gerenciamento adicional pelo Apple Configurator** - Defina para **Não permitir** para impedir a sincronização de arquivos com o iTunes ou o gerenciamento por meio do Apple Configurator. A Microsoft recomenda que você defina como **Não permitir**, exportar qualquer configuração adicional do Apple Configurator e, em seguida, implantar como um perfil de configuração do iOS Personalizado por meio do Intune, em vez de usar essa configuração para permitir a implantação manual com ou sem um certificado.
        - **Não permitir** - Impede que o dispositivo se comunique via USB (desabilita emparelhamento) - **Permitir** - Permite que o dispositivo se comunique via conexão USB em qualquer PC ou Mac - **Exigir certificado** - Permite o emparelhamento com um Mac com um certificado importado para o perfil de registro

6.  **Atribuir Dispositivos DEP para Gerenciamento** Vá até o [Portal do Programa de Registro de Dispositivo](https://deploy.apple.com) (https://deploy.apple.com) e entre com sua ID da Apple corporativa. Vá até o **Programa de Implantação** &gt; **Programa de Registro de Dispositivo** &gt; **Gerenciar Dispositivos**. Especifique como você vai **escolher dispositivos**, forneça informações do dispositivo e especifique os detalhes por **número de série**, **número do pedido**do dispositivo ou **carregue o arquivo CSV**. Em seguida, selecione **Atribuir ao Servidor** e selecione o &lt;ServerName&gt; especificado para o Microsoft Intune e, em seguida, clique em **OK**.

7.  **Sincronizar Dispositivos Gerenciados por DEP** Como usuário administrativo, abra o [console de administração do Microsoft Intune](http://manage.microsoft.com), acesse **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS** &gt; **Programa de Registro de Dispositivo** e clique em **Sincronizar agora**. Uma solicitação de sincronização é enviada à Apple. Para ver os dispositivos gerenciados pelo DEP após a sincronização, no [console de administração do Microsoft Intune](http://manage.microsoft.com) vá para **Grupos** &gt; **Todos os Dispositivos Corporativos**. No espaço de trabalho **Dispositivos Corporativos**, o **Estado** para dispositivos gerenciados lê "Não contatado" até que o dispositivo esteja ligado e executa o Assistente de Configuração para registrar o dispositivo.

    Para cumprir os termos da Apple para tráfego DEP aceitável, o Intune impõe as seguintes restrições:
     -  Uma sincronização completa do DEP pode executar não mais do que uma vez a cada sete dias. Durante uma sincronização completa, o Intune atualiza cada número de série que a Apple atribuiu ao Intune, tenha o número de série sido sincronizado anteriormente ou não. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
     -  Qualquer solicitação de sincronização tem 10 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de sincronização fica desabilitado.

8.  **Distribuir dispositivos para usuários** Seus dispositivos de propriedade corporativa agora podem ser distribuídos para usuários. Quando um dispositivo iOS for ativado, ele será registrado para gerenciamento pelo Intune.



### Consulte também
[Prepare-se para registrar dispositivos](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


