---
title: "Visão geral do SDK do Aplicativo do Microsoft Intune | Microsoft Docs"
description: "O SDK do Intune App está disponível para as plataformas Android e iOS, e habilita os recursos de gerenciamento de aplicativos móveis com o Microsoft Intune."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f46f13e9dbf03fa2b3e2ec7339cad927ea0b38e0
ms.openlocfilehash: 99f3aa3c8640dd41133584b3e1cb056dfd493efa


---

# <a name="overview-of-the-microsoft-intune-app-sdk"></a>Visão geral do SDK de Aplicativos do Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O SDK do Intune App está disponível para as plataformas Android e iOS, e habilita os recursos de gerenciamento de aplicativos móveis com o Microsoft Intune. Além disso, ele busca sempre reduzir a quantidade de alterações de código que o desenvolvedor tem que fazer.

Você descobrirá que é possível habilitar a maioria dos recursos do SDK sem alterar o comportamento do seu aplicativo. Para o usuário final avançado e a experiência do administrador de TI, você pode usar nossas APIs para personalizar o comportamento do seu aplicativo para recursos que exigem a participação do seu aplicativo.

Depois de habilitar seu aplicativo, os administradores de TI podem implantar políticas para aplicativos gerenciados pelo Intune e aproveitar esses recursos para proteger seus dados corporativos.

## <a name="features"></a>Recursos
### <a name="control-users-ability-to-move-corporate-documents"></a>Controlar a capacidade dos usuários de mover documentos corporativos
Os administradores de TI podem controlar a realocação de arquivos de documentos corporativos em aplicativos gerenciados pelo Intune. Por exemplo, eles podem implantar uma política que desabilita que aplicativos de backup de arquivo realizem backup de dados corporativos para a nuvem.  

### <a name="configure-clipboard-restrictions"></a>Configurar restrições da área de transferência
Os administradores de TI podem configurar o comportamento da área de transferência em aplicativos gerenciados pelo Intune. Por exemplo, eles podem implantar uma política para que os usuários finais não usem a área de transferência para recortar ou copiar de um aplicativo gerenciado pelo Intune e colem em um aplicativo não gerenciado.

### <a name="enforce-encryption-on-saved-data"></a>Impor criptografia em dados salvos
Os administradores de TI podem impor uma política que garante que os dados sejam salvos no dispositivo pelo aplicativo sejam criptografados.

### <a name="remotely-wipe-corporate-data"></a>Apagar dados corporativos remotamente
Os administradores de TI podem apagar remotamente dados corporativos de um aplicativo gerenciado pelo Intune quando o registro do dispositivo é cancelado no Microsoft Intune. Esse recurso é baseado em identidade e apenas excluirá os arquivos relacionados à identidade corporativa do usuário final. Para fazer isso, o recurso requer a participação do aplicativo. O aplicativo pode especificar a identidade para o qual o apagamento deve ocorrer com base nas configurações do usuário. Na ausência dessas configurações de usuário especificadas no aplicativo, o comportamento padrão é apagar o diretório do aplicativo e notificar o usuário final que o acesso aos recursos da empresa foi removido.

### <a name="enforce-the-use-of-a-managed-browser"></a>Impor o uso de um navegador gerenciado
Os administradores de TI podem impor o uso de um navegador gerenciado quando os usuários abrem links em aplicativos gerenciados pelo Intune. Quando os usuários finais usam o navegador gerenciado pelo Microsoft Intune, ele ajuda a garantir que os links que aparecem nos emails em um cliente de email gerenciado pelo Intune sejam mantidos dentro do domínio dos aplicativos gerenciados pelo Intune.

### <a name="enforce-a-pin-policy"></a>Impor uma política PIN
Os administradores de TI podem impor uma política PIN quando um aplicativo gerenciado pelo Intune é iniciado. Essa política ajuda a garantir que os usuários finais que registraram seus dispositivos com o Microsoft Intune são as mesmas pessoas que estão abrindo os aplicativos. Quando os usuários finais configuram seus PINs, o SDK de Aplicativo do Intune usa o Azure Active Directory para verificar as credenciais deles em relação às credenciais de registro do dispositivo.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Os usuários devem inserir credenciais para poderem abrir os aplicativos
Os administradores de TI podem exigir que os usuários finais digitem suas credenciais para poderem abrir um aplicativo gerenciado pelo Intune. O SDK de aplicativo do Intune usa o Azure Active Directory para fornecer uma experiência de logon único. Isso significa que as credenciais, uma vez inseridas, são reutilizadas para entradas subsequentes. O SDK também dá suporte à autenticação de soluções de gerenciamento de identidade [federadas com o Azure Active Directory](/active-directory/active-directory-aadconnect-federation-compatibility).

### <a name="check-device-health-and-compliance"></a>Verificar a integridade e conformidade do dispositivo
Os administradores de TI podem realizar a verificação de integridade do dispositivo e sua conformidade com políticas corporativas antes que os usuários finais possam acessar aplicativos gerenciados pelo Intune. Na plataforma iOS, esta política verifica se o dispositivo foi desbloqueado com jailbreak. Na plataforma Android, esta política verifica se o dispositivo apresenta raiz.  



<!--HONumber=Dec16_HO3-->


