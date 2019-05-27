---
title: Configurações de Wi-Fi para dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de configuração de Wi-Fi usando as configurações de Wi-Fi para dispositivos Windows 10 e posterior no Microsoft Intune. Defina configurações Básicas ou configurações de nível empresarial.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/8/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 502babf80b4286adb19a09988d16bd56562d4925
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66046660"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Adicionar configurações de Wi-Fi para dispositivos Windows 10 e posterior no Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e implantar esse perfil para seus dispositivos Windows 10 e posteriores. O Microsoft Intune oferece muitos recursos, incluindo autenticação na rede, uso de uma chave pré-compartilhada e muito mais.

Este artigo descreve essas configurações.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](device-profile-create.md).

## <a name="basic-profile"></a>Perfil básico

- **Tipo de Wi-Fi**: escolha **Básico**. 

- **Nome de Wi-Fi (SSID)** : abreviação de identificador SSID. Esse valor é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **Nome da conexão** definido ao escolher a conexão.

- **Nome da conexão**: insira um nome amigável para essa conexão Wi-Fi. O texto inserido é o nome que os usuários veem ao navegarem pelas conexões disponíveis no dispositivo.

- **Conectar automaticamente quando estiver no intervalo**: quando essa opção estiver marcada como **Sim**, os dispositivos se conectarão automaticamente quando estiverem no intervalo dessa rede. Quando ela estiver marcada como **Não**, os dispositivos não se conectarão automaticamente.

  - **Conectar-se à rede preferencial, se disponível**: se os dispositivos estiverem no intervalo de uma rede preferencial, escolha **Sim** para usar a rede preferencial. Escolha **Não** para usar a rede Wi-Fi nesse perfil de configuração.

    Por exemplo, crie uma rede Wi-Fi **ContosoCorp** e use **ContosoCorp** dentro desse perfil de configuração. Você também tem uma rede Wi-Fi **ContosoGuest** dentro do intervalo. Quando os dispositivos corporativos estão dentro do intervalo, você deseja que eles se conectem automaticamente a **ContosoCorp**. Nesse cenário, defina a propriedade **Conectar-se à rede preferencial se disponível** como **Não**.

  - **Conectar-se a esta rede, mesmo quando ela não difundir seu SSID**: escolha **Sim** para que o perfil de configuração se conecte automaticamente à rede, mesmo quando a rede estiver oculta (ou seja, seu SSID não for difundido publicamente). Escolha **Não** se você não deseja que esse perfil de configuração se conecte à rede oculta.

- **Limite de Conexão Medido**: um administrador pode escolher como o tráfego da rede é monitorado. Os aplicativos então podem ajustar seu comportamento de tráfego de rede com base nessa configuração. Suas opções:

  - **Irrestrito**: padrão. A conexão não é monitorada e não existem restrições em relação ao tráfego.
  - **Fixa**: use essa opção se a rede estiver configurada com um limite fixo para o tráfego de rede. Depois que esse limite for atingido, o acesso à rede será proibido.
  - **Variável**: use essa opção se o tráfego de rede for cobrado por byte (custo por byte).

- **Tipo de Segurança Sem Fio**: insira o protocolo de segurança usado para autenticar dispositivos na rede. As opções são:
  - **Abrir (sem autenticação)** : use essa opção somente se a rede não for segura.
  - **WPA/WPA2-Personal**: uma opção mais segura e normalmente usada para conectividade de Wi-Fi. Para obter mais segurança, você também pode inserir uma chave de rede ou senha de chave pré-compartilhada. 

    - **Chave pré-compartilhada** (PSK): opcional. Mostrada quando você escolhe **WPA2/WPA-Personal** como o tipo de segurança. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK. Insira uma cadeia de caracteres com 8 a 64 caracteres. Se a senha ou chave de rede tiver 64 caracteres, insira caracteres hexadecimais.
    
      > [!NOTE]
      > Quando você salva o perfil de Wi-Fi, o valor PSK inserido não é mostrado por motivos de segurança. A marca-d'água da chave pré-compartilhada ainda mostra **Não configurado**, embora a PSK esteja salva no perfil. Para alterar a PSK, insira uma nova chave e salve o perfil. Se você salvar uma PSK, edite a política e deixe a PSK em branco e a PSK existente ainda será usada.

