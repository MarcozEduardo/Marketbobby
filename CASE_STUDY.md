# Case Study — MarketBobby

## Um sistema de lista de compras com IA, OCR de preços, fallback entre modelos e uma batalha real de 15 horas com Firebase, prompts, parsers e UX

**Autor:** Marcos Eduardo  
**Projeto:** MarketBobby  
**Data de origem do projeto:** 14/08/2026  
**Formato:** HTML, CSS, JavaScript puro, Firebase Cloud Functions, APIs de IA  
**Contexto:** Projeto de portfólio com foco em produto, experiência real de uso, integração com IA e demonstração de raciocínio técnico aplicado  
**Copilotos de desenvolvimento utilizados durante a construção:** Bobby IA, DeepSeek e Claude  

---

## 1. Introdução

O **MarketBobby** nasceu como um projeto de lista de compras, mas rapidamente deixou de ser apenas isso.

A ideia inicial parecia simples:
criar um sistema útil, bonito, com cara de app de verdade, que ajudasse uma pessoa durante a compra.

Mas a cada nova camada, o projeto foi exigindo mais.

O que começou como:
- criar lista
- marcar item
- editar preço
- somar total

evoluiu para:
- organizar listas bagunçadas com IA
- extrair produtos e preços de fotos reais
- suportar encartes, placas de supermercado e imagens múltiplas
- ter fallback entre modelos e provedores
- ocultar chaves no backend
- manter uma UX clara mesmo quando a IA demora, falha ou oscila

No fim, o MarketBobby se transformou em um caso muito mais interessante do que um simples CRUD.

Ele virou uma prova real de:
- visão de produto
- insistência em refinamento
- arquitetura prática
- debugging em camadas
- uso de IA como ferramenta de produção
- e principalmente:
- **capacidade de construir enquanto o sistema resiste**

---

## 2. O contexto real do projeto

O projeto foi desenvolvido em um contexto muito específico:
não como exercício de curso,
não como tutorial,
não como “clone” de produto famoso.

Ele foi construído como uma peça de portfólio com propósito.

A intenção era mostrar, de forma concreta, que é possível criar algo com valor real mesmo sem seguir o caminho tradicional da formação técnica.

Mais do que “escrever código”, o objetivo era demonstrar:

- visão de produto
- capacidade de estruturar uma experiência
- entendimento de comportamento do usuário
- senso de arquitetura
- habilidade de diagnosticar erro
- insistência em resolver problema real
- e uso estratégico de IA como motor de desenvolvimento

A primeira base funcional do sistema surgiu rápido.

Mas o que realmente define este projeto não é a primeira versão.

O que define o MarketBobby é o que veio depois:
o processo de **não aceitar solução meia-boca**.

---

## 3. O problema que o MarketBobby queria resolver

Listas de compras, na vida real, raramente nascem organizadas.

Elas aparecem como:

- texto corrido
- mensagem no WhatsApp
- anotação da esposa
- itens sem acento
- abreviação
- item repetido
- peso faltando
- marca no meio do nome
- foto de placa de preço
- foto de encarte
- foto de produto
- observação misturada no texto

Além disso, no mercado de verdade, o usuário não quer “mexer num sistema”.

Ele quer resolver a compra.

Isso significa que o sistema precisa:

- aceitar bagunça
- organizar depois
- ajudar sem atrapalhar
- mostrar preço com clareza
- separar o que já foi resolvido do que ainda falta
- permitir adicionar coisa nova rápido
- funcionar no celular
- não depender de um único modo de entrada

Esse foi o problema central do projeto.

Não era “fazer uma lista”.

Era fazer uma lista que aguentasse o mundo real.

---

## 4. A hipótese de produto

A hipótese era a seguinte:

> Se o usuário puder montar sua lista por texto, por organização com IA ou por foto, e o sistema conseguir estruturar isso de maneira clara, visual e útil, a experiência deixa de ser uma simples anotação e passa a ser uma ferramenta real de compra.

