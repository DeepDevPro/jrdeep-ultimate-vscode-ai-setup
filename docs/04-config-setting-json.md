# 📘 **CAPÍTULO 4 — CONFIGURAÇÃO DETALHADA DO SETTINGS.JSON (AIR / MINI / AGENT)**

### *“Agora você domina cada linha do seu editor. Nada fica oculto.”*

Este capítulo é técnico, profundo e 100% prático.
Aqui você aprende:

* **O que cada linha do seu settings.json faz**
* **Como o VSCode interpreta configurações de IA**
* **Como personalizar cada extensão**
* **Como evitar conflitos**
* **Como impedir desperdício de créditos**
* **Como configurar inline, chat, agent e terminal com precisão cirúrgica**
* **Como adicionar, remover e validar configs**

Também incluo **screenshots ASCII** para representar o VSCode real.

---

# 🧩 **4.1 — Como o VSCode lê seu settings.json (ordem secreta)**

Poucos sabem disso:
o VSCode NÃO lê o settings.json inteiro.
Ele lê em **camadas**, nesta ordem:

```
1. Settings Internos do VSCode
2. Settings das Extensões Instaladas
3. Settings do Perfil Ativo
4. settings.json (User)
5. settings.json (Workspace)
6. settings.json (.vscode folder)
7. Overrides de AI Access Panel
8. Overrides do Agent Mode
```

Quando existe conflito:

👉 **O nível mais baixo da lista vence.**
(workspace vence user, que vence perfil, que vence defaults)

**Por isso perfis são essenciais.**

---

# 🧱 **4.2 — Estrutura ideal do seu settings.json (Air)**

O settings do Air é dividido assim:

```
1) Núcleo do Editor
2) IA – Modelos
3) IA – Inline
4) IA – Terminal Execution
5) IA – Agent Mode
6) IA – Extensões Bloqueadas
7) Performance
8) UX e Interface
9) Behavior (salvar, deletar, auto-import)
10) Linguagens específicas
11) Segurança
```

Agora vamos explicar linha por linha do que você tem —
e do que ainda vamos adicionar nos próximos capítulos.

---

# 🧠 **4.3 — SEÇÃO 1 — Núcleo do Editor**

Trecho:

```json
{
  "editor.insertSpaces": false,
  "editor.wordWrap": "on",
  "explorer.confirmDragAndDrop": false,
  "explorer.confirmDelete": false,
  "makefile.configureOnOpen": true
}
```

### ✔️ `"editor.insertSpaces": false`

Tab real ao invés de 4 espaços.
Você programa rápido, então tabs são coerentes com seu estilo.

### ✔️ `"editor.wordWrap": "on"`

Quebra linha automaticamente.
Bom para leitura de logs, JSON, configs, markdown.

### ✔️ `"explorer.confirmDragAndDrop": false`

Evita janelas chatas ao mover arquivos.
**Você trabalha rápido → precisa disso.**

### ✔️ `"explorer.confirmDelete": false`

Deletar sem popup → combina com seu fluxo veloz.

### ✔️ `"makefile.configureOnOpen": true`

VSCode detecta Makefiles sozinhos.
Bom para C, C++, automações e builds.

---

# ⚡ **4.4 — SEÇÃO 2 — Modelos da IA (Air)**

Trecho:

```json
{
  "github.copilot.chat.model": "gpt-5.1",
  "github.copilot.inlineSuggest.model": "gpt-5.1-codex",
  "github.copilot.editor.customModel": "gpt-5.1-codex-mini"
}
```

### ✔️ `"github.copilot.chat.model": "gpt-5.1"`

Seu modelo *principal* de pensamento.
Você usa para:

* blueprint
* arquitetura
* planos
* análises profundas
* sistemas
* estratégias

### ✔️ `"github.copilot.inlineSuggest.model": "gpt-5.1-codex"`

Quando digitando, este é o modelo que escreve código rápido.

Ele é:
⚡ mais rápido
⚡ mais assertivo
⚡ menos prolixo
⚡ mais “ninja do teclado”

### ✔️ `"github.copilot.editor.customModel": "gpt-5.1-codex-mini"`

Mini Codex = barato + rápido.
Usado em:

* autocomplete leve
* sugestões basicamente sintáticas
* padrão ideal para economizar créditos

---

# 🖥️ **4.5 — SEÇÃO 3 — Inline + Editor IA**

Trecho:

```json
{
  "github.copilot.editor.enableAutoCompletions": true,
  "github.copilot.nextEditSuggestions.enabled": true
}
```

