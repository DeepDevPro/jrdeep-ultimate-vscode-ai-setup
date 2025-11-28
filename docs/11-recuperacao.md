# 📘 **CAPÍTULO 11 — GUIA DE RECUPERAÇÃO TOTAL**

### *“Quando tudo quebra — este capítulo salva sua vida.”*

Este é o capítulo mais crítico do Manual Ultra JrDeep Edition™.
Aqui você aprende a:

* Recuperar o VSCode quando ele trava, buga ou não abre
* Restaurar perfis Air / Mini / Agent
* Reparar o GPT-5 e o Claude quando param de executar comandos
* Consertar extensões corrompidas
* Reverter permissões quebradas
* Resetar o terminal do Copilot
* Detectar conflitos entre extensões
* Recuperar a IA quando ela PARA DE OUVIR o VSCode (bug típico)
* E até reconstruir seu ambiente inteiro em 60 segundos

Este capítulo transforma você na pessoa que **NUNCA** quebra o VSCode de forma irreversível.

---

---

← Capítulo anterior: [10 — Migrar entre Máquinas](10-migrar.md)  

Próximo capítulo → [12 — GPT vs Claude](12-gpt-vs-claude.md)
# 🟥 **11.1 — O QUE PODE QUEBRAR NO SEU SETUP (lista oficial)**

O VSCode pode “quebrar” em 8 áreas diferentes:

1. **Perfis corrompidos**
2. **settings.json corrompido**
3. **Extensões incompatíveis**
4. **Copilot Agent quebrado**
5. **Terminal não autorizado**
6. **GPT-5.1 ou Claude presos em “safe mode”**
7. **Profiles com IDs misturados**
8. **Cache interno do VSCode corrompido**

Você vai aprender a reparar TODAS elas sem reinstalar o VSCode.

---

# 🟦 **11.2 — SINTOMA → DIAGNÓSTICO**

Use esta tabela ninja:

| Sintoma                      | Causa provável                          |
| ---------------------------- | --------------------------------------- |
| GPT não cria arquivos        | Permissão incompleta ou Agent desligado |
| Claude não executa terminal  | Safe Mode ativo                         |
| Inline autocomplete some     | settings.json errado ou extensão bugada |
| Copilot para de responder    | cache corrompido                        |
| Perfis somem                 | pasta profiles danificada               |
| Extensões param de carregar  | conflito entre versões                  |
| VSCode fecha ao abrir perfis | settings.json inválido                  |
| Chat não reconhece OS        | VSCode sem API host                     |

---

# 🟨 **11.3 — PRIMEIRA AÇÃO UNIVERSAL (resolve 50%)**

Sempre comece com o “reload avançado”:

```
Developer: Reload Window With Extensions Disabled
```

Se **tudo funcionar com este modo**, significa que:

➡️ **Alguma extensão está quebrando seu VSCode.**

---

# 🟧 **11.4 — SEGUNDA AÇÃO UNIVERSAL (resolve 15%)**

Limpe o cache corrompido:

```
rm -rf ~/Library/Application\ Support/Code/Cache/*
rm -rf ~/Library/Application\ Support/Code/CachedData/*
```

Reabra o VSCode.

---

# 🔥 **11.5 — RECUPERAR SEU AMBIENTE DE IA (GPT & Claude)**

Aqui vai o protocolo JrDeep quando a IA para de obedecer.

---

## **SINTOMA:**

GPT não cria arquivos, mesmo em Agent.

## **SOLUÇÃO NINJA:**

**PASSO 1 — Verificar o modo**

No chat:

```
Qual é o meu modo atual? (Agent / Chat)
```

Se ele responder **Chat**, faça:

```
/mode agent
```

---

## **SINTOMA:**

Claude não executa comandos no terminal.

## **SOLUÇÃO NINJA:**

```
/mode agent
/agent enable terminal
```

---

## **SINTOMA:**

GPT-5.1 diz: “Não tenho permissão.”

## **SOLUÇÃO NINJA:**

Abra:

```
CMD + SHIFT + P
> Preferences: Open Settings (JSON)
```

Adicione:

```json
"github.copilot.chat.executeCommands": "allow"
```

Recarregue:

```
Developer: Reload Window
```

---

# 🟥 **11.6 — RESTAURAR PERFIS AIR / MINI / AGENT**

Perfis podem corromper se:

* Você editar o settings global por engano
* Trocar extensões entre perfis
* Mudar permissões do chat
* VSCode atualizar no meio de um comando da IA

Siga o protocolo.

---

## **PASSO 1 — Exportar o perfil atual (mesmo quebrado)**

```
Profiles: Export Profile
```

---

