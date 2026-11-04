# Plano de Teste: OrangeHRM (Login e PIM)

## 1. Identificação

| Item | Detalhe |
|---|---|
| **Projeto** | Testes funcionais manuais do OrangeHRM Demo |
| **Aplicação** | OrangeHRM Demo (https://opensource-demo.orangehrmlive.com/) |
| **Módulos testados** | Login e PIM (Personnel Information Management) |
| **Tipo de teste** | Funcional, manual, caixa-preta |
| **Responsável** | Karoliny Carvalho |
| **Navegador** | Google Chrome |
| **Sistema operacional** | Windows 11 |
| **Período de execução** | 10/2026 |

---

## 2. Objetivo

Validar o comportamento dos módulos de Login e PIM do OrangeHRM, verificando:

- se o sistema permite o acesso com credenciais válidas e trata corretamente dados inválidos ou ausentes;
- se o cadastro de funcionários aplica as validações de campos obrigatórios, duplicidade e geração de identificadores esperadas.

---

## 3. Escopo

### Dentro do escopo

**Login**

- Login com usuário e senha válidos
- Login com senha inválida
- Login com usuário inválido
- Login com usuário e senha inválidos
- Login com os dois campos vazios
- Login com usuário vazio
- Login com senha vazia
- Validação das mensagens exibidas ao usuário

**PIM (cadastro de funcionários)**

- Cadastro de funcionário com dados válidos
- Validação de First Name e Last Name obrigatórios
- Alteração do Employee ID
- Cadastro sem Middle Name (campo opcional)
- Validação de Employee ID duplicado
- Validação de Username e Password obrigatórios
- Validação de Username duplicado
- Geração automática de Employee ID

### Fora do escopo

- Demais módulos do OrangeHRM além de Login e PIM
- Testes de performance e de carga
- Testes de API
- Testes de banco de dados
- Testes automatizados (previstos como evolução futura do projeto)

---

## 4. Estratégia de Teste

Os testes foram executados manualmente, com cenários positivos e negativos. As técnicas aplicadas foram:

- Testes funcionais
- Testes positivos e negativos
- Validação de campos obrigatórios
- Validação de dados duplicados
- Validação de mensagens de erro
- Comparação entre resultado esperado e resultado obtido
- Reexecução de cenários para confirmação de comportamento
- Identificação e documentação de defeitos

---

## 5. Cenários de Teste

### Login

| ID | Cenário |
|---|---|
| CT-LOGIN-01 | Login com senha inválida |
| CT-LOGIN-02 | Login com usuário inválido |
| CT-LOGIN-03 | Login com usuário e senha inválidos |
| CT-LOGIN-04 | Login com usuário e senha válidos |
| CT-LOGIN-05 | Login com os campos vazios |
| CT-LOGIN-06 | Login com usuário vazio |
| CT-LOGIN-07 | Login com senha vazia |

### PIM

| ID | Cenário |
|---|---|
| CT-PIM-01 | Cadastro de funcionário com dados válidos |
| CT-PIM-02 | Validação de First Name obrigatório |
| CT-PIM-03 | Validação de Last Name obrigatório |
| CT-PIM-04 | Alteração do Employee ID |
| CT-PIM-05 | Cadastro sem Middle Name |
| CT-PIM-06 | Validação de Employee ID duplicado |
| CT-PIM-07 | Validação de Username obrigatório |
| CT-PIM-08 | Validação de Password obrigatório |
| CT-PIM-09 | Validação de Username duplicado |
| CT-PIM-10 | Geração automática de Employee ID |

Os casos detalhados, com pré-condições, passos, dados de teste, resultado esperado e resultado obtido, estão em [`test-cases-manual`](../test-cases-manual):

- [Login-test-cases.xlsx](../test-cases-manual/Login-test-cases.xlsx)
- [PIM-test-cases.xlsx](../test-cases-manual/PIM-test-cases.xlsx) (casos de teste e Bug Report)

---

## 6. Dados de Teste

- **Login:** credenciais válidas (usuário `Admin` e senha `admin123`), senha inválida (`admin1`), usuário inválido (`Administrator`) e campos vazios
- **PIM:** dados fictícios de funcionário, Employee ID existente (`9999`), username existente (`Admin`) e username de teste (`loginteste01`)

Os dados têm finalidade exclusivamente de demonstração e estudo.

---

## 7. Critérios de Entrada

- Aplicação disponível para acesso
- Página de login acessível
- Ambiente de execução definido
- Casos de teste elaborados e dados de teste disponíveis

## 8. Critérios de Saída

- Todos os casos planejados executados
- Resultados obtidos registrados
- Evidências registradas
- Defeitos identificados e documentados

---

## 9. Registro de Defeitos

Os defeitos são documentados com ID, módulo, caso de teste de origem, severidade, prioridade, passos para reproduzir, resultado esperado, resultado obtido, reprodutibilidade e evidência.

O detalhamento está no [README](../README.md) e na aba **Bug Report** da planilha [PIM-test-cases.xlsx](../test-cases-manual/PIM-test-cases.xlsx).

---

## 10. Resultados

| Módulo | Executados | Aprovados | Reprovados |
|---|---:|---:|---:|
| Login | 7 | 7 | 0 |
| PIM | 10 | 9 | 1 |
| **Total** | **17** | **16** | **1** |

**Defeito identificado:** BUG-PIM-001, sistema gera automaticamente Employee ID já existente (caso de origem: CT-PIM-10).

---

## 11. Evidências

### Login

| ID | Evidência |
|---|---|
| CT-LOGIN-01 | [01-Login-com-senha-invalida.mp4](../evidences/videos/01-Login-com-senha-invalida.mp4) |
| CT-LOGIN-02 | [02-Login-com-usuario-invalido.mp4](../evidences/videos/02-Login-com-usuario-invalido.mp4) |
| CT-LOGIN-03 | [03-Login-com-usuario-e-Senha-invalidos.mp4](../evidences/videos/03-Login-com-usuario-e-Senha-invalidos.mp4) |
| CT-LOGIN-04 | [04-Login-com-usuario-e-senha-validos.mp4](../evidences/videos/04-Login-com-usuario-e-senha-validos.mp4) |
| CT-LOGIN-05 | [05-Campos-vazios.mp4](../evidences/videos/05-Campos-vazios.mp4) |
| CT-LOGIN-06 | [06-Usuario-vazio.mp4](../evidences/videos/06-Usuario-vazio.mp4) |
| CT-LOGIN-07 | [07-Senha-vazia.mp4](../evidences/videos/07-Senha-vazia.mp4) |

### PIM

| ID | Evidência |
|---|---|
| CT-PIM-01 | [CT-PIM-01-Cadastro-valido.mp4](../evidences/videos/CT-PIM-01-Cadastro-valido.mp4) |
| CT-PIM-02 | [CT-PIM-02-First-Name-vazio.mp4](../evidences/videos/CT-PIM-02-First-Name-vazio.mp4) |
| CT-PIM-03 | [CT-PIM-03-Last-Name-vazio.png](../evidences/prints/CT-PIM-03-Last-Name-vazio.png) |
| CT-PIM-04 | [CT-PIM-04-Editar-Employee-ID.png](../evidences/prints/CT-PIM-04-Editar-Employee-ID.png) |
| CT-PIM-05 | [CT-PIM-05-Cadastro-sem-Middle-Name.mp4](../evidences/videos/CT-PIM-05-Cadastro-sem-Middle-Name.mp4) |
| CT-PIM-06 | [vídeo](../evidences/videos/CT-PIM-06-Employee-ID-duplicado.mp4) · [print](../evidences/prints/CT-PIM-06-Employee-ID-duplicado.png) |
| CT-PIM-07 | [CT-PIM-07-Username-obrigatorio.png](../evidences/prints/CT-PIM-07-Username-obrigatorio.png) |
| CT-PIM-08 | [CT-PIM-08-Password-obrigatorio.png](../evidences/prints/CT-PIM-08-Password-obrigatorio.png) |
| CT-PIM-09 | [CT-PIM-09-Username-duplicado.png](../evidences/prints/CT-PIM-09-Username-duplicado.png) |
| CT-PIM-10 | [BUG-PIM-001-anexo5.png](../evidences/prints/BUG-PIM-001-anexo5.png) |

---

## 12. Observações

Projeto desenvolvido como prática de QA manual, com o objetivo de aplicar planejamento, elaboração de casos de teste, execução, registro de evidências e documentação de defeitos em uma aplicação web.
