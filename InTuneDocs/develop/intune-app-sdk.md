---
# required metadata

title: Benefícios do SDK de Aplicativo do Intune | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Visão Geral do SDK de Aplicativo do Intune
O SDK do Intune App está disponível para as plataformas Android e iOS, e habilita os recursos de gerenciamento de aplicativos móveis com o Microsoft Intune. Além disso, buscamos sempre reduzir a quantidade de alterações de código necessárias por parte do desenvolvedor. Você descobrirá que é possível habilitar a maioria dos recursos do SDK sem alterar o comportamento do seu aplicativo. Para o usuário final avançado e a experiência do administrador de TI, você pode usar nossas APIs para personalizar o comportamento do seu aplicativo para recursos que exigem a participação do seu aplicativo. 
Depois de habilitar seu aplicativo, os administradores de TI podem implantar políticas para aplicativos gerenciados pelo Intune e aproveitar esses recursos para proteger seus dados corporativos.

## Recursos Comuns

### Controlar a capacidade dos usuários de mover documentos corporativos
Os administradores de TI podem controlar a realocação de arquivos de documentos corporativos em aplicativos gerenciados pelo Intune. Por exemplo, eles podem implantar uma política que desabilita que aplicativos de backup de arquivo realizem backup de dados corporativos para a nuvem.

### Configurar restrições da área de transferência
Os administradores de TI podem configurar o comportamento da área de transferência em aplicativos gerenciados pelo Intune. Por exemplo, eles podem implantar uma política para que os usuários finais não usem a área de transferência para recortar/copiar de um aplicativo gerenciado pelo Intune e colem em um aplicativo não gerenciado.

### Configurar restrições de captura de tela
Os administradores de TI podem impedir que os usuários realizem captura de tela se um aplicativo gerenciado pelo Intune for exibido. Aplicar essa restrição impede a captura e a divulgação do conteúdo corporativo confidencial. Esse recurso só está disponível para dispositivos Android.

### Impor criptografia em dados salvos
Os administradores de TI podem impor uma política que garante que os dados salvos no dispositivo pelo aplicativo sejam criptografados.

### Apagar dados corporativos remotamente
Os administradores de TI podem apagar remotamente dados corporativos de um aplicativo gerenciado pelo Intune quando o registro do dispositivo é cancelado no Microsoft Intune. Esse recurso é baseado em identidade e excluirá apenas os arquivos relacionados à identidade corporativa do usuário final. Para fazer isso, o recurso requer a participação do aplicativo. O aplicativo pode especificar a identidade para o qual o apagamento deve ocorrer com base nas configurações do usuário. Na ausência dessas configurações de usuário especificadas no aplicativo, o comportamento padrão é apagar o diretório do aplicativo e notificar o usuário final que o acesso aos recursos da empresa foi removido.

### Impor o uso de um navegador gerenciado
Os administradores de TI podem impor o uso de um navegador gerenciado ao abrir links em aplicativos gerenciados pelo Intune. Usar o navegador gerenciado pelo Microsoft Intune ajuda a garantir que os links que aparecem nos emails (que estão em um cliente de email gerenciado pelo Intune) sejam mantidos dentro do domínio dos aplicativos gerenciados pelo Intune.

### Impor uma política PIN
Os administradores de TI podem impor uma política PIN quando um aplicativo gerenciado pelo Intune é iniciado. Essa política ajuda a garantir que os usuários finais que registraram seus dispositivos com o Microsoft Intune são as mesmas pessoas que estão abrindo os aplicativos. Quando os usuários finais configuram seus PINs, o SDK de Aplicativo do Intune usa o Azure Active Directory para verificar as credenciais de usuários finais em relação às credenciais de registro do dispositivo

### Os usuários devem inserir credenciais para poderem abrir os aplicativos
Os administradores de TI podem exigir que os usuários digitem suas credenciais para poderem abrir um aplicativo gerenciado pelo Intune. O SDK do Intune App usa o Active Directory do Azure para fornecer uma experiência de logon único, em que as credenciais, uma vez inseridas, são reutilizadas para logons subsequentes. Também há suporte para autenticação de soluções de gerenciamento de identidade [federadas com o Azure Active Directory](https://msdn.microsoft.com/library/azure/jj679342.aspx).

### Verificar a integridade e conformidade do dispositivo
Os administradores de TI podem realizar uma verificação de integridade do dispositivo e sua conformidade com políticas corporativas antes que os usuários finais possam acessar aplicativos gerenciados pelo Intune. Na plataforma iOS, esta política verifica se o dispositivo foi desbloqueado com jailbreak. Na plataforma Android, esta política verifica se o dispositivo apresenta raiz.

## Recursos em Visualização
O SDK do Microsoft Intune App inclui vários recursos que estão em "visualização". Você pode começar a integração com as APIs de visualização, mas somente para fins de teste. Observe que essas visualizações complementam os cenários existentes em vez de substitui-los.

### Suporte a várias identidades do SDK do Microsoft Intune App
O suporte a várias identidades é um recurso que possibilita a coexistência de contas gerenciadas (corporativas) pela política e não gerenciadas (pessoais) em um mesmo aplicativo.

### Exemplo de um cenário de várias identidade
Muitos usuários configuram ambas as contas de email pessoal e corporativa no aplicativo Outlook para iOS e Android. Quando um usuário acessa os dados na sua conta corporativa, o administrador de TI deve ter certeza de que o gerenciamento de política de MAM será aplicado. No entanto, quando um usuário está acessando uma conta de email pessoal, esses dados devem ficar fora do controle do administrador de TI. O Microsoft Intune possibilita isso ao segmentar a política de gerenciamento apenas para a conta corporativa no aplicativo. Esse recurso de várias identidades ajuda a solucionar o problema de proteção de dados que as organizações enfrentam com dispositivos e aplicativos que dão suporte a contas pessoais e corporativas.

### Como dar suporte a várias identidades
APIs de visualização permitem que você especifique um nome UPN com operações de dados específicos, como operações na área de transferência e de arquivo. O SDK do Microsoft Intune App usa o UPN para corresponder a chamada feita para o UPN que foi usado para registrar o dispositivo ao serviço do Microsoft Intune. Se os UPNs corresponderem, a chamada será tratada como uma chamada de "dados corporativos" e os dados serão protegidos. Se os UPNs não coincidirem, a chamada será tratada como uma chamada de "dados pessoais" e os dados não serão protegidos.

### Gerenciamento de aplicativo sem registro de dispositivo
Muitos usuários com dispositivos pessoais desejam ver e usar dados corporativos sem registrar seus dispositivos pessoais com um produto MDM (Gerenciamento de Dispositivo Móvel). Como o registro de MDM requer controle global do dispositivo, os usuários hesitam conceder esse controle global em seu próprio dispositivo pessoal para a empresa.

O gerenciamento de aplicativo sem registro de dispositivo permite que o serviço do Microsoft Intune implante a política de MAM a um aplicativo diretamente, sem depender de um canal MDM para implantar a política. Como não é necessário nenhum canal MDM, o registro de MDM não é necessário.



<!--HONumber=May16_HO2-->


