# 📜 Histórias de Usuário - Sistema de Gestão Olímpica

**Projeto:** Jogos Olímpicos 2028 | **Versão:** 2.0 | **Data:** 13/05/2026

---

## 🔐 Acesso e Segurança

| ID | Ator | História |
|:---:|:---|:---|
| US12 | Usuário do sistema | Como **Usuário do sistema**, quero **autenticar-me com login e senha**, para que apenas perfis autorizados acessem funcionalidades restritas (cadastros, alocações e resultados). |

---

## 🏛️ Cadastros Básicos

| ID | Ator | História |
|:---:|:---|:---|
| US04 | Administrador | Como **Administrador**, quero **cadastrar atletas e países participantes**, para que eles fiquem disponíveis para inscrição nas competições. |

---

## 📋 Gestão de Competições

| ID | Ator | História | RN |
|:---:|:---|:---|---|
| US01 | Administrador | Como **Administrador**, quero **cadastrar uma nova competição informando modalidade, data, horário e local**, para que o evento seja oficialmente programado na agenda olímpica. | RN1 |
| US02 | Administrador | Como **Administrador**, quero **editar ou cancelar uma competição já cadastrada**, para que eu possa corrigir erros ou tratar imprevistos antes da realização da prova. | RN1 |
| US03 | Administrador | Como **Administrador**, quero **alocar um local a uma competição garantindo que não haja conflito de horário com outro evento no mesmo local**, para que a infraestrutura seja utilizada sem sobreposições. | RN3 |

---

## ✍️ Inscrições

| ID | Ator | História | RN |
|:---:|:---|:---|---|
| US05 | Atleta | Como **Atleta**, quero **me inscrever em uma competição representando o meu país**, para que eu possa participar oficialmente da modalidade. | RN2 |
| US06 | Sistema | Como **Sistema**, quero **evitar que um mesmo atleta represente mais de um país em uma mesma modalidade**, para que a regra olímpica seja respeitada. | RN2 |
| US11 | Atleta | Como **Atleta**, quero **visualizar minhas inscrições confirmadas e meus resultados**, para que eu acompanhe a participação nos jogos. | — |

---

## 🏁 Resultados

| ID | Ator | História | RN |
|:---:|:---|:---|---|
| US07 | Árbitro/Juiz | Como **Árbitro/Juiz**, quero **registrar o resultado de uma competição informando 1º, 2º e 3º lugares**, para que o pódio seja oficializado e as medalhas atribuídas. | RN4 |

---

## 📊 Relatórios e Consultas

| ID | Ator | História | RN |
|:---:|:---|:---|---|
| US08 | Administrador | Como **Administrador**, quero **gerar relatório de medalhas por país (ouro, prata e bronze)**, para que o desempenho de cada delegação seja divulgado de forma clara. | RN5 |
| US09 | Público | Como **Público**, quero **consultar a programação das competições**, para que eu possa acompanhar dias, horários e locais dos eventos. | — |
| US10 | Público | Como **Público**, quero **consultar o quadro geral de medalhas**, para que eu acompanhe em tempo real o desempenho dos países participantes. | RN5 |

---

## 🔗 Rastreabilidade

| Regra de Negócio | Descrição | US |
|:---:|:---|:---:|
| RN1 | Cadastro de competições com nome, data, horário, local e lista de inscritos | US01, US02 |
| RN2 | Atleta participa de várias competições, mas só representa um país por modalidade | US05, US06 |
| RN3 | Local só abriga uma competição por vez (sem conflito de horário) | US03 |
| RN4 | Registrar 1º, 2º e 3º lugares após a realização da prova | US07 |
| RN5 | Relatórios de medalhas com desempenho por país | US08, US10 |
