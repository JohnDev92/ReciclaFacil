# ReciclaFácil - Santa Cruz da Serra

## 📋 Descrição

ReciclaFácil é uma aplicação web interativa de mapeamento projetada para a comunidade de Santa Cruz da Serra, facilitando os esforços de reciclagem. A aplicação fornece uma interface de mapa interativo onde os usuários podem visualizar, adicionar e gerenciar pontos de coleta de reciclagem. Funciona como um serviço de localização que ajuda os moradores a encontrar instalações de reciclagem próximas e contribuir para as iniciativas ambientais da comunidade.

A aplicação foi construída como uma aplicação web leve, do lado do cliente, sem necessidade de servidor backend, facilitando sua implantação e manutenção.

## 🚀 Como Começar

1. Abra o arquivo `index.html` no seu navegador
2. Explore o mapa interativo e visualize os pontos de reciclagem disponíveis
3. Use o formulário para adicionar novos pontos de coleta
4. Gerenciede locais existentes através do painel lateral

## 🏗️ Arquitetura do Sistema

### Frontend

**Stack Tecnológico:**
- HTML/CSS/JavaScript puro (Vanilla JS, sem dependências de frameworks)
- Leaflet.js para funcionalidade de mapeamento interativo
- Plugin Leaflet MarkerCluster para agrupamento eficiente de marcadores
- Design responsivo com layout flexbox

**Componentes da Interface:**
1. **Contêiner do Mapa Interativo** - Exibição de mapa em tela cheia usando Leaflet
2. **Contêiner de Formulário** - Formulário sobreposto para adicionar novos pontos de reciclagem
3. **Painel Lateral** - Painel deslizável para gerenciar locais existentes
4. **Barra de Controle** - Barra fixa inferior contendo:
   - Botões de contato (esquerda): WhatsApp Disk Entulho e Prefeitura
   - Controles do mapa (direita): Alternância de camadas e alternância do painel lateral

### Recursos do Mapa

- Posicionamento interativo de marcadores
- Agrupamento de marcadores em áreas densas
- Controles de pan e zoom
- Integração de serviços baseados em localização

### Modelo de Dados

**Pontos de Reciclagem:**
- Nome/descrição da localização
- Coordenadas geográficas (latitude/longitude)
- Metadados do marcador (tipo, status, etc.)

A aplicação suporta operações CRUD através da interface do painel lateral (Criar via formulário, Ler via exibição de mapa, Excluir via botão "excluir").

## 📞 Recursos de Comunicação

**Integração de Contatos:**

- **WhatsApp Disk Entulho**: Link direto para (21) 99019-1331
  - Botão verde com emoji de telefone
  - Abre o WhatsApp com número pré-configurado  
  
- **Telefone Prefeitura**: Chamada direta para (21) 3900-1651
  - Botão azul com emoji de telefone
  - Horário de funcionamento: Seg-Sex 8h-17h
  - Abre o discador de telefone nativo em dispositivos móveis

## 📚 Dependências Externas

### Bibliotecas de Terceiros

1. **Leaflet.js** (CDN unpkg)
   - Funcionalidade de mapeamento interativo
   - Renderização de tiles, gerenciamento de marcadores, interações do usuário

2. **Leaflet MarkerCluster** (CDN unpkg)
   - Agrupamento eficiente de marcadores
   - Otimização de desempenho com múltiplos pontos de reciclagem

### Estratégia de CDN

Todas as dependências externas são carregadas via CDN unpkg:
- ✅ Sem processo de build necessário
- ✅ Setup mais rápido
- ✅ Armazenamento em cache automático
- ✅ Requisitos de hospedagem reduzidos

### Provedor de Tiles de Mapa

A aplicação utiliza OpenStreetMap ou provedores de tiles similares:
- Tiles carregados sob demanda ao fazer pan/zoom
- O armazenamento em cache do navegador trata solicitações repetidas de tiles

## 🔮 Considerações Futuras

A implementação atual é totalmente do lado do cliente. Possíveis integrações futuras incluem:
- API backend para armazenamento persistente de dados
- Serviço de autenticação para gerenciamento de usuários
- API de geolocalização para posicionamento automático do usuário
- Integrações de compartilhamento social
- Rastreamento de análise (Google Analytics ou similar)

## 🎯 Preferências

- **Estilo de Comunicação**: Linguagem simples e cotidiana
- **Idioma Preferido**: Português (Brasileiro)

## 📄 Licença

Este projeto está disponível sob licença MIT. Sinta-se livre para usar, modificar e distribuir conforme necessário.