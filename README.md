# UI E2E Tests – SauceDemo

Projeto de automação de testes end-to-end utilizando **[Playwright](https://playwright.dev/)** com **TypeScript** para o site [SauceDemo](https://www.saucedemo.com/).

Este projeto explora os **Playwright Agents** integrados ao VSCode — ferramentas de IA que auxiliam na criação de planos de teste em Markdown, na geração automática de código de testes e no diagnóstico de falhas.

---

## 🛠️ Tecnologias

| Ferramenta | Versão |
|---|---|
| [Playwright](https://playwright.dev/) | ^1.60.0 |
| TypeScript | via `@types/node ^25.9.1` |
| Node.js | 18+ recomendado |

---

## 📁 Estrutura do Projeto

```
UI-E2E-Playwright-Saucedemo.com/
├── .github/                    # Workflows de CI (GitHub Actions)
├── .vscode/                    # Configurações do VS Code
├── prompts/                    # Prompts utilizados com os Playwright Agents
├── specs/                      # Planos de teste em Markdown (gerados pelo Planner Agent)
├── tests/                      # Testes automatizados em TypeScript (gerados pelo Generator Agent)
├── .gitignore
├── package.json
├── playwright.config.ts        # Configuração do Playwright
└── README.md
```

---

## ⚙️ Configuração do Playwright

O arquivo `playwright.config.ts` define o seguinte comportamento:

- **`testDir`**: `./tests`
- **Paralelismo**: execução paralela completa (`fullyParallel: true`)
- **Retries**: 2 tentativas no CI, nenhuma localmente
- **Workers**: 1 no CI, automático no local
- **Reporter**: `html` (relatório interativo gerado automaticamente)
- **Trace**: coletado na primeira tentativa de retry (`on-first-retry`)

### Browsers Configurados

| Projeto | Browser |
|---|---|
| `chromium` | Desktop Chrome |
| `firefox` | Desktop Firefox |
| `webkit` | Desktop Safari |

---

## 🤖 Playwright Agents

Este projeto utiliza os três agentes integrados do Playwright para VSCode:

### 1. Planner
Gera planos de teste estruturados em formato Markdown, salvos na pasta `specs/`. Os planos descrevem os cenários de forma legível antes da implementação.

### 2. Generator
Lê os planos em Markdown e gera automaticamente o código dos testes em TypeScript, salvos na pasta `tests/`.

### 3. Healer
Diagnostica testes que estão falhando e sugere correções, mantendo a suíte atualizada mesmo quando a UI da aplicação muda.

---

## 🚀 Instalação

### Pré-requisitos

- Node.js 18+
- npm

### Passos

```bash
# Clone o repositório
git clone https://github.com/geovanegustavo/UI-E2E-Playwright-Saucedemo.com.git
cd UI-E2E-Playwright-Saucedemo.com

# Instale as dependências
npm install

# Instale os browsers do Playwright
npx playwright install
```

### Inicializar os Playwright Agents no VSCode

```bash
npx playwright init-agents --loop=vscode
```

---

## ▶️ Execução dos Testes

```bash
# Executar todos os testes (headless)
npx playwright test

# Executar com UI interativa (headed)
npx playwright test --headed

# Executar em um browser específico
npx playwright test --project=chromium
npx playwright test --project=firefox
npx playwright test --project=webkit

# Abrir o Playwright UI Mode (debug visual)
npx playwright test --ui

# Executar um arquivo de teste específico
npx playwright test tests/nome-do-arquivo.spec.ts
```

---

## 📊 Relatório HTML

Após a execução, o Playwright gera automaticamente um relatório HTML interativo:

```bash
# Abrir o relatório no browser
npx playwright show-report
```

---

## 🌐 Aplicação Testada

**SauceDemo** — [https://www.saucedemo.com](https://www.saucedemo.com)

Aplicação de e-commerce de demonstração da Sauce Labs, amplamente utilizada para prática de automação de testes de UI.

### Usuários disponíveis para testes

| Usuário | Senha | Comportamento |
|---|---|---|
| `standard_user` | `secret_sauce` | Fluxo padrão sem problemas |
| `locked_out_user` | `secret_sauce` | Bloqueado no login |
| `problem_user` | `secret_sauce` | Problemas na interface |
| `performance_glitch_user` | `secret_sauce` | Lentidão simulada |
| `error_user` | `secret_sauce` | Erros em ações específicas |
| `visual_user` | `secret_sauce` | Inconsistências visuais |

---

## 🔗 Links Úteis

- [Documentação Playwright](https://playwright.dev/docs/intro)
- [Playwright Agents (VSCode)](https://playwright.dev/docs/getting-started-vscode)
- [Playwright Test Reporter](https://playwright.dev/docs/test-reporters)
- [SauceDemo](https://www.saucedemo.com)

---

## 👤 Autor

**Geovane Gustavo**
[github.com/geovanegustavo](https://github.com/geovanegustavo)
