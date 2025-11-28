# 📘 Capítulo 13 — Fluxo de Trabalho JrDeep™

## 13.1 Visão geral

Este capítulo define o **Fluxo de Trabalho JrDeep™**, ou seja, como combinar:

- **GPT-5.1** → pensar e criar,
- **Claude 4.5** → executar e depurar,
- **Codex Mini** → completar e refinar código,

dentro do VSCode, para produtividade máxima.

A ideia central:

> **Nenhum modelo faz tudo. Cada um joga numa posição.**

---

## 13.2 As fases do fluxo

O ciclo completo é:

1. **GPT-5.1 → Planejamento (pensar)**
2. **GPT-5.1 → Criação de arquivos e módulos**
3. **Claude 4.5 → Execução e terminal**
4. **Claude 4.5 → Debug e correções**
5. **Codex Mini → Autocomplete e micro-refactors**
6. **GPT-5.1 → Refinamento e polimento**
7. **Claude 4.5 → Validação final**

---

### Fase 1 — Ideação e Planejamento (GPT-5.1)

Use GPT-5.1 para:

- levantar requisitos;
- escolher tecnologias;
- desenhar arquitetura;
- dividir o projeto em módulos e microtarefas;
- criar o blueprint inicial.

Exemplos de prompts:

- “Me ajude a planejar um app X com foco em Y.”
- “Gere um blueprint completo com módulos, pastas, endpoints e fluxos.”

---

### Fase 2 — Criação de Arquivos (GPT-5.1)

Ainda com GPT-5.1, você:

- cria `app.py`, `main.js`, `api/routes/user.ts`, etc.;
- gera código base (boilerplate) com boas práticas;
- prepara estrutura de pastas.

Exemplos:

- “Crie o arquivo `app.py` com um servidor Flask básico.”
- “Implemente o módulo X seguindo o padrão definido no blueprint.”

---

### Fase 3 — Execução (Claude 4.5)

Agora entra **Claude 4.5 Sonnet**:

- instala dependências;
- executa comandos no terminal;
- roda servidores (`npm run dev`, `flask run`, etc.);
- inicializa containers Docker;
- navega no filesystem.

Exemplos:

- “Instale as dependências listadas no README e rode o servidor.”
- “Liste os arquivos da pasta atual e confirme se X está presente.”

---

### Fase 4 — Debug (Claude 4.5)

Claude é o melhor modelo para:

- interpretar erros do terminal;
- reagir a falhas;
- ajustar comandos;
- corrigir permissões;
- repetir o comando corrigido.

Exemplo:

> “Esse comando falhou, analise o erro acima e corrija até funcionar.”

---

### Fase 5 — Autocomplete e Micro-Refactors (Codex Mini)

Aqui entra o **Codex Mini (inline suggestions)**:

- completa funções enquanto você digita;
- cria loops simples;
- produz validações;
- sugere pequenos refactors.

Regra prática:

> Qualquer mudança de **1 a 15 linhas** → faça no editor com autocomplete.

---

### Fase 6 — Refinamento (GPT-5.1)

Volte ao GPT-5.1 para:

- melhorar a qualidade do código;
- aplicar padrões de projeto;
- organizar arquivos;
- gerar documentação e README.

Exemplos:

- “Melhore esse módulo aplicando boas práticas.”
- “Crie a documentação da API com exemplos de uso.”

---

### Fase 7 — Validação final (Claude 4.5)

Claude verifica:

- se tudo roda do zero;
- se as dependências estão ok;
- se o app levanta sem erro;
- se scripts de teste passam.

Prompt típico:

> “Vamos testar o projeto do zero: rode os comandos necessários e confirme que está tudo funcionando.”

---

## 13.3 Diagrama do ciclo

- GPT-5.1 → planeja, cria, refina
- Claude 4.5 → executa, debuga, valida
- Codex Mini → completa e polimenta código


## 13.4 Benefícios do fluxo JrDeep™

- Você pensa menos em detalhes e mais em arquitetura.
- Seus projetos ficam mais consistentes entre si.
- Fica fácil retomar um projeto após semanas.
- Qualquer agente futuro (Lovable, etc.) pode ser treinado com este padrão.