### ✔️ AutoCompletions

Liga a escrita automática enquanto você digita.

### ✔️ nextEditSuggestions

Permite “refinamentos de linha” sem abrir chat.
É como pedir um mini-refactor local.

---

# 🧨 **4.6 — SEÇÃO 4 — Terminal Execution (Crítico!)**

Trecho:

```json
{
  "github.copilot.chat.executeCommands": "allow"
}
```

### ✔️ Isto habilita:

* GPT-5.1 executando comandos
* Claude executando comandos
* Modo Agent funcionando completamente
* Criação de ambiente
* Instalações automáticas
* Scaffold de projetos
* Ações reais no sistema

Sem esta linha → **o Agent é só um chat glorificado**.

---

# 🗂️ **4.7 — SEÇÃO 5 — Chat Tools Terminal (Automation Rules)**

Trecho:

```json
"chat.tools.terminal.autoApprove": {
    "git add": true,
    "git commit": true,
    "git push": true,
    "/^cd ~/Automaster && pip3 install supabase boto3 python-dotenv$/": {
        "approve": true,
        "matchCommandLine": true
    }
}
```

Essa parte permite:

✔️ aprovar automaticamente comandos confiáveis
✔️ acelerar automações
✔️ remover pop-ups de confirmação

### **Isso TE TRANSFORMA em um dev 2x mais rápido.**

Você pode adicionar mais comandos depois.

---

# ❌ **4.8 — SEÇÃO 6 — Extensões com IA Desativada**

Trecho:

```json
{
  "github.copilot.excludedExtensions": [
    "esbenp.prettier-vscode",
    "ms-python.python",
    "ms-python.black-formatter",
    "ms-python.isort",
    "streetsidesoftware.code-spell-checker",
    "editorconfig.editorconfig",
    "ms-vscode.vscode-typescript-next",
    "ms-azuretools.vscode-docker",
    "eamodio.gitlens",
    "davidanson.vscode-markdownlint"
  ]
}
```

### Por que desligamos IA dessas extensões?

Porque:

* **nenhuma delas precisa de IA para funcionar**
* elas só desperdiçam crédito
* elas interceptam recursos que ficam no caminho do Agent
* elas tornam o VSCode mais lento

Extensões como:

* Prettier
* GitLens
* Docker
* Spell Checker
* Python

… **NÃO deveriam nem tentar usar IA.**

---

# 🎨 **4.9 — SEÇÃO 7 — UX e Interface**

Trecho:

```
{
  "liveServer.settings.donotShowInfoMsg": true
}
```

Uma besteirinha, mas tira aquele popup chato do Live Server.

---

# 🧬 **4.10 — SEÇÃO 8 — Lógica de Programação / Linguagens**

Trecho:

```json
"[dart]": {
    "editor.formatOnSave": true,
    "editor.formatOnType": true,
    "editor.rulers": [80],
    "editor.selectionHighlight": false,
    "editor.tabCompletion": "onlySnippets",
    "editor.wordBasedSuggestions": "off"
}
```

Isso é altamente especializado.
Seu Dart está configurado profissionalmente.

(E podemos criar configs assim para Python, JS, TS, C++, etc.
Se quiser — só pedir.)

---

# 🪪 **4.11 — SEÇÃO 9 — Segurança**

Trecho:

```json
"docker.host": "unix:///var/run/docker.sock",
"git.ignoreMissingGitWarning": true,
"update.mode": "manual"
```

### ✔️ `"update.mode": "manual"`

MUITO importante.

VSCode não deve atualizar sozinho seu ambiente crítico.
Você decide quando muda.

---

# 🎛️ **4.12 — Representação ASCII do Settings (Air)**

```
Settings.json (Air)
 ├── Editor Core
 ├── AI - Chat Model (GPT-5.1)
 ├── AI - Inline (Codex)
 ├── AI - Mini Inline
 ├── Agent Mode (enabled)
 ├── Terminal Execution (allowed)
 ├── AI Disabled Extensions
 ├── Performance Tweaks
 ├── UX Tweaks
 ├── Language Tweaks
 └── Security Rules
```

---

# 🔚 **Fim do Capítulo 4**

Você agora entende COMPLETAMENTE cada parte do seu settings.json.

Próximo capítulo será profundíssimo:


---

← Capítulo anterior: [03 — Sistemas Air / Mini / Agent](03-sistemas-air-mini-agent.md)  

Próximo capítulo → [05 — Inline, Chat e Agent Mode](05-inline-chat-agent.md)

