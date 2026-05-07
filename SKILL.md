---
name: handoff
description: Use when the user wants to end a session and continue later, needs to document progress for another Claude session, says things like "preciso encerrar", "vou parar por aqui", "quero continuar em outra conversa", "gera um handoff", "documenta o que fizemos", "contexto para próxima sessão", or asks to capture the current state of work. Always invoke this skill when the user signals they're wrapping up and wants continuity — even if they don't say "handoff" explicitly.
---

# Handoff Skill

The goal is to produce a single Markdown document dense enough that a fresh Claude session — with zero memory of this conversation — can pick up exactly where you left off. Think of it as writing for your future self who forgot everything overnight.

## What to do

Read back through the entire conversation. Reconstruct what was built, decided, attempted, and abandoned. Then write the handoff document below.

Don't ask the user to summarize — you have the full context. Do the work yourself and offer to adjust afterward.

## Output format

Save the file as `handoff-[slug].md` in the current working directory (or ask the user where to save if it's ambiguous). Use today's date in the slug when helpful, e.g. `handoff-auth-refactor-2026-05-07.md`.

Use this exact structure:

```markdown
# Handoff: [título curto e descritivo]

**Data:** [data atual]  
**Status:** [em andamento | bloqueado | aguardando decisão]

## 1. Objetivo
O que está sendo feito e por quê, em 2-4 frases.

## 2. Contexto essencial
Stack técnica, restrições, decisões já tomadas e seus motivos.

## 3. O que já foi feito
Lista cronológica do que foi produzido, tentado ou descartado.
Se algo foi descartado, explique por quê.

## 4. Estado atual
Onde exatamente paramos. O que funciona, o que está quebrado.

## 5. Próximos passos
Lista ordenada e acionável do que fazer a seguir. Seja específico.

## 6. Perguntas em aberto
Coisas que ainda precisam de decisão ou investigação.

## 7. Artefatos relevantes
Arquivos, snippets, links ou comandos que a próxima sessão vai precisar.

## 8. Instruções pra próxima sessão
Tom esperado, nível de detalhe, armadilhas a evitar.
```

## Writing principles

**Be ruthlessly specific.** Vague entries like "trabalhou no backend" são inúteis. Prefira "modificou `src/auth/middleware.ts` linha 42 para aceitar JWT com expiração customizada".

**Explain the why behind decisions.** A próxima sessão vai encontrar código que parece errado. Se você não explicar por que aquela escolha foi feita, ela vai desfazê-la.

**Document dead ends.** Se algo foi tentado e descartado, registre — economiza horas de retrabalho.

**Make next steps actionable.** Cada item em "Próximos passos" deve ser algo que a próxima sessão pode começar imediatamente, sem precisar investigar o que isso significa.

**Artefatos are gold.** Inclua comandos exatos, paths completos, snippets de código relevantes, variáveis de ambiente necessárias. Qualquer coisa que a próxima sessão precisaria descobrir do zero.

## After writing

Tell the user where the file was saved and offer to:
1. Adjust any section they think is incomplete or wrong
2. Add more detail to a specific area
3. Create a shorter "quick start" summary for the top of the file
