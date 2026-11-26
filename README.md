# Modelagem de Bancos de Dados Relacionais (MySQL)

Este repositório apresenta projetos práticos de modelagem de dados relacionais (Diagramas Entidade-Relacionamento Estendido — EER) desenvolvidos no **MySQL Workbench**. O objetivo é estruturar regras de negócio reais aplicando normalização, chaves primárias (`PK`), chaves estrangeiras (`FK`), cardinalidade e integridade referencial.

---

## 1. Fluxo Comercial e Operacional (Ordem de Serviço)

Modelagem voltada à rastreabilidade ponta a ponta de operações comerciais e atendimento, simulando a espinha dorsal de sistemas **CRM / ERP** e processos de **Sales & Service Operations**.

![Diagrama Ordem de Serviço](Ordem.png)

### Regras de Negócio e Arquitetura:
* **Cliente & Pedido (`1:N`):** Um cliente pode realizar múltiplos pedidos ao longo do tempo (`Cliente_Cliente`), registrando data, serviço solicitado e status de liberação.
* **Análise e Governança (`N:N` via `Analise de pedido`):** Resolve o relacionamento entre pedidos e responsáveis técnicos/helpdesk, permitindo auditar quem analisou cada solicitação antes da execução.
* **Geração de Ordem de Serviço (`1:N`):** Pedidos aprovados desdobram-se em uma ou mais Ordens de Serviço (`Ordem_Servico`) com controle de status operacional.

---

## 2. Sistema de Gestão Acadêmica (Universidade)

Modelagem de alta complexidade relacional contemplando herança/especialização de entidades, vínculos departamentais e grades curriculares.

![Diagrama Universidade](Universidade.png)

### Regras de Negócio e Arquitetura:
* **Especialização de Entidades (`Pessoa` → `Aluno` / `Professor`):** Centraliza dados cadastrais comuns (Nome, CPF, Endereço) na tabela `Pessoa`, evitando redundância e garantindo integridade cadastral.
* **Estrutura Departamental e Cursos:** Relaciona `Departamento`, `Professor` (incluindo vínculo de coordenação) e `Curso`.
* **Relacionamentos Muitos-para-Muitos (`N:N`):** Estruturados por meio de tabelas associativas para controle de matrículas em cursos (`Aluno_Matriculado_Curso`), inscrições em disciplinas (`Matriculado`), atividades complementares (`Horas Complementares`), pré-requisitos (`Pré-Requisitos das Disciplinas`) e alocação de docentes por semestre (`Oferta de Disciplina`).

---

## Tecnologias e Conceitos Aplicados
* **Ferramentas:** MySQL Workbench, SQL (DDL / DML)
* **Conceitos:** Modelagem Conceitual e Lógica (DER/EER), Normalização (1FN, 2FN, 3FN), Integridade Referencial e Cardinalidade.
