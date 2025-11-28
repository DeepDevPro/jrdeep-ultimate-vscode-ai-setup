# 📘 **CAPÍTULO 10 — MIGRAR TODA SUA CONFIGURAÇÃO PARA OUTRA MÁQUINA EM 10 MINUTOS**

### *“Levar a sua Fort Knox de IA de uma máquina pra outra sem quebrar nada.”*

Você pediu este capítulo — e ele é um dos mais importantes do Manual Ultra JrDeep Edition™.

---

← Capítulo anterior: [09 — Reset de Perfis](09-profiles-reset.md)  

Próximo capítulo → [11 — Recuperação Total](11-recuperacao.md)
Esse capítulo te permite:

* Trocar de Mac sem estresse
* Formatar a máquina sem medo
* Sincronizar o Air e o Mini
* Criar um ambiente identicamente configurado em qualquer Mac futuro
* Rodar projetos com Copilot, GPT-5.1 e Claude exatamente como hoje

E tudo em **menos de 10 minutos**.

Vamos lá.

---

# 🧩 **10.1 — O PRINCÍPIO: TUDO SE RESUME A 4 PASTAS**

Você só precisa levar **quatro pastas**:

---

## 🔹 **1. Extensões instaladas**

```
~/.vscode/extensions/
```

Armazena:

* Copilot
* Python
* Prettier
* Docker
* GitLens
* E tudo mais

---

## 🔹 **2. Perfis do VSCode (seus ambientes Air/Mini/Agent)**

```
~/Library/Application Support/Code/User/profiles/
```

Cada perfil tem:

* settings.json
* state.json
* keybindings
* storage
* IA habilitada/desabilitada
* tudo que define cada ambiente do seu setup ninja

---

## 🔹 **3. Settings globais**

```
~/Library/Application Support/Code/User/settings.json
```

**Importante:**
Esse NÃO é o seu ambiente de programação — mas contém configs de sistema, como:

* Code Runner
* Live Server
* Formatters
* Comandos aprovados automaticamente

Ele precisa ir junto.

---

## 🔹 **4. Snippets**

```
~/Library/Application Support/Code/User/snippets/
```

São os “atalhos de código” que você pode criar:

* templates
* padrões de código
* funções repetidas
* padrões de arquivo

---

# 🧠 **10.2 — O MÉTODO JRDEEP DE MIGRAÇÃO**

Sua migração sempre tem 3 fases:

1. **Exportação**
2. **Transferência**
3. **Importação**

---

# 🚀 **10.3 — PASSO A PASSO PARA EXPORTAR (MAC ORIGEM)**

## **PASSO 1 — Exportar os perfis**

No VSCode:

```
CMD + SHIFT + P
> Profiles: Export Profile
```

Exporte:

* **JuniorDeep-Air**
* **JuniorDeep-Mini**
* **JuniorDeep-Agent**

Guarde os arquivos `.profile.json`.

---

## **PASSO 2 — Exportar a pasta de perfis (backup 1:1)**

Terminal:

```
mkdir ~/Desktop/VSCode-Migration-Backup
cp -R "~/Library/Application Support/Code/User/profiles" ~/Desktop/VSCode-Migration-Backup/
```

---

## **PASSO 3 — Exportar as extensões**

```
cp -R ~/.vscode/extensions ~/Desktop/VSCode-Migration-Backup/
```

---

## **PASSO 4 — Exportar settings globais**

```
cp "~/Library/Application Support/Code/User/settings.json" ~/Desktop/VSCode-Migration-Backup/
```

---

## **PASSO 5 — Exportar snippets**

```
cp -R "~/Library/Application Support/Code/User/snippets" ~/Desktop/VSCode-Migration-Backup/
```

---

# 📤 **10.4 — TRANSFERÊNCIA PARA OUTRA MÁQUINA**

Você pode passar via:

* Airdrop
* Pendrive
* iCloud
* Dropbox
* HD externo
* Drive do Google
* Repositório Git privado

**Recomendado:** Airdrop ou pendrive (mais rápido e limpo).

---

# 🖥️ **10.5 — IMPORTAÇÃO NA MÁQUINA DESTINO (MAC NOVO)**

## **PASSO 1 — Instalar VSCode (versão estável)**

Nada de Insiders.

---

## **PASSO 2 — Copiar extensões**

```
cp -R ~/Desktop/VSCode-Migration-Backup/extensions ~/.vscode/
```

---

## **PASSO 3 — Copiar perfis**

```
cp -R ~/Desktop/VSCode-Migration-Backup/profiles "~/Library/Application Support/Code/User/"
```

---

## **PASSO 4 — Copiar settings globais**

```
cp ~/Desktop/VSCode-Migration-Backup/settings.json "~/Library/Application Support/Code/User/settings.json"
```

---

## **PASSO 5 — Copiar snippets**

```
cp -R ~/Desktop/VSCode-Migration-Backup/snippets "~/Library/Application Support/Code/User/"
```

---

## **PASSO 6 — Importar os perfis exportados**

No VSCode:

```
CMD + SHIFT + P
> Profiles: Import Profile
```

Selecione:

* JuniorDeep-Air.json
* JuniorDeep-Mini.json
* JuniorDeep-Agent.json

---

## **PASSO 7 — Finalizar com Reload**

```
Developer: Reload Window
```

---

# 💥 **10.6 — E AGORA, TESTAR OS DOIS MODELOS (CLAUDE e GPT)**

### **Teste GPT-5.1 Agent**

```
Crie um arquivo chamado teste_migracao_gpt.txt
```

Ele deve criar.

### **Teste Claude 4.5 Sonnet Agent**

```
Liste todos os arquivos dessa pasta
```

Ele deve rodar o comando **sem pedir permissão**.

---

# 🛡️ **10.7 — COMO SABER SE TUDO DEU CERTO**

Sinais perfeitos de migração bem-sucedida:

✔ perfis aparecem iguais
✔ GPT-5.1 cria arquivos normalmente
✔ Claude executa terminal
✔ inline suggestions funcionando
✔ extensões compatíveis com IA desativadas
✔ Copilot executa ações sem erro
✔ terminal vinculado ao Agent

Se algo falhar → capítulo 11 ensina recuperação total.

---

# 💡 **10.8 — MIGRAÇÃO AUTOMÁTICA (SCRIPT JRDEEP)**

Posso gerar um script `.sh` que:

* Exporta tudo da máquina origem
* Zipa
* Transferir via pendrive
* Restaura automaticamente na máquina destino

**Se quiser, digite:**

```
Quero o script de migração
```

---

# 🧬 **10.9 — SE VOCÊ TROCAR DE MACBOOK NO FUTURO…**

Você vai migrar sua IA inteira em **menos de 10 minutos**.

E tudo:

* identicamente configurado
* com o mesmo comportamento
* sem conflitos
* sem quebrar perfis
* sem reconfigurar extensões
* sem perder permissões

Porque agora você sabe exatamente onde tudo vive.

---
