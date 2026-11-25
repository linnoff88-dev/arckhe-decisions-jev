# ê¢Å¡âê¯Â¸Â Decisions êâ Jev

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="48" />
  <p><strong>Arckhé AI</strong></p>
</div>


[![Decisions êâ Jev](guia/assets/banner.jpg)](https://linnoff88-dev.github.io/

**ê°Å¸â¡Â§ê°Å¸â¡Â· [PortuguêÂªs](README.md) êÂ· ê°Å¸â¡Âºê°Å¸â¡Â¸ [English](README.en.md) êÂ· ê°Å¸â¡Âªê°Å¸â¡Â¸ [EspaêÂ±ol](README.es.md)**

## O que êÂ©

A OpenAI lanêÂ§ou a Decisions API: vocêÂª manda um texto ou uma foto com perguntas fechadas e recebe sêÂ³ a resposta ê¢â¬â sim/nêÂ£o, uma opêÂ§êÂ£o da sua lista ou uma nota ê¢â¬â com a probabilidade, sem texto corrido. êâ° a mesma ideia do Jev, o modelo de decisêÂ£o que o ARCKHê jêÂ¡ estuda. Este projeto explica as diferenêÂ§as com a fonte de cada informaêÂ§êÂ£o e traz uma ponte em Python que converte as perguntas de um formato para o outro e compara as respostas. Para estudar basta ler e rodar a demonstraêÂ§êÂ£o offline; para chamar as APIs de verdade, vocêÂª precisa das suas chaves.

## ê°Å¸ââ Guia de uso

Guia completo (landing + passo a passo): **https://linnoff88-dev.github.io/

## Em 30 segundos

| | OpenAI Decisions API | Jev | Microsoft-Decision-1 |
|---|---|---|---|
| Sim/nêÂ£o | `predicate` | `noul` | sim/nêÂ£o |
| OpêÂ§êÂ£o da lista | `choice` + `choices` | `choice` + `criteria` | mêÂºltipla escolha |
| Nota | `score` + `levels` | `score` + `criteria` | nota e rubrica |
| Imagem | sim (base64) | nêÂ£o | nêÂ£o (sêÂ³ texto, atêÂ© 32.768 tokens) |
| Recusa | `refusal` | nêÂ£o existe | nêÂ£o informado |
| PreêÂ§o de entrada | US$ 0,10 / 1M tokens | US$ 0,042 / 1M tokens | US$ 0,042 / 1M tokens (saêÂ­da grêÂ¡tis) |

Fontes, nêÂºmeros dos vêÂ­deos e quando usar cada um: [docs/comparacao.md](docs/comparacao.md).

## Uso

```bash
python3 -m ponte demo                                              # offline, respostas simuladas
python3 -m ponte converter jev-openai exemplos/plantao-pet.jev.json [--imagem foto.jpg]
python3 -m ponte converter openai-jev exemplos/devolucao-foto.openai.json
PERMITIR_API=1 python3 -m ponte ao-vivo exemplos/plantao-pet.jev.json  # chamada paga, nos dois
python3 -m unittest discover -s testes                             # 12 testes
```

O modo `ao-vivo` lêÂª `OPENAI_API_KEY` e `OPENROUTER_API_KEY` do ambiente (ou de um `.env` em `PONTE_ENV`) e ainda nêÂ£o foi executado pelo ARCKHê. Prompt para o seu agente integrar a API: [docs/prompt-integracao.md](docs/prompt-integracao.md).

## Estrutura

- `ponte/` ê¢â¬â conversêÂ£o, normalizaêÂ§êÂ£o, comparaêÂ§êÂ£o e CLI (sêÂ³ biblioteca padrêÂ£o).
- `exemplos/` ê¢â¬â requisiêÂ§êÂµes autorais; `exemplos/simulado/` ê¢â¬â respostas simuladas da demo.
- `docs/` ê¢â¬â comparaêÂ§êÂ£o com fonte e prompt de integraêÂ§êÂ£o.
- `guia/` ê¢â¬â landing + guia em PT/EN/ES.

## Relacionados

- [êÂrea JEV no ARCKHê Eventos](https://eventos.ARCKHê.pro/jev/) êÂ· [projeto jev](https://github.com/linnoff88-dev/jev) êÂ· [curso JEV](https://linnoff88-dev.github.io/

Projeto educacional independente. Jev êÂ© um modelo da TypeSafe; Decisions API êÂ© um produto da OpenAI. LicenêÂ§a MIT.

## VêÂ­deo

[Assistir ao vêÂ­deo explicativo](https://linnoff88-dev.github.io/ (PT, 5min41s, avatar e voz do Nei; tambêÂ©m [no YouTube](https://www.youtube.com/watch?v=O2061m5FG_I)). Fonte: vêÂ­deo de Mark Kashef no YouTube.

---

<div align="center">
  <img src="capa/logo.svg" alt="Arckhé AI" height="32" />
  <p><strong>Arckhé AI</strong></p>
</div>