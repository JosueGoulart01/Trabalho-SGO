# 📜 Histórias de Usuário - Sistema de Gestão Olímpica

**Projeto:** Jogos Olímpicos 2028 | **Versão:** 3.0 | **Data:** 13/05/2026

---

## 🔐 Acesso e Segurança

| ID | Ator | História |
|:---:|:---|:---|
| US12 | Usuário do sistema | Como **Usuário do sistema**, quero **autenticar-me com login e senha**, para que apenas perfis autorizados acessem funcionalidades restritas (cadastros, alocações e resultados). |
| US13 | Administrador | Como **Administrador**, quero **cadastrar novos usuários definindo perfis de acesso** (Admin, Árbitro, Delegação), para que cada função tenha permissões adequadas ao seu papel. |
| US14 | Usuário do sistema | Como **Usuário do sistema**, quero **recuperar minha senha por e-mail**, para que eu não perca o acesso em caso de esquecimento. |

---

## 🏛️ Cadastros Básicos

| ID | Ator | História |
|:---:|:---|:---|
| US04 | Administrador | Como **Administrador**, quero **cadastrar atletas e países participantes**, para que eles fiquem disponíveis para inscrição nas competições. |
| US15 | Administrador | Como **Administrador**, quero **cadastrar locais de prova com capacidade máxima de público**, para que a ocupação seja controlada e a segurança garantida. |
| US16 | Administrador | Como **Administrador**, quero **cadastrar modalidades esportivas com suas regras específicas** (ex: limite de atletas por país), para que o sistema valide as inscrições automaticamente. |

---

## 📋 Gestão de Competições

| ID | Ator | História | RN |
|:---:|:---|:---|---|
| US01 | Administrador | Como **Administrador**, quero **cadastrar uma nova competição informando modalidade, data, horário e local**, para que o evento seja oficialmente programado na agenda olímpica. | RN1 |
| US02 | Administrador | Como **Administrador**, quero **editar ou cancelar uma competição já cadastrada**, para que eu possa corrigir erros ou tratar imprevistos antes da realização da prova. | RN1 |
| US03 | Administrador | Como **Administrador**, quero **alocar um local a uma competição garantindo que não haja conflito de horário com outro evento no mesmo local**, para que a infraestrutura seja utilizada sem sobreposições. | RN3 |
| US17 | Administrador | Como **Administrador**, quero **definir a duração estimada de cada competição no momento do cadastro**, para que o sistema valide automaticamente conflitos de horário com maior precisão. | RN3 |
| US18 | Administrador | Como **Administrador**, quero **reagendar em lote competições de uma mesma modalidade afetadas por condições climáticas**, para que eu não precise editar uma a uma em situações de emergência. | RN1 |

---

## ✍️ Inscrições

| ID | Ator | História | RN |
|:---:|:---|:---|---|
| US05 | Atleta | Como **Atleta**, quero **me inscrever em uma competição representando o meu país**, para que eu possa participar oficialmente da modalidade. | RN2 |
| US06 | Sistema | Como **Sistema**, quero **evitar que um mesmo atleta represente mais de um país em uma mesma modalidade**, para que a regra olímpica seja respeitada. | RN2 |
| US11 | Atleta | Como **Atleta**, quero **visualizar minhas inscrições confirmadas e meus resultados**, para que eu acompanhe a participação nos jogos. | — |
| US19 | Delegação | Como **Delegação**, quero **substituir um atleta inscrito por outro do mesmo país antes do início da prova**, para que eu possa lidar com lesões ou imprevistos de última hora. | RN2 |
| US20 | Sistema | Como **Sistema**, quero **encerrar automaticamente as inscrições de uma competição 24 horas antes do seu início**, para que a lista de participantes esteja consolidada para a organização. | — |
| US21 | Árbitro/Juiz | Como **Árbitro/Juiz**, quero **registrar a desclassificação de um atleta durante a prova**, para que o resultado reflita apenas os participantes que concluíram validamente. | RN4 |

---

## 🏁 Resultados

| ID | Ator | História | RN |
|:---:|:---|:---|---|
| US07 | Árbitro/Juiz | Como **Árbitro/Juiz**, quero **registrar o resultado de uma competição informando 1º, 2º e 3º lugares**, para que o pódio seja oficializado e as medalhas atribuídas. | RN4 |
| US22 | Árbitro/Juiz | Como **Árbitro/Juiz**, quero **registrar empate em qualquer posição do pódio**, para que ambos os atletas recebam a mesma medalha oficialmente. | RN4 |
| US23 | Administrador | Como **Administrador**, quero **retificar um resultado já homologado com justificativa e registro de auditoria**, para que correções por doping ou erro técnico sejam rastreáveis. | RN4 |

---

## 📊 Relatórios e Consultas

| ID | Ator | História | RN |
|:---:|:---|:---|---|
| US08 | Administrador | Como **Administrador**, quero **gerar relatório de medalhas por país (ouro, prata e bronze)**, para que o desempenho de cada delegação seja divulgado de forma clara. | RN5 |
| US09 | Público | Como **Público**, quero **consultar a programação das competições**, para que eu possa acompanhar dias, horários e locais dos eventos. | — |
| US10 | Público | Como **Público**, quero **consultar o quadro geral de medalhas**, para que eu acompanhe em tempo real o desempenho dos países participantes. | RN5 |
| US24 | Público | Como **Público**, quero **filtrar a programação por modalidade, data ou local**, para que eu encontre rapidamente os eventos do meu interesse. | — |

---

## 🔗 Rastreabilidade

| Regra de Negócio | Descrição | US |
|:---:|:---|:---:|
| RN1 | Cadastro de competições com nome, data, horário, local e lista de inscritos | US01, US02, US18 |
| RN2 | Atleta participa de várias competições, mas só representa um país por modalidade | US05, US06, US19 |
| RN3 | Local só abriga uma competição por vez (sem conflito de horário) | US03, US17 |
| RN4 | Registrar 1º, 2º e 3º lugares após a realização da prova | US07, US21, US22, US23 |
| RN5 | Relatórios de medalhas com desempenho por país | US08, US10 |