Essa hipótese guiou todo o projeto.

A partir dela, surgiram três modos centrais de uso:

### 4.1. Modo Direto
Para quem quer velocidade e independência.

A pessoa escreve:
- `2 arroz, feijão, leite`
- `salsicha aurora, pão hot dog, catchup`
- `banana 3,99, 2 creme de leite`

O sistema precisa entender e adicionar.

### 4.2. Modo Organizar com IA
Para quando a entrada vem bagunçada.

Exemplos:
- texto informal
- recado colado
- erros de digitação
- mistura de marcas, pesos e observações

A IA corrige, organiza e categoriza.

### 4.3. Modo Foto
Para quando a informação já está no mundo físico:
- placa
- encarte
- etiqueta
- produto
- cupom
- lista fotografada

A IA precisa olhar e devolver algo utilizável.

Esses três modos transformaram a proposta do projeto.

---

## 5. A estrutura do sistema

O MarketBobby foi construído com uma base deliberadamente simples:

- HTML
- CSS
- JavaScript puro
- localStorage
- Firebase Cloud Functions
- APIs de IA

Sem framework.

Isso não foi limitação.
Foi escolha.

### Motivos da escolha
- facilitar o deploy
- manter portabilidade
- evitar complexidade gratuita
- demonstrar domínio da base
- permitir iteração rápida
- manter o projeto compreensível e controlável

A base local resolve:
- persistência
- navegação
- lista
- resumo
- edição
- renderização
- estados visuais

O backend entra onde realmente faz sentido:
- esconder chaves
- permitir modo demonstração
- processar IA sem expor credenciais
- controlar fluxos com fallback

---

## 6. O papel da IA no projeto

A IA não entrou como “efeito especial”.
Ela entrou como ferramenta funcional.

### No texto
A IA organiza listas informais:
- corrige grafia
- detecta quantidade
- sugere peso padrão
- separa marca
- define categoria

### Na imagem
A IA lê:
- produto
- marca
- peso
- preço
- quantidade implícita ou explícita
- múltiplos produtos no mesmo encarte

### No processo de desenvolvimento
As IAs também atuaram como copilotos de construção:
- Bobby IA
- DeepSeek
- Claude

Cada uma ajudou de forma diferente:
- uma estruturava
- outra ajudava na cobertura
- outra cavava os bugs mais chatos
- e Marcos fazia a parte mais importante:
  **avaliar, testar, insistir e decidir**

O projeto não saiu de um prompt só.
Saiu de dezenas e dezenas de iterações.

---

## 7. Como o projeto foi realmente construído

O MarketBobby não foi feito no modelo tradicional de sentar e escrever tudo do zero na mão.

Ele foi construído por **orquestração iterativa**.

O ciclo era:

1. imaginar o comportamento desejado
2. pedir implementação
3. testar no app real
4. perceber onde quebrava
5. identificar se o problema era:
   - prompt
   - parser
   - renderização
   - backend
   - estado visual
   - timing
   - fallback
6. ajustar
7. testar de novo

E repetir isso até parar de ficar “aceitável” e começar a ficar “bom”.

Essa foi a alma do projeto.

---

## 8. A primeira fase: o sistema nasceu rápido

A base do projeto saiu surpreendentemente rápido.

Em poucas horas, já existiam:

- home
- criação de lista
- navegação entre telas
- armazenamento local
- listagem de itens
- cálculo de total
- categorias
- estados visuais
- resumo com gráficos
- lista finalizada
- reaproveitamento de lista
- tela de perfil
- configuração de API

Essa velocidade mostrou duas coisas:

### 8.1. A visão do produto estava muito clara
Não havia dúvida sobre o que o sistema precisava parecer.

### 8.2. O problema nunca foi “ter ideia”
O problema sempre foi o refinamento fino.

Porque a primeira versão funcional não era o fim.
Era o começo da briga.

