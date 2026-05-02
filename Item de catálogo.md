## Item de Catálogo

Este **Item de Catálogo** foi desenvolvido para a gestão de solicitações de um condomínio, permitindo que moradores registrem pedidos de manutenção e limpeza, 
além de enviar comunicações como reclamações, sugestões e elogios.  

### Solicitação de Serviço no Condomínio

## 1. Criação do Item de Catálogo no Service Catalog

Em All > Service Catalog > Catalog Definitions > Maintain Items > New

<img width="1420" height="455" alt="image" src="https://github.com/user-attachments/assets/2cdd6c3a-6d2a-4bde-b234-062aba940694" />

## 2. Criação das variáveis / questions

Rolando a tela para baixo, em *Related List*, na aba *Variables* clicando em *New*, criamos as seguintes variáveis/questions:

- **Tipo de solicitação**, do tipo *Select Box*, na aba *Type Specifications*, com as seguintes *Questions Choices*: Manutenção, Limpeza, Reclamação, Sugestão, Elogio;
- **Descrição**, do tipo *Multi Line Text*;
- **Local**, do tipo *Reference* à tabela `cmn_location`;
- **Urgência**, do tipo *Select Box*, na aba *Type Specifications*, com as seguintes *Questions Choices*: Baixa, Média, Alta;
- **Anexo**, do tipo *Attachment*;

<img width="1411" height="390" alt="image" src="https://github.com/user-attachments/assets/758a7220-eb2d-4d41-80b4-95e07f61b1a8" />

## 3. Criação do Variable Set

Criei um **Variable Set** intitulado `Dados do morador` - para centralizar os dados do morador solicitante, permitindo a reutilização destes dados em múltiplos itens de catálogo e 
melhorando a consistência e a manutenção do formulário - contendo as seguintes variáveis/questions:  
- **Nome completo**, do tipo *Reference* à tabela `sys_user`;
- **Apto e bloco**, do tipo Single Line Text;
- **Telefone**, do tipo Single Line Text;
- **E-mail**, do tipo Email;

> Os dados do morador, como `E-mail` e `Telefone` foram configurados com a ativação do preenchimento automático do *Auto-populate*, otimizando assim o
tempo de preenchimento do form.  

<img width="1428" height="713" alt="image" src="https://github.com/user-attachments/assets/95032164-ef58-4c3c-b31c-35cf53ae67ee" />

## 4. Resultado

<img width="1289" height="567" alt="image" src="https://github.com/user-attachments/assets/cf85fd07-101c-43fa-aa0e-c86f7dda344e" />
