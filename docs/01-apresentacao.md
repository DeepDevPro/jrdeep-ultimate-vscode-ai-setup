# 01 — Apresentação

Este manual é a documentação oficial do **JrDeep Ultimate VSCode AI Setup**, um ambiente otimizado para:

* Trabalhar com múltiplas IAs ao mesmo tempo (GPT, Claude e Codex)
* Desenvolvimento acelerado
* Execução autônoma de tarefas por agentes
* Criação de projetos complexos com velocidade e confiabilidade

Ele funciona em **todas as suas máquinas**:

* **MacBook Air (principal)**
* **Mac Mini 2014 (servidor / dev secundário)**

E foi desenhado para permitir que você desenvolva projetos com qualidade profissional, mesmo alternando entre máquinas e ambientes.

---

# 02 — Arquitetura Geral de Perfis

O sistema JrDeep funciona com **duas camadas**:

## **1. Perfis do VSCode (contêineres de configuração)**

Cada perfil possui:

* um conjunto próprio de extensões
* configurações específicas
* permissões diferentes para cada IA
* prioridades de performance

Perfis incluídos:

### **Perfil Air — para máquina principal**

* máximo desempenho
* IA full power
* terminal aberto para agentes
* tudo automatizado

### **Perfil Mini — para o Mac Mini 2014**

* performance otimizada
* consumo reduzido de RAM
* IA com limites ajustados
* aceleração para hardware antigo

---

## **2. Perfis de IA (comportamento dentro do VSCode)**

Cada IA pode operar em modos diferentes:

### **Modo Chat**

* usado para raciocínio profundo
* explicações
* revisão de código

### **Modo Agent**

* cria arquivos
* move pastas
* roda comandos no terminal
* edita o projeto sozinho

### **Modo Inline**

* sugestões dentro do editor
* alta velocidade

Essa arquitetura permite que você escolha **qual IA faz o quê**, dependendo da tarefa.

---

# 03 — Modelos de IA Suportados

O ambiente JrDeep tem suporte total a três grandes classes de modelos:

## **1. GPT-5.1 (Preview — via Copilot)**

* melhor para raciocínio estruturado
* melhor em criar arquivos e executar ações de agente
* forte em Python, Flask, Node.js e infra
* excelente para refatorar projetos inteiros

## **2. Claude 3.5 / 4.5 Sonnet**

* melhor para interpretar contexto longo
* superior em organização de código
* excelente para preparar documentação, fluxos e arquitetura
* muito bom em tarefas de agente

## **3. Codex (Copilot Inline)**

* ultra rápido
* feito para completar código
* ideal para detalhes, microtarefas e escrita contínua

---

# 04 — Perfil Air (MacBook Air)

Este perfil é o seu **perfil principal**. Ele carrega:

* GPT-5.1 Preview liberado
* Claude Sonnet liberado
* Execução total no terminal (`chat.tools.terminal.autoApprove`)
* Todas as permissões de edição automática de arquivos
* Extensões pesadas incluídas (GitLens, Docker, Python completo)

É o perfil para:

* desenvolvimento de projetos grandes
* uso diário
* automações
* workflows profissionais

### **Configurações chave do Perfil Air**

* IA com acesso total
* terminal aberto para comandos de agente
* nenhuma limitação de edição automática
* inline completions no modo máximo
* extensões avançadas ativas

Este é o ambiente utilizado no seu **MacBook Air** — sua estação de trabalho principal.

---

---

← Capítulo anterior: [00 — Índice Geral](00-indice.md)  

Próximo capítulo → [01 — Filosofia](01-filosofia.md)
