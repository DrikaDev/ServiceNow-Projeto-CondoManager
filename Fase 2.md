### 🗄️ Fase 2 – Modelagem de Dados

## 2️⃣ Criar Tabelas

## 🏠 Tabela: Apartment

Campos:
- Number (String)
- Block (String)
- Owner (Reference → User)
- Status (Choice: Occupied / Vacant)

---

## 👤 Tabela: Resident

Campos:

- Name (String)
- Apartment (Reference → Apartment)
- Phone (String)
- Email (Email)
- Type (Choice: Owner / Tenant)

---

## 🛠️ Tabela: Maintenance Request

> Estender a tabela **Task** para reaproveitar funcionalidades padrão.

Campos adicionais:

- Apartment (Reference → Apartment)
- Category (Choice: Hidráulica / Elétrica / Estrutural)
- Priority
- Status (Open / In Progress / Resolved / Closed)

---

## 🎉 Tabela: Reservation

Campos:

- Area (Choice: Salão de Festas / Churrasqueira / Quadra)
- Apartment (Reference → Apartment)
- Date (Date/Time)
- Status (Requested / Approved / Rejected)
