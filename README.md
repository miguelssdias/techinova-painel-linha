# 🏭 TechInova - Painel de Linha

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Status](https://img.shields.io/badge/status-ativo-brightgreen.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

O **TechInova - Painel de Linha** é uma solução completa para monitoramento, controle e visualização em tempo real do chão de fábrica. Desenvolvido para transformar dados operacionais em insights visuais imediatos, o painel permite acompanhar o desempenho de linhas de produção, indicadores OEE, andamento de ordens de fabricação (OPs) e ocorrências de paradas de forma simples e intuitiva.

---

## 📌 Sumário

- [Visão Geral](#-visão-geral)
- [Funcionalidades Principais](#-funcionalidades-principais)
- [Arquitetura e Tecnologias](#-arquitetura-e-tecnologias)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Pré-requisitos](#-pré-requisitos)
- [Instalação e Execução](#-instalação-e-execução)
- [Variáveis de Ambiente](#-variáveis-de-ambiente)
- [Modo TV / Kiosk](#-modo-tv--kiosk)
- [Contribuição](#-contribuição)
- [Licença](#-licença)

---

## 👁️ Visão Geral

Nas operações industriais modernas, a visibilidade em tempo real do processo produtivo é fundamental para minimizar tempos de inatividade (*downtime*) e garantir a máxima eficiência. O **Painel de Linha TechInova** foi projetado para atender tanto telas de operação e tablets de supervisão quanto grandes exibições (TVs/Monitores) no chão de fábrica, garantindo alta legibilidade e atualização contínua de dados sem necessidade de recarregar a página.

---

## ✨ Funcionalidades Principais

- ⚡ **Monitoramento em Tempo Real**: Atualizações automáticas de status via WebSockets/Sockets sem necessidade de *refresh*.
- 📊 **Indicadores OEE (Overall Equipment Effectiveness)**:
  - **Disponibilidade**: Percentual de tempo em operação efetiva vs. tempo planejado.
  - **Desempenho**: Velocidade atual de produção em relação ao ciclo padrão.
  - **Qualidade**: Contagem de peças boas vs. refugos/retrabalhos.
- 📋 **Gestão de Ordens de Produção (OP)**: Acompanhamento numérico e percentual da meta do turno/dia, lote atual e tempo estimado de conclusão (*ETA*).
- 🚨 **Central de Alertas e Ocorrências**: Registro instantâneo de paradas (manutenção, falta de insumo, setup, falha de qualidade) com temporizador ativo.
- 📺 **Otimização para Modo Kiosk (TV Industrial)**: Layout expansível, alto contraste e elementos visuais adaptados para leitura à distância.
- 👥 **Gestão de Turnos e Operadores**: Identificação visual dos responsáveis e troca rápida de turnos.
- 📈 **Relatórios e Histórico**: Exportação de logs de produção e gráficos de tendência por linha.

---

## 🛠️ Arquitetura e Tecnologias

O projeto é estruturado utilizando tecnologias modernas focadas em alto desempenho e responsividade:

### **Frontend & Interface**
- **React.js / Next.js**: Biblioteca/Framework para renderização ágil de componentes.
- **Tailwind CSS**: Estilização utilitária moderna e totalmente responsiva.
- **Lucide Icons / Feather**: Coleção de ícones vetoriais leves.
- **Recharts / Chart.js**: Gráficos dinâmicos para visualização de métricas e tendências.

### **Backend & Comunicação em Tempo Real**
- **Node.js (Express) / Python (FastAPI)**: Serviços de API RESTful.
- **Socket.io / WebSockets**: Transmissão bidirecional de eventos e telemetria de sensores/CLPs em tempo real.

### **Banco de Dados & Cache**
- **PostgreSQL**: Armazenamento relacional para dados operacionais e históricos.
- **Redis**: Gerenciamento de sessões, cache e pub/sub de mensageria instantânea.

### **DevOps & Containers**
- **Docker & Docker Compose**: Padronização dos ambientes de desenvolvimento e produção.

---

## 📁 Estrutura do Projeto

```text
techinova-painel-linha/
├── public/                  # Arquivos estáticos, favicons e assets visuais
├── src/
│   ├── assets/              # Imagens, estilos globais e fontes
│   ├── components/          # Componentes Reutilizáveis
│   │   ├── Cards/           # Cards de métricas (KPIs, OEE, Produção)
│   │   ├── Charts/          # Componentes de gráficos interativos
│   │   ├── Header/          # Cabeçalho com relógio, status da conexão e linha
│   │   └── Modals/          # Modais de registro de parada e observações
│   ├── hooks/               # Custom Hooks (ex: useWebSocket, useProductionData)
│   ├── pages/ / app/        # Páginas e rotas da aplicação
│   ├── services/            # Clientes HTTP (Axios) e conexão WebSocket
│   ├── styles/              # Configurações do Tailwind e CSS global
│   └── utils/               # Funções utilitárias e formatadores
├── .env.example             # Modelo de variáveis de ambiente
├── .gitignore               # Arquivos ignorados pelo Git
├── docker-compose.yml       # Orquestração dos containers Docker
├── Dockerfile               # Configuração da imagem de produção
├── package.json             # Dependências e scripts do Node.js
└── README.md                # Documentação do projeto
