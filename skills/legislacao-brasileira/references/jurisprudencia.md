# Jurisprudência — ctresb/leis

## Estrutura

`jurisprudencia/<tribunal>/<tipo>/` — súmulas, teses vinculantes e controle concentrado.

| Tribunal | Tipos no acervo |
| --- | --- |
| `stf/` | `sumulas/` (~736 arquivos), `sumulas-vinculantes/`, `repercussao-geral/`, `controle-concentrado/` |
| `stj/` | `sumulas/`, `repetitivos/` |
| `tst/` | `sumulas/`, `orientacoes-jurisprudenciais/` |
| `tnu/`, `trf4/` | |
| `outros-tribunais/` | `stm/`, `tcu/` |
| `regimentos/` | `regimento-tcu.md`, `regimento-tst.md` |

Nomenclatura verificada: `sumulas/sumula-1.md`, `sumula-10.md`, … (`sumula-<num>.md`).

## Como buscar

- Número da súmula → URL raw direta:
  `https://raw.githubusercontent.com/ctresb/leis/main/jurisprudencia/stf/sumulas/sumula-<NUM>.md`
- Tese de repercussão geral, repetitivo ou controle concentrado → listar a pasta via contents
  API (`https://api.github.com/repos/ctresb/leis/contents/jurisprudencia/<tribunal>/<tipo>?ref=main`,
  60 req/h sem token).

## Limitações

- O acervo cobre súmulas, teses vinculantes e controle concentrado — não o universo de
  acórdãos. Para julgado concreto, cite o site oficial do tribunal.
- `_falhas.jsonl` na pasta registra o que não entrou e o motivo.

## Fontes oficiais de complemento

- **STF**: https://portal.stf.jus.br/jurisprudencia/ — acórdãos, súmulas, temas de
  repercussão geral.
- **STJ**: jurisprudência em scon.stj.jus.br (responde 403 a fetches automatizados — usar o
  site no navegador e citar a fonte).
- **TST**: https://www.tst.jus.br/ — jurisprudência e orientações jurisprudenciais.
