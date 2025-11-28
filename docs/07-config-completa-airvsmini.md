# 📘 **CAPÍTULO 7 — CONFIGURAÇÃO COMPLETA: MACBOOK AIR vs MAC MINI**

### *“Dois ambientes. Duas máquinas. Um só cérebro: o seu.”*

Este capítulo explica **como cada máquina deve ser configurada**, por quê, e quais otimizações deixam tudo rodando liso — com diagramas, fluxos e boas práticas.

Você vai entender:

* por que seus dois Macs **NÃO** devem usar as mesmas configurações
* como deixar o Air extremamente poderoso e rápido
* como transformar o Mini 2014 num **servidor de IA inteligente**
* como manter tudo sincronizado
* limites de hardware e como driblar
* como usar os dois juntos como um verdadeiro **cluster pessoal**

Vamos abrir o cofre.

---

# 🧭 **7.1 — VISÃO GERAL DOS DOIS AMBIENTES**

## 🖥️ **MacBook Air (Sequoia)**

Seu **computador principal**, para:

* Criar sistemas
* Planejar projetos
* Escrever código real
* Rodar IAs grandes
* Executar microtarefas
* Testar localmente
* Usar Docker ocasionalmente
* Edição, automação, testes, tudo

No Air você usa:

* **GPT-5.1** para pensar e planejar
* **Claude 4.5** para executar
* **Codex** para escrever
* **Modelos premium** SEM medo
* **Perfis completos**

O Air é **o cérebro**.

---

## 🧱 **Mac Mini 2014 (Monterey via OCLP)**

Seu **servidor pessoal de automação**, para:

* Rodar jobs 24h
* Processamento de áudio
* Scripts Python
* Bot de automação
* Daemons
* Pipelines contínuos
* Escrita e manipulação de arquivos
* Manutenção remota
* Execução de Agentes com IA leve

No Mini você usa:

* **Modelos mini** por padrão
* **Modelos grandes quando necessário**
* Configuração leve
* Terminal sempre disponível
* Perfis minimalistas
* Zero extensões pesadas
* Zero frescura
* Zero UI desnecessária

O Mini é **sua linha de produção**.

---

# 🔥 **7.2 — A FILOSOFIA JRDEEP DOS DOIS AMBIENTES**

### Air = **Criação**

### Mini = **Execução**

### Air = **Inteligência**

### Mini = **Força bruta contínua**

### Air = **Think + Architect + Build**

### Mini = **Run + Monitor + Serve**

Essa divisão aumenta sua velocidade de desenvolvimento **em 2 a 3×**.

---

# ⚙️ **7.3 — CONFIGURAÇÃO DETALHADA DO MACBOOK AIR (SEQUOIA)**

*(JuniorDeep-Air Profile)*

### ✔️ **Perfis:**

* **JuniorDeep-Air** (principal)
* Extensions completas
* UI otimizada
* Terminal execution full
* Agent full
* Modelos premium
* Inline Codex forte
* GPT-5.1 como Chat principal
* Claude 4.5 para execução/agent
* Atualizações do VSCode **manuais**
* Extensões pesadas permitidas (Docker, Python, GitLens — MAS SEM IA)

---

## ⚙️ **7.3.1 — Machine Power**

O MacBook Air:

* roda IAs grandes sem travar
* gera logs rápido
* navega entre projetos gigantes
* gerencia Docker sem sofrer
* suporta extensões pesadas
* não limita VSCode com RAM baixa

---

## 🧠 **7.3.2 — Modelos ideais no Air**

### **Chat default: GPT-5.1**

para blueprint e estratégia.

### **Agent default: Claude 4.5 Sonnet**

para executar tudo com precisão.

### **Inline default: GPT-5.1 Codex**

para escrever código como água.

### **Opções premium acessíveis:**

* Gemini 3 Pro (para multimodal)
* GPT-5.1 Codex Mini (para economia)
* Sonnet 4.5 HA (quando disponível)

---

## 🧩 **7.3.3 — Atalhos ideais (Air)**

* **TAB** → aceitar inline
* **CTRL + Enter** → completar com Copilot
* **CTRL + Shift + I** → abrir Agent refinado
* **CMD + K CMD + S** → gerenciar keybindings
* **CMD + Shift + P** → alternar perfis rapidamente

---

## 💾 **7.3.4 — Extensões (Air)**

### Ativas com IA:

* Copilot
* Copilot Chat
* VSCode Chat
* GitHub Agents

### Ativas sem IA:

* Docker
* Python
* GitLens
* ESLint
* Prettier
* Markdownlint

### Bloqueadas com IA:

* Tudo que não deve consumir créditos.

---

# 🧱 **7.4 — CONFIGURAÇÃO DETALHADA DO MAC MINI (MONTEREY)**

*(JuniorDeep-Mini Profile)*

O objetivo é manter:

