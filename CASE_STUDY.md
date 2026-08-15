# Case Study — MarketBobby

## Visão Geral

O **MarketBobby** é um aplicativo de lista de compras com foco em praticidade, organização visual e apoio de IA para reduzir atrito no uso cotidiano.

O sistema foi pensado para parecer um aplicativo real de mercado: leve, bonito, direto e funcional, com decisões de UX voltadas para uso rápido no celular.

---

## Contexto

Este projeto foi construído em **14/08/2026**, em aproximadamente **5 horas diretas de iteração**, como parte de uma proposta de portfólio.

A intenção não era apenas “mostrar código”, mas demonstrar:

- capacidade de arquitetar uma solução
- visão de produto
- leitura crítica de UX
- entendimento de comportamento do usuário
- habilidade de usar IA como instrumento de desenvolvimento

---

## Problema

Listas de compras costumam falhar em 3 pontos:

1. **são feias ou engessadas**
2. **não ajudam na organização do gasto**
3. **não acompanham o ritmo real de quem está no mercado**

Além disso, sistemas simples de checklist geralmente não resolvem:
- separação por categoria
- reaproveitamento de listas
- controle de preço por item
- entrada dinâmica de informação
- experiência mobile de verdade

---

## Objetivo

Criar uma aplicação com aparência profissional e utilidade real, capaz de:

- registrar listas de compras
- permitir edição rápida e intuitiva
- apoiar o usuário no controle de valor
- diferenciar itens apenas listados, itens no carrinho e itens sem preço
- reaproveitar listas anteriores
- gerar visão resumida de gasto
- servir como projeto forte de portfólio

---

## Estratégia de Produto

O sistema foi desenhado para unir 3 camadas:

### 1. Camada operacional
A lista precisa funcionar rápido:
- adicionar item
- marcar item
- editar preço
- somar total

### 2. Camada visual
O usuário precisa entender o estado de cada item sem esforço:
- verde = item resolvido / no carrinho
- amarelo = item marcado sem preço
- neutro = item ainda em aberto

### 3. Camada de expansão
Mesmo em versão portfolio, o sistema já precisava parecer preparado para crescer:
- filtros de resumo
- múltiplos gráficos
- listas finalizadas
- reutilização de listas
- integração com IA
- leitura por imagem

---

## Solução Implementada

O projeto evoluiu para incluir:

- **criação de listas livres**
- **organização por IA**
- **classificação por categorias**
- **check visual inteligente**
- **controle de preço por item**
- **soma automática do carrinho**
- **estado visual de atenção para item sem preço**
- **resumo geral com gráficos**
- **modo lista finalizada**
- **reutilização de listas anteriores**
- **configuração de perfil**
- **estrutura preparada para APIs**
- **layout mobile-first**
- **pixel art personalizada**

---

## Decisões Técnicas

### Arquivo único
Foi adotada uma estrutura em **HTML + CSS + JavaScript puro**, concentrada em um único arquivo principal.

**Motivo:**
- facilitar portabilidade
- facilitar demonstração
- evitar complexidade desnecessária
- mostrar domínio da base sem depender de framework

### localStorage
Foi escolhido **localStorage** como persistência.

**Motivo:**
- simplicidade
- zero backend
- facilidade para deploy
- foco no produto e na experiência

### Canvas para gráficos
Os gráficos foram tratados em **Canvas** para reforçar controle visual e estética customizada.

### IA como motor auxiliar
A IA foi tratada como camada opcional de inteligência:
- organizar lista textual
- interpretar contexto de produto
- preparar expansão para imagem

---

## Processo de Construção

O MarketBobby não foi feito por código manual tradicional.

Ele foi construído por **orquestração iterativa**:
- observação
- teste
- crítica
- correção
- refinamento

A cada etapa, o sistema era avaliado não só pelo que fazia, mas por:
- como parecia
- como reagia
- como comunicava estado
- como o usuário se sentiria usando

Esse processo mostrou uma habilidade essencial:
> construir software não é apenas saber sintaxe, mas compreender estrutura, lógica, experiência e necessidade.

---

## Papel de Marcos Eduardo

Marcos foi responsável por:

- definir a proposta do produto
- observar inconsistências de UX
- detectar excesso ou falta de informação
- ajustar estados visuais
- decidir o que deveria ou não existir
- conduzir o refinamento do sistema
- transformar uma ideia simples em uma solução mais madura

Mesmo sem fluência completa na linguagem ou nos termos técnicos mais formais, demonstrou:

- leitura lógica
- visão de engenharia de produto
- capacidade de debug
- pensamento sistêmico
- direção clara de evolução

---

## Resultado

O resultado final deixou de ser apenas uma “lista de compras” e passou a ser um **app utilitário com potencial real de uso**, além de um projeto forte de apresentação em portfólio.

O sistema demonstra:

- domínio de fluxo CRUD expandido
- visão de UX/UI
- modelagem de estados
- preparação para escala
- uso prático e inteligente de IA
- capacidade de transformar iteração em produto

---

## Próximos Passos

Melhorias futuras previstas:

- copiar lista pronta para WhatsApp
- múltiplos modos de exportação
- favoritos de compra
- histórico temporal real para gráficos
- leitura mais robusta por imagem
- integração com modelos de IA alternativos
- melhorias no resumo de carrinho
- compartilhamento de listas

---

## Conclusão

O MarketBobby é a prova de que **capacidade de construir software não depende apenas de escrever código manualmente**, mas também de:

- fazer as perguntas certas
- entender o problema
- conduzir decisões
- iterar com critério
- usar IA como instrumento de produção

Este projeto representa exatamente isso.
