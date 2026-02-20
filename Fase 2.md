## 🗄️ Fase 2 – Modelagem de Dados

## Criar Tabelas

## 🏠 Tabela: Apartment - from scratch

Tabela de cadastro das unidades habitacionais.  

<img width="716" height="324" alt="image" src="https://github.com/user-attachments/assets/bd0c3bc0-00a7-4801-8ca9-8b5fd3ad75b5" />

Campos:
- Number (String)
- Block (String)
- Owner (Reference → User)
- Status (Choice: Occupied / Vacant)

---

## 👤 Tabela: Resident - from scratch

Tabela para gerenciar as pessoas vinculadas aos apartamentos.  

<img width="717" height="321" alt="image" src="https://github.com/user-attachments/assets/402ea8fe-0b72-43c5-a308-e2419e47b77f" />

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