- **Configurações de Proxy da Empresa**: opte por usar as configurações de proxy em sua organização. Suas opções:
  - **Nenhum**: nenhuma configuração de proxy é definida.
  - **Configurar manualmente**: insira o **Endereço de IP do servidor proxy** e o **Número da porta**.
  - **Configurar automaticamente**: insira a URL que aponta para um script PAC (configuração automática de proxy). Por exemplo, insira `http://proxy.contoso.com/proxy.pac`.

Selecione **OK** > **Criar** para salvar suas alterações. O perfil será criado e exibido na lista de perfis.

## <a name="enterprise-profile"></a>Perfil corporativo

- **Tipo de Wi-Fi**: escolha **Corporativo**. 

- **Nome de Wi-Fi (SSID)** : abreviação de identificador SSID. Esse valor é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **Nome da conexão** definido ao escolher a conexão.

- **Nome da conexão**: insira um nome amigável para essa conexão Wi-Fi. O texto inserido é o nome que os usuários veem ao navegarem pelas conexões disponíveis no dispositivo.

- **Conectar automaticamente quando estiver no intervalo**: quando essa opção estiver marcada como **Sim**, os dispositivos se conectarão automaticamente quando estiverem no intervalo dessa rede. Quando ela estiver marcada como **Não**, os dispositivos não se conectarão automaticamente.
  - **Conectar-se à rede preferencial, se disponível**: se os dispositivos estiverem no intervalo de uma rede preferencial, escolha **Sim** para usar a rede preferencial. Escolha **Não** para usar a rede Wi-Fi nesse perfil de configuração.

    Por exemplo, crie uma rede Wi-Fi **ContosoCorp** e use **ContosoCorp** dentro desse perfil de configuração. Você também tem uma rede Wi-Fi **ContosoGuest** dentro do intervalo. Quando os dispositivos corporativos estão dentro do intervalo, você deseja que eles se conectem automaticamente a **ContosoCorp**. Nesse cenário, defina a propriedade **Conectar-se à rede preferencial se disponível** como **Não**.

  - **Conectar-se a esta rede, mesmo quando ela não difundir seu SSID**: escolha **Sim** para que o perfil de configuração se conecte automaticamente à rede, mesmo quando a rede estiver oculta (ou seja, seu SSID não for difundido publicamente). Escolha **Não** se você não deseja que esse perfil de configuração se conecte à rede oculta.

- **Limite de Conexão Medido**: um administrador pode escolher como o tráfego da rede é monitorado. Os aplicativos então podem ajustar seu comportamento de tráfego de rede com base nessa configuração. Suas opções:

  - **Irrestrito**: padrão. A conexão não é monitorada e não existem restrições em relação ao tráfego.
  - **Fixa**: use essa opção se a rede estiver configurada com um limite fixo para o tráfego de rede. Depois que esse limite for atingido, o acesso à rede será proibido.
  - **Variável**: use essa opção se o tráfego de rede for orçado por byte.

- **SSO (logon único)** : permite que você configure o SSO (logon único), no qual as credenciais são compartilhadas para entrar no computador e na rede Wi-Fi. As opções são:
  - **Desabilitar**: desabilita o comportamento do SSO. O usuário precisa autenticar à rede separadamente.
  - **Habilitar antes que o usuário entre no dispositivo**: use o SSO para autenticar na rede antes do processo de entrada do usuário.
  - **Habilitar depois que o usuário entrar no dispositivo**: use o SSO para autenticar na rede imediatamente após a conclusão do processo de entrada do usuário.
  - **Tempo máximo de autenticação antes do tempo limite**: insira o número máximo de segundos a aguardar antes da autenticação com a rede, de 1 a 120 segundos.
  - **Permitir que o Windows solicite ao usuário credenciais de autenticação adicionais**: a escolha da opção **Sim** permitirá que o sistema Windows solicite ao usuário credenciais adicionais se for exigido pelo método de autenticação. Escolha **Não** para ocultar esses prompts.

- **Habilitar o cache da Chave PMK**: selecione **Sim** para armazenar em cache o PMK usado na autenticação. Esse cache normalmente permite que a autenticação na rede seja concluída mais rapidamente. Escolha **Não** para forçar o handshake de autenticação ao se conectar à rede Wi-Fi todas as vezes.

  - **Tempo máximo que um PMK é armazenado em cache**: insira o número de minutos que uma Chave PMK é armazenada no cache, de 5 a 1.440 minutos.
  - **Número máximo de PMKs armazenados em cache**: insira o número de chaves armazenadas em cache, de 1 a 255.

