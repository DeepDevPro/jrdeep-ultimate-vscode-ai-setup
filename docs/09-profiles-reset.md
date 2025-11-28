# 📘 **CAPÍTULO 9 — RESET INDIVIDUAL DE PERFIS DO VSCode**

### *“Limpar só o que precisa — sem quebrar o resto.”*

Esse capítulo é ouro puro, porque o VSCode **não foi projetado originalmente** para perfis avançados como você usa (Air, Mini, Agent), e por isso muitas pessoas acabam misturando configurações, corrompendo perfis ou perdendo setup.

Aqui você aprende a:

* Resetar **apenas 1 perfil**
* Exportar e importar perfis
* Clonar perfis
* Reparar perfis quebrados
* Migrar perfis entre Mac Air → Mac Mini
* Revisar dependências de IA por perfil
* Restaurar perfis que sumiram
* Colocar perfis sob versionamento

Isso faz parte do seu treinamento ninja avançado de ambiente de desenvolvimento.

---

# 🧩 **9.1 — ENTENDER A ARQUITETURA DE PERFIS**

Perfis no VSCode são compostos por:

1. **settings.json** específicos do perfil
2. **extensions.json** específicos
3. **state.json**
4. **storage.json**
5. **keybindings.json**
6. **Extensões ativadas/desativadas**

Cada perfil é uma pasta dentro de:

```
~/Library/Application Support/Code/User/profiles/
```

Dentro de cada pasta existe algo como:

```
profile-155ae27a/
    settings.json
    keybindings.json
    globalState.json
    workspaceState.json
    tasks.json
    snippets/
    extensions.json
```

👉 Cada perfil é totalmente isolado.

---

# 🔥 **9.2 — O GRANDE ERRO DA MAIORIA**

As pessoas editam o settings.json *errado*.

Você **NUNCA** deve editar:

```
~/Library/Application Support/Code/User/settings.json
```

Esse é o **User global** — e ele sobrescreve seus perfis.

Você sempre deve editar via Command Palette:

```
> Preferences: Open Settings (JSON)
```

*Quando estiver dentro do perfil correto*.

---

# ✨ **9.3 — COMO RESETAR APENAS UM PERFIL (MÉTODO SEGURO)**

Você não vai mexer com terminal.

Apenas use o gerenciador de perfis do VSCode.

---

## **PASSO 1 — Abra o seletor de perfis**

```
CMD + SHIFT + P
> Profiles: Manage
```

---

## **PASSO 2 — Selecione o perfil a resetar**

Exemplo:

* **JuniorDeep-Air**
* **JuniorDeep-Mini**
* **JuniorDeep-Agent**

---

## **PASSO 3 — Execute o reset individual**

Command Palette:

```
> Profiles: Reset Profile
```

Esse comando:

✔ limpa o settings.json daquele perfil
✔ limpa keybindings
✔ limpa todos os estados e storage
✔ mantém suas extensões
✔ não afeta nenhum outro perfil
✔ recria tudo automaticamente

⛔ **Não apaga seus projetos.**
⛔ **Não apaga suas extensões.**

---

# 🧨 **9.4 — RESET HARD DE UM PERFIL (AVANÇADO)**

Se você quiser deletar absolutamente tudo de um perfil só:

---

## **PASSO 1 — Descobrir o ID do perfil**

```
CMD + SHIFT + P
> Profiles: Export Profile
```

Exporte para ver o nome interno (ex: `155ae27a`).

---

## **PASSO 2 — Apagar manualmente o perfil**

```
rm -rf ~/Library/Application\ Support/Code/User/profiles/155ae27a
```

(ou o ID correto)

---

## **PASSO 3 — Reimportar o perfil limpo**

```
Profiles: Import Profile
```

Selecione:

* `JuniorDeep-Air.json`
* `JuniorDeep-Mini.json`
* `JuniorDeep-Agent.json`

---

# 🔧 **9.5 — COMO CLONAR UM PERFIL**

Quer criar um perfil novo baseado no Air?
Use:

```
CMD + SHIFT + P
> Profiles: Export Profile
```

Isso cria um `.profile.json` com:

* extensões
* settings
* keybindings
* aparência
* agent configs

Depois:

```
> Profiles: Import Profile
```