---

## 9. A segunda fase: o sábado inteiro de hiperfoco

A parte mais importante do projeto aconteceu na fase em que ele precisou sair do navegador e ganhar backend de verdade.

Foi aí que entrou o Firebase.

E foi aí que o sistema deixou de ser “bonitinho” e começou a exigir engenharia real.

Essa fase não durou 30 minutos.
Não foi ajuste leve.
Não foi só “trocar uma linha”.

Foi um sábado inteiro de foco bruto.

Terminal aberto.
Deploy atrás de deploy.
Alteração.
Teste.
Erro.
Log.
Nova hipótese.
Mais alteração.
Novo deploy.
Novo teste.
Mais um bug escondido.

Foi uma batalha de cerca de **15 horas** em cima de:

- Cloud Functions
- runtime
- versão de dependência
- prompt
- parser
- UI
- foto
- preço
- duplicação de função
- loading
- fallback

Essa parte precisa ser registrada porque foi ela que amadureceu o projeto de verdade.

---

## 10. O primeiro choque: Firebase quebrando antes de tudo

O primeiro grande bloqueio veio da própria infraestrutura.

A lógica estava pronta.
O backend parecia certo.
Mas o deploy quebrava.

Depois de fuçar logs, terminal e mensagens do Google Cloud, o erro ficou claro:

> `functions.config() has been removed in firebase-functions v7`

Ou seja:
o código fazia sentido em uma versão,
mas o ambiente estava em outra.

### O que isso causou
- erro 500
- function sem acessar chave
- comportamento enganoso
- sensação de que o problema era no código da IA

### A solução prática
Foi feito downgrade para uma versão compatível do Firebase Functions.

### O valor disso
Essa decisão é importante porque mostra maturidade:
em vez de se perder em migração no meio da batalha, o foco foi estabilizar o sistema e seguir.

Isso é engenharia pragmática.

---

## 11. O modo Bobby e o backend de demonstração

Uma necessidade central do projeto era permitir demonstração sem obrigar o visitante a criar ou colar sua própria chave.

Daí nasceu o **Modo Bobby**.

### A ideia
- visitante entra no projeto
- clica
- usa IA
- testa foto
- organiza lista
- sem configurar API

### Como isso foi resolvido
- o frontend chama Firebase Functions
- as Functions guardam as chaves do lado do servidor
- o usuário usa o sistema como demo
- se quiser, também pode desligar esse modo e usar sua própria chave local

Esse desenho trouxe dois modos importantes:

### Modo Bobby
- backend serverless
- experiência pronta
- ideal para portfólio

### Modo Local
- usuário pluga a própria chave
- armazenamento local
- ideal para testes e liberdade

Essa decisão arquitetural elevou bastante o valor do projeto.

---

## 12. O benchmark de modelos e a recusa ao hardcode cego

Um dos pontos mais inteligentes da construção foi não aceitar hardcode de modelo como se fosse verdade eterna.

A pergunta que guiou isso foi, na prática:

> “Se o endpoint já lista os modelos, por que vamos confiar num nome fixo e torcer?”

Essa provocação foi certeira.

### O problema do hardcode
- modelo muda
- some do endpoint
- perde acesso
- entra em preview
- sofre rate limit
- funciona numa chave e não em outra

### A solução
Foi criado um testador de modelos em HTML que:
- consultava o endpoint do Gemini
- listava modelos disponíveis
- filtrava os incompatíveis
- enviava uma imagem real
- media tempo
- mostrava log em tempo real
- permitia cancelar
- gerava ranking

Esse testador foi crucial porque revelou um padrão:

### Descoberta importante
- modelos **lite** eram muito rápidos
- mas nem sempre entendiam o prompt profundamente
- alguns modelos liam o nome do produto e pulavam o preço
- outros eram mais lentos, mas muito mais consistentes

Essa descoberta mudou a lógica do fallback.