## **PASSO 2 — Resetar**

```
Profiles: Reset Profile
```

---

## **PASSO 3 — Importar de volta**

```
Profiles: Import Profile
```

Selecione o `.profile.json` salvo previamente.

---

## **PASSO 4 — Apagar só o storage do perfil**

Se ainda estiver bugado:

```
rm -rf ~/Library/Application\ Support/Code/User/profiles/<ID>/globalState.json
```

Ou:

```
rm -rf ~/Library/Application\ Support/Code/User/profiles/<ID>/workspaceState.json
```

Isso limpa o ambiente sem perder configurações.

---

# 🟩 **11.7 — RECUPERAR settings.json GLOBAL**

Se você acidentalmente estragou o settings global:

## **OPÇÃO 1 — Voltar ao estado anterior**

```
mv settings.json.bak settings.json
```

(Se tiver backup automático)

---

## **OPÇÃO 2 — Criar settings limpo zerado**

Crie:

```
{}
```

Isso restaura **tudo de volta ao padrão**, sem apagar seus perfis.

---

# 🟦 **11.8 — RECUPERAR EXTENSÕES CORROMPIDAS**

Primeiro, descubra quais estão quebrando:

```
Developer: Show Running Extensions
```

Se aparecerem “slow”, “blocked” ou “crashed”, anote.

---

## ❌ Extensões mais comuns que quebram setups de IA:

* Docker
* GitLens
* Python
* Prettier antiga
* Formatters duplicados
* VSCode ESLint

❗ Por isso no seu setup já deixamos várias sem IA.

---

## ✔️ Reset de extensões específicas

```
rm -rf ~/.vscode/extensions/<nome>
```

E depois reinstale via marketplace.

---

# 🔄 **11.9 — QUANDO O VSCode NÃO ABRE**

Se clicar no VSCode e nada acontecer:

---

## **PASSO 1 — Abrir via terminal**

```
code --verbose
```

O terminal mostrará **onde está o erro**.

---

## **PASSO 2 — Resetar o armazenamento**

```
rm -rf ~/Library/Application\ Support/Code/User/workspaceStorage/*
```

---

## **PASSO 3 — Resetar o cache**

```
rm -rf ~/Library/Application\ Support/Code/Cache/*
rm -rf ~/Library/Application\ Support/Code/CachedData/*
```

---

## **PASSO 4 — Reset sem deletar perfis**

```
code --disable-extensions
```

Se abrir → é alguma extensão quebrada.

---

# 💣 **11.10 — QUANDO NADA FUNCIONA (O MÉTODO NUCLEAR)**

### *“Reinstala o VSCode sem perder NENHUM perfil ou configuração.”*

Este método salva absolutamente tudo.

---

## **PASSO 1 — Salve os perfis**

```
cp -R "~/Library/Application Support/Code/User/profiles" ~/Desktop/backups/
```

---

## **PASSO 2 — Salve extensões**

```
cp -R ~/.vscode/extensions ~/Desktop/backups/extensions/
```

---

## **PASSO 3 — Salve settings.json global**

```
cp "~/Library/Application Support/Code/User/settings.json" ~/Desktop/backups/
```

---

## **PASSO 4 — Apague apenas o aplicativo (não suas configs)**

```
sudo rm -rf /Applications/Visual\ Studio\ Code.app
```

---

## **PASSO 5 — Baixe de novo do site oficial**

VSCode → Download for macOS (x64/M1)

---

## **PASSO 6 — Reabra e tudo estará igualzinho**

VSCode automaticamente recarrega:

* perfis
* extensões
* IA
* permissões
* settings
* terminal
* inline autocomplete

**É magia.**
Mas é magia científica.

---

# 🟩 **11.11 — CHECKLIST RÁPIDO DE RECUPERAÇÃO (cole na parede)**

```
1. Reload com extensões desativadas
2. Limpar cache
3. Verificar modo Agent
4. Reautorizar execução
5. Resetar perfil
6. Resetar extensões problemáticas
7. Apagar storage do perfil
8. code --verbose para logs
9. code --disable-extensions
10. Reinstalar o app (sem apagar perfis)
```

---

# 🟦 **11.12 — Como criar um “Bot de Recuperação” no Lovable**

Se quiser, posso criar:

* um agente
* com este capítulo como base
* que diagnostica o VSCode
* e te dá a solução certa para cada sintoma

Ele funciona assim:

Você diz:

> “GPT não está mais criando arquivos no Air.”

Ele responde:

→ problema no executeCommands
→ solução aplicada
→ te dá o comando certo
→ testa junto com você

Se quiser, diga:

```
Quero o agente de recuperação
```

---
