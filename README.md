# GPT-6.2 rende mais

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

[![GPT-6.2 rende mais](guia/assets/banner.jpg)](https://inematds.github.io/gpt62-rende-mais/guia/)

## O que Ã©

GPT-6.2 rende mais Ã© uma coleÃ§Ã£o viva de dicas para usar melhor o Astra e o Sol, os modelos novos da OpenAI. Serve para quem delega trabalho Ã  IA e quer menos paradas e menos surpresas. Cada dica diz o que fazer, para que tipo de uso serve e, quando faz sentido, traz um texto pronto para colar. A base sÃ£o as publicaÃ§Ãµes oficiais da OpenAI, e novas dicas entram conforme forem conferidas. Ã‰ sÃ³ ler e copiar.

## ðŸ“– Guia

**https://inematds.github.io/gpt62-rende-mais/guia/**

As dicas estÃ£o em [`DICAS.md`](DICAS.md) e os textos prontos, em [`prompts/`](prompts/).

## PeÃ§a para a sua IA analisar o seu caso

```text
Leia as dicas em https://github.com/inematds/gpt62-rende-mais/blob/main/DICAS.md. Depois olhe como eu uso a IA aqui, incluindo as instruÃ§Ãµes que jÃ¡ existem, e me responda em linguagem simples: 1. Quais dicas resolvem um problema real meu? 2. Alguma instruÃ§Ã£o minha atrapalha o GPT-6.2? 3. O que vocÃª mudaria primeiro? NÃ£o mude nada ainda. Se nÃ£o conseguir abrir o link ou ver as minhas instruÃ§Ãµes, diga o que devo colar aqui. Mostre o plano e espere eu dizer sim.
```

## Baseado em publicaÃ§Ãµes da OpenAI

- [Using GPT-6.2](https://developers.openai.com/api/docs/guides/latest-model/gpt-6.2-astra): comportamento, prompts, esforÃ§o e migraÃ§Ã£o.
- [GPT-6.2 System Card](https://deploymentsafety.openai.com/gpt-6-2-astra-sol): omissÃ£o de obstÃ¡culos (22,28% no GPT-6.2 Astra e 11,09% no GPT-6 Astra, em tarefas de programaÃ§Ã£o preparadas para provocar o erro; nÃ£o indica necessariamente a taxa no uso real) e efeito do prompt do Codex.
- [Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra): escrito para a versÃ£o anterior; aqui entra como dica para testar.

Conferido em 18/11/2026. Os textos de `prompts/` foram escritos por nÃ³s.

---

## InstalaÃ§Ã£o tÃ©cnica

NÃ£o hÃ¡ nada para instalar: copie o texto de `prompts/` para o seu pedido, `AGENTS.md` ou prompt de sistema.

Ao migrar uma integraÃ§Ã£o, a documentaÃ§Ã£o oficial pede para conferir:

| Item | O que fazer |
|---|---|
| Modelo | `gpt-6.2-astra` ou `gpt-6.2-sol` |
| EsforÃ§o | em integraÃ§Ã£o nova, comeÃ§ar em `medium`; quem usa `none` ou `minimal` passa para `low` |
| Ferramentas | usar a Responses API |
| ParÃ¢metros | remover `temperature`, `top_p` e `top_logprobs`; em Chat Completions, tambÃ©m `logprobs`; em Responses, tirar `message.output_text.logprobs` de `include` |
| RaciocÃ­nio | nÃ£o editar o inÃ­cio da conversa entre respostas |
| Cache | vindo do GPT-5.5 ou anterior, trocar `prompt_cache_retention` por `prompt_cache_options.ttl` = `"30m"` |

Para repetir o teste, na pasta do projeto e com o Codex CLI autenticado pela assinatura (`3` gera 12 execuÃ§Ãµes; o script sÃ³ guarda as respostas, e a classificaÃ§Ã£o Ã© feita lendo cada uma):

```bash
teste/medir_bloqueio.sh 3 teste/nova-rodada
```

O resultado de 18/11/2026 estÃ¡ em [`teste/PROVA.md`](teste/PROVA.md).

## O processo, do inÃ­cio ao fim

ðŸ§  = pessoa com agente Â· âš™ï¸ = script Â· ðŸ¤– = agente de IA pela assinatura

| # | Passo | Comando / o que acontece | Quem |
|---|---|---|---|
| 1 | Chega uma dica | issue no GitHub | comunidade |
| 2 | Conferir | ler a publicaÃ§Ã£o oficial da OpenAI ou rodar um teste prÃ³prio; blogs de terceiros, vÃ­deos e redes nÃ£o entram como fonte | ðŸ§  |
| 3 | Registrar | acrescentar em `DICAS.md`, com data e situaÃ§Ã£o; texto novo em `prompts/` | ðŸ§  |
| 4 | Testar, se couber | `teste/medir_bloqueio.sh 3 teste/nova-rodada` ou um teste novo em `teste/` | âš™ï¸ / ðŸ¤– |
| 5 | Atualizar o guia | editar `guia/index.html` e refazer `guia/en/` e `guia/es/` | ðŸ§  / ðŸ¤– |
| 6 | Revisar | um revisor que nÃ£o escreveu a mudanÃ§a lÃª o guia | ðŸ¤– |
| 7 | Publicar | commit + push; o GitHub Pages publica sozinho | ðŸ§  |
| 8 | Divulgar, se for novidade grande | avisar no portal INEMA.CLUB e no grupo INEMA.LLMS | ðŸ§  |

## LicenÃ§a

MIT.

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>