---

## 13. O prompt da foto precisou virar especificação técnica

No começo, o prompt de imagem ainda era genérico demais.

Ele dizia algo como:
- analise a imagem
- retorne JSON
- extraia produto

Mas isso não bastava para cenário real.

Quando o usuário enviava:
- encarte com vários produtos
- preço promocional
- preço por kg
- produto + slogan + oferta
- valor pequeno ao lado do item

a IA oscilava.

### O que foi necessário fazer
Transformar o prompt em uma especificação quase contratual.

Ele passou a dizer com clareza:

- não converse
- não explique
- não use markdown
- extraia todos os produtos visíveis
- procure o valor monetário mais próximo do nome
- entenda formato brasileiro
- trate `R$ 24,90` como `24.90`
- trate `1.299,90` como `1299.90`
- se houver “de X por Y”, use o promocional
- se for “2 por 10,00”, extraia preço unitário e quantidade
- se não houver produto, devolva array vazio

Esse refinamento foi decisivo.

---

## 14. O bug do preço: o valor existia, mas parecia que não

Essa foi uma das batalhas mais traiçoeiras.

A foto funcionava.
O backend respondia.
O log mostrava claramente:

-json:
{"items":[{"name":"Mussarela Peça Inteira","price":16.99,"qty":1}]}-

Mas no sistema parecia que o preço estava sumindo.

O que foi descoberto
Não era um bug só.

Era uma combinação:

## 14.1. O frontend matava o preço
No organizeWithAI, havia um bloco que fazia:

`price: 0`

Ou seja:
qualquer valor vindo da IA era descartado.

14.2. Havia função duplicada
transcribeWithFirebase apareceu duas vezes no arquivo.
A segunda sobrescrevia a primeira.

14.3. O R$ era só placeholder
Visualmente parecia que o campo tinha moeda.
Mas o R$ não fazia parte do valor.
Era apenas placeholder.

Então o preço numérico aparecia sem R$, e a percepção era de que ele havia sido “limpo”.

O que essa etapa ensinou
Às vezes o bug está:

no dado
no mapeamento
na duplicação de função
e no componente visual ao mesmo tempo
Foi investigação de verdade.

---

## 15. Os centavos fantasmas e a briga com a vírgula brasileira

Depois que a foto passou a injetar texto corretamente na nova lista, surgiu outro bug bizarro.

Exemplo de texto injetado:

`Arroz Tio João 5kg R$24,90,`
`Feijão Camil 1kg R$8,49,`

Ao clicar em Direto, o sistema criava itens como:

`90`
`49`
`99`

O motivo
O parser separava por vírgula.
A vírgula do preço também estava sendo usada como separador.

O efeito
R$24,90 virava:

R$24
90
O 90 virava item.

A solução
Foi criado um parse mais inteligente:

se tiver quebra de linha, separar por linha
se não tiver, separar por vírgula protegendo decimal
Além disso, o parser passou a:

ignorar números soltos curtos
extrair peso
extrair marca
extrair preço
limpar o nome final
Essa parte foi crítica para manter o botão Direto útil mesmo sem IA.

---

## 16. O papel do botão Direto no sistema

Esse é um ponto importante do produto.

O botão Direto não é um plano B improvisado.
Ele é parte essencial da proposta.

Porque mesmo que:

a IA falhe
o backend caia
a chave expire
o usuário não queira usar IA
o sistema ainda precisa funcionar.

Por isso o Direto importa
Ele garante:

independência
velocidade
confiabilidade
uso offline/local
fallback humano
Ao mesmo tempo, ele exigiu muito cuidado porque:

não organiza com a inteligência semântica da IA
depende de parser
sofre mais com ambiguidade textual
O equilíbrio entre esses dois mundos foi uma parte muito rica do projeto.

---

## 17. A UX da foto: não bastava funcionar, precisava comunicar

