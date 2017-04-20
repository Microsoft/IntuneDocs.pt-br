---
title: "Registrar dispositivos iOS – Programa de registro de dispositivos"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como registrar dispositivos iOS da empresa usando o Programa de registro de dispositivos."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 61fbc2af9a7c43d01c20f86ff26012f63ee0a3c2
ms.openlocfilehash: c56bea46c8b505e0d357cfe90678ab149559b896
ms.lasthandoff: 04/07/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Registrar dispositivos iOS usando o Programa de registro de dispositivos

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Este tópico ajuda os administradores de TI a registrar dispositivos iOS de propriedade da empresa adquiridos por meio do [programa de registro de dispositivo (DEP) da Apple](https://deploy.apple.com). O Microsoft Intune pode implantar um perfil de registro que registra o DEP "pelo ar" para que o administrador nunca precise tocar em cada dispositivo gerenciado. Um perfil DEP contém as configurações de gerenciamento que você deseja aplicar a dispositivos durante o registro. O pacote de registro pode incluir opções do Assistente de Instalação para o dispositivo.

>[!NOTE]
>O registro DEP não pode ser usado com o [gerenciador de registro de dispositivos](enroll-devices-using-device-enrollment-manager.md).
>Além disso, se os usuários registrarem seus dispositivos iOS usando o aplicativo de Portal da empresa e os números de série desses dispositivos forem importados e receberem um perfil DEP, o registro do dispositivo no Intune será cancelado.

**Etapas de registro de DEP**
1. [Obtenha um token DEP da Apple](#get-the-apple-dep-certificate)
2. [Crie um perfil DEP](#create-anapple-dep-profile)
3. [Atribua números de série DEP da Apple a seu servidor Intune](#assign-apple-dep-serial-numbers-to-your-mdm-server)
4. [Sincronize dispositivos gerenciados por DEP](#synchronize-dep-managed-devices)
5. Distribuir dispositivos para usuários



## <a name="get-the-apple-dep-certificate"></a>Obtenha o certificado DEP da Apple
Para poder registrar dispositivos iOS de propriedade da empresa com o Programa de registro de dispositivos (DEP) da Apple, você precisa de um arquivo de certificado de DEP (.p7m) da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos de sua empresa que fazem parte do DEP. Ele também permite que o Intune realize carregamentos de perfis de registro para a Apple e atribua dispositivos a esses perfis.

Para gerenciar dispositivos iOS corporativos com o DEP, sua organização deve ingressar no DEP da Apple e obter dispositivos por meio do programa. Mais detalhes desse processo estão disponíveis em: https://deploy.apple.com. As vantagens do programa incluem a instalação não assistida de dispositivos sem usar um cabo USB para conectar cada dispositivo a um computador.

> [!NOTE]
> Se seu locatário Intune migrou do console clássico do Intune para o portal do Azure e você excluiu um token de DEP da Apple no console de administração do Intune durante o período de migração, o token de DEP pode ter sido restaurado para sua conta do Intune. Você pode excluir o token de DEP novamente no portal do Azure.




**Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token de DEP da Apple.**<br>
1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**. Na folha do Intune, selecione **Registro de dispositivo** > **Token de DEP da Apple**.
2. Selecione **Baixar sua chave pública** para baixar e salvar a chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.

**Etapa 2. Baixe um token de DEP da Apple do site da Apple adequado.**<br>
Selecione [Criar um token de DEP por meio de Programas de Implantação da Apple](https://deploy.apple.com) (https://deploy.apple.com) e entre com sua ID da Apple corporativa. Você pode usar essa ID da Apple para renovar seu token de DEP.

   1.  No [Portal do programa de registro de dispositivo](https://deploy.apple.com) da Apple, vá para **Programa de registro de dispositivo** &gt; **Gerenciar servidores** e, em seguida, escolha **Adicionar servidor MDM**.
   2.  Insira o **Nome do servidor MDM** e escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.
   3.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta. Escolha **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.
   4.  A caixa de diálogo **Adicionar &lt;ServerName&gt;** mostra um link **Seu Token do Servidor**. Baixe o arquivo do token (.p7m) do servidor em seu computador e escolha **Concluído**.

**Etapa 3. Insira a ID da Apple usada para criar o token de DEP da Apple. Essa ID pode ser usada para renovar seu token de DEP da Apple.**

**Etapa 4. Navegue até seu token de DEP da Apple a ser carregado. O Intune vai sincronizar-se automaticamente com a sua conta do DEP.**<br>
Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados.

## <a name="create-an-apple-dep-profile"></a>Crie um perfil de DEP da Apple

Um perfil de registro de dispositivos define as configurações aplicadas a um grupo de dispositivos. As etapas a seguir mostram como criar um perfil de registro de dispositivo para dispositivos iOS registrados usando o DEP.

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
2. Na folha Intune, escolha **Registrar dispositivos** e escolha **Registro Apple**.
3. Em **Gerenciar configurações de DEP (Programa de registro de dispositivos) da Apple**, selecione **Perfis de DEP**.
4. Na folha **Perfis de DEP da Apple**, selecione **Criar**.
5. Na folha **Criar Perfil de Registro**, insira um nome e uma descrição para o perfil.
6. Para **Afinidade de Usuário**, escolha se os dispositivos com esse perfil serão registrados com ou sem afinidade de usuário.

 - **Inscrever com afinidade do utilizador** – O dispositivo deve ser afiliado a um usuário durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa. Escolha afinidade de usuário para dispositivos gerenciados por DEP que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos. Observe que a MFA (Autenticação Multifator) não funciona durante o registro em dispositivos DEP com afinidade de usuário. Após o registro, a MFA funciona conforme o esperado nesses dispositivos. Novos usuários que precisam alterar a senha ao se conectarem pela primeira vez não podem receber um prompt durante o registro em dispositivos DEP. Além disso, os usuários cujas senhas expiraram não receberão um prompt para redefinir a senha durante o registro DEP e deverão redefinir a senha em um dispositivo diferente.

    >[!NOTE]
    >O DEP com afinidade de usuário requer que o [ponto de extremidade nome do usuário/misto WS-Trust 1.3](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints) esteja habilitado para solicitar um token de usuário. [Saiba mais sobre o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inscrever sem afinidade do utilizador** – O dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.

7. Selecione as **Configurações de Gerenciamento de Dispositivo**, defina as seguintes configurações de perfil e, em seguida, selecione **Salvar**:

    - **Supervisionado** – Um modo de gerenciamento que habilita mais opções de gerenciamento e desabilitou o Bloqueio de Ativação por padrão. Se você deixar a caixa de seleção, terá recursos de gerenciamento limitados.

    - **Registro bloqueado** – (Requer o Modo de Gerenciamento = Supervisionado) Desabilita as configurações de iOS que podem permitir a remoção do perfil de gerenciamento. Se você deixar a caixa de seleção em branco, permitirá que o perfil de gerenciamento seja removido do menu Configurações. Esse item é definido durante a ativação e não pode ser alterado sem uma redefinição de fábrica.

    - **Permitir Emparelhamento** – Especifica se os dispositivos iOS podem sincronizar com computadores. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

    - **Certificados do Apple Configurator** – Se que você escolheu **Permitir Apple Configurator por certificado** em **Permitir Emparelhamento**, selecione um Certificado do Apple Configurator para ser importado.

8. Selecione as **Configurações de Assistente de Instalação**, defina as seguintes configurações de perfil e, em seguida, selecione **Salvar**:

    - **Nome do Departamento** – Aparece quando os usuários tocam em **Sobre a Configuração** durante a ativação.

    - **Telefone do Departamento** – Aparece quando o usuário clica no botão Precisa de Ajuda durante a ativação.
    - **Opções do Assistente de Instalação** – Essas configurações opcionais podem ser configuradas no menu **Configurações** do iOS.
        - **Senha** - Solicitar senha durante a ativação. Sempre exija uma senha, a menos que o dispositivo esteja protegido ou tenha o acesso controlado de alguma outra maneira (ou seja, o modo de quiosque que restringe o dispositivo a um aplicativo).
        - **Serviços de Localização** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Restaurar** - Se habilitado, o Assistente de Instalação solicitará o backup do iCloud durante a ativação
        - **ID da Apple** – Se habilitado, o iOS solicitará aos usuários uma ID da Apple quando o Intune tentar instalar um aplicativo sem uma ID. Uma ID da Apple é exigida para baixar aplicativos na App Store do iOS, incluindo aqueles instalados pelo Intune.
        - **Termos e Condições** - Se habilitado, o Assistente de Instalação solicitará que os usuários aceitem os termos e as condições da Apple durante a ativação
        - **ID de Toque** - Se habilitada, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Pagamento da Apple** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Aplicar zoom** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Siri** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Dados de Diagnóstico** – Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação

9. Para salvar as configurações de perfil, selecione **Criar** na folha **Criar Perfil de Registro**.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Atribuir números de série de DEP da Apple ao seu servidor MDM

1. Vá até o [Portal do Programa de Registro do Dispositivo](https://deploy.apple.com) (https://deploy.apple.com) e entre com sua ID Apple corporativa.

2. Vá para **Programa de Implantação** &gt; **Programa de Registro de Dispositivo** &gt; **Gerenciar Dispositivos**.

3. Especifique como você vai **Escolher Dispositivos**, forneça informações do dispositivo e especifique os detalhes por **Número de Série**, **Número do Pedido** ou **Carregar o Arquivo CSV**.

4. Escolha **Atribuir ao Servidor**, escolha o &lt;ServerName&gt; especificado para o Microsoft Intune e escolha **OK**.

## <a name="synchronize-dep-managed-devices"></a>Sincronize dispositivos gerenciados pelo DEP

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha do Intune no Portal do Azure, escolha **Registrar Dispositivos** e escolha **Registro Apple**.

3. Em **Gerenciar configurações de DEP (Programa de registro de dispositivos) da Apple**, selecione **Números de Série de DEP**.

4. Na folha **Números de Série de DEP da Apple**, selecione **Sincronizar**.

5. Na folha **Sincronizar**, selecione **Solicitar Sincronização**. A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.

    Para cumprir os termos da Apple para tráfego DEP aceitável, o Intune impõe as seguintes restrições:
     -    Uma sincronização completa do DEP pode executar não mais do que uma vez a cada sete dias. Durante uma sincronização completa, o Intune atualiza cada número de série que a Apple atribuiu ao Intune, tenha o número de série sido sincronizado anteriormente ou não. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
     -    Qualquer solicitação de sincronização tem 10 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.

>[!NOTE]
>Você também pode atribuir números de série de DEP a perfis na folha **Números de Série de DEP da Apple**.

## <a name="distribute-devices-to-users"></a>Distribuir dispositivos para usuários

Agora você pode distribuir dispositivos da empresa para os usuários. Quando um dispositivo iOS for ativado, ele será registrado para gerenciamento pelo Intune.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Como os usuários instalam e usam o Portal da Empresa em seus dispositivos

Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos. Assim que os usuários receberem seus dispositivos, eles deverão realizar várias etapas adicionais descritas abaixo para concluir o Assistente de Configuração e instalar o aplicativo do Portal da Empresa.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Como os usuários registram dispositivos iOS corporativos com afinidade de usuário

1. Quando os usuários ligam seus dispositivos, eles recebem uma solicitação para concluir o Assistente de Configuração. Durante a configuração, os usuários receberão uma solicitação por suas credenciais. Eles devem usar as credenciais (ou seja, o nome pessoal exclusivo ou UPN) associadas à assinatura do Intune.

2. Durante a configuração, os usuários receberão uma solicitação por uma ID Apple. Eles precisam fornecer uma ID Apple para permitir que o dispositivo instale o Portal da Empresa. Também podem fornecer a ID pelo menu de ajustes do iOS após a conclusão da instalação.

3. Após concluir a configuração, os usuários deverão instalar o aplicativo do Portal da Empresa na App Store.

4. Agora, os usuários entrarão no Portal da Empresa usando o UPN utilizado durante a configuração do dispositivo.

5. Após o logon, os usuários recebem uma solicitação para registrar seu dispositivo. A primeira etapa é identificar o dispositivo. O aplicativo apresenta uma lista de dispositivos iOS que já foram registrados pela empresa e atribuídos à conta do Intune do usuário. O usuário deve escolher o dispositivo correspondente. Se o dispositivo ainda não tiver sido registrado pela empresa, eles deverão escolher Novo dispositivo para continuar com o fluxo de registro padrão.

6. Na próxima tela, os usuários confirmarão o número de série do novo dispositivo. Para fazer isso, os usuários selecionam um link que é exibido. O link inicia o aplicativo Configurações, que permite aos usuários verificar o número de série. Os usuários deverão inserir os quatro últimos caracteres do número de série no aplicativo do Portal da Empresa.

   Essa etapa verifica se o dispositivo é o dispositivo corporativo registrado no Intune. Se o número de série no dispositivo não corresponde, o usuário selecionou o dispositivo incorreto. O usuário deverá voltar à tela anterior e selecionar um dispositivo diferente.

7. Após a verificação do número de série, o aplicativo Portal da Empresa redirecionará para o site do Portal da Empresa a fim de finalizar o registro. Em seguida, o site solicita que os usuários retornem ao aplicativo.

Agora o registro foi concluído, e os usuários podem usar este dispositivo com o conjunto completo de recursos.

