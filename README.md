# Projeto de Testes Automatizados com Cypress

Este projeto contém testes automatizados end-to-end (E2E) para a aplicação Adopet usando Cypress.

## 📋 Pré-requisitos

- Node.js (versão 14 ou superior)
- npm ou yarn

## 🚀 Instalação

1. Clone o repositório:
```bash
git clone https://github.com/rafaelgoesti/adopet-cypress-tests.git
cd Cypress
```

2. Instale as dependências:
```bash
npm install
```

## 🧪 Executando os Testes

### Modo Interativo (Cypress Dashboard)
```bash
npx cypress open
```

### Modo Headless (linha de comando)
```bash
npx cypress run
```

### Executar testes específicos
```bash
npx cypress run --spec "cypress/e2e/login-correto.cy.js"
```

## 📁 Estrutura do Projeto

```
cypress/
├── e2e/                    # Testes end-to-end
│   ├── api-mensagens.cy.js
│   ├── cadastro-correto.cy.js
│   ├── cadastro-incorreto.cy.js
│   ├── cadastro-massa.cy.js
│   ├── login-correto.cy.js
│   └── login-incorreto.cy.js
├── fixtures/               # Dados de teste estáticos
│   ├── example.json
│   └── usuarios.json
├── results/               # Relatórios de teste (Mochawesome)
├── screenshots/           # Screenshots de falhas
├── support/               # Comandos customizados
│   ├── commands.js
│   └── e2e.js
└── videos/               # Gravações dos testes
```

## 📊 Relatórios

Os testes geram relatórios HTML usando Mochawesome, que são salvos em `cypress/results/`.

### Configuração do Reporter
- **Reporter**: Mochawesome
- **Diretório**: `cypress/results`
- **Formato**: HTML com timestamp

## 🔧 Configurações

### Cypress Configuration (`cypress.config.js`)
- Vídeos habilitados para todos os testes
- Reporter configurado para Mochawesome
- Project ID configurado para Cypress Dashboard

### Variáveis de Ambiente
Configure suas variáveis de ambiente no arquivo `cypress.env.json`:
```json
{
  "baseUrl": "https://adopet-frontend-cypress.vercel.app/",
  "apiUrl": "sua-api-url-aqui"
}
```

## 🧩 Comandos Customizados

O projeto inclui comandos customizados definidos em `cypress/support/commands.js`:

- `cy.login(email, password)` - Comando para realizar login

## 📝 Cenários de Teste

### Login
- ✅ Login com credenciais corretas
- ❌ Login com credenciais incorretas

### Cadastro
- ✅ Cadastro com dados válidos
- ❌ Cadastro com dados inválidos
- 📊 Cadastro em massa (data-driven testing)

### API
- 🔌 Testes de API para mensagens

## 🏃‍♂️ Scripts NPM

Adicione estes scripts ao seu `package.json`:

```json
{
  "scripts": {
    "cy:open": "cypress open",
    "cy:run": "cypress run",
    "cy:run:headed": "cypress run --headed",
    "cy:run:chrome": "cypress run --browser chrome",
    "cy:run:firefox": "cypress run --browser firefox"
  }
}
```

## 📸 Screenshots e Vídeos

- Screenshots são capturadas automaticamente em caso de falha
- Vídeos são gravados para todos os testes
- Arquivos são salvos nas pastas `cypress/screenshots/` e `cypress/videos/`

## 🤝 Contribuindo

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT.

## 🔗 Links Úteis

- [Documentação do Cypress](https://docs.cypress.io/)
- [Mochawesome Reporter](https://github.com/adamgruber/mochawesome)
- [Aplicação Adopet](https://adopet-frontend-cypress.vercel.app/)

---

**Última atualização**: 14 de setembro de 2025