Outro aprendizado forte foi perceber que a ausência de feedback visual gera sensação de bug, mesmo quando tudo está funcionando.

Quando o usuário enviava uma foto, a IA podia levar alguns segundos.

Sem feedback, parecia travado.

O que foi implementado
loading visual
mensagens progressivas
etapas como:
Lendo a imagem...
Extraindo produtos e preços...
Analisando redundâncias...
Quase lá...
bloqueio de ação durante processamento
destaque visual nos itens novos
toast em caso de erro
Esse refinamento curou uma dor de UX real.

---

## 18. O notepad como palco da organização

A tela de nova lista virou uma peça muito interessante do sistema.

Ela funciona quase como um campo de preparação.

O usuário pode:

digitar
colar
escrever errado
tirar foto
deixar a IA organizar
ou seguir direto
E tudo isso acontece no mesmo fluxo.

A injeção no textarea ficou importante porque:

mantém sensação de controle
permite revisar
deixa o usuário ver o que foi entendido
facilita ir misturando texto humano com texto da IA
Além disso, foi refinado o comportamento visual:

piscar quando algo novo entra
jogar o cursor para o final
manter experiência viva e clara
Esse tipo de detalhe dá sensação de produto “acordado”.

---

## 19. O parser local também precisou amadurecer

O parser de entrada manual foi saindo de um separador simples e se tornando algo mais semântico.

Ele passou a identificar:

quantidade
peso
marca
preço
categoria
e estrutura mínima do item
Exemplos de evolução
reconhecer 2x arroz
reconhecer Arroz R$24,90
não quebrar o preço brasileiro
isolar 5kg
diferenciar o que é parte do nome e o que é dado auxiliar
Isso foi importante porque o parser local precisou conviver com:

texto humano
texto injetado pela foto
texto que já foi parcialmente tratado por IA
---

## 20. A organização por IA também precisou aprender preço

No início, a IA organizadora estava voltada a:

nome
quantidade
marca
peso
categoria
Mas o preço não estava sendo pedido explicitamente no prompt do organizador.

Isso gerava um comportamento curioso:

a foto injetava o preço certo
mas ao clicar em Organizar com IA, o valor podia desaparecer
A correção
O prompt do organizador precisou ser alterado para incluir:

preservação do preço
formato price
retorno explícito em JSON com o campo presente
Além disso, o frontend precisou parar de zerar esse dado.

Foi um ótimo exemplo de como:

o prompt
o backend
e o mapeamento de resposta
precisam estar alinhados.
---

## 21. O papel de Marcos na construção

Esse projeto não foi uma “IA fazendo tudo sozinha”.

Pelo contrário.

O papel de Marcos foi o centro do processo.

O que Marcos fez ao longo do projeto
definiu o comportamento esperado
avaliou o fluxo como produto
percebeu inconsistências visuais
testou cenários reais
recusou soluções rasas
insistiu em refinamento
conectou bugs espalhados
cobrou qualidade sem romantizar a IA
Houve momentos em que a diferença entre um sistema meia-boca e uma solução boa veio justamente da teimosia em não aceitar o primeiro resultado.

Isso apareceu em várias falas e atitudes, como:

não aceitar hardcode sem testar
benchmark de modelos
insistência em entender onde o preço estava morrendo
percepção de que o R$ era placeholder
preocupação com UX enquanto a IA processa
busca por algo que parecesse realmente usável e elegante
Esse tipo de postura mostra raciocínio de produto e de engenharia ao mesmo tempo.

---

## 22. O papel do DeepSeek, do Claude e dos copilotos

As IAs usadas durante o processo tiveram papéis complementares.

DeepSeek
Ajudou em partes estruturais, cobertura e blocos de implementação.

Claude
Atuou fortemente na parte de:

debugging contextual
análise de fluxo
identificação de sabotagens cruzadas
refinamento da narrativa técnica do projeto
Bobby IA
Foi o copiloto-base da proposta e da evolução iterativa do sistema.

