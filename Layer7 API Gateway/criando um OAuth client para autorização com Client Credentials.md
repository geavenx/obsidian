> [!NOTE] Versão utilizada
> - OTK -> **4.6**
> - API Gateway -> **10.1**

---
Acesse o OAuth Manager através do endpoint */oauth/manager* e faça login com as credenciais definidas na configuração do API Gateway.

Acesse a aba *clients* e clique em *register new client*

![[Pasted image 20240307153512.png]]
![[Pasted image 20240307153612.png]]
---
Preencha os campos *client name, organization e description* de forma adequada, e em seguida faça as alterações conforme as instruções:

| Campo            | Valor            |
| ---------------- | ---------------- |
| Client Type      | **confidential** |
| [mag] Master Key | **true**         |
| Scope            | [[scopes]]       |

---
Registre o OAuth client

![[Pasted image 20240307154420.png]]