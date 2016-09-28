---
title: Configurar sua assinatura da Consulta MTP | Microsoft Intune
description: "Este tópico fornece detalhes de como configurar a Consulta MTP."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: 8e2c71127801afc21d52e08d13dd9099b263e801


---

# Configurar sua assinatura para a proteção contra ameaças móveis do Lookout
Para preparar sua assinatura para o serviço da Consulta MTP, o suporte do Lookout (enterprisesupport@lookout.com) precisará das seguintes informações sobre seu Azure AD (Azure Active Directory). 

* ID do locatário do Azure AD
* ID do objeto de grupo do Azure AD para acesso completo ao console da Consulta MTP
* ID do objeto de grupo do Azure AD para acesso restrito ao console do Consulta MTP (opcional)

Use as instruções na seção a seguir para coletar as informações que você precisa fornecer à equipe de suporte do Lookout.  

## Obter as informações do Azure AD
### Obter sua ID do locatário do Azure AD
Faça logon no portal de gerenciamento do Azure AD: https://manage.windowsazure.com e selecione sua assinatura. 

![captura de tela da página do Azure AD mostrando o nome do locatário](../media/mtp/aad_tenant_name.png) Quando você escolhe o nome de sua assinatura, a URL resultante inclui a ID da assinatura.  Se você tiver problemas para localizar sua ID da assinatura, o [artigo do suporte da Microsoft](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) fornece dicas adicionais.   
### Obter sua ID do grupo do Azure AD
O console da Consulta MTP dá suporte a dois níveis de acesso:  
* **Acesso completo:** o administrador do Azure AD pode criar um grupo para usuários que terão Acesso completo e, opcionalmente, pode criar um grupo para usuários que terão Acesso restrito.  Somente os usuários nesses grupos poderão fazer logon no **console da Consulta MTP**.
* **Acesso restrito:** não há acesso a vários módulos relacionados à configuração e ao registro do console da Consulta MTP e há acesso somente leitura ao módulo **Política de Segurança** do console da Consulta MTP.  

