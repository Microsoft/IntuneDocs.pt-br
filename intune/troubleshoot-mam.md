---
title: Solucionar problemas do gerenciamento de aplicativos móveis
titleSuffix: Microsoft Intune
description: Este tópico descreve algumas dicas de solução de problemas para implantações de Acesso Condicional.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bde64e9bbe756b61b41dd8e7d55ba327491ae55b
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67046230"
---
# <a name="troubleshoot-mobile-application-management"></a>Solucionar problemas do gerenciamento de aplicativos móveis

Este tópico fornece soluções para problemas comuns que ocorreram ao usar o gerenciamento de aplicativos móveis do Intune.

Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](get-support.md) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.

## <a name="common-it-administrator-issues"></a>Problemas comuns do administrador de TI

Esses são problemas comuns que um administrador de TI pode enfrentar ao usar a política de proteção de aplicativos do Intune.

| Problema | Descrição | Resolução |
| -- | -- | -- |
| A política não é aplicada ao Skype for Business | A política de proteção do aplicativo sem registro de dispositivo, feita no Portal do Azure, não está sendo aplicada ao aplicativo Skype for Business em dispositivos iOS e Android. | O Skype for Business deve ser configurado para a autenticação moderna.  Siga as instruções em [Habilitar o locatário para autenticação moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) para configurar a autenticação moderna para o Skype. |
| Política de aplicativos do Office não aplicada | As políticas de proteção do aplicativo não estão sendo aplicadas aos [aplicativos do Office com suporte](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) de nenhum usuário. | Confirme se o usuário está licenciado para o Intune e se os aplicativos do Office são afetados por uma política de proteção do aplicativo implantada. A aplicação de uma política de proteção de aplicativo implantada recentemente pode levar até 8 horas. |
| O administrador não pode configurar a política de proteção do aplicativo no Portal do Azure | O usuário administrador de TI não consegue configurar políticas de proteção do aplicativo no Portal do Azure. | As funções de usuário a seguir têm acesso ao Portal do Azure: <ul><li>Administrador global, que pode ser configurada no [Centro de administração do Microsoft 365](https://admin.microsoft.com/)</li><li>Proprietário, que pode ser configurada no [Portal do Azure](https://portal.azure.com/).</li><li>Colaborador, que pode ser configurada no [Portal do Azure](https://portal.azure.com/).</li></ul> Para obter ajuda sobre como configurar essas funções, confira [RBAC (controle de administração baseado em funções) com o Microsoft Intune](role-based-access-control.md).|
|Contas de usuário ausentes dos relatórios da política de proteção do aplicativo | Os relatórios do console do administração não mostram as contas de usuário nas quais a política de proteção do aplicativo foi implantada recentemente. | Se uma política de proteção do aplicativo for destinada a um usuário recentemente, poderá levar até 24 horas para que esse usuário seja mostrado nos relatórios como um usuário de destino. |
| As alterações da política não funcionam | As alterações e atualizações da política de proteção do aplicativo podem levar até 8 horas para serem aplicadas. | Se aplicável, o usuário final poderá fazer logoff do aplicativo e fazer logon novamente para forçar a sincronização com o serviço. |
| A política de proteção do aplicativo não funciona com o DEP | A política de proteção do aplicativo não está sendo aplicada a dispositivos Apple DEP. | Garanta que você está usando a Afinidade de Usuário com o Apple DEP (Programa de Registro de Dispositivos). A afinidade de usuário é necessária para qualquer aplicativo que exigir a autenticação do usuário no DEP. <br><br>Para saber mais sobre o registro de DEP do iOS, confira [Registrar automaticamente dispositivos iOS com o Programa de registro de dispositivos da Apple](device-enrollment-program-enroll-ios.md).|
| A política de transferência de dados não funciona com o iOS | As políticas **Permitir que o aplicativo transfira dados para outros aplicativos** e **Permitir que o aplicativo receba dados de outros aplicativos** não gerenciam a transferência de dados no iOS com êxito. | Confira [Como gerenciar a transferência de dados entre aplicativos iOS no Microsoft Intune](data-transfer-between-apps-manage-ios.md). |

## <a name="common-end-user-issues"></a>Problemas comuns do usuário final

Os problemas comuns do usuário final são divididos nas seguintes categorias:

* **Cenários de uso normal**: um usuário final pode observar esses cenários em aplicativos que têm uma política de Proteção de Aplicativo do Intune. Esses não são problemas reais, mas podem ser considerados como bugs ou erros.

* **Caixas de diálogo de uso normal**: são caixas de diálogo de uso que um usuário final poderá ver em aplicativos que têm uma política de Proteção de Aplicativo do Intune. Essas mensagens e caixas de diálogo **não** indicam um erro nem um bug.

* **Mensagens e caixas de diálogo de erro**: são mensagens e caixas de diálogo de erro que um usuário final poderá ver em aplicativos que têm uma política de Proteção de Aplicativo do Intune. Em geral, elas indicam um erro do administrador de TI ou um bug na proteção do aplicativo do Intune.

### <a name="normal-usage-scenarios"></a>Cenários de uso normal

Plataforma | Cenário | Explicação |
---| --- | --- |
iOS | O usuário final pode usar a extensão de compartilhamento do iOS para abrir dados corporativos ou de estudante em aplicativos não gerenciados, mesmo com a política de transferência de dados definida como **Apenas aplicativos gerenciados** ou **Nenhum aplicativo.** Isso não causa a perda de dados? | A política de proteção do aplicativo do Intune não pode controlar a extensão de compartilhamento do iOS sem gerenciar o dispositivo. Portanto, o **Intune criptografa os dados “corporativos” antes de compartilhá-los fora do aplicativo**. É possível validar isso ao tentar abrir o arquivo “corporativo” fora do aplicativo gerenciado. O arquivo deve ser criptografado e não pode ser aberto fora do aplicativo gerenciado.
Android | Por que o usuário final **precisa instalar o aplicativo Portal da Empresa** mesmo ao usar a proteção do aplicativo de MAM sem registro de dispositivo?  | No Android, grande parte da funcionalidade de proteção do aplicativo é criada no aplicativo Portal da Empresa. **O registro de dispositivo não é necessário, embora o aplicativo Portal da Empresa seja sempre obrigatório**. Para a proteção do aplicativo sem registro, o usuário final precisa apenas ter o aplicativo Portal da Empresa instalado no dispositivo.

### <a name="normal-usage-dialogs"></a>Caixas de diálogo de uso normal

Plataforma | Mensagem ou caixa de diálogo | Explicação |
--- | --- | --- |
iOS, Android | **Conexão**: para proteger os dados, sua organização precisa gerenciar esse aplicativo. Para concluir essa ação, entre com sua conta corporativa ou de estudante. | O usuário final deverá se conectar com sua conta corporativa ou de estudante para usar esse aplicativo, o que exige uma política de proteção do aplicativo. Para aplicar a política, o usuário deve se autenticar no Azure Active Directory.
iOS, Android |**Reinicialização Necessária**: sua organização agora está protegendo os dados nesse aplicativo. É necessário reiniciar o aplicativo para continuar. | O aplicativo acabou de receber uma política de proteção do aplicativo do Intune e deve ser reiniciado para que ela seja aplicada.
iOS, Android |**Ação Não Permitida**: sua organização permite apenas que você abra dados corporativos ou de estudante nesse aplicativo. | O administrador de TI definiu a opção **Permitir que o aplicativo receba dados de outros aplicativos** como **Apenas aplicativos gerenciados**. Portanto, o usuário final pode apenas transferir dados para esse aplicativo de outros aplicativos que têm uma política de proteção do aplicativo.
iOS, Android |**Ação Não Permitida**: sua organização permite apenas que você transfira os dados para outros aplicativos gerenciados. | O administrador de TI definiu a política **Permitir que o aplicativo transfira dados para outros aplicativos** como **Apenas aplicativos gerenciados**. Portanto, o usuário final pode apenas transferir dados desse aplicativo para outros aplicativos que têm uma política de proteção do aplicativo.
iOS, Android |**Apagar Alerta**: sua organização removeu os dados associados a esse aplicativo. Para continuar, reinicie o aplicativo. | O administrador de TI iniciou um apagamento do aplicativo usando a proteção do aplicativo do Intune.
Android | **Portal da Empresa necessário**: para usar sua conta corporativa ou de estudante com esse aplicativo, é necessário instalar o aplicativo Portal da Empresa do Intune. Clique em “Ir para a loja” para continuar. | No Android, grande parte da funcionalidade de proteção do aplicativo é criada no aplicativo Portal da Empresa. **O registro de dispositivo não é necessário, embora o aplicativo Portal da Empresa seja sempre obrigatório**. Para a proteção do aplicativo sem registro, o usuário final precisa apenas ter o aplicativo Portal da Empresa instalado no dispositivo.

### <a name="error-messages-and-dialogs-on-ios"></a>Mensagens de erro e caixas de diálogo no iOS

Mensagem de erro ou caixa de diálogo | Causa | Remediação |
-- | --- | --- |
**Aplicativo Não Configurado**: este aplicativo não foi configurado para uso. Entre em contato com seu administrador de TI para obter ajuda. | Falha ao detectar uma política de proteção de aplicativo necessária para o aplicativo. |Verifique se uma política de proteção de aplicativo iOS está implantada no grupo de segurança do usuário e se ela se destina a esse aplicativo.
**Bem-vindo ao Intune Managed Browser**: este aplicativo funciona melhor quando gerenciado pelo Microsoft Intune. Sempre é possível usar esse aplicativo para navegar na Web e, quando ele é gerenciado pelo Microsoft Intune, você obtém acesso a recursos adicionais de proteção de dados. | Falha ao detectar uma política de proteção de aplicativo necessária para o aplicativo do Intune Managed Browser. <br><br>O usuário ainda pode usar o aplicativo para navegar na Web, mas ele não é gerenciado pelo Intune. | Verifique se uma política de proteção de aplicativo iOS está implantada no grupo de segurança do usuário e se ela se destina ao aplicativo do Intune Managed Browser.
**Falha ao Entrar**: não é possível entrar neste momento. Tente novamente mais tarde. | Falha ao registrar o usuário com o serviço de MAM depois que o usuário tenta entrar com a conta corporativa ou de estudante. | Verifique se uma política de proteção de aplicativo iOS está implantada no grupo de segurança do usuário e se ela se destina a esse aplicativo.
**Conta Não Configurada**: a organização não configurou sua conta para acessar dados corporativos ou de estudante. Entre em contato com o administrador de TI para obter ajuda. | A conta de usuário não tem uma licença do Intune A Direct. | Verifique se a conta do usuário tem uma licença do Intune atribuída no [Centro de administração do Microsoft 365](https://admin.microsoft.com).
**Dispositivo Não Compatível**: este aplicativo não pode ser utilizado porque você está usando um dispositivo com jailbreak. Entre em contato com seu administrador de TI para obter ajuda. | Intune detectou que o usuário está em um dispositivo com jailbreak. | Redefina o dispositivo para as configurações padrão de fábrica. Siga [estas instruções](https://support.apple.com/HT201274) do site de suporte da Apple.
**Conexão à Internet Necessária**: é necessário estar conectado à Internet para verificar se você pode usar este aplicativo. | Este dispositivo não está conectado à Internet. | Conecte o dispositivo a uma rede WiFi ou de Dados.
**Falha Desconhecida**: tente reiniciar o aplicativo. Se o problema persistir, entre em contato com o administrador de TI para obter ajuda. | Ocorreu uma falha desconhecida. | Aguarde um momento e tente novamente. Se o erro persistir, crie um [tíquete de suporte](get-support.md#create-an-online-support-ticket) com o Intune.
**Acessando os Dados da Organização**: a conta corporativa ou de estudante especificada não tem acesso a este aplicativo. Você terá que entrar com uma conta diferente. Entre em contato com seu administrador de TI para obter ajuda. | O Intune detecta que o usuário tentou entrar com uma segunda conta corporativa ou de estudante, diferente da conta registrada no MAM para o dispositivo. Somente uma conta corporativa ou de estudante pode ser gerenciada pelo MAM de cada vez por dispositivo. | Solicite ao usuário que entre com a conta cujo nome de usuário é previamente preenchido pela tela de credenciais. <br> <br> Ou solicite que o usuário entre com a nova conta corporativa ou de estudante e remova a conta existente registrada no MAM.
**Problema de Conexão**: ocorreu um problema de conexão inesperado. Verifique a conexão e tente novamente.  |  Falha inesperada. | Aguarde um momento e tente novamente. Se o erro persistir, crie um [tíquete de suporte](get-support.md#create-an-online-support-ticket) com o Intune.
**Alerta**: este aplicativo não pode mais ser usado. Para obter mais informações, entre em contato com o administrador de TI. | Falha ao validar o certificado do aplicativo. | Verifique se a versão do aplicativo está atualizada. <br><br> Reinstale o aplicativo.
**Erro**: este aplicativo encontrou um problema e precisa ser fechado. Se o erro persistir, entre em contato com o administrador de TI. | Falha ao ler o PIN do aplicativo MAM do conjunto de chaves do iOS da Apple. | Reinicie o dispositivo. Verifique se a versão do aplicativo está atualizada. <br><br> Reinstale o aplicativo.

### <a name="error-messages-and-dialogs-on-android"></a>Mensagens de erro e caixas de diálogo no Android

Mensagem de erro/caixa de diálogo | Causa | Remediação |
-- | --- | --- |
**Aplicativo não configurado**: este aplicativo não foi configurado para uso. Entre em contato com seu administrador de TI para obter ajuda. | Falha ao detectar uma política de proteção de aplicativo necessária para o aplicativo. |Verifique se uma política de proteção do aplicativo do Android é implantada no grupo de segurança do usuário e se destina a esse aplicativo.
**Falha na Inicialização do Aplicativo**: houve um problema ao iniciar o aplicativo. Tente atualizar o aplicativo ou o aplicativo do Portal da Empresa do Intune. Se você precisar de Ajuda, entre em contato com o administrador de TI. | O Intune detectou a política de proteção de aplicativo válida para o aplicativo, mas ele está falhando durante a inicialização do MAM. | Verifique se a versão do aplicativo está atualizada. <br><br> Verifique se o aplicativo do Portal da Empresa do Intune está instalado e atualizado no dispositivo. <br><br> Se o erro persistir, use o aplicativo do Portal da Empresa para enviar logs ao Intune ou criar um [tíquete de suporte](get-support.md#create-an-online-support-ticket).
**Nenhum Aplicativo Encontrado**: não há nenhum aplicativo com permissão da organização para abrir este conteúdo neste dispositivo. Entre em contato com seu administrador de TI para obter ajuda. | O usuário tentou abrir dados corporativos ou de estudante com outro aplicativo, mas o Intune não consegue encontrar outros aplicativos gerenciados que têm permissão para abrir os dados. | Verifique se uma política de proteção de aplicativo Android está implantada para a segurança do usuário e se ela se destina a pelo menos um outro aplicativo habilitado para MAM com permissão para abrir os dados em questão.
**Falha ao entrar**: tente entrar novamente. Se o problema persistir, entre em contato com o administrador de TI para obter ajuda. | Falha ao autenticar a conta com a qual o usuário tentou entrar. | Certifique-se de que o usuário entre com a conta corporativa ou de estudante registrada com o serviço de MAM do Intune (a primeira conta corporativa ou de estudante a entrar com êxito no aplicativo). <br><br> Limpe os dados do aplicativo. <br><br> Verifique se a versão do aplicativo está atualizada. <br><br> Verifique se a versão do Portal da Empresa está atualizada.
**Conexão à Internet necessária**: é necessário estar conectado à Internet para verificar se você pode usar este aplicativo. | Este dispositivo não está conectado à Internet. | Conecte o dispositivo a uma rede WiFi ou de Dados.
**Dispositivo não compatível**: este aplicativo não pode ser utilizado porque você está usando um dispositivo desbloqueado por rooting. Entre em contato com seu administrador de TI para obter ajuda. | O Intune detectou que o usuário está usando um dispositivo com raiz. | Redefina o dispositivo para as configurações padrão de fábrica.
**Conta Não Configurada**: o aplicativo deve ser gerenciado pelo Microsoft Intune, mas sua conta não foi configurada. Entre em contato com seu administrador de TI para obter ajuda. | A conta de usuário não tem uma licença do Intune A Direct. | Verifique se a conta do usuário tem uma licença do Intune atribuída no [Centro de administração do Microsoft 365](https://admin.microsoft.com).
**Não é possível registrar o aplicativo**: o aplicativo deve ser gerenciado pelo Microsoft Intune, mas não foi possível registrá-lo agora. Entre em contato com seu administrador de TI para obter ajuda. | Falha ao registrar automaticamente o aplicativo com o serviço MAM quando a política de proteção de aplicativo é solicitada. | Limpe os dados do aplicativo. <br><br> Envie os logs ao Intune por meio do aplicativo do Portal da Empresa ou emita um tíquete de suporte. Para obter mais informações, confira [Como obter suporte para o Microsoft Intune](get-support.md).

## <a name="next-steps"></a>Próximas etapas

- [Validar a configuração do gerenciamento de aplicativo móvel](app-protection-policies-validate.md)
- Para saber mais sobre a solução de problemas do Intune, confira [Usar o portal de solução de problemas para ajudar os usuários na empresa](help-desk-operators.md). 
- Saiba mais sobre os problemas conhecidos do Microsoft Intune. Para obter mais informações, consulte [Problemas conhecidos no Microsoft Intune](known-issues.md).
- Precisa de mais ajuda? Veja [Como obter suporte para o Microsoft Intune](get-support.md).