Digite um nome, por exemplo:

* “JuniorDeep-Server”
* “JuniorDeep-MacMini-Legacy”
* “JuniorDeep-Automaster-VM”
* “JuniorDeep-NodeCluster”

---

# 🌀 **9.6 — COMO MIGRAR PERFIS ENTRE MÁQUINAS (AIR → MINI)**

Melhor processo:

---

## ✔️ **PASSO 1 — Exportar o perfil no Mac Air**

```
CMD + SHIFT + P
> Profiles: Export Profile
```

Salve o arquivo em:

```
~/Desktop/Air-Profiles/
```

---

## ✔️ **PASSO 2 — Sincronizar com o Mini**

4 opções:

* Airdrop
* iCloud
* Dropbox
* GitHub (pasta privada)

---

## ✔️ **PASSO 3 — Importar no Mini**

No Mini:

```
Profiles: Import Profile
```

Selecione:

* `JuniorDeep-Mini.profile.json`
  ou
* `JuniorDeep-Agent.profile.json`

👉 Instantâneo, funciona igual no Air.

---

# ⚠️ **9.7 — COMO EVITAR CORRUPÇÃO DE PERFIS**

### Nunca misture:

❌ Settings globais com settings de perfil
❌ Usar Sync Settings com perfis ativos
❌ Usar Code Insiders com perfis do stable
❌ Copilot Agent ativado em perfis que não têm permissões
❌ GitLens AI ativo
❌ Docker com recursos de IA

### Sempre:

✔ Salve perfis exportados
✔ Use o manual de reset
✔ Teste perfis após grandes alterações
✔ Reinicie o VSCode 1× por dia
✔ Mantenha perfis separados por máquina e objetivo

---

# 🎭 **9.8 — QUANDO CRIAR UM NOVO PERFIL?**

Crie um perfil novo quando você muda de contexto:

### exemplos:

| Perfil    | Uso                                             |
| --------- | ----------------------------------------------- |
| **Air**   | programar pesado, arquitetura, projetos grandes |
| **Mini**  | manutenção, scripts leves, servidor caseiro     |
| **Agent** | automação total com IA, comandos perigosos      |

Outros perfis úteis:

| Perfil                   | Motivo                         |
| ------------------------ | ------------------------------ |
| **JuniorDeep-Node**      | projetos Node/Next             |
| **JuniorDeep-Flutter**   | isolar Android SDK             |
| **JuniorDeep-Audio**     | C++ / VST / libs de áudio      |
| **JuniorDeep-TestLab**   | sandbox para testar extensões  |
| **JuniorDeep-Streaming** | automações do Radio Importante |

---

# 🔍 **9.9 — TESTE RÁPIDO: O PERFIL ESTÁ FUNCIONANDO?**

Pergunte ao Copilot Chat:

```
Qual é o modelo que você está usando agora?
```

Ele deve responder com exatidão:

* GPT-5.1 Preview
* Claude 4.5 Sonnet
* gpt-5.1-codex-mini

Se ele der resposta confusa → perfil corrompido.

Outro teste:

```
Crie um arquivo chamado perfil_teste.txt
```

Se ele não criar → o Agent está quebrado.

---

# 🛡️ **9.10 — PROCEDIMENTO COMPLETO DE RESTAURAÇÃO DE UM PERFIL**

Tempo total: **1 minuto.**

---

### **PASSO 1 — Exportar o perfil (backup antes da cirurgia)**

```
Profiles: Export Profile
```

---

### **PASSO 2 — Reset Profile**

```
Profiles: Reset Profile
```

---

### **PASSO 3 — Importar novamente o perfil exportado**

```
Profiles: Import Profile
```

---

### **PASSO 4 — Forçar reload**

```
Developer: Reload Window
```

→ Perfil restaurado.

---

# 🎉 **Fim do Capítulo 9**

Se quiser, posso gerar:

* 📝 **Checklist A4**
* 📄 **Versão para imprimir**
* 📁 **Script automático para resetar perfis**
* 🌐 **Versão para usar no Lovable como agente de recuperação**

---

---

← Capítulo anterior: [08 — Disaster Recovery](08-disaster-recovery.md)  

Próximo capítulo → [10 — Migrar entre Máquinas](10-migrar.md)
