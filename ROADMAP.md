# Roadmap — MarketBobby

> Planejamento de evolução do sistema.
> Itens marcados estão implementados, desmarcados são melhorias futuras.

---

## ✅ Implementado (v1.0)

- [x] Criação de listas com texto livre
- [x] Separação automática por vírgula
- [x] Organização por IA com categorização
- [x] 3 estados visuais de item (normal, carrinho, sem preço)
- [x] Controle de preço por item
- [x] Soma automática do carrinho
- [x] Alerta visual para itens sem preço
- [x] Finalizar carrinho com registro
- [x] Reutilizar listas finalizadas
- [x] Resumo geral com 4 tipos de gráfico
- [x] Leitura de foto de preço com Gemini
- [x] Perfil do usuário
- [x] Configuração de APIs
- [x] Pixel art personalizada em Canvas
- [x] Layout mobile-first
- [x] Persistência em localStorage
- [x] Seção "Sobre Nós" com carrossel

---

## 🔄 Em Desenvolvimento (v1.1)

### Compartilhamento
- [ ] Copiar lista pronta para WhatsApp em um clique
- [ ] Mensagem formatada automática (itens + quantidades + preços)
- [ ] Modo "só carrinho" para compartilhar apenas o que foi pego
- [ ] Modo "lista completa" com tudo que falta
- [ ] Copiar resumo de gastos para compartilhar

### IA — Evolução
- [ ] Detecção automática de provedor pela API Key
- [ ] Usuário cola a key, sistema identifica o provedor
- [ ] Seleção de modelo pelo usuário (lista de modelos disponíveis)
- [ ] Prompt interno mais robusto e contextualizado
- [ ] Firewall de prompt — proteção contra manipulação da IA
- [ ] Sanitização de entrada do usuário
- [ ] Validação de resposta da IA antes de processar
- [ ] Fallback local se IA falhar (categorização offline)

### Segurança
- [ ] Proteção contra injeção de prompt
- [ ] Rate limiting local (evitar spam de requisições)
- [ ] Validação de formato de API Key antes de salvar
- [ ] Limpeza automática de dados sensíveis em memória
- [ ] Aviso visual quando key está inválida ou expirada

---

## 📋 Planejado (v1.2)

### Lista e Carrinho
- [ ] Ordenação manual de itens (arrastar)
- [ ] Agrupar itens iguais automaticamente
- [ ] Modo "compra rápida" (só check, sem preço obrigatório)
- [ ] Duplicar item dentro da lista
- [ ] Notas por item (ex: "pegar o da promoção")
- [ ] Histórico de preço por produto
- [ ] Alerta de preço acima da média

### Exportação
- [ ] Exportar lista como texto simples
- [ ] Exportar como PDF
- [ ] Exportar resumo como imagem (Canvas to PNG)
- [ ] Gerar link compartilhável da lista

### Perfil e Preferências
- [ ] Itens favoritos / frequentes
- [ ] Sugestão automática baseada em histórico
- [ ] Perfil de compra recorrente
- [ ] Nome automático de lista baseado na data
- [ ] Tema claro / escuro
- [ ] Tamanho de fonte ajustável

---

## 📊 Planejado (v2.0)

### Resumo Avançado
- [ ] Gastos reais por semana
- [ ] Gastos reais por mês
- [ ] Histórico anual com comparativo
- [ ] Gráfico de evolução de preço por produto
- [ ] Comparativo entre listas (esta semana vs anterior)
- [ ] Meta de gasto mensal com barra de progresso
- [ ] Alerta quando ultrapassar meta

### IA Avançada
- [ ] Sugestão de produtos baseada em padrão de compra
- [ ] Correção contextual de marcas e pesos
- [ ] Detecção de duplicatas inteligente
- [ ] Modo "lista saudável" (IA sugere substituições)
- [ ] Análise de gasto por categoria com recomendações
- [ ] Leitura de nota fiscal por foto

### Integração
- [ ] Compatibilidade com múltiplos provedores de LLM
- [ ] Groq, Mistral, OpenRouter, Ollama (local)
- [ ] API de visão: Gemini, Claude Vision, GPT-4V
- [ ] Webhook para notificações
- [ ] Integração com calendário (dia de compra)

---

## 🚀 Visão Futura (v3.0+)

### Multiusuário
- [ ] Login simples (sem backend pesado)
- [ ] Listas compartilhadas em tempo real
- [ ] "Modo casal" — dois celulares, mesma lista
- [ ] Permissões (quem edita, quem só visualiza)

### Backend Opcional
- [ ] Sincronização em nuvem (Firebase / Supabase)
- [ ] Backup automático
- [ ] Acesso em múltiplos dispositivos
- [ ] Histórico completo de compras

### PWA (Progressive Web App)
- [ ] Instalar como app no celular
- [ ] Funcionar offline
- [ ] Notificação de lembrete de compra
- [ ] Ícone na tela inicial

### Marketplace
- [ ] Comparar preço entre mercados
- [ ] Localização de mercados próximos
- [ ] Ofertas e promoções por região
- [ ] Lista otimizada por mercado (menor preço total)

---

## 🛡️ Segurança — Roadmap Específico

| Prioridade | Item |
|---|---|
| Alta | Firewall de prompt (bloquear manipulação) |
| Alta | Sanitização de input do usuário |
| Alta | Validação de resposta JSON da IA |
| Média | Rate limiting local |
| Média | Validação de formato de API Key |
| Média | Limpeza de dados sensíveis em memória |
| Baixa | Criptografia local de keys no storage |
| Baixa | Auditoria de chamadas à API |

---

## 📝 Notas de Desenvolvimento

- O sistema foi projetado para evoluir sem reescrita
- Cada feature nova deve respeitar a arquitetura de arquivo único (até v2.0)
- A partir da v3.0, considerar migração para estrutura modular
- Todas as integrações de IA devem ter fallback offline
- UX é prioridade: nenhuma feature deve complicar a experiência

---

> Este roadmap é um documento vivo.
> Atualizado conforme o projeto evolui.
>
> Última atualização: Agosto 2026
