---
title: "Solucionar problemas de instalação do cliente"
description: "Solucione problemas comuns de instalação do cliente."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e46d292b-1d16-46db-a87f-d53eefa4d22a
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: bb0eea78d469bb45b833251482d55b44894f32e8
ms.contentlocale: pt-br
ms.lasthandoff: 06/08/2017


---

# <a name="troubleshoot-client-setup-in-microsoft-intune"></a>Solucionar problemas de instalação do cliente no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use as informações a seguir para ajudá-lo a solucionar problemas comuns de instalação do cliente. Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.

## <a name="client-installation-fails"></a>Falha na instalação do cliente

-   Se nenhum alerta de implantação do software cliente estiver visível no [console de administração do Microsoft Intune](https://manage.microsoft.com/), verifique a configuração de proxy e a conectividade do computador com a Internet e confirme se ele consegue se comunicar com a URL do serviço, [https://manage.microsoft.com](https://manage.microsoft.com/). Repita a instalação do software cliente.

-   Você pode enviar um email para destinatários selecionados quando ocorrer um alerta de falha de implantação de software cliente configurando uma regra de notificação no espaço de trabalho **Administração** . Para mais informações, confira [Get notified by Microsoft Intune alerts](/intune-classic/deploy-use/get-notified-by-alerts) (Ser notificado pelos alertas do Microsoft Intune).

-   O Intune exibe o alerta crítico **Falha na Implantação do Software Cliente** se ocorrer falha na implantação do software cliente. Esse alerta será exibido nas páginas **Visão Geral do Sistema** e **Alertas** do [console de administração do Microsoft Intune](https://manage.microsoft.com/). Aqui está como verificar se há alertas:

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Alertas** &gt; **Visão Geral**.

2.  Na página **Visão geral de alertas** , você pode examinar as seguintes informações:

    -   Os três principais alertas, que podem ser classificados por data, categoria ou severidade

    -   O número total de alertas ativos

3.  Clique em **Todos os Alertas** para exibir as seguintes informações sobre a página **Alertas**. Os alertas críticos são exibidos primeiro:

    -   **Nome** – O nome do tipo de alerta que gerou o alerta.

    -   **Origem** – Um link para a origem do alerta.  Se o limite de exibição do tipo de alerta estiver definido como **Tudo**, o link exibirá um único dispositivo afetado.  Se o limite de exibição do tipo de alerta estiver definido como um valor, esse link exibirá uma lista de todos os dispositivos afetados pelo alerta.

    -   **Última modificação** – Indica o horário em que o alerta foi modificado pela última vez. Se um alerta estiver fechado, o horário do fechamento será exibido.

    -   **Severidade** – Indica a severidade do alerta

## <a name="computer-enrollment-package-doesnt-download"></a>O pacote de registro do computador não faz o download
**Problema:** ao tentar registrar um computador, você observa o seguinte:
-  Falha ao baixar o pacote de registro
-  A caixa de diálogo do download é exibida, mas expira

**Resolução:** no navegador que você está usando para o download, durante o seu período de duração, certifique-se de que os downloads estão habilitados e que os arquivos criptografados podem ser salvos em seu disco local.

## <a name="client-installation-hangs-with-error-code-0x80040154"></a>A instalação do cliente trava com o código de erro 0x80040154
**Problema:**

-  A instalação de cliente durante o registro trava

-  Não é possível registrar o dispositivo

-  Erro 0x80040154 no WindowsUpdate.log

Isso pode ser causado pela ausência de atualizações críticas de software no computador.

**Resolução:** certifique-se de que sua política de atualização de software permite a instalação de atualizações críticas, conforme descrito em [Keep Windows PCs up to date with software updates in Microsoft Intune](/intune-classic/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune) (Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune)


## <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Erros relacionados à política do Microsoft Intune em policyplatform.log
Para dispositivos do Windows não MDM, erros de política no arquivo policyplatform.log podem ser o resultado de configurações não padrão no UAC (Controle de Conta de Usuário) do Windows no dispositivo. Algumas configurações de UAC não padrão podem afetar as instalações de cliente do Microsoft Intune e a execução da política.

### <a name="to-resolve-uac-issues"></a>Para resolver problemas do UAC

1.  Desative o computador, conforme descrito em [Desativar dispositivos e dados do gerenciamento do Microsoft Intune](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Espere 20 minutos para o software cliente ser removido.

    > [!NOTE]
    > Não tente remover o cliente em Programas e Recursos.

3.  No menu Iniciar, digite **UAC** para abrir as configurações de Controle de Conta de Usuário.

4.  Mova o controle deslizante de notificação para a configuração padrão.

## <a name="what-to-do-if-the-client-will-not-uninstall-from-the-microsoft-intune-administrator-console"></a>O que fazer se o cliente não puder ser desinstalado do console do administrador do Windows Intune

### <a name="to-remove-the-client-software-by-using-the-microsoft-intune-command-line-tool"></a>Para remover o software cliente usando a ferramenta da linha de comando do Microsoft Intune

1.  Abra um prompt de comando no modo administrador.

2.  Vá para a pasta *%programfiles%\Microsoft\OnlineManagement\Common*

3.  Execute o seguinte comando ``ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune``

## <a name="client-installation-error-codes"></a>Códigos de erro de instalação do cliente
A tabela a seguir descreve os códigos de erro exibidos em **Alertas** se ocorrer falha na instalação do software cliente. Ele inclui sugestões para resolver o problema representado em cada código de erro.

|Código do erro|Possível problema|Resoluções sugeridas|
|--------------|--------------------|------------------------|
|**0x80CF0437**|O relógio no computador cliente não está definido com a hora correta.|Verifique se o relógio e o fuso horário do computador cliente estão definidos para a hora e o fuso horário corretos.|
|**0x80240438**, **0x80CF0438**, **0x80CF401B**|Não é possível se conectar ao serviço Intune. Verifique as configurações de proxy do cliente.|Verifique se a configuração de proxy no computador cliente tem suporte pelo Intune e se o computador tem acesso à Internet. Para mais informações sobre as configurações de proxy com suporte, confira [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) (Ajudar a proteger computadores Windows com o Endpoint Protection para o Microsoft Intune).|
|**0x80CF402C**|Não é possível se conectar ao serviço Intune. Verifique a conectividade de rede.|Verifique se o computador tem conectividade de rede. Certifique-se de que o cabo de rede está conectado ou que a rede sem fio está ativada.|
|**0x80240438, 0x80CF0438**|As configurações de proxy no Internet Explorer e no Sistema Local não estão definidas.|Verifique as configurações de proxy do cliente, confirme se a configuração de proxy no computador cliente tem suporte no Intune e se o computador cliente tem acesso à Internet. Para mais informações sobre as configurações de proxy com suporte, confira [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) (Ajudar a proteger computadores Windows com o Endpoint Protection para o Microsoft Intune).|
|**0x80043001**|O pacote de inscrição está desatualizado.|Baixe e instale o pacote do software cliente atual no espaço de trabalho **Administração** . Para instruções, confira o tópico [Install the Windows PC client with Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune) (Instalar o cliente do computador Windows com o Microsoft Intune).|
|**0x80043004**|A assinatura não existe ou está desabilitada.|Verifique se sua conta e assinatura do Intune continuam ativas. Para exibir suas configurações de conta, entre na sua conta do [centro de administração do Office 365](http://go.microsoft.com/fwlink/?LinkId=698854%20).|
|**0x80043002**|A conta está no modo de manutenção.|Não é possível inscrever novos computadores clientes quando a conta está no modo de manutenção. Para exibir suas configurações de conta, entre na sua conta do [centro de administração do Office 365](http://go.microsoft.com/fwlink/?LinkId=698854%20).|
|**0x80043003**|A conta está excluída.|Verifique se sua conta e assinatura do Intune continuam ativas. Para exibir suas configurações de conta, entre na sua conta.|
|**0x80043005**|O computador cliente está desativado.|Aguarde algumas horas, remova do computador as versões mais antigas do software cliente e tente instalar novamente o software cliente. Para obter instruções, consulte **O que fazer se o cliente não puder ser desinstalado do console do administrador do Microsoft Intune**, acima.|
|**0x80043006**|O número máximo de estações permitidas para a conta foi atingido.|Sua organização deve adquirir estações adicionais para poder inscrever mais computadores clientes no serviço.|
|**0x80043007**|Não foi possível localizar o arquivo de certificado na mesma pasta do programa de instalação.|Extrai todos os arquivos antes de iniciar a instalação. Não renomeie ou relocalize os arquivos extraídos: todos os arquivos devem existir na mesma pasta ou a instalação falhará. Para obter mais informações, confira [Install the Windows PC client with Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune) (Instalar o cliente do computador Windows com o Microsoft Intune).|
|**0x8024D015**, **0x00240005**, **0x80070BC2**, **0x80070BC9**, **0x80CFD015**|O software não pode ser instalado porque uma reinicialização do computador cliente está pendente.|Reinicie o computador e tente instalar novamente o software cliente.|
|**0x80070032**|Um ou mais pré-requisitos de instalação do software cliente não foram encontrados no computador cliente.|Verifique se todas as atualizações necessárias estão instaladas no computador cliente e tente instalar novamente o software cliente. Para obter mais informações sobre os pré-requisitos para instalar o software cliente, confira [Network infrastructure requirements for Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune) (Requisitos de infraestrutura de rede do Microsoft Intune).|
|**0x80043008**|Não foi possível iniciar o serviço de atualizações do Microsoft Online Management.|Entre em contato com suporte, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).|
|**0x80043009**|O computador cliente já está inscrito no serviço.|Você deve retirar o computador cliente antes de ser possível registrá-lo novamente no serviço. Para obter instruções, confira [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management) (Desativar dispositivos de gerenciamento do Microsoft Intune).|
|**0x8004300A**|(Estágio 21) Ocorre um erro quando o pacote de registro é implantado no GPO a ser instalado no escopo do usuário e não no escopo do computador. |Verifique se o GPO está direcionado corretamente por meio da GPSI no escopo do computador. Para ver as postagens do fórum sobre esse assunto, consulte [Fórum do TechNet](https://social.technet.microsoft.com/Forums/en-US/bb9fa71c-c132-4954-abb0-70be8acbd925/failed-to-install-windows-intune?forum=microsoftintuneprod).|
|**0x8004300B**|O pacote de instalação do software cliente não pode ser executado porque a versão do Windows que está em execução no cliente não é suportada.|O Intune não dá suporte à versão do Windows em execução no computador cliente. Para obter uma lista dos sistemas operacionais com suporte, confira [Network infrastructure requirements for Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune) (Requisitos de infraestrutura de rede do Microsoft Intune).|
|**0xAB2**|O Windows Installer não pode acessar o tempo de uma ação personalizada de execução do VBScript.|Este erro é causado por uma ação personalizada que se baseia em bibliotecas de vínculo dinâmico (DLLs). Ao solucionar problemas de DLL, pode ser necessário usar as ferramentas descritas em [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](http://go.microsoft.com/fwlink/?LinkID=234255) (Suporte da Microsoft KB198038: Ferramentas úteis para problemas de implantação e pacote).|
|**0x8004300f**|O software não pode ser instalado porque o cliente do System Center Configuration Manager já está instalado.|Remova o cliente do Configuration Manager e tente novamente a instalação do software cliente.|
|**0x80043010**|O software não pode ser instalado porque o cliente Open Mobile Alliance Device Management (OMADM) já está instalado.|Cancele registro do cliente OMADM e, em seguida, tente novamente a instalação do software cliente.|
Se os problemas de instalação persistirem, entre em contato com o suporte, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune). Tenha em mãos o log de registro do computador cliente (localizado em %*programfiles*%\Microsoft\OnlineManagement\Logs\Enrollment.log e %*userprofile*%\AppData\Local\Microsoft\OnlineManagement\Logs\Enrollement.log) e log do Windows Update (%*windir*%\windowsupdate.log) disponíveis para mostrar aos engenheiros de suporte.

## <a name="what-to-do-if-endpoint-protection-is-not-uninstalled-when-you-uninstall-the-client"></a>O que fazer se o Endpoint Protection não estiver desinstalado durante a desinstalação do cliente

Às vezes, o agente de Proteção do Host (Endpoint Protection) pode ser deixado após a execução dos comandos acima. Se isso acontecer, execute este comando em um prompt com privilégios elevados:

    ```
    "C:\Program Files\Managed Defender\Setup.exe" /x /q /s
    ```


### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).

