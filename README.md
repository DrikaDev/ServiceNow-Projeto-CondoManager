## 🏢 CondoManager - Aplicação de Gestão de Condomínio no ServiceNow

<p align="center">
<img width="400" alt="Gemini_Generated_Image_efe9w2efe9w2efe9" src="https://github.com/user-attachments/assets/14a8d6b5-86db-4c0d-a666-70fbbd9a9256" />
</p>

## 🎯 Objetivo do Projeto
Desenvolver uma aplicação escopada no ServiceNow para gestão de condomínio, permitindo: 
- Cadastro de moradores, 
- Controle de apartamentos, 
- Abertura e acompanhamento de chamados de manutenção, 
- Reservas de áreas comuns, 
- Controle de acesso em perfis (RBAC)
- Automação de notificações e processo

## 📌 Cenário Fictício

O Condomínio Residencial **Vila Constança** precisa de uma solução para:

- Registrar moradores e apartamentos
- Permitir abertura de chamados (ex: vazamento, elevador com defeito)
- Permitir reserva de salão de festas
- Permitir que o síndico acompanhe e finalize solicitações
- Controlar acessos conforme perfil do usuário

---

### 🏗️ FASE 1 – [Criação da Aplicação Escopada](https://github.com/DrikaDev/ServiceNow-Gestao-de-Condominio/blob/main/Fase%201.md)

### 🗄️ FASE 2 – [Modelagem de Dados](https://github.com/DrikaDev/ServiceNow-Projeto-CondoManager/blob/main/Fase%202.md)

### 🔐 FASE 3 – Segurança (RBAC)

## 3️⃣ Criar Roles

- condo_resident
- condo_doorman
- condo_manager
- condo_admin

---

## 4️⃣ Configurar ACLs

### Maintenance Request

- Morador:
  - Pode criar
  - Pode visualizar apenas chamados do seu apartamento

- Síndico:
  - Pode visualizar todos
  - Pode alterar status
  - Pode fechar chamados

- Porteiro:
  - Pode visualizar
  - Não pode fechar chamados

---

# 🔄 FASE 4 – Automação (Flow Designer)

## 5️⃣ Criar Fluxos

### Fluxo 1 – Novo Chamado

Trigger:
- Quando Maintenance Request for criado

Ações:
- Enviar notificação para o síndico

---

### Fluxo 2 – Chamado Resolvido

Trigger:
- Quando Status mudar para "Resolved"

Ações:
- Notificar morador

---

### Fluxo 3 – Solicitação de Reserva

Trigger:
- Quando Reservation for criada

Ações:
- Enviar solicitação de aprovação para síndico

---

# 🧩 FASE 5 – UI Policies

Exemplos:

- Se Category = Hidráulica → Mostrar campo "Urgency"
- Se Status = Resolved → Tornar campo "Resolution Notes" obrigatório
- Se Status = Closed → Tornar formulário somente leitura

---

# 🌐 FASE 6 – Portal para Moradores

Implementar:

- Record Producer para abertura de chamados
- Record Producer para reserva de áreas comuns
- Página personalizada no Employee Center ou Service Portal

Objetivo:
Melhorar a experiência do usuário final.

---

# 📊 FASE 7 – Dashboard

Criar Dashboard com:

- Total de chamados abertos
- Chamados por categoria
- Chamados por status
- Reservas por mês

---

## 🧠 Conceitos Aplicados

- Aplicação escopada
- Modelagem relacional
- Extensão da tabela Task
- RBAC (Role-Based Access Control)
- ACL (Access Control List)
- Flow Designer
- UI Policies
- Experiência do Usuário
- Governança e Segurança

---

## 🚀 Resultado Esperado

Uma aplicação funcional que simula um cenário real corporativo, demonstrando:

✔ Organização de dados  
✔ Controle de acesso  
✔ Automação de processos  
✔ Experiência do usuário  
✔ Boas práticas de desenvolvimento no ServiceNow  

---

## Funcionalidades Futuras

- Módulo Financeiro: Implementação da tabela de Billing para emissão e controle de boletos vinculados a cada unidade.
- Integração Bancária: Uso de IntegrationHub para automação de cobranças e conciliação de pagamentos via API.
- Automação de Notificações: Configuração de Flows para envio de alertas automáticos sobre vencimentos e comunicados do condomínio.

---
✨ Desenvolvido por Adriana G.
