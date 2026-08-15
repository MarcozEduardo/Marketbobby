
<div align="center">

# 🛒 MarketBobby

**Lista de compras inteligente com IA integrada**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Groq](https://img.shields.io/badge/Groq_AI-000000?style=for-the-badge&logo=groq&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)

<br>

*Sistema completo de lista de compras com organização por IA, leitura de fotos de preço, gráficos de gastos e reutilização de listas — tudo em um único arquivo HTML.*

<br>

[Funcionalidades](#-funcionalidades) •
[Como Usar](#-como-usar) •
[IA Integrada](#-ia-integrada) •
[Sobre o Projeto](#-sobre-o-projeto)

</div>

---

## ✨ Funcionalidades

### Lista Inteligente
- **Criação rápida** — digite itens separados por vírgula
- **Organização por IA** — a IA categoriza, entende contexto e separa marcas
- **Categorias automáticas** — Hortifruti, Carnes, Laticínios, Mercearia, Limpeza, Higiene, Bebidas, Padaria
- **Edição inline** — toque no nome, marca ou preço para editar direto na lista

### Controle de Preço
- **3 estados visuais** — item normal, no carrinho (verde) ou sem preço (amarelo piscando)
- **Soma automática** — só itens com preço entram na conta
- **Alerta visual** — aviso quando item está sem preço no carrinho

### Foto de Preço
- **Leitura por câmera** — tire foto da placa de preço no mercado
- **IA preenche tudo** — nome, preço, marca e peso extraídos automaticamente
- **Contexto de quantidade** — digite "3" antes da foto e a IA entende que são 3 unidades

### Gestão de Listas
- **Finalizar carrinho** — marca lista como concluída com registro de data
- **Reutilizar lista** — crie nova lista a partir de uma finalizada, escolhendo o que manter
- **Abas organizadas** — listas abertas e finalizadas separadas
- **Excluir com confirmação** — popups de confirmação com animação

### Resumo & Gráficos
- **4 tipos de gráfico** — Pizza, Barras, Linha e Rosca (Canvas)
- **Total por categoria** — veja onde seu dinheiro vai
- **Filtros de período** — preparado para crescer (Semana, Mês, Ano)

### UX Profissional
- **Design mobile-first** — interface de app nativo
- **Pixel art** — carrinho de compras em pixel art no canvas
- **Animações suaves** — transições, popups e feedback visual
- **Dados persistentes** — tudo salvo no localStorage
- **Zero dependência de backend** — funciona 100% no navegador

---

## 🚀 Como Usar

### 1. Abrir o app
Basta abrir o arquivo `index.html` no navegador. Sem instalação, sem servidor.

### 2. Configurar IA (opcional)
Vá em **Configurações → APIs** e adicione suas chaves:

| Serviço | Para quê | Onde conseguir |
|---------|----------|----------------|
| **Groq** | Organizar lista com IA | [console.groq.com](https://console.groq.com) |
| **Mistral** | Alternativa de organização | [console.mistral.ai](https://console.mistral.ai) |
| **Google Gemini** | Leitura de fotos de preço | [aistudio.google.com](https://aistudio.google.com) |

> As chaves ficam salvas **apenas no seu navegador** (localStorage). Nada é enviado para servidores externos além das próprias APIs.

### 3. Criar uma lista
- Toque em **Nova Lista**
- Digite os itens separados por vírgula
- Escolha **Organizar IA** ou **Direto**

### 4. No mercado
- Marque itens no carrinho com o check
- Adicione preços tocando no campo `R$ ?`
- Use o botão **+** para adicionar itens na hora
- Tire foto da placa de preço com o botão de câmera

---

## 🤖 IA Integrada

O MarketBobby entende contexto brasileiro:

| Você digita | IA entende |
|-------------|------------|
| `ovo` | Bandeja de ovos (30 unidades) |
| `arroz` | Arroz 5kg (pacote padrão) |
| `feijão` | Feijão 1kg |
| `creme` | Creme hidratante capilar |
| `café` | Café em pó 500g |
| `3 arroz Flora` | 3x Arroz, marca Flora |

### Compatibilidade de APIs

O sistema funciona com qualquer API compatível com o formato OpenAI Chat Completions:

- **Groq** (gratuito, rápido)
- **Mistral AI** (gratuito até certo uso)
- **OpenRouter** (acesso a múltiplos modelos)
- **Qualquer LLM** com endpoint compatível

Para leitura de imagens:
- **Google Gemini Vision** (gratuito)

---

## 🏗️ Arquitetura
MarketBobby/
├── index.html ← Aplicação completa (HTML + CSS + JS)
├── README.md ← Este arquivo
└── LICENSE ← MIT License

text


### Stack
- **Frontend:** HTML5 + CSS3 + JavaScript vanilla
- **Gráficos:** Canvas API nativa
- **Armazenamento:** localStorage
- **IA:** API REST (Groq/Mistral/Gemini)
- **Dependências externas:** Font Awesome 6 + Google Fonts (Nunito)

### Decisão de Arquivo Único
O projeto inteiro vive em um único `index.html` por decisão de design:
- Demonstra domínio da base (sem frameworks)
- Portabilidade total (abre em qualquer lugar)
- Facilita review de código
- ~1500+ linhas organizadas e comentadas com índice

---

## 📱 Screenshots

> *Em breve — tire prints do app e adicione aqui*

---

## 🧑‍💻 Sobre o Projeto

**MarketBobby** foi construído em **14/08/2026**, em aproximadamente **5 horas de iteração direta** entre **Marcos Eduardo** e **Bobby IA**.

Nenhuma linha de código foi escrita manualmente. Todo o sistema foi **orquestrado por Marcos** e **produzido por Bobby IA** — utilizada como instrumento de desenvolvimento.

### O Processo

Marcos não tem formação tradicional em programação. Mas tem algo que muitos desenvolvedores experientes não têm: **a capacidade de entender o que um sistema precisa**.

- Faz as perguntas certas
- Debugga UX observando comportamento
- Arquiteta fluxos de interface
- Analisa engenharia de interação
- Itera sem descansar até atingir excelência

**Hiperfocado e perfeccionista**, ele guia a IA linha por linha, iteração após iteração, até o resultado ficar no padrão que imaginou.

### Ficha Técnica

| Item | Detalhe |
|------|---------|
| **Data** | 14 de agosto de 2026 |
| **Tempo** | ~5 horas de iteração |
| **Método** | Orquestração humana + produção IA |
| **Custo** | R$ 0 (IA gratuita) |
| **Código manual** | 0 linhas |
| **Resultado** | Sistema completo e funcional |

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

<div align="center">

Feito com ❤️ por [Marcos Eduardo](https://www.linkedin.com/in/sir-marcos-eduardo/) + Bobby IA

**Portfolio 2026**

</div>
