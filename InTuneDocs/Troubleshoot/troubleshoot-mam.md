---
title: "Solucionar problemas do gerenciamento de aplicativos móveis | Microsoft Docs"
description: "Este tópico descreve algumas dicas de solução de problemas para implantações de acesso condicional."
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>Solucionar problemas do gerenciamento de aplicativos móveis

Se você tiver problemas com o gerenciamento de aplicativos móveis do Intune, comece por aqui. Este tópico contém alguns problemas comuns e dúvidas que você pode ter e oferece soluções e respostas.

## <a name="common-it-administrator-issues"></a>Problemas comuns do administrador de TI

1. **Problema:** a política de proteção do aplicativo sem registro no dispositivo, feita no Portal do Azure, não está sendo aplicada ao aplicativo do Skype for Business em dispositivos iOS e Android.

  **Resolução**: o Skype for Business deve ser configurado para autenticação moderna.  Siga as instruções em [Habilitar o locatário para autenticação moderna](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) para configurar a autenticação moderna para o Skype.

2. **Problema:** as políticas de proteção do aplicativo não estão sendo aplicadas aos [aplicativos do Office com suporte](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) para nenhum usuário.

  **Resolução**: confirme se o usuário está licenciado para o Intune e se os aplicativos do Office são destino de uma política de proteção de aplicativo implantado. A aplicação de uma política de proteção de aplicativo implantada recentemente pode levar até 8 horas.

