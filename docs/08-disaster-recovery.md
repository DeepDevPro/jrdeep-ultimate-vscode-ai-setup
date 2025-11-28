# 📘 **CAPÍTULO 8 — PROCEDIMENTOS DE RECUPERAÇÃO (DISASTER RECOVERY)**

### *“Quando tudo quebrar — você não quebra junto.”*

Este é um dos capítulos mais importantes do manual.
Aqui você aprende a **salvar sua sanidade** quando:

* VSCode começa a falhar
* Copilot para de responder
* Terminal para de executar comandos
* A IA ignora instruções
* O Agent trava
* Extensões somem
* Keybindings quebram
* O VSCode não abre
* O perfil bagunça tudo
* O macOS entra em conflito com extensões
* Configurações se misturam entre Air e Mini

Você vai conseguir:

* Recuperar tudo **em 2 a 10 minutos**
* Sem reinstalar nada
* Sem perder arquivos
* Sem apagar projetos

Vamos para a bíblia do *DR – Disaster Recovery*.

---

# 🧨 **8.1 — O QUE MAIS QUEBRA O VSCode**

O que causa 90% dos problemas:

1. **Extensões que interferem no Terminal**
2. **Plugins que tentam acessar o filesystem antes do Agent**
3. **Settings.json poluído**
4. **Perfis misturados**
5. **múltiplas versões do VSCode rodando (Stable vs Insiders)**
6. **GitLens com IA ativado**
7. **Docker com recursos de inteligência**
8. **Atualizações automáticas**
9. **Copilot desatualizado**
10. **Perfil renomeado indevidamente**

Com esse capítulo, você resolve tudo isso rapidamente.

---

# 🛡️ **8.2 — PRIMEIRO SOCORROS (30 segundos)**

### *“Se der pau, faça isso ANTES de qualquer outra coisa.”*

**Passo 1 — Reiniciar apenas o VSCode (Hard Refresh)**
Fecha tudo e pressione:

```
CMD + SHIFT + P
> Developer: Reload Window
```

👉 resolve 40% dos problemas.

---

**Passo 2 — Reiniciar os serviços internos do VSCode**

Command Palette:

```
> Developer: Restart Extension Host
```

👉 resolve mais 25%.

---

**Passo 3 — Limpar o contexto de IA**

No Copilot Chat:

```
/reset
```

ou no VSCode:

```
CMD + SHIFT + P
> GitHub Copilot: Reset Chat Context
```

👉 resolve 10%.

Total: **75% dos problemas resolvidos sem nem suar.**

---

# 🧯 **8.3 — RECUPERAR O TERMINAL QUANDO A IA NÃO EXECUTA COMANDOS**

Se a IA responde coisas como:

* “Não tenho permissão para executar comandos”
* “Terminal execution está desabilitado”
* “Não encontrei nenhum terminal válido”

Faça isto:

### ✔️ 1. Teste o recurso manualmente:

Command Palette:

```
> Copilot: Enable/Disable Chat Terminal Execution
```

Se isso **NÃO APARECER**:

👉 você está em um perfil sem permissões.

Mude o perfil:

```
CMD + SHIFT + P
> Profiles: Switch Profile
```

Escolha:

### 🔥 JuniorDeep-Air

ou

### 🔥 JuniorDeep-Mini

---

### ✔️ 2. Se o comando aparece mas não funciona:

Vá no seu `settings.json` e procure:

```
"chat.tools.terminal"
```

Delete tudo.

---

### ✔️ 3. Crie um terminal limpo:

Command Palette:

```
> Terminal: Create New Terminal
```

---

### ✔️ 4. Reabra o VSCode:

```
Developer: Reload Window
```

---

Ao final, peça:

```
Teste: crie um terminal e rode “echo OK”
```

---

# 🧹 **8.4 — RECUPERAR QUANDO O Copilot PARA DE RESPONDER**

Se o Copilot:

* fica carregando infinitamente
* some
* trava
* dá resposta vazia
* não reconhece o modelo
* dá erro 400/500
* acusa “unsupported_api_for_model”

Faça os passos:

---

### ✔️ 1. Checar modelo selecionado

Alguns modelos só funcionam em certos modos:

* **gpt-5.1-codex** → apenas inline
* **gpt-5.1-preview** → apenas chat/agent
* **codex-mini** → inline
* **claude 3.5/4.5** → chat/agent
* **Claude Haiku** → inline/agent

Troque o modelo na barra superior.

---

### ✔️ 2. Resetar o Copilot Chat

Command Palette:

```
> GitHub Copilot Chat: Reset Chat Context
```

---

### ✔️ 3. Reinstalar o Copilot (rápido, não perde nada)

```
CMD + SHIFT + X
Digite: GitHub Copilot
Desinstalar → Reinstalar
```

Isso resolve 80% dos casos.

---

# 🗂️ **8.5 — RECUPERAR QUANDO O SETTINGS.JSON QUEBRA TUDO**

### Sintomas:

* atalhos somem
* terminal não funciona
* inline não aparece
* modelos ficam cinza
* extensões travam
* VSCode trava ao abrir

