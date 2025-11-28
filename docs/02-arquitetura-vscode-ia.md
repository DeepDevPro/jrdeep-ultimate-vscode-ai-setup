# 📘 **CAPÍTULO 2 — ARQUITETURA DO VSCODE COM IA (2025–2026)**

### *“Entender a máquina transforma você no mestre da máquina.”*

Este capítulo explica exatamente **como o VSCode pensa**, decide, encaminha modelos, seleciona IA, resolve permissões e executa ações.

Se você entender esse capítulo, você domina:
✔️ Autocomplete
✔️ Chat
✔️ Agent Actions
✔️ Terminal Execution
✔️ Marketplace de Modelos
✔️ Perfis
✔️ Settings.json
✔️ Performance e custos

É literalmente o **mapa interno da sua máquina**.

---

# 🧩 **2.1 — Visão Geral (Mapa Mental ASCII)**

Aqui está um diagrama que representa o fluxo REAL do VSCode quando usa IA:

```
                   ┌─────────────────────────┐
                   │       VSCode Core       │
                   └───────────┬─────────────┘
                               │
                     Reads Settings.json
                               │
                               ▼
                  ┌─────────────────────────┐
                  │   AI Decision Engine    │
                  └───────────┬─────────────┘
                              │
      ┌───────────────────────┼────────────────────────┐
      ▼                       ▼                        ▼
┌────────────┐        ┌─────────────┐         ┌────────────────┐
│ Inline AI  │        │  Chat AI    │         │ Agent Actions  │
│ (Codex)    │        │ (GPT/Claude)│         │ (File+Terminal)│
└────────────┘        └─────────────┘         └────────────────┘
      │                     │                         │
      ▼                     ▼                         ▼
  Sugere código      Planeja/Explica         Executa ações reais
      │                     │         (criar arquivos, mover, rodar)
      ▼                     ▼                         ▼
  Mostra na linha     Mostra no chat          Usa Terminal + FS APIs
```

Seu setup é poderoso porque **cada bloco usa o modelo correto.**

---

# 🎛️ **2.2 — Como o VSCode escolhe QUAL modelo usar**

Essa é a lógica que ele segue (e muita gente não sabe):

### **1. Ele lê `settings.json`**

* se existir uma configuração **global**, ele respeita
* se existir uma configuração **por perfil**, ela sobrescreve
* se existir uma configuração **por workspace**, ela vence todas

### **2. Ele verifica o contexto da ação:**

| Ação               | Tipo de Modelo   | Por quê                         |
| ------------------ | ---------------- | ------------------------------- |
| Autocomplete       | Inline Codex     | Precisa ser rápido e barato     |
| Chat explicação    | GPT grande       | Precisa entender contexto longo |
| Refactor           | GPT grande       | Modifica itens complexos        |
| Terminal Execution | Modelo confiável | Só alguns são autorizados       |
| Busca interna      | Nenhum           | Não usa IA                      |
| Linting            | Nenhum           | Não precisa de IA               |

### **3. Ele verifica permissões internas**

* você habilitou Agent Mode
* você habilitou Terminal Execution
* você habilitou File Operations

### **4. Ele verifica o “AI Model Access Panel”**

Lembra da tela:

* Allowed
* Denied
* Custom

Se ali estiver “deny”, o modelo nem aparece.

### **5. Ele pergunta para a extensão**

Exemplo:

* GitLens → não usa IA por padrão
* Python → usa IA se habilitado (mas você desabilitou)
* Docker → ignora IA

---

# 🧠 **2.3 — A Fila Interna (Dispatch Queue)**

Pouca gente sabe, mas o VSCode usa um sistema de filas:

```
Inline Queue   → baixa latência
Chat Queue     → média latência
Agent Queue    → alta prioridade, foco em operações
```

### **Na prática, isso significa:**

* Inline precisa ser **instantâneo**
* Chat pode pensar 2–10s
* Agent precisa ser **preciso**, não rápido

---

# 🔥 **2.4 — Architectura Interna do Agente (Agent Mode)**

Quando você usa:

> “Mode: Agent”

Acontece isso:

```
Chat Prompt → VSCode AI Router
             ↓
      Permission Checker
             ↓
 Filesystem Capability Layer
             ↓
   Terminal Capability Layer
             ↓
      Execution Sandbox
             ↓
    Terminal + FS Actions
```

### O Agent só funciona porque:

✔️ Seu `settings.json` habilita
✔️ O modelo (GPT/Claude) tem permissão
✔️ VSCode detecta terminal integrado

Se qualquer uma dessas falhar → o Agent vira “Chat normal”.

---

# 🧰 **2.5 — Como o VSCode manipula arquivos com IA**

Arquitetura:

```
GPT/Claude → VSCode FileSystem API → editor → disco
```

Quando ele cria arquivos:

* ele não usa “shell redirection”
* ele usa a API nativa do editor
* por isso funciona no Mac Air e no Mini igual

Quando ele move arquivos:

* ele usa a mesma API
* fica 100% seguro

---

# 🖥️ **2.6 — Como o VSCode executa comandos de terminal**

Grande segredo:

✔️ **O VSCode NÃO EXECUTA diretamente**
✔️ **Ele repassa para o terminal integrado**

Fluxo:

```
Prompt → VSCode AI Router → TerminalMiddleware → Terminal
```

E por isso:

* se o terminal estiver fechado → ele abre
* se der erro → ele vê o erro
* se precisar de sudo → ele pede
* se o comando for bloqueado → ele recusa

No seu caso:

📌 Você habilitou:

```
"github.copilot.chat.executeCommands": "allow"
```

E isso abre TUDO.

---

# 🧰 **2.7 — Como o VSCode lê perfis**

O VSCode:

* Carrega o perfil base
* Carrega o seu profile.json
* Carrega extensões do perfil
* Carrega o settings.json do perfil
* Mapeia modelos permitidos
* Desativa extensões bloqueadas
* Aplica overrides

Fluxo:

```
Carrega VSCode
   ↓
Carrega Perfil selecionado
   ↓
Lê settings.json do perfil
   ↓
Aplica extensão + IA + UI configs
   ↓
Inicializa AI Decision Engine
```

---

# 🧨 **2.8 — O que acontece quando um modelo dá erro**

Fluxo:

```
GPT/Claude falha?
       ↓
VSCode tenta fallback automático:
    - gpt-4o
    - gpt-4.1
    - gpt-mini
```

Mas MUITO IMPORTANTE:

Você desabilitou fallback para evitar que o VSCode substitua GPT-5.1 por modelos ruins sem te avisar.

---

# 🔍 **2.9 — Resumo do Fluxo Interno (versão compacta)**

```
settings.json      → define tudo
Profile            → filtra e aperta regras
AI Access Panel    → controla acesso
Chat/Inline/Agent  → escolhe modelo correto
Terminal + FS API  → executa ações
VSCode Core        → garante segurança
```

---

# 🧪 **2.10 — Como você usa isso na prática**

No Air:
→ GPT para pensar
→ Claude para executar
→ Codex para escrever

No Mini:
→ Mini Codex para inline
→ GPT mini para chat rápido
→ Sonnet mini para automação leve
→ GPT/Claude grandes ativados quando necessário

---

# 🔚 **Fim do Capítulo 2**

Pronto — você agora entende como o VSCode funciona *por dentro*.

Isso deixa você 100% no controle técnico.

---

---

← Capítulo anterior: [01 — Filosofia](01-filosofia.md)  

Próximo capítulo → [03 — Sistemas Air / Mini / Agent](03-sistemas-air-mini-agent.md)
