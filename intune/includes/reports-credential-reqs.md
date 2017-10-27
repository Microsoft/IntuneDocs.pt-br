<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Requisitos de credencial do Intune e Azure AD

Autenticação e autorização têm base em credenciais do Azure AD e controle de acesso com base em função do Intune (RBAC). Todos os administradores globais e os administradores de serviço do Intune de seu locatário têm acesso ao Data warehouse por padrão. Use funções do Intune para fornecer acesso a mais usuários, oferecendo a eles acesso para o **recurso de Emissão de relatórios**.

Os requisitos para acessar o Data Warehouse do Intune (incluindo a API) são:

  -  A licença do Intune deve ser atribuída ao usuário
  -  O usuário deve ser um destes:
      -  Administrador global do Azure AD
      -  Um administrador de serviços do Intune
      -  Usuário com acesso baseado em função para o recurso de **relatórios**