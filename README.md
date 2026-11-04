# Portfólio de QA: Testes Manuais no OrangeHRM

Projeto de portfólio que demonstra, na prática, a atuação em **Quality Assurance (QA)** por meio de testes manuais funcionais (caixa-preta) na aplicação OrangeHRM Demo.

O trabalho abrange elaboração de casos de teste, execução dos cenários, análise dos resultados, registro de evidências e documentação de defeitos.

## Resumo

| Casos executados | Aprovados | Reprovados | Defeitos registrados |
|-----------------:|----------:|-----------:|---------------------:|
| 17 | 16 | 1 | 1 |

---

## Sistema Testado

**OrangeHRM Demo**: aplicação web de gestão de recursos humanos.

Acesso: https://opensource-demo.orangehrmlive.com/

## Ambiente de Teste

| Item | Detalhe |
|---|---|
| Navegador | Google Chrome |
| Sistema operacional | Windows 11 |
| Período de execução | 10/2026 |
| Tipo de teste | Manual, funcional, caixa-preta |

---

## Escopo dos Testes

### Login (7 casos)

| ID | Cenário |
|---|---|
| CT-LOGIN-01 | Login com senha inválida |
| CT-LOGIN-02 | Login com usuário inválido |
| CT-LOGIN-03 | Login com usuário e senha inválidos |
| CT-LOGIN-04 | Login com credenciais válidas |
| CT-LOGIN-05 | Campos obrigatórios vazios |
| CT-LOGIN-06 | Usuário vazio |
| CT-LOGIN-07 | Senha vazia |

### PIM: Personnel Information Management (10 casos)

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

---

## Resultados da Execução

| Módulo | Casos Executados | Aprovados | Reprovados |
|---|---:|---:|---:|
| Login | 7 | 7 | 0 |
| PIM | 10 | 9 | 1 |
| **Total** | **17** | **16** | **1** |

---

## Exemplos de Casos de Teste

Os casos completos estão nas planilhas da pasta [`test-cases-manual`](./test-cases-manual). Dois exemplos:

| ID | Título | Pré-condição | Passos | Dados de entrada | Resultado esperado |
|:--|:--|:--|:--|:--|:--|
| **CT-LOGIN-01** | Login com senha inválida | Usuário cadastrado no sistema | 1. Acessar a tela de Login<br>2. Informar usuário válido<br>3. Informar senha inválida<br>4. Clicar em "Login" | **Usuário:** Admin<br>**Senha:** admin1 (inválida) | Usuário permanece na tela de Login, a autenticação não é realizada e a mensagem `Invalid credentials` é exibida. |
| **CT-PIM-06** | Validação de Employee ID duplicado | Usuário autenticado; existir funcionário com o Employee ID usado no teste | 1. Abrir Add Employee<br>2. Preencher campos obrigatórios<br>3. Informar ID existente<br>4. Tentar salvar | **Employee ID existente:** 9999 | Cadastro bloqueado e mensagem informando que o Employee ID já existe. |

---

## Defeito Identificado

### BUG-PIM-001: Sistema gera automaticamente Employee ID já existente

| Campo | Descrição |
|---|---|
| **Módulo** | PIM > Add Employee |
| **Caso de teste de origem** | CT-PIM-10 |
| **Severidade** | Média |
| **Prioridade** | Média |
| **Reprodutibilidade** | Reproduzido em múltiplas tentativas |
| **Evidência** | [BUG-PIM-001-anexo5.png](./evidences/prints/BUG-PIM-001-anexo5.png) |

**Pré-condição:** usuário autenticado e acesso à tela Add Employee.

**Passos para reproduzir**

1. Acessar **PIM > Add Employee**.
2. Observar o Employee ID preenchido automaticamente.
3. Repetir o acesso ao formulário em novas tentativas.
4. Verificar se o ID gerado já pertence a outro funcionário.

**Resultado esperado:** o sistema gera automaticamente um Employee ID único e disponível.

**Resultado obtido:** em múltiplas tentativas, o sistema gerou IDs já existentes (por exemplo, 0445 e 0374) e exibiu `Employee Id already exists`. Em outra tentativa, o ID 0380 foi aceito.

**Observação:** a validação de duplicidade funciona, mas a geração automática do ID apresenta comportamento inconsistente.

![BUG-PIM-001: Employee Id already exists](./evidences/prints/BUG-PIM-001-anexo5.png)

