# 📘 **CAPÍTULO 13 — FLUXO DE TRABALHO JRDEEP™**

### *“Como combinar GPT + Claude + Codex para produtividade MÁXIMA dentro do VSCode.”*

### *O capítulo mais prático e direto do manual inteiro.*

Você já tem o melhor setup do mundo:
**GPT-5.1** (arquitetura, pensamento, criação)
**Claude 4.5** (execução, terminal, debugging)
**Codex Mini** (autocomplete, micro-edições, refactors curtos)

O segredo agora é **como combinar** esses três dentro de um ciclo de trabalho **rápido, natural e econômico**.

Este capítulo é isso:
👉 O **workflow perfeito** para construir QUALQUER projeto.

---

# 🧭 **13.1 — O PRINCÍPIO CENTRAL DO JRDEEP WORKFLOW**

> **NUNCA use um único modelo para tudo.**
> 👉 Cada um faz uma parte do trabalho MUITO melhor.

Assim como na música:

* você não usa o mesmo plug-in pra mixar, equalizar e masterizar,
  você também **não usa o mesmo modelo para planejar, criar, executar e depurar**.

O fluxo JrDeep é inspirado em uma pipeline de produção musical:

```
Planejamento (GPT) → Composição (GPT) → Arranjo (GPT)  
→ Execução (Claude) → Correções (Claude) → Detalhes (Codex)  
→ Finalização (GPT) → Masterização (Claude)
```

---

# 🧨 **13.2 — O CICLO JRDEEP (padrão ouro)**

O ciclo tem 7 fases.
Todas são rápidas.
E cada modelo entra onde é mais forte.

---

## 🔵 **FASE 1 — Ideação e Planejamento (GPT-5.1)**

Aqui você usa:

```
GPT-5.1 (Preview)
```

### Ele faz:

* Levanta requisitos
* Sugere tecnologias
* Cria arquitetura
* Cria os módulos
* Divide em microtarefas
* Gera roadmap
* Gera diagramas
* Define dependências
* Desenha a API
* Cria blueprints

### Seu prompt típico:

```
Me ajude a pensar nisso.
Me ajude a planejar.
Qual a melhor forma de construir isso?
Gere o blueprint completo.
Explore alternativas.
Refaça a arquitetura.
```

👉 **O GPT-5.1 pensa melhor que todos.**

---

## 🔵 **FASE 2 — Criação de Arquivos e Estruturas (GPT-5.1)**

Ainda é GPT que cria:

* pastas
* arquivos
* templates
* módulos
* rotas
* componentes
* modelos de dados

### Seu prompt típico:

```
Crie este arquivo para mim.
Implemente o módulo X nesse padrão.
Gere o boilerplate completo.
Crie a estrutura do projeto.
```

👉 GPT = melhor programador de “primeira versão”.

---

## 🔴 **FASE 3 — Execução, Testes e Terminal (Claude 4.5)**

Agora você troca:

```
/model claude-3.5-sonnet
```

Ou no Copilot:

> “Switch to Claude 4.5 Sonnet”

### Ele faz as partes que exigem ação real:

* rodar comandos
* instalar libs
* depurar
* criar bancos
* criar tabelas
* manipular filesystem
* interpretar erros
* rodar scripts
* consertar falhas
* reiniciar serviços
* compilar C++
* fazer deploy local

### Seu prompt típico:

```
Instale as dependências.
Rode esse comando.
Execute esse arquivo.
Analise o erro acima.
Corrija isso.
Continue executando.
```

👉 Claude é o **executor do time**.

GPT pensa.
Claude age.

---

## 🟠 **FASE 4 — Correção de Erros (Claude 4.5)**

Quando algo dá erro:

**Claude reage instantaneamente.**

Ele entende:

* o diretório errado
* comandos inválidos
* dependências ausentes
* syntax error
* versões conflitantes
* logs longos
* stack trace
* warnings de compilação
* erros de permissionamento

### Seu prompt típico:

```
Esse comando falhou. Analise e corrija.
Esse erro aconteceu, como resolver?
Continue até funcionar.
```

➡️ GPT não faz isso tão bem.
➡️ Codex não entende o terminal.

---

## 🟡 **FASE 5 — Autocomplete e Detalhes (Codex Mini)**

Depois que o GPT criou e o Claude executou…
Agora é hora do acabamento.

Codex Mini completa:

