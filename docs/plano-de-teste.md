# Plano de Teste: OrangeHRM (Login e PIM)

## 1. Identificação

| Item | Detalhe |
|---|---|
| **Projeto** | Testes funcionais manuais do OrangeHRM Demo |
| **Aplicação** | OrangeHRM Demo (https://opensource-demo.orangehrmlive.com/) |
| **Módulos testados** | Login e PIM (Personnel Information Management) |
| **Tipo de teste** | Funcional, manual, caixa-preta |
| **Responsável** | Karoliny Carvalho |
| **Navegador e versão** | Google Chrome |
| **Sistema operacional** | Windows 11 |
| **Período de execução** | 10/2026 |

---

## 2. Objetivo

Validar o comportamento dos módulos de Login e PIM do OrangeHRM, verificando:

- se o sistema permite o acesso com credenciais válidas e trata corretamente dados inválidos ou ausentes;
- se o cadastro de funcionários aplica as validações de campos obrigatórios, duplicidade e regras de negócio esperadas.

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
- Validação de First Name obrigatório
- Validação de Last Name obrigatório
- Alteração do Employee ID
- Cancelamento do cadastro
- Validação de Username duplicado
- Validação de senha e confirmação de senha
- Validação de Employee ID duplicado
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

- Testes positivos e negativos
- Validação de campos obrigatórios
- Testes de valores duplicados
- Análise de resultado esperado x resultado obtido
- Registro e documentação de defeitos

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
| CT-PIM-05 | Cancelamento do cadastro |
| CT-PIM-06 | Validação de Username duplicado |
| CT-PIM-07 | Validação de senha e confirmação de senha |
| CT-PIM-08 | Validação de Employee ID duplicado |
| CT-PIM-09 | Geração automática de Employee ID |

Os casos detalhados, com pré-condições, passos, dados de entrada e resultado esperado, estão em [`test-cases-manual`](../test-cases-manual):

- [Login-test-cases.xlsx](../test-cases-manual/Login-test-cases.xlsx)
- [PIM-test-cases.xlsx](../test-cases-manual/PIM-test-cases.xlsx)

---

## 6. Dados de Teste

- **Credenciais válidas:** usuário `Admin` e senha `admin123`
- **Senha inválida:** `admin1`
- **Usuário inválido:** `Administrator`
- **Campos vazios:** usuário e/ou senha sem preenchimento
- **PIM:** dados de funcionário válidos, inválidos e duplicados, conforme as planilhas de casos de teste

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

Os defeitos identificados são documentados com:

- ID do defeito
- Módulo e funcionalidade
- Severidade e prioridade
- Passos para reproduzir
- Resultado esperado e resultado obtido
- Reprodutibilidade
- Evidência (print ou vídeo)

O detalhamento completo está no [README](../README.md) do repositório.

---

## 10. Resultados

| Módulo | Executados | Aprovados | Reprovados |
|---|---:|---:|---:|
| Login | 7 | 7 | 0 |
| PIM | 9 | 8 | 1 |
| **Total** | **16** | **15** | **1** |

**Defeito identificado:** BUG-PIM-001, geração automática de Employee ID já existente (módulo PIM).

---

## 11. Evidências

| Evidência | Arquivo |
|---|---|
| Login com senha inválida | [01-Login-com-senha-invalida.mp4](../evidences/videos/01-Login-com-senha-invalida.mp4) |
| Login com usuário inválido | [02-Login-com-usuario-invalido.mp4](../evidences/videos/02-Login-com-usuario-invalido.mp4) |
| Login com usuário e senha inválidos | [03-Login-com-usuario-e-Senha-invalidos.mp4](../evidences/videos/03-Login-com-usuario-e-Senha-invalidos.mp4) |
| CT-PIM-02: First Name vazio | [CT-PIM-02-First-Name-vazio.mp4](../evidences/videos/CT-PIM-02-First-Name-vazio.mp4) |
| BUG-PIM-001 | [BUG-PIM-001-anexo5.png](../evidences/prints/BUG-PIM-001-anexo5.png) |

---

## 12. Observações

Projeto desenvolvido como prática de QA manual, com o objetivo de aplicar planejamento, elaboração de casos de teste, execução, registro de evidências e documentação de defeitos em uma aplicação web.