Para obter mais detalhes sobre as permissões, leia [este artigo](https://personal.support.lookout.com/hc/en-us/articles/114094105653) no site do Lookout.

A **ID do objeto do grupo** pode ser encontrada na página de propriedades do grupo no console de gerenciamento do Azure AD.

![captura de tela da página de propriedades com o campo GroupID realçado](../media/mtp/aad_group_object_id.png)

Depois de reunir essas informações, contate o suporte do Lookout (email: enterprisesupport@lookout.com).

O suporte do Lookout trabalhará com seu contato principal para integrar sua assinatura e criar a conta da Consulta MTP Enterprise, usando as informações coletadas.


## Configurar sua assinatura com a Consulta MTP
### Etapa 1: Configurar seu MTP
Após o suporte do Lookout criar sua conta da Consulta MTP Enterprise, você poderá fazer logon no console da Consulta MTP.   Um email do Lookout é enviado para o contato principal da sua empresa com um link da URL de logon: https://aad.lookout.com/les?action=consent

Você precisa usar uma conta de usuário com a função de Administrador Global do Azure AD quando fizer logon pela primeira vez no console da Consulta MTP, uma vez que a Consulta MTP exige isso para registrar seu locatário do Azure AD.   Logons posteriores não exigirão que o usuário tenha esse nível de privilégio do Azure AD.  Nesse primeiro logon, será exibida uma página de consentimento. Escolha **aceitar** para concluir o registro.

![captura de tela da primeira página de logon do console da Consulta MTP](../media/mtp/lookout_mtp_initial_login.png) Após aceitar e dar o consentimento, você será redirecionado para o Console da Consulta MTP. Logons posteriores, após o registro inicial, podem ser feitos usando a URL: https://aad.lookout.com

Consulte o [artigo de solução de problemas](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)  se você se deparar com problemas de logon.

As próximas etapas descrevem as tarefas que devem ser realizadas para concluir a configuração da Consulta MTP dentro do [Console da Consulta MTP](https://aad.lookout.com).

### Etapa 2: Configurar o Conector do Intune

No console da Consulta MTP, vá até o módulo **Sistema**, escolha a guia **Conectores** e selecione **Intune**.

![captura de tela do console da Consulta MTP com a guia Conectores aberta e a opção Intune realçada](../media/mtp/lookout_mtp_setup-intune-connector.png)

Na opção de configurações de conexão, configure a frequência de pulsação em minutos.  Com a conclusão dessa etapa, seu conector do Intune agora está pronto.  

![captura de tela da guia Configurações de conexão mostrando a frequência de pulsação configurada](../media/mtp/lookout-mtp-connection-settings.png)

### Etapa 3: Configurar grupos de registro
Na opção **Gerenciamento de Registro**, defina um conjunto de usuários cujos dispositivos devem ser registrados no Lookout.   A melhor prática é começar com um grupo pequeno de usuários para testar e se familiarizar com o funcionamento da integração.  Quando estiver satisfeito com os resultados do teste, você pode estender o registro para grupos de usuários adicionais.

Para começar a usar os grupos de registro, primeiro defina um grupo de segurança do Azure AD que representaria um bom conjunto de usuários para registrar na Consulta MTP. Após ter criado o grupo no Azure AD, no console da Consulta MTP, vá para a opção **Gerenciamento de Registro** e adicione o(s) **Nome(s) de Exibição** do grupo de segurança do Azure AD para registro.

Quando um usuário estiver em um grupo de registro, qualquer um de seus dispositivos que estiver identificado e tiver suporte no Azure AD estará registrado e qualificado para ativação na Consulta MTP.  Na primeira vez que o usuário abrir o aplicativo Lookout for Work em seu dispositivo com suporte, ele será ativado na Consulta MTP.
![captura de tela da página de registro do conector do Intune](../media/mtp/lookout-mtp-enrollment.png)

A melhor prática é deixar o incremento da verificação de novos dispositivos como o padrão de 5 minutos.

>[!IMPORTANT]
> O nome de exibição diferencia maiúsculas de minúsculas.  Use o **Nome de Exibição** conforme exibido na página **Propriedades** do grupo de segurança no portal do Azure. Observe na imagem abaixo que na página **Propriedades** do grupo de segurança, o nome de exibição segue o padrão camelCase.  No entanto, o título é exibido com todas as letras minúsculas e não deve ser usado para entrar no console da Consulta MTP.
>![captura de tela do portal do Azure, serviço do Azure Active Directory, página de propriedades](../media/mtp/aad-group-display-name.png)

A versão atual tem as limitações a seguir:  
* Não há validação para os nomes de exibição do grupo.  Certifique-se de usar o valor no campo **NOME DE EXIBIÇÃO** mostrado no portal do Azure para o grupo de segurança do Azure AD.
* Atualmente, não há suporte para a criação de grupos dentro de grupos.  Os grupos de segurança do Azure AD especificados devem conter apenas usuários, e não grupos aninhados.


### Etapa 4: Configurar a sincronização de estado
Na opção **Sincronização de Estado**, especifique o tipo de dados que deve ser enviado ao Intune.  No momento, você precisa habilitar o status do dispositivo e o status de ameaça para que a integração do Lookout com o Intune funcione corretamente.  Eles são habilitados por padrão.
### Etapa 5: Configurar informações do destinatário do email de relatório de erros
Na opção **Gerenciamento de Erros**, insira o endereço de email que deve receber os relatórios de erros.

![captura de tela da página de gerenciamento de erros do conector do Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

### Etapa 6: Configurar notificações por email
Se quiser receber alertas de ameaças por email, entre no [console da Consulta MTP](https://aad.lookout.com) com a conta de usuário que deve receber as notificações.  Vá até o módulo **Sistema** e, na guia **Preferências**, escolha as notificações desejadas e defina-as como **ATIVADO**. Salve as alterações.

![captura de tela da página Preferências com a conta de usuário exibida](../media/mtp/lookout-mtp-email-notifications.png) Se quiser deixar de receber notificações por email, defina as notificações como **DESATIVADO** e salve as alterações.
### Etapa 7: Configurar a classificação das ameaças
a Consulta MTP classifica ameaças móveis de vários tipos. As [classificações de ameaças da Consulta MTP](http://personal.support.lookout.com/hc/en-us/articles/114094130693) têm níveis de risco padrão associados a elas. Eles podem ser alterados a qualquer momento para se adequar aos requisitos da sua empresa.

![captura de tela da página de política mostrando ameaças e classificações](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Os níveis de risco especificados aqui são um aspecto importante do MTP porque a integração com o Intune calcula a conformidade do dispositivo de acordo com esses níveis de risco no tempo de execução. Em outras palavras, o administrador do Intune define uma regra na política para determinar que um dispositivo não é compatível se ele tiver uma ameaça ativa com um nível mínimo de alto, médio ou baixo. A política de classificação de ameaças no MTP alimenta diretamente o cálculo de conformidade do dispositivo no Intune.

## Verificar o registro
Quando a instalação estiver concluída, a Consulta MTP começará a sondar o Azure AD em busca de dispositivos que correspondem aos grupos de registro especificado.  Informações sobre os dispositivos registrados podem ser encontradas no módulo Dispositivos.  O status inicial dos dispositivos é pendente.  O status do dispositivo será alterado depois que o aplicativo Lookout for Work for instalado, aberto e ativado no dispositivo.  Detalhes de como fazer com que o aplicativo Lookout for Work seja enviado ao dispositivo podem ser encontrados no tópico [Configurar e implantar o aplicativo Lookout for Work](configure-and-deploy-lookout-for-work-apps.md).
## Próximas etapas
[Habilitar a conexão da Consulta MTP com o Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO2-->


