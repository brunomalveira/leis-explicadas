# Tratados internalizados — ctresb/leis

## Coleções

| Pasta | Conteúdo | Nomenclatura |
| --- | --- | --- |
| `tratados/bitributacao/` | acordos de dupla tributação (51 arquivos) | descritivo: `acordo-alemanha-dupla-tributacao.md`, `adt-brasil-singapura.md` |
| `tratados/direitos-humanos/` | convenções de direitos humanos (12) | `belem.md`, `cartagena.md` |
| `tratados/oit/` | convenções da OIT (98) | `D12936.md`, `OIT_003.md` |

Nomenclatura sem ano e não-numérica — para localizar, liste a coleção via contents API
(`https://api.github.com/repos/ctresb/leis/contents/tratados/<colecao>?ref=main`,
60 req/h sem token).

## Como o ato de internalização entra

A promulgação de tratados entra na esfera federal: decretos legislativos de aprovação em
`federal/decretos-legislativos/` e decretos de promulgação em `federal/decretos/`. Para citar
o ato oficial, ir por lá (rotas em [`federal.md`](federal.md)).

## Fontes oficiais de complemento

- **Planalto**: https://www.planalto.gov.br/legislacao — atos internacionais internalizados
  e respectivos decretos de promulgação.
- **DOU**: https://www.in.gov.br/servicos/diario-oficial-da-uniao — publicação oficial do
  decreto de promulgação (usar user-agent de navegador em fetches).