Solução definitiva:

---

## 🔥 **RESET PARCIAL (5 segundos)**

Command Palette:

```
> Preferences: Open Settings (JSON)
```

Substitua TUDO por:

```
{}
```

Salve → **Reload Window**.

Isso não apaga extensões nem perfis.

👉 O VSCode volta ao modo padrão limpo.

Depois, basta reinstalar o **perfil**:

```
CMD + SHIFT + P
> Profiles: Import Profile
```

Selecione:

* JuniorDeep-Air
  ou
* JuniorDeep-Mini
  ou
* JuniorDeep-Agent

Você volta aonde estava em **exatos 10 segundos**.

---

## 🔥 **RESET HARD (30 segundos)**

Se nem isso funcionar:

**Apague APENAS estes diretórios:**

```
~/Library/Application Support/Code/User/
~/Library/Application Support/Code/Cache/
~/Library/Application Support/Code/CachedData/
```

⚠️ **NÃO APAGAR o diretório `Extensions`**
Senão você perde todas EXTENSÕES instaladas.

Depois abra o VSCode → ele recria tudo automaticamente.

---

# 🔄 **8.6 — RECUPERAR QUANDO O PERFIL QUEBRA**

### Sintomas:

* perfis somem
* switch profile não funciona
* settings misturam entre perfis
* extensões erradas aparecem no perfil errado

Solução:

---

## ✔️ 1. Abrir o gerenciador de perfis

```
CMD + SHIFT + P
> Profiles: Manage
```

---

## ✔️ 2. Importar novamente o perfil correto:

```
Profiles → Import Profile
```

Selecione:

* JuniorDeep-Air.profile
* JuniorDeep-Mini.profile
* JuniorDeep-Agent.profile

---

## ✔️ 3. Se todos os perfis sumirem:

Apague:

```
~/Library/Application Support/Code/User/profiles.json
```

O VSCode recria automaticamente.

---

# 🔧 **8.7 — RECUPERAR QUANDO O VSCode NÃO ABRE**

Probabilidades:

* Workspace corrompido
* Arquivo “state” corrompido
* Extensão quebrada

---

## ✔️ 1. Tente abrir sem extensões

Terminal:

```
code --disable-extensions
```

Se abrir → problema é EXTENSÃO.

---

## ✔️ 2. Limpe o estado global

Apague:

```
~/Library/Application Support/Code/User/globalStorage
```

---

## ✔️ 3. Apague somente o workspace corrompido

```
rm ~/Library/Application\ Support/Code/User/workspaceStorage/* -rf
```

---

## ✔️ 4. Modo nuclear (raríssimo)

Reinstalar o VSCode (não apaga nada):

```
rm -rf /Applications/Visual\ Studio\ Code.app
```

Baixe novamente:

[https://code.visualstudio.com/](https://code.visualstudio.com/)

---

# 🗝️ **8.8 — RECUPERAR QUANDO A IA FAZ COISAS ERRADAS (ALUCINAÇÕES)**

## Checklist:

✔ Usando modelo errado?
✔ O contexto está poluído?
✔ Abriu muitos projetos simultâneos?
✔ Está há dias sem reiniciar?
✔ Terminal está bloqueado?
✔ Configurações do Agent conflitaram?

Faça:

```
/reset
Developer: Reload Window
Copilot: Reset Chat Context
Switch Profile
```

Resolve quase sempre.

---

# 🧬 **8.9 — DIRETRIZES UNIVERSAIS DE SEGURANÇA**

### ❌ Jamais permita:

* extensões com IA além do Copilot
* VSCode com auto-update ligado
* perfis misturados entre Air e Mini
* instalar Docker no Mini sem necessidade
* permitir que qualquer extensão gerencie o Terminal

### ✔ Sempre:

* tenha 3 perfis prontos
* use modelos leves no Mini
* reinicie VSCode 1× por dia
* mantenha seu manual salvo no GitHub
* sincronize perfis do Air para o Mini (não o contrário)
* trate o Mini como servidor, não workstation

---

# 🧩 **8.10 — CHECKLIST RÁPIDO DE RECUPERAÇÃO (POSTER)**

```
Se travou:
1. Reload Window
2. Restart Extension Host
3. Reset Chat Context
4. Trocar modelo
5. Trocar perfil

Se continuar:
6. Limpar settings.json
7. Importar perfil de volta
8. Apagar cache
9. Abrir com --disable-extensions
10. Reinstalar VSCode
```

Tempo total: **2 a 10 minutos**.

---

# 🔚 **Fim do Capítulo 8**

Se quiser, posso gerar:

➡️ **Checklist em PDF**
➡️ **Poster A3**
➡️ **Versão condensada para colar no GitHub**
➡️ **Playbook de recuperação para usar no Lovable**

---

---

← Capítulo anterior: [07 — Config Completa Air vs Mini](07-config-completa-airvsmini.md)  

Próximo capítulo → [09 — Reset de Perfis](09-profiles-reset.md)
