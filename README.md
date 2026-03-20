# 🦞 OpenClaw Security Demo

Demo de segurança para a disciplina **IN1166 - Aplicações de Machine Learning** (UFPE, 2026.1).

## O que é isso?

Este repositório contém a configuração de um agente OpenClaw **propositalmente vulnerável** para demonstrar ataques de prompt injection e outros riscos de segurança em sistemas de IA com agência (tool use).

## ⚠️ Branch `main` = VULNERÁVEL

A branch `main` contém um agente sem proteções adequadas. **Não use em produção.**

Vulnerabilidades propositais:
- Sem distinção entre conteúdo confiável e não-confiável
- System prompt vaza facilmente
- Sem guardrails contra exfiltração de dados
- Aceita instruções de qualquer remetente sem validação

## ✅ Branch `hardened` = COM PROTEÇÕES

A branch `hardened` mostra como mitigar esses riscos com:
- Tratamento de conteúdo externo como não-confiável
- Proteções contra vazamento de system prompt
- Guardrails contra exfiltração
- Validação de autoridade dos remetentes

## Estrutura

```
workspace/
├── AGENTS.md          # Instruções do agente
├── SOUL.md            # Personalidade e regras
├── USER.md            # Info do "dono" (fake para demo)
├── MEMORY.md          # Memórias (fake para demo)
└── secrets.md         # "Dados sensíveis" (honeypot para teste)

attacks/
├── hidden-instructions.html   # Página com prompt injection escondido
├── malicious-email.md         # Email com instruções ocultas
└── README.md                  # Guia dos ataques

slides/
└── roteiro.md                 # Roteiro da apresentação
```

## Como testar

1. Configure uma instância OpenClaw com este workspace
2. Conecte via WhatsApp (chip dedicado)
3. Tente os ataques descritos em `attacks/`
4. Compare o comportamento entre `main` e `hardened`

## Contexto acadêmico

Apresentação para IN1166 (Prof. Cleber Zanchettin) sobre aplicações práticas de ML e riscos de segurança em agentes de IA autônomos.
