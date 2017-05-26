---
title: "Benefícios do SDK de Aplicativo do Intune | Microsoft Docs"
description: "O SDK do Intune App está disponível para as plataformas Android e iOS, e habilita os recursos de gerenciamento de aplicativos móveis com o Microsoft Intune."
keywords: 
author: mtillman
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a2e43444bff3b189c1516c6ca7131771035313ea
ms.openlocfilehash: a967758387e9904eb9ce794b3783e777322c83a7


---

# <a name="intune-app-sdk-overview"></a>Visão geral do SDK do Aplicativo do Intune
O SDK do Aplicativo do Intune, disponível para iOS e Android, habilita o aplicativo para as políticas de proteção do aplicativo do Intune. Ele se esforça para minimizar a quantidade de alterações de código necessárias do desenvolvedor do aplicativo. Você descobrirá que é possível habilitar a maioria dos recursos do SDK sem alterar o comportamento do seu aplicativo. Para o usuário final avançado e a experiência do administrador de TI, você pode usar nossas APIs para personalizar o comportamento do seu aplicativo para recursos que exigem a participação do seu aplicativo.

Depois de habilitar seu aplicativo para políticas de proteção do aplicativo, os administradores de TI poderão implantar essas políticas para proteger seus dados corporativos no aplicativo.

## <a name="app-protection-features"></a>Recursos de proteção do aplicativo

Veja a seguir exemplos de recursos de proteção do aplicativo do Intune que podem ser habilitados com o SDK.

### <a name="control-users-ability-to-move-corporate-files"></a>Controlar a capacidade dos usuários de mover arquivos corporativos
Os administradores de TI podem controlar o local para o qual podem ser movidos os dados corporativos ou de estudante no aplicativo. Por exemplo, eles podem implantar uma política que desabilita o backup de dados corporativos pelo aplicativo na nuvem.

### <a name="configure-clipboard-restrictions"></a>Configurar restrições da área de transferência
Os administradores de TI podem configurar o comportamento da área de transferência em aplicativos gerenciados pelo Intune. Por exemplo, eles podem implantar uma política para impedir o recorte ou a cópia de dados do aplicativo pelos usuários finais e a colagem em um aplicativo pessoal não gerenciado.

### <a name="enforce-encryption-on-saved-data"></a>Impor criptografia em dados salvos
Os administradores de TI podem impor uma política que garante que os dados salvos no dispositivo pelo aplicativo sejam criptografados.

### <a name="remotely-wipe-corporate-data"></a>Apagar dados corporativos remotamente
Os administradores de TI podem apagar remotamente dados corporativos de um aplicativo gerenciado pelo Intune. Esse recurso é baseado em identidade e excluirá apenas os arquivos relacionados à identidade corporativa do usuário final. Para fazer isso, o recurso requer a participação do aplicativo. O aplicativo pode especificar a identidade para o qual o apagamento deve ocorrer com base nas configurações do usuário. Na ausência dessas configurações de usuário especificadas no aplicativo, o comportamento padrão é apagar o diretório do aplicativo e notificar o usuário final que o acesso foi removido.

### <a name="enforce-the-use-of-a-managed-browser"></a>Impor o uso de um navegador gerenciado
Os administradores de TI podem forçar a abertura dos links da Web no aplicativo com o [aplicativo Intune Managed Browser](../deploy-use/manage-internet-access-using-managed-browser-policies.md). Isso garante que os links que aparecem em um ambiente corporativo serão mantidos dentro do domínio de aplicativos gerenciados pelo Intune.

### <a name="enforce-a-pin-policy"></a>Impor uma política PIN
Os administradores de TI podem exigir que o usuário final insira um PIN antes de acessar dados corporativos no aplicativo. Isso garante que a pessoa que usa o aplicativo é a mesma pessoa que se conectou inicialmente com sua conta corporativa ou de estudante. Quando os usuários finais configuram seus PINs, o SDK do Aplicativo do Intune usa o Azure Active Directory para verificar as credenciais de usuários finais em relação à conta do Intune registrada.

### <a name="require-users-to-sign-in-with-work-or-school-account-for-app-access"></a>Exigir que os usuários se conectem com a conta corporativa ou de estudante para acesso ao aplicativo
Os administradores de TI podem exigir que os usuários se conectem com sua conta corporativa ou de estudante para acessar o aplicativo. O SDK do Aplicativo do Intune usa o Azure Active Directory para fornecer uma experiência de logon único, em que as credenciais, uma vez inseridas, são reutilizadas para os próximos logons. Também damos suporte à autenticação de soluções de gerenciamento de identidade federadas com o Azure Active Directory.

### <a name="check-device-health-and-compliance"></a>Verificar a integridade e conformidade do dispositivo
Os administradores de TI podem verificar a integridade do dispositivo e sua conformidade com as políticas do Intune antes que os usuários finais acessem o aplicativo. No iOS, essa política verifica se o dispositivo foi desbloqueado com jailbreak. No Android, essa política verifica se o dispositivo foi desbloqueado com root.

### <a name="multi-identity-support"></a>Suporte a várias identidades
O suporte a várias identidades é um recurso do SDK que habilita a coexistência de contas gerenciadas por política (corporativas) e não gerenciadas (pessoais) em um único aplicativo.

Por exemplo, muitos usuários configuram as contas de email pessoal e corporativa nos aplicativos móveis do Office para iOS e Android. Quando um usuário acessa dados com sua conta corporativa, o administrador de TI deve ter certeza de que a política de proteção do aplicativo será aplicada. No entanto, quando um usuário está acessando uma conta de email pessoal, esses dados devem ficar fora do controle do administrador de TI. O SDK do Aplicativo do Intune consegue isso direcionando a política de proteção do aplicativo **somente** à identidade corporativa no aplicativo.

O recurso de várias identidades ajuda a resolver o problema de proteção de dados que as organizações enfrentam com aplicativos de loja que dão suporte a contas pessoais e corporativas.


### <a name="app-protection-without-device-enrollment"></a>Proteção do aplicativo sem registro de dispositivo

>[!IMPORTANT]
>A proteção do aplicativo do Intune sem registro de dispositivo ainda não está disponível no SDK do Aplicativo do Intune para Android. Ela está disponível nas Ferramentas de Disposição do Aplicativo do Intune, no SDK para iOS, Componente do Xamarin no SDK e Plug-in do Cordova no SDK.


Muitos usuários com dispositivos pessoais desejam acessar dados corporativos sem registrar seus dispositivos pessoais em um provedor de MDM (gerenciamento de dispositivo móvel). Como o registro de MDM exige o controle global do dispositivo, os usuários costumam hesitar em fornecer o controle de seus dispositivos pessoais à empresa.

A proteção do aplicativo sem registro de dispositivo permite que o serviço Microsoft Intune implante a política de proteção do aplicativo em um aplicativo diretamente, sem depender de um canal de gerenciamento de dispositivo para implantá-la.



<!--HONumber=Dec16_HO5-->

