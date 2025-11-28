# 📘 Capítulo 14 — As 3 Zonas do VSCode

Este capítulo divide o seu trabalho em **3 zonas**:

1. **Chat** (GPT / Claude) → pensar e decidir;
2. **Editor** (Codex Mini) → escrever e ajustar código;
3. **Terminal** (Claude / GPT Agent) → executar e depurar.

---

## 14.1 Zona 1 — Chat

Use o Chat para:

- arquitetura;
- planning;
- explicações;
- criação de arquivos inteiros;
- refactors grandes;
- decisões de design.

Regra:  
> Se exige muito raciocínio → vá pro Chat.

---

## 14.2 Zona 2 — Editor

O Editor é sua **mesa de produção**.

Use com Codex Mini para:

- completar funções;
- escrever loops;
- pequenas validações;
- micro-refactors;
- pequenos ajustes.

Regra:  
> Até ~15 linhas → faça direto no editor com autocomplete.

---

## 14.3 Zona 3 — Terminal

O Terminal é a **sala de comando**.

Use principalmente com Claude para:

- rodar comandos;
- instalar libs;
- subir servidor;
- rodar testes;
- criar pastas/arquivos via shell;
- depurar erros reais.

Regra:  
> Tudo que “acontece de verdade” no sistema → é Terminal.

---

## 14.4 Regra de ouro das 3 zonas

- **Pensar → Chat**
- **Codar pequeno → Editor**
- **Executar → Terminal**