---

## Técnicas Aplicadas

- Testes funcionais
- Testes positivos e negativos
- Validação de campos obrigatórios
- Validação de dados duplicados
- Validação de mensagens de erro
- Comparação entre resultado esperado e resultado obtido
- Reexecução de cenários para confirmação de comportamento
- Identificação e documentação de defeitos

---

## Evidências

### Login (vídeos)

| ID | Evidência |
|---|---|
| CT-LOGIN-01 | [01-Login-com-senha-invalida.mp4](./evidences/videos/01-Login-com-senha-invalida.mp4) |
| CT-LOGIN-02 | [02-Login-com-usuario-invalido.mp4](./evidences/videos/02-Login-com-usuario-invalido.mp4) |
| CT-LOGIN-03 | [03-Login-com-usuario-e-Senha-invalidos.mp4](./evidences/videos/03-Login-com-usuario-e-Senha-invalidos.mp4) |
| CT-LOGIN-04 | [04-Login-com-usuario-e-senha-validos.mp4](./evidences/videos/04-Login-com-usuario-e-senha-validos.mp4) |
| CT-LOGIN-05 | [05-Campos-vazios.mp4](./evidences/videos/05-Campos-vazios.mp4) |
| CT-LOGIN-06 | [06-Usuario-vazio.mp4](./evidences/videos/06-Usuario-vazio.mp4) |
| CT-LOGIN-07 | [07-Senha-vazia.mp4](./evidences/videos/07-Senha-vazia.mp4) |

### PIM (vídeos e prints)

| ID | Evidência |
|---|---|
| CT-PIM-01 | [CT-PIM-01-Cadastro-valido.mp4](./evidences/videos/CT-PIM-01-Cadastro-valido.mp4) |
| CT-PIM-02 | [CT-PIM-02-First-Name-vazio.mp4](./evidences/videos/CT-PIM-02-First-Name-vazio.mp4) |
| CT-PIM-03 | [CT-PIM-03-Last-Name-vazio.png](./evidences/prints/CT-PIM-03-Last-Name-vazio.png) |
| CT-PIM-04 | [CT-PIM-04-Editar-Employee-ID.png](./evidences/prints/CT-PIM-04-Editar-Employee-ID.png) |
| CT-PIM-05 | [CT-PIM-05-Cadastro-sem-Middle-Name.mp4](./evidences/videos/CT-PIM-05-Cadastro-sem-Middle-Name.mp4) |
| CT-PIM-06 | [vídeo](./evidences/videos/CT-PIM-06-Employee-ID-duplicado.mp4) · [print](./evidences/prints/CT-PIM-06-Employee-ID-duplicado.png) |
| CT-PIM-07 | [CT-PIM-07-Username-obrigatorio.png](./evidences/prints/CT-PIM-07-Username-obrigatorio.png) |
| CT-PIM-08 | [CT-PIM-08-Password-obrigatorio.png](./evidences/prints/CT-PIM-08-Password-obrigatorio.png) |
| CT-PIM-09 | [CT-PIM-09-Username-duplicado.png](./evidences/prints/CT-PIM-09-Username-duplicado.png) |
| CT-PIM-10 | [BUG-PIM-001-anexo5.png](./evidences/prints/BUG-PIM-001-anexo5.png) |

---

## Documentação

| Item | Localização |
|---|---|
| Plano de teste | [docs/plano-de-teste.md](./docs/plano-de-teste.md) |
| Casos de teste (Login) | [test-cases-manual/Login-test-cases.xlsx](./test-cases-manual/Login-test-cases.xlsx) |
| Casos de teste e Bug Report (PIM) | [test-cases-manual/PIM-test-cases.xlsx](./test-cases-manual/PIM-test-cases.xlsx) |
| Evidências em vídeo | [evidences/videos](./evidences/videos) |
| Evidências em imagem | [evidences/prints](./evidences/prints) |

---

## Próximos Passos

- Automação dos principais cenários com Cypress e JavaScript
- Geração de relatórios de execução automatizada

---

## Autoria

Desenvolvido por **Karoliny Carvalho**, QA Júnior, com foco em testes manuais e funcionais, documentação de casos de teste e identificação de defeitos.

[LinkedIn](https://www.linkedin.com/in/karoliny-p-o-carvalho-10554b113/)
