# GPT-6.2 rinde más

**🇧🇷 [Português](README.md) · 🇺🇸 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

[![GPT-6.2 rinde más](guia/assets/banner-es.jpg)](https://inematds.github.io/gpt62-rende-mais/guia/es/)

## Qué es

GPT-6.2 rinde más es una colección viva de consejos para aprovechar mejor Astra y Sol, los nuevos modelos de OpenAI. Está dirigida a quienes delegan trabajo a la IA y quieren menos interrupciones y sorpresas. Cada consejo indica qué hacer, para qué tipo de uso sirve y, cuando tiene sentido, incluye un texto listo para copiar y pegar. La base son las publicaciones oficiales de OpenAI, y se agregan nuevos consejos a medida que se verifican. Solo hay que leer y copiar.

## 📖 Guía

**https://inematds.github.io/gpt62-rende-mais/guia/es/**

Los consejos están en [`DICAS.md`](DICAS.md) y los textos listos para usar, en [`prompts/`](prompts/) (ambos en portugués; el texto en español está en la guía).

## Pídele a tu IA que analice tu caso

```text
Lee los consejos en https://github.com/inematds/gpt62-rende-mais/blob/main/DICAS.md. Después revisa cómo uso la IA aquí, incluidas las instrucciones que ya existen, y respóndeme en lenguaje sencillo: 1. ¿Qué consejos resuelven un problema real mío? 2. ¿Alguna instrucción mía dificulta el uso de GPT-6.2? 3. ¿Qué cambiarías primero? Todavía no cambies nada. Si no puedes abrir el enlace o ver mis instrucciones, dime qué debo pegar aquí. Muéstrame el plan y espera a que te diga que sí.
```

## Basado en publicaciones de OpenAI

- [Using GPT-6.2](https://developers.openai.com/api/docs/guides/latest-model/gpt-6.2-astra): comportamiento, prompts, esfuerzo y migración.
- [GPT-6.2 System Card](https://deploymentsafety.openai.com/gpt-6-2-astra-sol): omisión de obstáculos (22,28% en GPT-6.2 Astra y 11,09% en GPT-6 Astra, en tareas de programación preparadas para provocar el error; no indica necesariamente la tasa en el uso real) y efecto del prompt de Codex.
- [Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra): escrito para la versión anterior; aquí se incluye como consejo para probar.

Verificado el 18/11/2026. Nosotros escribimos los textos de `prompts/`.

---

## Instalación técnica

No hay nada que instalar: copia el texto de `prompts/` en tu solicitud, `AGENTS.md` o prompt del sistema.

Al migrar una integración, la documentación oficial pide verificar lo siguiente:

| Elemento | Qué hacer |
|---|---|
| Modelo | `gpt-6.2-astra` o `gpt-6.2-sol` |
| Esfuerzo | en una integración nueva, empezar en `medium`; quienes usan `none` o `minimal` deben pasar a `low` |
| Herramientas | usar la Responses API |
| Parámetros | quitar `temperature`, `top_p` y `top_logprobs`; en Chat Completions, también `logprobs`; en Responses, quitar `message.output_text.logprobs` de `include` |
| Razonamiento | no editar el inicio de la conversación entre respuestas |
| Caché | si vienes de GPT-5.5 o anterior, cambiar `prompt_cache_retention` por `prompt_cache_options.ttl` = `"30m"` |

Para repetir la prueba, desde la carpeta del proyecto y con Codex CLI autenticado mediante la suscripción (`3` genera 12 ejecuciones; el script solo guarda las respuestas y la clasificación se hace leyendo cada una):

```bash
teste/medir_bloqueio.sh 3 teste/nova-rodada
```

El resultado del 18/11/2026 está en [`teste/PROVA.md`](teste/PROVA.md) (en portugués).

## El proceso, de principio a fin

🧠 = persona con agente · ⚙️ = script · 🤖 = agente de IA mediante la suscripción

| # | Paso | Comando / qué sucede | Quién |
|---|---|---|---|
| 1 | Llega un consejo | issue en GitHub | comunidad |
| 2 | Verificar | leer la publicación oficial de OpenAI o ejecutar una prueba propia; los blogs de terceros, videos y redes no se usan como fuente | 🧠 |
| 3 | Registrar | agregarlo a `DICAS.md`, con fecha y estado; texto nuevo en `prompts/` | 🧠 |
| 4 | Probar, si corresponde | `teste/medir_bloqueio.sh 3 teste/nova-rodada` o una nueva prueba en `teste/` | ⚙️ / 🤖 |
| 5 | Actualizar la guía | editar `guia/index.html` y rehacer `guia/en/` y `guia/es/` | 🧠 / 🤖 |
| 6 | Revisar | un revisor que no haya escrito el cambio lee la guía | 🤖 |
| 7 | Publicar | commit + push; GitHub Pages publica automáticamente | 🧠 |
| 8 | Divulgar, si es una novedad importante | avisar en el portal INEMA.CLUB y en el grupo INEMA.LLMS | 🧠 |

## Licencia

MIT.
