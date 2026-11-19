# âš–ï¸ Decisions Ã— Jev

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


[![Decisions Ã— Jev](guia/assets/banner.jpg)](https://inematds.github.io/decisions-jev/guia/)

**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

## O que Ã©

A OpenAI lanÃ§ou a Decisions API: vocÃª manda um texto ou uma foto com perguntas fechadas e recebe sÃ³ a resposta â€” sim/nÃ£o, uma opÃ§Ã£o da sua lista ou uma nota â€” com a probabilidade, sem texto corrido. Ã‰ a mesma ideia do Jev, o modelo de decisÃ£o que o INEMA jÃ¡ estuda. Este projeto explica as diferenÃ§as com a fonte de cada informaÃ§Ã£o e traz uma ponte em Python que converte as perguntas de um formato para o outro e compara as respostas. Para estudar basta ler e rodar a demonstraÃ§Ã£o offline; para chamar as APIs de verdade, vocÃª precisa das suas chaves.

## ðŸ“– Guia de uso

Guia completo (landing + passo a passo): **https://inematds.github.io/decisions-jev/guia/**

## Em 30 segundos

| | OpenAI Decisions API | Jev | Microsoft-Decision-1 |
|---|---|---|---|
| Sim/nÃ£o | `predicate` | `noul` | sim/nÃ£o |
| OpÃ§Ã£o da lista | `choice` + `choices` | `choice` + `criteria` | mÃºltipla escolha |
| Nota | `score` + `levels` | `score` + `criteria` | nota e rubrica |
| Imagem | sim (base64) | nÃ£o | nÃ£o (sÃ³ texto, atÃ© 32.768 tokens) |
| Recusa | `refusal` | nÃ£o existe | nÃ£o informado |
| PreÃ§o de entrada | US$ 0,10 / 1M tokens | US$ 0,042 / 1M tokens | US$ 0,042 / 1M tokens (saÃ­da grÃ¡tis) |

Fontes, nÃºmeros dos vÃ­deos e quando usar cada um: [docs/comparacao.md](docs/comparacao.md).

## Uso

```bash
python3 -m ponte demo                                              # offline, respostas simuladas
python3 -m ponte converter jev-openai exemplos/plantao-pet.jev.json [--imagem foto.jpg]
python3 -m ponte converter openai-jev exemplos/devolucao-foto.openai.json
PERMITIR_API=1 python3 -m ponte ao-vivo exemplos/plantao-pet.jev.json  # chamada paga, nos dois
python3 -m unittest discover -s testes                             # 12 testes
```

O modo `ao-vivo` lÃª `OPENAI_API_KEY` e `OPENROUTER_API_KEY` do ambiente (ou de um `.env` em `PONTE_ENV`) e ainda nÃ£o foi executado pelo INEMA. Prompt para o seu agente integrar a API: [docs/prompt-integracao.md](docs/prompt-integracao.md).

## Estrutura

- `ponte/` â€” conversÃ£o, normalizaÃ§Ã£o, comparaÃ§Ã£o e CLI (sÃ³ biblioteca padrÃ£o).
- `exemplos/` â€” requisiÃ§Ãµes autorais; `exemplos/simulado/` â€” respostas simuladas da demo.
- `docs/` â€” comparaÃ§Ã£o com fonte e prompt de integraÃ§Ã£o.
- `guia/` â€” landing + guia em PT/EN/ES.

## Relacionados

- [Ãrea JEV no INEMA Eventos](https://eventos.inema.pro/jev/) Â· [projeto jev](https://github.com/inematds/jev) Â· [curso JEV](https://inematds.github.io/jev-curso/)

Projeto educacional independente. Jev Ã© um modelo da TypeSafe; Decisions API Ã© um produto da OpenAI. LicenÃ§a MIT.

## VÃ­deo

[Assistir ao vÃ­deo explicativo](https://inematds.github.io/decisions-jev/videos/) (PT, 5min41s, avatar e voz do Nei; tambÃ©m [no YouTube](https://www.youtube.com/watch?v=O2061m5FG_I)). Fonte: vÃ­deo de Mark Kashef no YouTube.

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>