# Dicas para o GPT-6.2 Astra e Sol

Coleção viva, com a mesma numeração do guia. Cada dica traz data, situação e para quem serve (qualquer trabalho, só código, design, onde houver o ajuste ou só sistema próprio):

- **Oficial:** está em documento da OpenAI sobre o GPT-6.2.
- **Para testar:** veio de orientação oficial de outra versão ou ainda não foi confirmada no 6.2.
- **Problema oficial, texto nosso:** o problema está em documento da OpenAI; o texto é nosso e ainda não tem efeito medido.
- **Testada:** mostrou efeito num teste nosso, registrado em `teste/`.

**Termos:** API é a ligação direta entre um programa e o modelo. `AGENTS.md` é um arquivo de instruções para agentes num projeto. Skill é um conjunto de instruções salvo para uma tarefa. Tokens são as unidades de texto que o modelo processa e que entram na conta. `none`, `minimal`, `low` e `medium` são níveis de esforço. Issue é uma mensagem aberta no GitHub.

## Pedir melhor

1. **Deixe ele ir até o fim.** Qualquer trabalho. Oficial, 18/11/2026. Diga o que ele resolve sozinho e quando deve parar. Texto: [`prompts/ir-ate-o-fim.md`](prompts/ir-ate-o-fim.md).
2. **Peça para saber o que faltou.** Qualquer trabalho. Problema oficial, texto nosso, 18/11/2026. Em tarefas de programação preparadas para provocar esse erro, o GPT-6.2 Astra omitiu um obstáculo conhecido em 22,28% das tentativas; o GPT-6 Astra, em 11,09%. A OpenAI avisa que isso não indica necessariamente a taxa no uso real e suspeita de relação com o próprio esforço de deixar as respostas concisas. O prompt padrão do Codex reduz muito o problema, mas não vale nas chamadas diretas pela API. Texto: [`prompts/contar-bloqueios.md`](prompts/contar-bloqueios.md). Nosso teste no Codex ainda não mostrou efeito do texto: [`teste/PROVA.md`](teste/PROVA.md).
3. **Peça uma resposta que se entenda sozinha.** Qualquer trabalho. Oficial, 18/11/2026. O 6.2 já vem mais curto e direto; reveja instruções como "seja conciso". Texto: [`prompts/resposta-completa.md`](prompts/resposta-completa.md).
4. **Em código, ensine o jeito do projeto.** Só código. Oficial, 18/11/2026. Texto: [`prompts/codigo-do-projeto.md`](prompts/codigo-do-projeto.md).
5. **Em telas e sites, mostre o visual que quer.** Design. Oficial, 18/11/2026. Diga o tipo de imagem e a tipografia, ou entregue uma referência e peça para comparar o resultado com ela.

## Ajustar o uso

6. **Comece no esforço médio.** Onde houver o ajuste. Oficial, 18/11/2026, para integrações novas. Quem usa `none` ou `minimal` passa para `low`. Em tarefas longas e complexas, mais esforço ajuda nas conferências finais.
7. **Escolha entre Astra e Sol.** Qualquer trabalho. Oficial, 18/11/2026. Astra para as tarefas mais exigentes; Sol para trabalho complexo com custo menor.
8. **Não reescreva o começo da conversa.** Só sistema próprio. Oficial, 18/11/2026. Mudanças no histórico, rebaixar o modelo ou trocar usuário ou organização fazem a API descartar o raciocínio guardado. A qualidade pode cair e o modelo pode gastar mais tokens refazendo trabalho.

## Limpar instruções

9. **Reveja regras antigas.** Qualquer trabalho. Para testar, 18/11/2026. A orientação foi escrita para o GPT-6 Astra: descrições de skill curtas, `AGENTS.md` só com o que ainda é necessário e permissões claras para fluxos seguros. Teste no 6.2 uma mudança por vez.

## Como entra uma dica nova

Abra uma [issue](https://github.com/inematds/gpt62-rende-mais/issues/new?template=dica.md) com o que fez, em qual modelo e o que mudou. Ela entra aqui depois de conferida em documento oficial ou num teste registrado.

## Documentos oficiais

- [Using GPT-6.2](https://developers.openai.com/api/docs/guides/latest-model/gpt-6.2-astra)
- [GPT-6.2 System Card](https://deploymentsafety.openai.com/gpt-6-2-astra-sol)
- [Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra)