Mas o mais importante é:
essas IAs não substituíram a direção do projeto.

Elas foram instrumentos.

A inteligência organizadora, crítica e persistente partiu da condução humana.

---

## 23. O que o projeto prova tecnicamente

O MarketBobby prova, de forma concreta, competência em:

Frontend
HTML, CSS e JavaScript puro
modelagem de fluxo
renderização de estados
UX mobile-first
componentes próprios
visual system funcional
Backend
Firebase Cloud Functions
integração com IA
uso de config e ambiente
deploy e debug em ambiente serverless
fallback entre chaves e modelos
IA aplicada
prompt engineering
OCR semântico
benchmark de modelos
normalização de resposta
uso combinado de IA local e backend
Produto
foco em comportamento real de uso
sistema de entrada múltipla
clareza de estados
feedback visual adequado
estrutura pronta para evolução
---

## 24. O que o projeto prova humanamente

Talvez essa seja a parte mais importante.

O MarketBobby prova que desenvolvimento não é apenas escrever sintaxe manualmente.

Ele prova a importância de:

persistência
visão
hiperfoco
capacidade de testar
desconfiar do que parece certo
insistir em entender o sistema
usar ferramenta sem se submeter a ela
transformar bug em pista, não em derrota
Esse projeto foi construído num sábado inteiro de cabeça mergulhada.
Com terminal.
Com deploy atrás de deploy.
Com ajuste atrás de ajuste.
Com tentativa, erro e repetição.

Isso diz muito sobre a forma de construir.

---

## 25. Próximos passos

O projeto já aponta evoluções naturais:

Curto prazo
impedir duplicata de item de forma mais robusta
melhorar popup de foto com câmera e galeria
loading melhor no popup de adicionar
feedback mais rico de redundância
Médio prazo
chips/tags visuais no lugar de parser textual em alguns fluxos
compressão de imagem antes do envio
mais refinamento de OCR para casos extremos
melhoria na lógica de redundância semântica
Longo prazo
Firestore
listas compartilhadas
família / multiusuário
PWA
histórico temporal real
sugestão inteligente de compras recorrentes
---

## 26. Resultado final

O MarketBobby terminou essa fase como muito mais do que um experimento.

Ele virou:

um app funcional
um case técnico forte
um estudo de UX
uma prova de raciocínio sistêmico
e um retrato fiel de como software de verdade nasce:
não em perfeição imediata,
mas em iteração disciplinada
---

## 27. Conclusão

O MarketBobby é a prova viva de que software bom não nasce só de código.
Nasce de:

direção
paciência
insistência
repertório de teste
leitura de comportamento
e coragem para refinar até ficar certo
A base saiu rápido.
Mas o valor do projeto nasceu na batalha.

Na hora em que:

o Firebase quebrou
o preço sumiu
o parser explodiu os centavos
o placeholder enganou a percepção
os modelos oscilaram
o prompt falhou
e mesmo assim o trabalho continuou
Esse projeto mostra produto.
Mostra engenharia.
Mostra cabeça.
Mostra construção orientada por critério.

E acima de tudo mostra uma coisa muito importante:

capacidade de fazer software direito mesmo quando ele decide resistir.

---

## 28. Créditos

Projeto idealizado, conduzido, testado e refinado por Marcos Eduardo, com apoio de copilotos de IA ao longo da construção, debugging e documentação.

Copilotos utilizados no processo
Bobby IA
DeepSeek
Claude
Frases que resumem o espírito da construção
“Eu não sou usuário comum.”

“Eu quero coisa bem feita.”

“Pra que a gente vai definir um nome de modelo se a lista já tá no endpoint?”

“Isso não é só pra funcionar. Tem que ficar bom.”

Essas frases dizem muito sobre o projeto.

Porque o MarketBobby não foi construído para parecer pronto.

Ele foi construído para ficar pronto de verdade.
