# Claude Handoff Skill

Um skill para Claude Code que facilita a transição entre sessões, documentando o progresso de forma estruturada para continuidade perfeita.

## 🎯 O que é?

O **Handoff Skill** gera um documento Markdown denso que permite que uma nova sessão de Claude — sem qualquer memória da conversa anterior — continue exatamente de onde você parou. É como escrever para seu "eu do futuro" que esqueceu de tudo.

## 📋 Quando usar?

Invoque este skill quando:
- Você quer encerrar uma sessão e continuar depois
- Precisa documentar o progresso para outra sessão de Claude
- Diz coisas como:
  - "preciso encerrar"
  - "vou parar por aqui"
  - "quero continuar em outra conversa"
  - "gera um handoff"
  - "documenta o que fizemos"
  - "contexto para próxima sessão"

O skill se ativa automaticamente quando sinais de encerramento são detectados.

## 📦 Instalação

### No Claude Code

Coloque a pasta em `~/.claude/skills/`:

```bash
cp -r handoff ~/.claude/skills/
```

### Structure

```
handoff/
└── SKILL.md          # Definição e instruções da skill
```

## 🚀 Como usar

Quando estiver finalizando uma sessão:

```
Preciso parar por aqui. Gera um handoff com o que fizemos.
```

O skill vai:
1. Ler toda a conversa
2. Reconstruir o que foi construído, decidido, tentado e abandonado
3. Gerar um documento estruturado em Markdown

## 📄 Formato do documento

O handoff gerado segue estrutura com 8 seções:
1. **Objetivo** - O que está sendo feito e por quê
2. **Contexto essencial** - Stack, restrições, decisões
3. **O que já foi feito** - Lista cronológica com explicações
4. **Estado atual** - Onde paramos, o que funciona
5. **Próximos passos** - Lista acionável
6. **Perguntas em aberto** - Coisas a decidir
7. **Artefatos relevantes** - Arquivos, snippets, comandos
8. **Instruções pra próxima sessão** - Tom esperado, armadilhas

## 💡 Princípios de escrita

- **Seja específico:** Nomes exatos de arquivos e linhas
- **Explique o porquê:** Justifique decisões
- **Documente dead ends:** Registre tentativas descartadas
- **Próximos passos acionáveis:** Tudo deve ser imediatamente executável
- **Inclua artefatos:** Comandos, paths, variáveis de ambiente

## 🤝 Contribuindo

Tem sugestões? Abra uma issue ou PR!

## 📄 Licença

MIT

---

**Criado por:** jpambrosi-floripa  
**Última atualização:** 2026-05-07
