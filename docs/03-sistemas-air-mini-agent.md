# 📘 **CAPÍTULO 3 — SISTEMA DE PERFIS JRDEEP (AIR / MINI / AGENT)**

### *“Perfis são como modos de batalha. Cada um transforma o VSCode em uma máquina diferente.”*

Este capítulo aprofunda totalmente o funcionamento dos **três perfis oficiais**:

* **JuniorDeep-Air**
* **JuniorDeep-Mini**
* **JuniorDeep-Agent**

Você vai entender:

✔️ Por que existem
✔️ Quando usar cada um
✔️ O que muda internamente
✔️ O que cada perfil habilita/desabilita
✔️ Como trocar perfis sem quebrar nada
✔️ O fluxo interno de decisão
✔️ Como restaurá-los

Vamos começar.

---

# 🧱 **3.1 — Por que perfis existem?**

A realidade do seu workflow é única:

* Você usa **duas máquinas** com capacidades MUITO diferentes
* Você trabalha com **múltiplos projetos ao mesmo tempo**
* Você usa **IA de forma intensiva e técnica**
* Você alterna entre:

  * pensar
  * planejar
  * executar
  * automatizar
  * testar
  * codar
  * operar servidores

Perfis permitem transformar o VSCode em **três ambientes completamente diferentes**, cada um otimizado para o tipo de trabalho.

Sem perfis, tudo mistura e vira bagunça:

❌ extensões demais
❌ modelos conflitantes
❌ settings quebrando recursos
❌ IA rodando no modelo errado
❌ lentidão
❌ colapso mental

Perfis trazem:

✔️ ordem
✔️ controle
✔️ isolamento
✔️ foco
✔️ segurança
✔️ previsibilidade
✔️ custo menor

---

# 🎯 **3.2 — Estrutura dos Perfis (Visualização Pro)**

```
VSCode
 ├── Profile: JuniorDeep-Air
 │        ├── settings.json
 │        ├── extensions.json
 │        ├── keybindings.json
 │        ├── AI access rules
 │        └── interface layout
 │
 ├── Profile: JuniorDeep-Mini
 │        ├── settings.json
 │        ├── extensions.json
 │        ├── AI access rules
 │        └── performance-optimized config
 │
 └── Profile: JuniorDeep-Agent
          ├── elevated settings.json
          ├── full terminal execution
          ├── full FS access
          ├── security bypass
          └── restricted extensions
```

Cada perfil é um **micro universo independente**.

---

# 🖥️ **3.3 — Perfil JuniorDeep-Air**

### *“O cérebro criativo. A máquina estratégica.”*

Este é seu perfil PRINCIPAL.

Ele é feito para:

🧠 **planejar**
🧩 **arquitetar**
⚙️ **codar projetos grandes**
🤖 **usar IAs fortes**
🔍 **depurar com raciocínio avançado**
🔥 **construir automações complexas**
🎵 **trabalhar com workflows de áudio**
📦 **projetos fullstack**

### **Modelos habilitados:**

* GPT-5.1 (Blueprint, decisões importantes)
* Claude 4.5 Sonnet (Execução + Terminal)
* GPT-5.1-Codex (Refactor e inline avançado)
* Gemini 2.5/3 (quando quiser variedade)

### **Extensões que usam IA no Air:**

* GitHub Copilot Chat
* GitHub Copilot Inline
* GitHub Copilot Agent
* VSCode Chat (opcional, com Claude)

### **Extensões que NÃO usam IA:**

(para economizar e evitar lentidão)

* GitLens
* Docker
* ESLint
* Prettier
* Python
* Markdownlint
* Code Spell Checker

O Air é otimizado com:

✔️ IA forte
✔️ Permissões amplas
✔️ Auto-execução de terminal
✔️ Zero extensões inúteis consumindo IA
✔️ Alto poder de contexto

O resultado?
**Você cria software muito rápido e com foco total.**

---

# 🧱 **3.4 — Perfil JuniorDeep-Mini**

### *“O braço operacional. A máquina que trabalha enquanto você vive a vida.”*

O Mini tem funções completamente diferentes:

🟦 **Executar scripts**
🟦 **Rodar automações 24/7**
🟦 **Gerenciar pipelines**
🟦 **Servir como servidor caseiro inteligente**
🟦 **Rodar agentes com IA leve**
🟦 **Operar tarefas repetitivas**
🟦 **Trabalhar com arquivos**

### **Modelos padrão:**

* GPT-5 Mini
* GPT-4o Mini
* Sonnet Mini
* Codex Mini

Esses modelos:

✔️ são mais leves
✔️ não sobrecarregam o Mini
✔️ não gastam muito token
✔️ rodam mais rápido em hardware limitado

Mas quando você quer:

> “Mano, agora preciso GPT-5.1 full aqui”

Você só troca o modelo no chat.
Você tem **poder total**, mas **usa com moderação**.

### **Recursos ativos no Mini:**

* Terminal execution
* File manipulation
* Agent Mode
* Autocomplete Codex mini

### **Extensões desativadas:**

* tudo que não serve para automação
* tudo que consome IA sem necessidade
* tudo que deixa a máquina lenta

---

# 🤖 **3.5 — Perfil JuniorDeep-Agent**

### *“Não é para escrever código. É para EXECUTAR.”*

Esse perfil é especial.

Ele serve para:

⚡ **Dar acesso total a GPT-5 e Claude para operar sua máquina**
⚡ **Rodar automações complexas**
⚡ **Montar e destruir projetos**
⚡ **Executar scripts perigosos**
⚡ **Criar e mover centenas de arquivos**
⚡ **Fazer operações no sistema**
⚡ **Build/Deploy**

Ele é o modo:

> **“IA com poder sem travas.”**

Mas ele tem proteções fortes:

* Extensões limitadas
* Nada que desvie IA
* Nada que interfira no sandbox
* Zero plugins que interceptam terminal

Aqui, o VSCode é o mais “limpo” possível.
Puro.
Perfeito para actions.

---

# 🧠 **3.6 — Como trocar perfis corretamente**

### Método 1 — Rápido (via barra lateral)

```
Click no ícone de Profiles (lado esquerdo)
→ Selecionar JuniorDeep-Air / Mini / Agent
```

### Método 2 — Command Palette

```
>Profiles: Switch Profile
```

### Recomendações Ninja:

* **Air:** 80% do tempo
* **Mini:** quando estiver usando o Mini ou rodando automações remotas
* **Agent:** quando vai executar tarefas críticas

---

# 🔄 **3.7 — Fluxo Interno ao trocar perfis**

Quando você troca de perfil, estas ações acontecem:

1. Fecha projetos
2. Recarrega extensão do Copilot
3. Aplica o novo `settings.json` do perfil
4. Revalida permissões de terminal
5. Reavalia modelos permitidos
6. Recarrega o AI Router
7. Recarrega layout visual
8. Recarrega extensões
9. Carrega o novo conjunto de keybindings
10. Inicializa o contexto do Agent

**Isso explica porque às vezes o VSCode fica 2–5 segundos parado.**

---

# 🛡️ **3.8 — Por que isso te dá segurança operacional**

Perfis diferentes evitam:

* acionar IA pesada no Mini
* que modelos ruins assumam operações críticas
* que o VSCode gaste créditos com extensões inúteis
* que suas automações quebrem por conflito
* usar GPT grande quando Claude seria melhor (e vice-versa)
* quebrar configurações do Air mexendo no Mini
* deixar o Agent exposto em perfis normais

---

# 📦 **3.9 — Como perfis controlam custo**

Isso é muito importante:

### **No Air**

* GPT forte → usados para design, blueprint, arquitetura
* Codex forte → inline
* Agent com Claude ou GPT-5.1 → execução precisa

Custo maior, mas você usa IA inteligente (não volume).

### **No Mini**

* IA leve → barata
* Inline Mini → gratuito
* Agent → só quando necessário

### **No Agent Profile**

* Zero desperdício
* Zero modelos extras
* Zero outras extensões chamando IA

É o perfil mais barato de todos.

---

# 🧲 **3.10 — Como perfis se conectam com settings.json**

Cada perfil tem seu próprio:

* settings.json
* extensions.json
* keybindings.json
* UI config

Por isso você pode:

* habilitar terminal em 1 perfil
* bloquear terminal no outro
* permitir modelos grandes no Air
* permitir modelos leves no Mini
* deixar o Agent puro

Sem perfis, isso seria impossível.

---

# 🔍 **3.11 — Como recuperar perfis quebrados**

O capítulo 8 do manual vai ensinar isso passo a passo.

Mas a lógica é:

```
Profiles → Edit Profile → Reset to Defaults
```

Ou:

```
~/Library/Application Support/Code/User/globalStorage/profile (carteiras)
```

E restaurar.

---

# 🔚 **Fim do Capítulo 3**

Você agora entende por completo o sistema que sustenta seu VSCode profissional.

Pronto para ir mais fundo?

---

---

← Capítulo anterior: [02 — Arquitetura VSCode + IA](02-arquitetura-vscode-ia.md)  

Próximo capítulo → [04 — Configuração settings.json](04-config-setting-json.md)
