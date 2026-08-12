# 📊 TechInova — Painel da Linha 3

Painel web desenvolvido para monitoramento das informações de sensores da **Linha 3 da TechInova**.

A aplicação apresenta as leituras dos sensores em uma interface simples e objetiva, permitindo visualizar o código, a descrição, a temperatura convertida para Celsius e o status de cada sensor. Os dados são carregados dinamicamente a partir de um arquivo JSON.

---

## 🚀 Funcionalidades

* 📡 Carregamento dos dados dos sensores através de arquivo JSON.
* 🌡️ Conversão automática de temperatura de Fahrenheit para Celsius.
* 📋 Exibição dos sensores em formato de tabela.
* 🟢 Identificação do status dos sensores.
* 🕐 Exibição da data e hora da última atualização.
* ⚠️ Estrutura preparada para exibição de alertas.
* 📁 Organização dos arquivos por responsabilidade.

---

## 🛠️ Tecnologias utilizadas

* **HTML5** — estrutura da aplicação.
* **CSS3** — estilização e apresentação visual.
* **JavaScript** — lógica, carregamento dos dados e atualização do painel.
* **JSON** — armazenamento dos dados dos sensores.
* **Git/GitHub** — versionamento e colaboração.

O projeto utiliza uma estrutura web simples, sem dependência de frameworks ou bibliotecas externas.

---

## 📂 Estrutura do projeto

```text
techinova-painel-linha/
│
├── .github/
│
├── config/
│   └── README.md
│
├── css/
│   └── style.css
│
├── dados/
│   └── sensores.json
│
├── js/
│   └── painel.js
│
├── .gitignore
├── index.html
├── README.md
└── RESPOSTAS.md
```

### Principais arquivos

#### `index.html`

Arquivo principal da aplicação.

É responsável pela estrutura do painel, incluindo:

* título do sistema;
* tabela de sensores;
* área de alertas;
* informação da última atualização;
* carregamento do JavaScript responsável pelo funcionamento do painel.

#### `css/style.css`

Arquivo responsável pela estilização e apresentação visual do painel.

#### `js/painel.js`

Contém a lógica principal da aplicação.

Entre suas responsabilidades estão:

* buscar os dados em `dados/sensores.json`;
* converter as temperaturas;
* criar dinamicamente as linhas da tabela;
* atualizar a data e hora exibida no painel.

#### `dados/sensores.json`

Arquivo utilizado como fonte de dados dos sensores.

Os dados são carregados pelo JavaScript através de uma requisição `fetch`.

#### `config/`

Diretório destinado às configurações relacionadas ao acesso ao broker. A documentação presente no projeto indica que as credenciais devem ser mantidas em um arquivo `credenciais.env`.

#### `RESPOSTAS.md`

Documento contendo as respostas e registros relacionados às atividades do laboratório, incluindo questões sobre Git, histórico de commits, conflitos e segurança de credenciais.

---

## 🌡️ Conversão de temperatura

As leituras recebidas pelo painel são convertidas de **Fahrenheit para Celsius** utilizando a fórmula:

```text
°C = (°F - 32) × 5/9
```

A conversão é realizada pela função `converterTemperatura()` presente no arquivo `js/painel.js`.

---

## ▶️ Como executar

Como o projeto é uma aplicação web estática, basta clonar o repositório e abrir o projeto através de um servidor local.

### 1. Clone o repositório

```bash
git clone https://github.com/miguelssdias/techinova-painel-linha.git
```

### 2. Acesse a pasta

```bash
cd techinova-painel-linha
```

### 3. Execute com um servidor local

Uma opção é utilizar o **Live Server** no Visual Studio Code.

Também é possível utilizar um servidor HTTP simples, por exemplo:

```bash
python -m http.server 8000
```

Depois, acesse:

```text
http://localhost:8000
```

> Recomenda-se utilizar um servidor local porque a aplicação realiza uma requisição `fetch()` para carregar o arquivo `dados/sensores.json`.

---

## 📊 Funcionamento

O fluxo básico da aplicação é:

```text
┌──────────────────────┐
│      index.html      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│      painel.js       │
└──────────┬───────────┘
           │
           │ fetch()
           ▼
┌──────────────────────┐
│   sensores.json      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Conversão Fahrenheit │
│      → Celsius       │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  Tabela de sensores  │
└──────────────────────┘
```

---

## 🔐 Segurança

Informações sensíveis, como credenciais de acesso a serviços externos ou brokers, **não devem ser armazenadas diretamente no código-fonte ou versionadas no Git**.

O projeto possui uma pasta `config/` destinada às configurações e documenta o uso de um arquivo `credenciais.env`.

Caso uma credencial tenha sido publicada acidentalmente em algum commit, apenas apagar o arquivo no commit atual **não é suficiente**, pois informações antigas podem continuar disponíveis no histórico do Git.

---

## 🧪 Projeto acadêmico

Este projeto faz parte de uma atividade prática envolvendo desenvolvimento web, manipulação de dados, Git e fluxo de colaboração em equipe.

O repositório também registra atividades relacionadas a:

* identificação de alterações em commits;
* análise do histórico do Git;
* resolução de conflitos;
* boas práticas de segurança;
* trabalho colaborativo utilizando Git.

---

## 👨‍💻 Autor

**Miguel Santana Dias**

Projeto: **TechInova — Painel da Linha 3**

---

## 📄 Licença

Este projeto não possui uma licença open source especificada no repositório no momento.