* **leveza**
* **velocidade**
* **estabilidade**
* **execução 24/7**
* **zero travamentos**
* **baixo consumo de RAM**

---

## ⚙️ **7.4.1 — Perfis no Mini**

### Ativo: **JuniorDeep-Mini**

### Ajustes principais:

✔️ Inline Codex Mini
✔️ Chat com GPT-5-Mini por padrão
✔️ Agent permitido, mas com IA leve
✔️ Extensões mínimas
✔️ VSCode super leve
✔️ Nada de UI pesada
✔️ Nada de extensões que interceptam terminal
✔️ Nada de Docker (a não ser que precise)

---

## 🧠 **7.4.2 — Modelos no Mini**

Padrões:

* **GPT-5 Mini**
* **GPT-4o Mini**
* **Claude Haiku**
* **GPT-5.1 Codex Mini**

Mas quando você quiser usar o Mini para projetos reais:

👉 basta mudar manualmente para GPT-5.1 ou Claude 4.5.

### Sim, o Mini pode usar IA forte — *mas manualmente*.

Isso evita lentidão desnecessária.

---

## 🧩 **7.4.3 — Extensões (Mini)**

### Ativas:

* Copilot
* Copilot Chat
* Python (somente se for rodar scripts)
* Git
* Remote Development

### Desativadas:

* Docker
* GitLens com IA
* Prettier com IA
* Tudo que exige RAM sobrando

### Regras:

* Nenhuma extensão usa IA exceto Copilot
* Terminal sempre disponível
* Perfil minimalista
* UI básica
* Nenhum pacote pesado

---

# ⚡ **7.5 — O PAPEL DO PERFIL “JRDEEP-AGENT”**

*(é o “modo deus”, mas seguro)*

Esse perfil é seu:

🟣 **Modo Automação Absoluta**
🟣 **Modo Executor Universal**
🟣 **Modo Tarefas Pesadas**
🟣 **Modo Instalação de ambientes**
🟣 **Modo scripts destrutivos**
🟣 **Modo reestruturação de projetos**

Esse perfil tem:

* As regras de IA mais fortes
* Qualquer modelo permitido
* Terminal full
* FS full
* Zero extensões atrapalhando
* Zero overhead
* Velocidade máxima

Use este perfil quando quiser que a IA:

* crie projetos enormes
* reestruture pastas inteiras
* implemente sistemas do zero
* execute pipelines complexos
* gerencie automações no Mini

---

# 🧬 **7.6 — “CROSS-POWER”: USANDO AIR + MINI COMO UM CLUSTER PESSOAL**

Aqui está o segredo que muda tudo:

### O Air pensa.

### O Mini executa.

Você pode fazer:

```
No Air: GPT-5.1 planeja o pipeline
No Mini: Claude Sonnet executa o pipeline via Agent
```

Ou:

```
No Air: GPT planeja um script
No Mini: Agent executa o script continuamente
```

Ou:

```
No Air: arquitetar app Flask/Next
No Mini: rodar o app 24/7 enquanto vc dorme
```

Isso transforma seus dois Macs em um **cluster profissional de desenvolvimento + automação**.

---

# 🔧 **7.7 — OTIMIZAÇÕES ESPECÍFICAS PARA O MINI 2014**

O Mini tem limitações:

* CPU Dual-Core
* RAM DDR3
* GPU integrada fraca
* SSD depende do que você instalou
* Monterey via OCLP (não nativo)

Então você deve:

### ✔️ Usar VSCode com UI leve

(retirar animações, retirar lista lateral, desativar minimap)

### ✔️ Usar tema escuro sem transparência

(Monokai, Dracula, Carbon, GitHub Dark)

### ✔️ Evitar extensões que monitoram FS

(podem travar a máquina)

### ✔️ Não usar Docker no Mini regularmente

(somente quando necessário)

### ✔️ Manter logs rotacionados

(o Mini sofre quando logs explodem)

### ✔️ Evitar múltiplas janelas do VSCode

(abra 1 instância por vez)

### ✔️ Usar modelos Mini quando possível

(mas permitir modelos grandes manualmente)

---

# 🧭 **7.8 — QUANDO USAR CADA MÁQUINA**

### **Use o Air para:**

* Planejar
* Codar
* Criar
* Testar
* Raciocinar
* Documentar
* Trabalhar com UI
* Criar automações
* Projetos críticos

### **Use o Mini para:**

* Rodar jobs 24/7
* Executar scripts
* Daemons
* Pipelines
* Testes contínuos
* Processos de áudio
* Bots
* Servidor local

---

# 🔚 **Fim do Capítulo 7**

Seu setup Air + Mini agora é um ecossistema profissional.

---

---

← Capítulo anterior: [06 — Modelos de IA](06-modelos.md)  

Próximo capítulo → [08 — Disaster Recovery](08-disaster-recovery.md)