- **Habilitar pré-autenticação**: a pré-autenticação permite que o perfil seja autenticado em todos os pontos de acesso da rede no perfil antes da conexão. Ao mover entre pontos de acesso, a pré-autenticação reconecta o usuário ou os dispositivos mais rapidamente. Escolha **Sim** para que o perfil se autentique em todos os pontos de acesso nessa rede que estão dentro do intervalo. Escolha **Não** para exigir que o usuário ou o dispositivo se autentique em cada ponto de acesso separadamente.

  - **Número máximo de tentativas de pré-autenticação**: insira o número de tentativas de pré-autenticação, de 1 a 16.

- **Tipo de EAP**: escolha o tipo de protocolo EAP usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **PEAP Protegido** (PEAP)

    **Configurações adicionais de EAP-TLS, EAP-TTLS e PEAP**:
    
    > [!NOTE]
    > Atualmente, apenas há suporte para perfis de certificado SCEP com o uso de um tipo de EAP. Não há suporte para perfis de certificado PKCS. Sempre que um usuário precisar inserir um certificado, lembre-se de escolher um certificado SCEP.

      - **Confiança do servidor**  

        **Nomes do servidor de certificado**: use com os tipos de EAP **EAP-TLS**, **EAP-TTLS** ou **PEAP**. Insira um ou mais nomes comuns usados nos certificados emitidos pela AC (autoridade de certificação) confiável. Se você inserir essas informações, poderá ignorar a caixa de diálogo de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.  

        **Certificado raiz para validação do servidor**: use com os tipos de EAP **EAP-TLS**, **EAP-TTLS** ou **PEAP**. Escolha o perfil de certificado raiz confiável usado para autenticar a conexão.  

        **Privacidade de identidade (identidade externa)** : use com o tipo de EAP **PEAP**. Insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.  

      - **Autenticação do Cliente**

        **Certificado do cliente para autenticação do cliente (certificado de identidade)** : use com o tipo de EAP **EAP-TLS**. Escolha o perfil de certificado usado para autenticar a conexão.

        **Método de autenticação**: use com o tipo de EAP **EAP-TTLS**. Selecione o método de autenticação para a conexão:  

          - **Certificados**: selecione o certificado do cliente que é o certificado de identidade apresentado ao servidor.
          - **Nome de usuário e senha**: insira um método de autenticação **que não seja de EAP (identidade interna)** . Suas opções:

            - **Senha não criptografada (PAP)**
            - **Protocolo CHAP**
            - **Microsoft CHAP (MS-CHAP)**
            - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

        **Privacidade de identidade (identidade externa)** : use com o tipo de EAP **EAP-TTLS**. Insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

- **Configurações de Proxy da Empresa**: opte por usar as configurações de proxy em sua organização. Suas opções:
  - **Nenhum**: nenhuma configuração de proxy é definida.
  - **Configurar manualmente**: insira o **Endereço de IP do servidor proxy** e o **Número da porta**.
  - **Configurar automaticamente**: insira a URL que aponta para um script PAC (configuração automática de proxy). Por exemplo, insira `http://proxy.contoso.com/proxy.pac`.

- **Forçar o perfil de Wi-Fi a estar em conformidade com o padrão FIPS**: escolha **Sim** ao validar em relação ao padrão FIPS 140-2. Esse padrão é necessário para todas as agências do governo federal dos EUA que usam sistemas de segurança baseados em criptografia para proteger informações confidenciais, mas não classificadas, armazenadas digitalmente. Escolha **não** para não estar em conformidade com o FIPS.

Selecione **OK** > **Criar** para salvar suas alterações. O perfil será criado e exibido na lista de perfis.

## <a name="use-an-imported-settings-file"></a>Usar um arquivo de configurações importadas

Para as configurações que não estão disponíveis no Intune, você pode exportar as configurações de Wi-Fi de outro dispositivo Windows. Essa exportação cria um arquivo XML com todas as configurações. Em seguida, importe esse arquivo no Intune e use-o como o perfil de Wi-Fi. Confira [Exportar e importar configurações de Wi-Fi para dispositivos Windows](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md).

## <a name="more-resources"></a>Mais recursos

- Veja as configurações disponíveis para o [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
- [Visão geral das configurações de Wi-Fi](wi-fi-settings-configure.md), incluindo outras plataformas
