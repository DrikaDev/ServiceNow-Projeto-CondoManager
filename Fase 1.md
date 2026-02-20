## 🏗️ Fase 1 – Criação da Aplicação Escopada

- Acessar: App Engine Studio
- Criar nova aplicação
- Nome: `CondoManager`
- Escopo: `x_980413_condoma_0`

<img width="683" height="502" alt="image" src="https://github.com/user-attachments/assets/fd930c65-a97f-48f7-8c96-47baf628a921" />

## 2 - Let's add roles to your new app

### Role 1: Admin do Condomínio
**Role name:** condo.admin  
**Description:** Acesso total à aplicação CondoManager.  
**CRUD:** Create, Read, Write, Delete.  
Pode gerenciar todos os cadastros de apartamentos, moradores, aprovar reservas de áreas comuns e configurar categorias de manutenção.  

### Role 2: Morador (Resident)
**Role name:** condo.resident  
**Description:** Acesso restrito ao portal do morador.  
**CRUD:** Read.  
Permite realizar reservas de áreas comuns, abrir solicitações de manutenção para sua própria unidade e atualizar seus dados de contato.  

### Role 3: Manutenção / Zeladoria
**Role name:** condo.maintenance  
**Description:** Permissão para visualizar e atualizar o status de solicitações de manutenção (Maintenance Requests).  
**CRUD:** Read e Write.  
Não possui acesso a dados financeiros ou cadastrais privados dos moradores.

<img width="639" height="489" alt="image" src="https://github.com/user-attachments/assets/4cdbb5cc-c8c1-43d0-9b86-878345c29545" />

### Por que estas roles são importantes?  
No ServiceNow, ao criar uma *Scoped Application*, as roles permitem que você utilize ACLs (Access Control Lists) para proteger as tabelas.  
Por exemplo:  
- A tabela de Apartamentos só deve ser editada pela role admin.  
- A tabela de Reservas permite que o resident crie novos registros, mas apenas o admin pode marcá-los como "Aprovados".  