* funções
* pequenos blocos
* padrões repetitivos
* trechos de validação
* loops
* imports
* handlers
* props
* chamadas assíncronas
* constantes
* refactors pequenos
* renomear variáveis
* remover duplicações

👉 É a fase **mais rápida** do fluxo.

Você simplesmente **digita → TAB → pronto**.

---

## 🟣 **FASE 6 — Polimento e Refinamento (GPT-5.1)**

Aqui você volta para o GPT:

```
Mode: Agent
Model: GPT-5.1
```

Ele faz:

* melhora a arquitetura
* refatora para padrões de mercado
* remove complexidade
* cria documentação
* cria README
* gera scripts auxiliares
* melhora código
* adiciona testes
* moderniza tudo

### Seu prompt típico:

```
Melhore esse código.
Simplifique isso.
Use boas práticas.
Crie a documentação.
Expanda esse módulo.
Adapte para produção.
```

---

## 🟣 **FASE 7 — Finalização (Claude 4.5)**

Sempre finalize com Claude:

* valida tudo
* checa erros
* confirma permissões
* roda testes
* executa o sistema final
* limpa dependências
* analisa performance

### Seu prompt típico:

```
Vamos testar o sistema.
Rode tudo do zero.
Verifique dependências.
Confirme se está funcionando.
```

---

# 🟡 **13.3 — O FLUXO JRDEEP EM FORMA DE LINHAS**

### Você:

> “Quero fazer X.”

### GPT-5.1:

→ “Aqui está o plano completo.”

### Você:

> “Crie os arquivos iniciais.”

### GPT-5.1:

→ cria.

### Você:

> “Claude, execute tudo.”

### Claude:

→ instala, roda, testa, corrige.

### Você:

> começa a codar e o Codex Mini vai completando.

### Você:

> “GPT, refine.”

### GPT-5.1:

→ limpa, melhora, organiza.

### Você:

> “Claude, valide.”

### Claude:

→ roda, verifica, confirma.

👉 Esse ciclo é **perfeito**.

---

# 🔥 **13.4 — FORMATO FINAL DO FLUXO JRDEEP**

```
1. GPT-5.1  → pensar e criar
2. GPT-5.1  → gerar estrutura e código base
3. Claude 4.5 → executar e testar
4. Codex Mini → completar e refinar microdetalhes
5. GPT-5.1 → polir e refatorar
6. Claude 4.5 → validar e finalizar
```

Este ciclo é:

* o mais rápido
* o mais barato
* o mais seguro
* o mais profissional
* o mais escalável
* usado pelos melhores devs com IA do mundo

---

# 🧩 **13.5 — UMA VERSÃO EM DIAGRAMA ASCII (visual)**

```
┌──────────────────────────────────────────────┐
│                FASE 1: GPT-5.1               │
│        Planeja → Arquitetura → Blueprint     │
└──────────────────────────────────────────────┘
                       ↓
┌──────────────────────────────────────────────┐
│                FASE 2: GPT-5.1               │
│        Cria arquivos → Estrutura do projeto  │
└──────────────────────────────────────────────┘
                       ↓
┌──────────────────────────────────────────────┐
│                FASE 3: CLAUDE                │
│   Executa → Testa → Depura → Roda Terminal   │
└──────────────────────────────────────────────┘
                       ↓
┌──────────────────────────────────────────────┐
│               FASE 4: CODEX MINI             │
│ Completa código → Microrefactors → Sugestões │
└──────────────────────────────────────────────┘
                       ↓
┌──────────────────────────────────────────────┐
│                FASE 5: GPT-5.1               │
│        Refinamento → Polimento → Padrões     │
└──────────────────────────────────────────────┘
                       ↓
┌──────────────────────────────────────────────┐
│                FASE 6: CLAUDE                │
│      Validação final → Execução final        │
└──────────────────────────────────────────────┘
```

---

# 💎 **13.6 — O “FLOW STATE” JRDEEP**

Quando você domina esse capítulo, você entra em um estado que quase nenhum programador entra:

* você pensa mais rápido
* codifica mais rápido
* resolve erros mais rápido
* aprende mais rápido
* finaliza mais projetos
* executa mais automações
* comete menos erros
* usa menos crédito

Esse fluxo te coloca no **top 1%** de devs que usam IA corretamente.

---

# 🎉 **Fim do Capítulo 13**

Se quiser seguir:

```
Capítulo 14 — Quando usar o Chat vs quando usar o Terminal vs quando usar o Editor (as 3 zonas do VSCode)
```
