---
title: "Solucionar problemas de implantação de aplicativo | Microsoft Intune"
description: "Este tópico ajuda você a solucionar problemas de implantação de aplicativo com o Microsoft Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa96cf3a1909e3ea2187a3beb0aede3228894504
ms.openlocfilehash: 9f4b91bd523c82665bcac54902b2e8cc9c72ef75


---

# Solucionar problemas de implantação de aplicativo no Microsoft Intune
Se você estiver tendo problemas ao implantar e gerenciar aplicativos com o Intune, comece aqui. Este tópico contém alguns problemas comuns que podem ocorrer, juntamente com as soluções.

## Problemas comuns de implantação de aplicativo

### As informações de contato de TI estão ausentes no Portal da Empresa

1.  No console de administração do Intune, clique em **Administrador** &gt; **Portal da Empresa**.

2.  Defina os detalhes de **Contato de TI** .

### Se você não conseguir ver os aplicativos específicos na lista

1.  Certifique-se de estar verificando a lista de aplicativos de um usuário ou dispositivo no qual o aplicativo foi implantado.

2.  Certifique-se de que o dispositivo atende aos requisitos para o aplicativo.

### Se você receber um erro durante o download de um aplicativo

1.  Certifique-se de que não há mais de um download simultâneo por usuário. Cada usuário pode baixar um aplicativo por vez.

2.  Verifique se não há muitos downloads simultâneos por conta. Aguarde alguns minutos e tente novamente.

3.  Se você receber uma mensagem nativa do iOS informando que não é possível instalar, que a instalação foi cancelada ou que você deve tentar novamente, talvez isso se deva a um aumento de tráfego. Aguarde alguns minutos e tente novamente.

4.  Se a barra de progresso do download do aplicativo iOS chegar ao final, mas a instalação do aplicativo falhar, talvez haja algum problema com os arquivos do aplicativo fornecidos por você.


### Se o seu aplicativo estiver preso em "em andamento" ao carregar

1.  Ao carregar um aplicativo, primeiro os metadados são adicionados, seguidos pelo pacote do aplicativo. Depois que os metadados forem carregados, o aplicativo será exibido em andamento. Se o seu aplicativo permanecer no estado "em andamento" por um tempo muito longo, exclua o aplicativo e carregue-o novamente.

2.  Lembre-se de não gerenciar a implantação do aplicativo enquanto está no estado de "em andamento".

### Se encontrar uma falha ao instalar um aplicativo iOS

1.  Certifique-se de que o firewall da organização permite acesso aos sites da web de provisionamento e de certificação da Apple.

2.  Para obter mais informações, exiba a documentação do desenvolvedor Apple.

### Se os aplicativos gerenciados não comunicarem o status da instalação

O status da instalação não foi coletado para instalações de aplicativo gerenciado antes da atualização do serviço Microsoft Intune em novembro de 2014. Para dispositivos que instalaram aplicativos gerenciados antes dessa atualização de serviço, atualize cada implantação de aplicativo associada com a ação de apropriada de implantação (por exemplo, **Instalação disponível**). Cada dispositivo atualizará o aplicativo durante a verificação automática de aplicativos disponíveis. Para obter mais informações, confira [Update apps using Microsoft Intune](/intune/deploy-use/update-apps-using-microsoft-intune) (Atualizar aplicativos usando o Microsoft Intune).

## <a name="BKMK_SoftDistErrorCodes"></a>Códigos de erro de implantação do aplicativo
A tabela a seguir relaciona os erros comuns que podem ocorrer durante a implantação do aplicativo Intune, as causas prováveis e as soluções possíveis para ajudar você a solucionar tais erros.

|Código do erro|Possível problema|Resoluções sugeridas|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (erro de cliente)|Para instalar esse aplicativo, você deve ter um sistema habilitado para carregamento.|Verifique se o pacote do aplicativo foi assinado com uma assinatura confiável e instalado em um dispositivo que tem a política AllowAllTrustedApps habilitada ou um dispositivo que tem uma licença do Windows Sideloading com a política AllowAllTrustedApps habilitada (aplicada quando o dispositivo Windows RT é registrado).|
|0x80073CF0|Não foi possível abrir o pacote.|Possíveis causas:<br /><br />-   O pacote não está assinado.<br />-   O nome do editor não corresponde ao assunto do certificado de assinatura.<br /><br />Consulte o log de eventos de AppxPackagingOM para obter mais informações.|
|0x80073CF3|Falha na atualização do pacote, dependência ou validação de conflito|Possíveis causas:<br /><br />-   O pacote de entrada está em conflito com um pacote instalado.<br />-   Uma dependência de pacote especificada não foi encontrada.<br />-   O pacote não dá suporte à arquitetura de processador correta.<br /><br />Consulte o log de eventos de AppXDeployment-Server para obter mais informações.|
|0x80073CFB|O pacote fornecido já foi instalado e sua reinstalação está bloqueada|Talvez você receba esse erro se estiver instalando um pacote que não é idêntico ao pacote já instalado. Confirme se a assinatura digital também faz parte do pacote. Quando um pacote é recriado ou assinado novamente, ele não é mais idêntico bit a bit ao pacote instalado anteriormente. Duas opções possíveis para corrigir esse erro são as seguintes:<br /><br />-   Aumente o número de versão do aplicativo e recrie e assine novamente o pacote.<br />-   Remova o pacote antigo para cada usuário no sistema antes de instalar o novo pacote.|
|0x87D1041C|Êxito na instalação do aplicativo, mas o aplicativo não foi detectado.|-O aplicativo foi implantado com êxito pelo Intune e subsequentemente desinstalado (possivelmente pelo usuário final). Instrua o usuário a reinstalar o aplicativo do portal da empresa. Os aplicativos necessários serão reinstalados automaticamente na próxima vez em que o dispositivo fizer check-in.|

### Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).



<!--HONumber=Aug16_HO5-->


