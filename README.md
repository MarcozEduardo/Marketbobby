<div align="center">

# 🛒 MarketBobby

**Lista de compras inteligente com IA integrada**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![Groq](https://img.shields.io/badge/Groq_AI-000000?style=for-the-badge&logo=groq&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)

<br>

*Sistema completo de lista de compras com organização por IA, leitura de fotos de preço, gráficos de gastos, reutilização de listas e suporte opcional a backend serverless via Firebase.*

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
- **Suporte a encartes e múltiplos produtos** — leitura de fotos com mais de um item visível
- **Fallback entre modelos** — se um modelo falhar, o sistema tenta outro automaticamente

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
- **Modo local ou com backend** — funciona no navegador com chave própria ou em modo demonstração via Firebase

---

## 🚀 Como Usar

### 1. Abrir o app
Basta abrir o arquivo `index.html` no navegador. Sem instalação, sem servidor para a interface principal.

### 2. Escolher o modo de uso
O sistema pode funcionar de duas formas:

#### **Modo Bobby**
Usa **Firebase Cloud Functions** para permitir demonstração pronta do sistema, sem exigir configuração manual de chave por parte do visitante.

#### **Modo Local**
Permite que o usuário configure suas próprias chaves de API, que ficam salvas apenas no navegador via `localStorage`.

### 3. Configurar IA (opcional no modo local)
Vá em **Configurações → APIs** e adicione suas chaves:

| Serviço | Para quê | Onde conseguir |
|---------|----------|----------------|
| **Groq** | Organizar lista com IA | [console.groq.com](https://console.groq.com) |
| **Mistral** | Alternativa de organização | [console.mistral.ai](https://console.mistral.ai) |
| **Google Gemini** | Leitura de fotos de preço | [aistudio.google.com](https://aistudio.google.com) |

> No **modo local**, as chaves ficam salvas **apenas no seu navegador** (`localStorage`).  
> No **modo Bobby**, as chamadas passam pelo Firebase para proteger as chaves da demonstração.

### 4. Criar uma lista
- Toque em **Nova Lista**
- Digite os itens separados por vírgula
- Escolha **Organizar IA** ou **Direto**

### 5. No mercado
- Marque itens no carrinho com o check
- Adicione preços tocando no campo de valor
- Use o botão **+** para adicionar itens na hora
- Tire foto da placa de preço com o botão de câmera
- Use encartes, etiquetas e produtos como entrada para a IA

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

O sistema trabalha com duas camadas de IA:

#### Organização textual
Usa modelos compatíveis com o formato **OpenAI Chat Completions** para organizar listas informais.

Exemplos de provedores suportados:
- **Groq**
- **Mistral AI**
- **OpenRouter**
- **DeepSeek**
- **Together**
- **Fireworks**
- **Perplexity**
- **Qualquer LLM** com endpoint compatível

#### Leitura de imagens
Usa **Google Gemini Vision** para:
- foto de produto
- placa de preço
- encarte
- cupom
- lista fotografada

### Estratégia de robustez
O sistema foi refinado para usar:
- **fallback entre modelos**
- **fallback entre chaves**
- **tratamento de erro**
- **extração orientada a preço**
- **normalização de resposta**

Isso evita dependência cega de um único modelo.

---

## 🏗️ Arquitetura

```text
MarketBobby/
├── index.html        ← Aplicação principal (HTML + CSS + JS)
├── README.md         ← Este arquivo
├── CASE_STUDY.md     ← Bastidores, processo e decisões do projeto
├── LICENSE           ← MIT License
└── functions/        ← Firebase Cloud Functions
```

### Stack
- **Frontend:** HTML5 + CSS3 + JavaScript vanilla
- **Gráficos:** Canvas API nativa
- **Armazenamento:** localStorage
- **Backend opcional:** Firebase Cloud Functions
- **IA:** API REST (Groq/Mistral/Gemini e compatíveis)
- **Dependências externas:** Font Awesome 6 + Google Fonts (Nunito)

### Decisão de Arquitetura
O frontend principal vive em um único `index.html` por decisão de design:

- demonstra domínio da base (sem frameworks)
- mantém alta portabilidade
- facilita review de código
- permite abertura rápida em qualquer ambiente
- reduz complexidade visual do projeto

Ao mesmo tempo, o sistema evoluiu para suportar **backend serverless opcional**, permitindo proteger chaves, viabilizar o modo demonstração e ampliar a robustez da integração com IA.

---

## 📱 Screenshots

> *Em breve — adicionar prints do app em uso, da tela de lista, do resumo e da leitura por foto.*

---

## 🧑‍💻 Sobre o Projeto

**MarketBobby** foi iniciado em **14/08/2026**.

A base funcional do sistema nasceu em aproximadamente **5 horas de iteração direta**, mas o projeto evoluiu muito além disso, com cerca de **15 horas adicionais de refinamento técnico**, integração com Firebase, OCR de preços, fallback entre modelos, ajustes de parser e melhorias de UX.

Ou seja: a primeira versão saiu rápido, mas a maturidade do sistema veio na batalha.

O projeto deixou de ser apenas uma lista de compras e passou a ser um estudo prático de:

- integração com IA
- experiência de usuário
- debugging em camadas
- fallback entre provedores
- leitura de imagem
- arquitetura híbrida entre frontend local e backend serverless

### O Processo

Marcos não tem formação tradicional em programação. Mas tem algo que muitos desenvolvedores experientes não têm: **a capacidade de entender o que um sistema precisa**.

- Faz as perguntas certas
- Debugga UX observando comportamento
- Arquiteta fluxos de interface
- Analisa engenharia de interação
- Itera sem descansar até atingir excelência
- Não aceita solução preguiçosa
- Testa cenário real
- Insiste até o sistema fazer sentido

**Hiperfocado e perfeccionista**, conduziu a IA linha por linha, iteração após iteração, até o resultado ficar no padrão que imaginou.

### O que foi necessário enfrentar
Ao longo da construção, o projeto passou por desafios reais como:

- integração com Firebase Cloud Functions
- deploy quebrando por mudança de versão de biblioteca
- `functions.config()` removido em versões novas
- benchmark e escolha de modelos de IA
- extração de preço em formato brasileiro
- parser quebrando centavos por causa da vírgula
- duplicidade de função no frontend
- placeholder mascarando valor real
- ajustes finos de loading e feedback visual

### Ficha Técnica

| Item | Detalhe |
|------|---------|
| **Data de início** | 14 de agosto de 2026 |
| **Base funcional** | ~5 horas |
| **Refinamento adicional** | ~15 horas |
| **Método** | Orquestração humana + produção IA |
| **Custo** | R$ 0 (IA gratuita + backend leve) |
| **Código manual** | 0 linhas em escrita tradicional |
| **Resultado** | Sistema funcional, demonstrável e pronto para portfólio |

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

<div align="center">

Feito com ❤️ por [Marcos Eduardo](https://www.linkedin.com/in/sir-marcos-eduardo/) + Bobby IA

**Portfolio 2026**

</div>

---

## 📚 Case do Projeto

O **MarketBobby** começou como uma ideia simples de lista de compras, mas rapidamente evoluiu para um sistema muito mais completo.

A proposta inicial era criar algo visualmente bonito, intuitivo e útil no dia a dia. Ao longo das iterações, o projeto deixou de ser apenas um CRUD e passou a incorporar:

- organização inteligente de itens
- categorização automática
- controle visual de status
- cálculo dinâmico de gastos
- reaproveitamento de listas
- leitura assistida por IA
- OCR orientado a preço
- fallback entre modelos
- backend opcional com Firebase
- UX pensada para uso real no mercado

O grande diferencial do projeto foi o processo de construção:  
**Marcos Eduardo orquestrou toda a lógica, estrutura e experiência do sistema usando IA como ferramenta de produção**, refinando comportamento, layout, estados visuais, fallback, parser, integração com imagem e decisões de fluxo a cada nova interação.

Mais do que escrever código, o foco foi:
- entender o problema
- modelar a experiência
- observar falhas
- corrigir a interface
- transformar um app simples em um produto com cara de solução real

Esse projeto representa a capacidade de transformar visão em software funcional, mesmo sem depender de conhecimento técnico tradicional completo da linguagem.

➡️ Para mais detalhes, veja o arquivo [CASE_STUDY.md](./CASE_STUDY.md)
