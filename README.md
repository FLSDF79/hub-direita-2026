# Hub Direita — Munição

**GitHub Pages:** https://flsdf79.github.io/hub-direita-2026/

Hub **local** de munição política em português (Brasil) para o 2º turno **Flávio Bolsonaro × Lula** (até **25/10/2026**).

Uso: Fabiano Lopes. Interface escura, agressiva e limpa — só HTML + CSS + JS vanilla (sem build, sem CDN autenticado).

## Como abrir

1. Entre na pasta do hub:
   ```bash
   cd /workspace/hub-direita
   ```
2. Suba um servidor local simples (o `fetch` dos JSON **não** funciona bem em `file://`):
   ```bash
   python3 -m http.server 8765
   ```
3. Abra no navegador:
   ```
   http://localhost:8765/
   ```
   (ou abra `index.html` direto se o navegador permitir CORS local — o servidor acima é o caminho confiável.)

Abas: **HOJE** · **COMENTARISTAS** · **NOTÍCIAS** · **ABSURDO ESQUERDA** · **STF** · **FORA DO COMUM** · **ARQUIVO**.

## Dados

Cada aba lê um array JSON em `data/`:

| Aba | Arquivo |
|-----|---------|
| Hoje | `data/hoje.json` |
| Comentaristas | `data/comentaristas.json` |
| Notícias | `data/noticias.json` |
| Absurdo Esquerda | `data/absurdo.json` |
| STF | `data/stf.json` |
| Fora do Comum | `data/fora.json` |
| Arquivo | `data/arquivo.json` |

Formato de cada card:

```json
{
  "id": "unico",
  "date": "AAAA-MM-DD",
  "source": "fonte / perfil",
  "title": "título curto",
  "summary": "2 a 4 frases de resumo / munição",
  "url": "https://...",
  "tags": ["tag1", "tag2"]
}
```

## Rotina diária

1. Coletar posts/notícias (Instagram, X, portais) nos perfis monitorados.
2. Anotar bruto em `/workspace/monitor-direita/AAAA-MM-DD.md` (ver abaixo).
3. Transformar em cards e **append** nos JSON de `data/` (manter array válido).
4. Recarregar o hub no navegador — as abas atualizam sozinhas.

Seed inicial (04/10/2026): resultado do 1º turno (Flávio **47,08%** × Lula **45,10%**) + reels Ruschel, Coppolla (anti-voto-nulo) e Ricardo Brasil.

## Monitor bruto

O monitoramento diário de perfis fica em:

```
/workspace/monitor-direita/
├── perfis.md          # lista de perfis monitorados
└── AAAA-MM-DD.md      # digest do dia (links, curtidas, notas)
```

- `perfis.md` — Ruschel, Coppolla, Ricardo Brasil, Alexandre Garcia, Augusto Nunes, Ana Paula Henkel, Paulo Figueiredo, Allan dos Santos, etc.
- Digests diários (ex.: `2026-10-04.md`) alimentam este hub.

Este hub **não** sobrescreve o monitor: o monitor é a matéria-prima; `data/*.json` é a munição pronta para leitura rápida.

## Estrutura

```
/workspace/hub-direita/
├── index.html      # UI única
├── README.md
└── data/
    ├── hoje.json
    ├── comentaristas.json
    ├── noticias.json
    ├── absurdo.json
    ├── stf.json
    ├── fora.json
    └── arquivo.json
```

## Cores

- Fundo `#0b0b0b` · acentos **verde/ouro** (direita)
- **Vermelho** em ABSURDO ESQUERDA e STF
- **Ouro** em FORA DO COMUM


## Deploy (GitHub Pages)

Site público: **https://flsdf79.github.io/hub-direita-2026/**

Fonte: repositório `FLSDF79/hub-direita-2026`, branch `main`, pasta raiz (`/`).