3. **Problema:** o usuário do administrador de TI não consegue configurar políticas de proteção de aplicativo no Portal do Azure.

  **Resolução**:

  As funções de usuário a seguir têm acesso ao Portal do Azure:

  - Administrador global, que pode ser configurada no [Portal do Office](http://portal.office.com/)
  - Proprietário, que pode ser configurada no [Portal do Azure](https://portal.azure.com/).
  - Colaborador, que pode ser configurada no [Portal do Azure](https://portal.azure.com/).<br>

  Consulte [Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) para obter ajuda para configurar essas funções.

4. **Problema:** os relatórios do console de administração não mostram a(s) conta(s) de usuário à(s) qual(is) a política de proteção de aplicativo foi implantada recentemente.

  **Resolução**: se uma política de proteção de aplicativo tiver sido destinada a um usuário recentemente, poderá levar até 24 horas para que esse usuário apareça nos relatórios como um usuário de destino.

5. **Problema:** alterações/atualizações de política podem levar até 8 horas para serem aplicadas.  

  **Resolução**: o usuário final pode fazer logoff do aplicativo e fazer logon novamente para forçar a sincronização com o serviço.  

6. **Problema:** a política de proteção de aplicativo não está sendo aplicada a dispositivos do DEP da Apple.

  **Resolução**: verifique se você está usando a Afinidade de Usuário com o Programa de Registro de Dispositivo (DEP) da Apple. A afinidade de usuário é necessária para qualquer aplicativo que exigir a autenticação do usuário no DEP.
Consulte [Registrar dispositivos iOS de propriedade corporativa usando o DEP](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md) para obter mais informações sobre o registro de dispositivos iOS com o DEP.

## <a name="common-end-user-issues"></a>Problemas comuns do usuário final

### <a name="issues-on-ios"></a>Problemas no iOS

Mensagem de erro/caixa de diálogo | Causa | Remediação |
-- | --- | --- |
**Aplicativo Não Configurado**: este aplicativo não foi configurado para uso. Entre em contato com seu administrador de TI para obter ajuda. | Falha ao detectar a política de proteção de aplicativo necessária para o aplicativo. |Verifique se uma política de proteção de aplicativo iOS está implantada no grupo de segurança do usuário e se ela se destina a esse aplicativo.
**Bem-vindo ao Intune Managed Browser**: este aplicativo funciona melhor quando gerenciado pelo Microsoft Intune. Sempre é possível usar esse aplicativo para navegar na Web e, quando ele é gerenciado pelo Microsoft Intune, você obtém acesso a recursos adicionais de proteção de dados. | Falha ao detectar a política de proteção de aplicativo necessária para o aplicativo do Intune Managed Browser. <br><br>O usuário ainda pode usar o aplicativo para navegar na Web, mas ele não é gerenciado pelo Intune. | Verifique se uma política de proteção de aplicativo iOS está implantada no grupo de segurança do usuário e se ela se destina ao aplicativo do Intune Managed Browser.
**Falha ao Entrar**: não é possível entrar neste momento. Tente novamente mais tarde. | Falha ao registrar o usuário com o serviço de MAM depois que o usuário tenta entrar com a conta corporativa ou de estudante. | Verifique se uma política de proteção de aplicativo iOS está implantada no grupo de segurança do usuário e se ela se destina a esse aplicativo.
**Conta Não Configurada**: a organização não configurou sua conta para acessar dados corporativos ou de estudante. Entre em contato com o administrador de TI para obter ajuda. | A conta de usuário não tem uma licença do Intune A Direct. | Verifique se a conta do usuário tem uma licença do Intune atribuída no [Portal do Office](http://portal.office.com).
**Dispositivo Não Compatível**: este aplicativo não pode ser utilizado porque você está usando um dispositivo com jailbreak. Entre em contato com seu administrador de TI para obter ajuda. | Intune detectou que o usuário está em um dispositivo com jailbreak. | Redefina o dispositivo para as configurações padrão de fábrica. Siga [estas instruções](https://support.apple.com/en-us/HT201274) do site de suporte da Apple.
**Conexão à Internet Necessária**: é necessário estar conectado à Internet para verificar se você pode usar este aplicativo. | Este dispositivo não está conectado à Internet. | Conecte o dispositivo a uma rede WiFi ou de Dados.
**Falha Desconhecida**: tente reiniciar o aplicativo. Se o problema persistir, entre em contato com o administrador de TI para obter ajuda. | Ocorreu uma falha desconhecida. | Aguarde um momento e tente novamente. Se o erro persistir, crie um tíquete de suporte com o Intune [aqui](/how-to-get-support-for-microsoft-intune.md).
**Acessando os Dados da Organização**: a conta corporativa ou de estudante especificada não tem acesso a este aplicativo. Você terá que entrar com uma conta diferente. Entre em contato com seu administrador de TI para obter ajuda. | O Intune detecta que o usuário tentou entrar com uma segunda conta corporativa ou de estudante, diferente da conta registrada no MAM para o dispositivo. Somente uma conta corporativa ou de estudante pode ser gerenciada pelo MAM de cada vez por dispositivo. | Solicite ao usuário que entre com a conta cujo nome de usuário é previamente preenchido pela tela de credenciais. <br> <br> Ou solicite que o usuário entre com a nova conta corporativa ou de estudante e remova a conta existente registrada no MAM.
**Problema de Conexão**: ocorreu um problema de conexão inesperado. Verifique a conexão e tente novamente.  |  Falha inesperada. | Aguarde um momento e tente novamente. Se o erro persistir, crie um tíquete de suporte com o Intune [aqui](/how-to-get-support-for-microsoft-intune.md).
**Alerta**: este aplicativo não pode mais ser usado. Para obter mais informações, entre em contato com o administrador de TI. | Falha ao validar o certificado do aplicativo. | Verifique se a versão do aplicativo está atualizada. <br><br> Reinstale o aplicativo.
**Erro**: este aplicativo encontrou um problema e precisa ser fechado. Se o erro persistir, entre em contato com o administrador de TI. | Falha ao ler o PIN do aplicativo MAM do conjunto de chaves do iOS da Apple. | Reinicie o dispositivo. Verifique se a versão do aplicativo está atualizada. <br><br> Reinstale o aplicativo.


### <a name="issues-on-android"></a>Problemas no Android

Mensagem de erro/caixa de diálogo | Causa | Remediação |
-- | --- | --- |
**Aplicativo não configurado**: este aplicativo não foi configurado para uso. Entre em contato com seu administrador de TI para obter ajuda. | Falha ao detectar a política de proteção de aplicativo necessária para o aplicativo. |Verifique se uma política de proteção de aplicativo iOS está implantada no grupo de segurança do usuário e se ela se destina a esse aplicativo.
**Falha na Inicialização do Aplicativo**: houve um problema ao iniciar o aplicativo. Tente atualizar o aplicativo ou o aplicativo do Portal da Empresa do Intune. Se você precisar de Ajuda, entre em contato com o administrador de TI. | O Intune detectou a política de proteção de aplicativo válida para o aplicativo, mas ele está falhando durante a inicialização do MAM. | Verifique se a versão do aplicativo está atualizada. <br><br> Verifique se o aplicativo do Portal da Empresa do Intune está instalado e atualizado no dispositivo. <br><br> Se o erro persistir, use o aplicativo do Portal da Empresa para enviar logs ao Intune ou criar um tíquete de suporte [aqui](/how-to-get-support-for-microsoft-intune.md).
**Nenhum Aplicativo Encontrado**: não há nenhum aplicativo com permissão da organização para abrir este conteúdo neste dispositivo. Entre em contato com seu administrador de TI para obter ajuda. | O usuário tentou abrir dados corporativos ou de estudante com outro aplicativo, mas o Intune não consegue encontrar outros aplicativos gerenciados que têm permissão para abrir os dados. | Verifique se uma política de proteção de aplicativo Android está implantada para a segurança do usuário e se ela se destina a pelo menos um outro aplicativo habilitado para MAM com permissão para abrir os dados em questão.
**Falha ao entrar**: tente entrar novamente. Se o problema persistir, entre em contato com o administrador de TI para obter ajuda. | Falha ao autenticar a conta com a qual o usuário tentou entrar. | Certifique-se de que o usuário entre com a conta corporativa ou de estudante registrada com o serviço de MAM do Intune (a primeira conta corporativa ou de estudante a entrar com êxito no aplicativo). <br><br> Limpe os dados do aplicativo. <br><br> Verifique se a versão do aplicativo está atualizada. <br><br> Verifique se a versão do Portal da Empresa está atualizada.
**Conexão à Internet necessária**: é necessário estar conectado à Internet para verificar se você pode usar este aplicativo. | Este dispositivo não está conectado à Internet. | Conecte o dispositivo a uma rede WiFi ou de Dados.
**Dispositivo Não Compatível**: este aplicativo não pode ser utilizado porque você está usando um dispositivo com raiz. Entre em contato com seu administrador de TI para obter ajuda. | O Intune detectou que o usuário está usando um dispositivo com raiz. | Redefina o dispositivo para as configurações padrão de fábrica.
**Conta Não Configurada**: o aplicativo deve ser gerenciado pelo Microsoft Intune, mas sua conta não foi configurada. Entre em contato com seu administrador de TI para obter ajuda. | A conta de usuário não tem uma licença do Intune A Direct. | Verifique se a conta do usuário tem uma licença do Intune atribuída no [Portal do Office](http://portal.office.com).
**Não é possível registrar o aplicativo**: o aplicativo deve ser gerenciado pelo Microsoft Intune, mas não foi possível registrá-lo agora. Entre em contato com seu administrador de TI para obter ajuda. | Falha ao registrar automaticamente o aplicativo com o serviço MAM quando a política de proteção de aplicativo é solicitada. | Limpe os dados do aplicativo. <br><br> Envie os logs ao Intune por meio do aplicativo do Portal da Empresa ou emita um tíquete de suporte [aqui](/how-to-get-support-for-microsoft-intune.md).





### <a name="see-also"></a>Consulte também
- [Validar a configuração do gerenciamento de aplicativo móvel](../deploy-use/validate-mobile-application-management.md)
- [Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


