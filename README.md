# 🏅 Sistema de Gestão Olímpica — Jogos Olímpicos 2028
 
> **Versão:** 3.0 &nbsp;|&nbsp; **Data:** 13/05/2026 &nbsp;|&nbsp; **Status:** Em Desenvolvimento
 
**Autores:** Maria Silva (Engenharia de Requisitos Sênior) · João Santos (Analista de Sistemas) · Ana Oliveira (Arquiteta de Software)
 
---
 
## 📑 Sumário
 
1. [Visão Geral](#visão-geral)
2. [Histórias de Usuário](#histórias-de-usuário)
3. [Regras de Negócio](#regras-de-negócio)
4. [Diagramas de Casos de Uso](#diagramas-de-casos-de-uso)
   - [Parte 1 — Gestão de Competições e Inscrições](#parte-1--gestão-de-competições-e-inscrições)
   - [Parte 2 — Resultados, Relatórios e Segurança](#parte-2--resultados-relatórios-e-segurança)
5. [Diagrama de Classes](#diagrama-de-classes)
6. [Diagrama de Componentes (AWS)](#diagrama-de-componentes-aws)
7. [Diagrama de Implantação](#diagrama-de-implantação)
8. [Rastreabilidade](#rastreabilidade)
---
 
## Visão Geral
 
O **Sistema de Gestão Olímpica** é uma plataforma digital para orquestrar todas as operações dos Jogos Olímpicos 2028, abrangendo:
 
- Cadastro de atletas, países, modalidades e locais de prova
- Gestão completa do ciclo de competições (criação → inscrição → resultado)
- Controle de acesso por perfil (Administrador, Árbitro, Delegação, Atleta, Público)
- Relatórios de medalhas e quadro geral em tempo real
- Arquitetura cloud-native na AWS com microsserviços, mensageria e serverless
---
 
## Histórias de Usuário
 
### 🔐 Acesso e Segurança
 
| ID | Ator | História |
|:---:|:---|:---|
| US12 | Usuário do sistema | Autenticar-me com login e senha, para que apenas perfis autorizados acessem funcionalidades restritas. |
| US13 | Administrador | Cadastrar novos usuários definindo perfis de acesso (Admin, Árbitro, Delegação). |
| US14 | Usuário do sistema | Recuperar minha senha por e-mail em caso de esquecimento. |
 
### 🏛️ Cadastros Básicos
 
| ID | Ator | História |
|:---:|:---|:---|
| US04 | Administrador | Cadastrar atletas e países participantes para inscrição nas competições. |
| US15 | Administrador | Cadastrar locais de prova com capacidade máxima de público. |
| US16 | Administrador | Cadastrar modalidades esportivas com suas regras específicas. |
 
### 📋 Gestão de Competições
 
| ID | Ator | História | RN |
|:---:|:---|:---|:---:|
| US01 | Administrador | Cadastrar nova competição informando modalidade, data, horário e local. | RN1 |
| US02 | Administrador | Editar ou cancelar uma competição já cadastrada. | RN1 |
| US03 | Administrador | Alocar local sem conflito de horário com outro evento. | RN3 |
| US17 | Administrador | Definir duração estimada de cada competição no momento do cadastro. | RN3 |
| US18 | Administrador | Reagendar em lote competições afetadas por condições climáticas. | RN1 |
 
### ✍️ Inscrições
 
| ID | Ator | História | RN |
|:---:|:---|:---|:---:|
| US05 | Atleta | Inscrever-me em uma competição representando meu país. | RN2 |
| US06 | Sistema | Evitar que um mesmo atleta represente mais de um país em uma modalidade. | RN2 |
| US11 | Atleta | Visualizar minhas inscrições confirmadas e resultados. | — |
| US19 | Delegação | Substituir atleta inscrito por outro do mesmo país antes da prova. | RN2 |
| US20 | Sistema | Encerrar automaticamente inscrições 24h antes do início. | — |
| US21 | Árbitro/Juiz | Registrar desclassificação de atleta durante a prova. | RN4 |
 
### 🏁 Resultados
 
| ID | Ator | História | RN |
|:---:|:---|:---|:---:|
| US07 | Árbitro/Juiz | Registrar resultado informando 1º, 2º e 3º lugares. | RN4 |
| US22 | Árbitro/Juiz | Registrar empate em qualquer posição do pódio. | RN4 |
| US23 | Administrador | Retificar resultado homologado com justificativa e auditoria. | RN4 |
 
### 📊 Relatórios e Consultas
 
| ID | Ator | História | RN |
|:---:|:---|:---|:---:|
| US08 | Administrador | Gerar relatório de medalhas por país. | RN5 |
| US09 | Público | Consultar a programação das competições. | — |
| US10 | Público | Consultar o quadro geral de medalhas em tempo real. | RN5 |
| US24 | Público | Filtrar programação por modalidade, data ou local. | — |
 
---
 
## Regras de Negócio
 
| RN | Descrição | User Stories |
|:---:|:---|:---:|
| **RN1** | Competição deve ter nome, data, horário, local e lista de inscritos | US01, US02, US18 |
| **RN2** | Atleta pode participar de várias competições, mas só representa um país por modalidade | US05, US06, US19 |
| **RN3** | Local só abriga uma competição por vez (sem conflito de horário) | US03, US17 |
| **RN4** | Registrar 1º, 2º e 3º lugares após realização da prova | US07, US21, US22, US23 |
| **RN5** | Relatórios de medalhas com desempenho por país | US08, US10 |
 
---

## Caso de Uso
<img width="1565" height="1425" alt="casos-de-uso1" src="https://github.com/user-attachments/assets/54dddab1-2d29-47cc-b7a7-7dff13f21573" />

<img width="945" height="1422" alt="casos-de-uso2" src="https://github.com/user-attachments/assets/30355bbc-0db0-4e96-84a8-c3d6f9a62f15" />

## Diagrama de Classe/Pacotes

<img width="2516" height="1597" alt="diagrama-de-classes-pacotes" src="https://github.com/user-attachments/assets/92ebbaee-777f-4201-88df-1fb795ed5cf0" />

## Diagrama de Componentes

<img width="1474" height="930" alt="componentes" src="https://github.com/user-attachments/assets/34843cd2-03a6-4233-aef2-2eb311da6017" />

## Diagrama de Implantação

<img width="993" height="1445" alt="implantacao" src="https://github.com/user-attachments/assets/a19c95b2-76ff-4dfa-8462-3ba69c1c0bc8" />

---
 
## Rastreabilidade
 
| Regra de Negócio | Descrição | User Stories |
|:---:|:---|:---:|
| **RN1** | Cadastro de competições com nome, data, horário, local e lista de inscritos | US01, US02, US18 |
| **RN2** | Atleta participa de várias competições, mas só representa um país por modalidade | US05, US06, US19 |
| **RN3** | Local só abriga uma competição por vez (sem conflito de horário) | US03, US17 |
| **RN4** | Registrar 1º, 2º e 3º lugares após a realização da prova | US07, US21, US22, US23 |
| **RN5** | Relatórios de medalhas com desempenho por país | US08, US10 |
 
---
 
> 📌 **Como renderizar os diagramas PlantUML:**
> - **Online:** [plantuml.com/plantuml/uml](https://www.plantuml.com/plantuml/uml/)
> - **VS Code:** Extensão *PlantUML* (jebbs.plantuml)
> - **IntelliJ / Eclipse:** Plugin PlantUML Integration
> - **CLI:** `java -jar plantuml.jar README.md`
