## 🗄️ Fase 2 – Modelagem de Dados

## Criar Tabelas

## 🏠 Tabela: Apartment - from scratch
Tabela de cadastro das unidades habitacionais.  
<img width="713" height="318" alt="image" src="https://github.com/user-attachments/assets/0a526ccf-6d4e-4bd1-b611-ff0cc19e7eaf" />

Campos:
- Number (String)
- Block (String)
- Owner (Reference → User)
- Status (Choice: Occupied / Vacant)

---

## 👤 Tabela: Resident - from scratch
Tabela para gerenciar as pessoas vinculadas aos apartamentos.
Campos:
- Name (String)
- Apartment (Reference → Apartment)
- Phone (String)
- Email (Email)
- Type (Choice: Owner / Tenant)

---

## 🛠️ Tabela: Maintenance Request - Extendida da Task

Estender a tabela **Task** para reaproveitar funcionalidades padrão.
> **Task** é usada para processos que têm um "fazer" (uma tarefa com início, meio e fim), como uma manutenção.  
> **Apartamentos e Moradores** são dados estáticos (registros de mestre), por isso não precisam das funcionalidades de uma tarefa.  

**Por que estender?**  
Ao fazer isso, ela herda automaticamente campos essenciais como Number, Short Description, State, Priority e a funcionalidade de histórico (Work Notes), facilitando a gestão do ciclo de vida do conserto.  

Campos adicionais:
- Apartment (Reference → Apartment)
- Category (Choice: Hidráulica / Elétrica / Estrutural)
- Priority
- Status (Open / In Progress / Resolved / Closed)

---

## 🎉 Tabela: Reservation - from scratch
Tabela para o controle de uso das áreas comuns.  
Campos:
- Area (Choice: Salão de Festas / Churrasqueira / Quadra)
- Apartment (Reference → Apartment)
- Date (Date/Time)
- Status (Requested / Approved / Rejected)
