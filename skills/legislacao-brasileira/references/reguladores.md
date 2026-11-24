# Atos de reguladores e ministérios — ctresb/leis

## Estrutura

`reguladores/<orgao>/<tipo>/…` — atos infralegais federais por órgão ou ministério. Os
`<tipo>` variam por órgão (cada fonte publica instrumentos diferentes).

Exemplos verificados:

- `reguladores/anvisa/` → `instrucoes-normativas/`, `portarias/`, `resolucoes/`,
  `solucoes-de-consulta/` (portarias organizadas por ano)
- `reguladores/contran/` → `deliberacoes/`, `resolucoes/`

Para ver os tipos de um órgão: contents API em
`https://api.github.com/repos/ctresb/leis/contents/reguladores/<orgao>?ref=main`
(60 req/h sem token). Nomenclatura dentro de `<tipo>` varia por fonte — listar antes de montar
URL raw.

## Órgãos no acervo (90 pastas — snapshot 2026-11-13)

`agu`, `ana`, `anac`, `anatel`, `ancine`, `aneel`, `anm`, `anp`, `ans`, `antaq`, `antt`,
`anvisa`, `atos-do-poder-executivo`, `bcb`, `bndes`, `cade`, `capes`, `carf`, `cfc`, `cgu`,
`cidades`, `cne`, `cnmp`, `cns`, `coaf`, `comunicacoes`, `conama`, `confaz`,
`conselhos-profissionais`, `contran`, `cultura`, `cvm`, `defesa`, `dpu`, `editais-e-avisos`,
`empreendedorismo`, `entidades-de-fiscalizacao-dos-profission`, `esporte`, `fazenda`, `gestao`,
`ibama`, `icmbio`, `igualdade-racial`, `inep`, `inmetro`, `inss`, `integracao`, `iphan`,
`mapa`, `mcti`, `mda`, `mdh`, `mdic`, `mds`, `mec`, `ministerio-da-cidadania`,
`ministerio-da-economia`, `ministerio-da-industria-comercio-exterio`,
`ministerio-da-infraestrutura`, `ministerio-da-mulher-da-familia-e-dos-di`,
`ministerio-da-seguranca-publica`, `ministerio-do-desenvolvimento-regional`,
`ministerio-extraordinario-da-seguranca-p`, `mj`, `mma`, `mme`, `mpi`, `mpu`, `mre`, `ms`,
`mte`, `mulheres`, `pesca`, `pgfn`, `planejamento`, `poder-judiciario`, `poder-legislativo`,
`portos-aeroportos`, `presidencia`, `previc`, `rfb`, `secretaria-especial-da-cultura`,
`senatran`, `sfb`, `sprev`, `stn`, `susep`, `tcu`, `transportes`, `turismo`

Alguns nomes de pasta vêm truncados do repo (ex.: `entidades-de-fiscalizacao-dos-profission`,
`ministerio-da-industria-comercio-exterio`) — são esses os caminhos reais; copiar verbatim.
A lista é um snapshot: para o estado atual, contents API em
`https://api.github.com/repos/ctresb/leis/contents/reguladores?ref=main`.

## Limitações

- Cobertura por órgão é desigual (cada órgão é uma fonte com formato próprio) — confirmar
  o que existe via contents API antes de concluir ausência.
- `_falhas.jsonl` em `reguladores/` registra o que não entrou e o motivo.

## Fontes oficiais de complemento

- Site oficial do órgão (gov.br) — texto vigente e atos mais recentes.
- **DOU**: https://www.in.gov.br/servicos/diario-oficial-da-uniao — publicação oficial dos
  atos; busca de matéria em https://www.in.gov.br/consulta/-/buscar/dou
  (usar user-agent de navegador).
- **Planalto**: https://www.planalto.gov.br/legislacao — regulamentos consolidados.
