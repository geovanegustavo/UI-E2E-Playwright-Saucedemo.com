# Playwright Tests – SauceDemo

Projeto de automação de testes end-to-end utilizando **[Playwright](https://playwright.dev/)** para o site [SauceDemo](https://www.saucedemo.com/).

Este repositório utiliza os **agentes do Playwright** para gerar arquivos no formato Markdown `.md` com cenários de testes e implementações dos próprios testes automatizados em si.  
Os casos incluem login, fluxo de compra, manipulação de carrinho e checkout.

---

## Instalação

Para instalar o Playwright no projeto, execute o seguinte comando:

```bash
npm init playwright@latest
```

Este comando irá:
- Instalar as dependências necessárias do Playwright
- Configurar os arquivos de configuração padrão
- Criar a estrutura de diretórios para os testes

## Agentes de Testes

O Playwright oferece três agentes de teste integrados ao VSCode que auxiliam na automação:

### Inicializar Agentes no VSCode

Para instalar os agentes do Playwright no VSCode, execute:

```bash
npx playwright init-agents --loop=vscode
```

### Agentes Disponíveis

1. **Planner** - Cria planos de teste estruturados em Markdown
2. **Generator** - Gera implementações de testes automatizados baseados nos planos
3. **Healer** - Diagnostica e corrige testes que estão falhando

---

