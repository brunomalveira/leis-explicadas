# Esfera federal — ctresb/leis

## Como buscar

1. Sabendo **tipo + número + data** → URL raw direta com o padrão de nomenclatura da tabela
   abaixo: `https://raw.githubusercontent.com/ctresb/leis/main/federal/<tipo>/<AAAA>/<arquivo>.md`
2. Sabendo só o **assunto** → identifique tipo/número/data numa fonte oficial (Planalto,
   normas.leg.br, legislação do Senado) e monte a URL raw; ou cite direto do site oficial.
3. Para ver **o que existe** num ano/tipo → contents API na pasta
   (`https://api.github.com/repos/ctresb/leis/contents/federal/<tipo>/<AAAA>?ref=main`,
   60 req/h sem token — navegue com parcimônia).
4. **O tipo importa**: a CLT é Decreto-Lei (`del-5452-1943-05-01.md`), não Lei. Verificar o
   tipo na fonte oficial antes de montar o caminho.

## Tipos e rotas

| Pasta | Alcance (pastas de ano) | Padrão de arquivo | Exemplo verificado |
| --- | --- | --- | --- |
| `leis-ordinarias/` | 176 anos (1822–2026) | `lei-<num>-<data>.md` | `leis-ordinarias/2002/lei-10406-2002-01-10.md` (Código Civil) |
| `leis-complementares/` | | `lcp-<num>-<data>.md` | `leis-complementares/2006/lcp-123-2006-12-14.md` |
| `decretos-lei/` | 34 anos (1937–1988) | `del-<num>-<data>.md` | `decretos-lei/1943/del-5452-1943-05-01.md` (CLT) |
| `decretos/` | 124 anos (1903–2026) | `dec-<num>-<data>.md` | `decretos/2023/dec-11325-2023-01-01.md` |
| `decretos-legislativos/` | 143 anos (1821–) | | |
| `decretos-nao-numerados/` | 30 anos | | |
| `medidas-provisorias/` | 39 anos (1988–) | `mpv-<num>-<data>.md` | `medidas-provisorias/2023/mpv-1154-2023-01-01.md` |
| `emendas-constitucionais/` | 46 anos (1969–) | `emc-<num>-<data>.md` | `emendas-constitucionais/1992/emc-1-1992-03-31.md` |
| `resolucoes-camara/` | 86 anos | | |
| `resolucoes-senado/` | 82 anos | `rsf-<num>-<data>.md` | `resolucoes-senado/2023/rsf-1-2023-03-16.md` |
| `resolucoes-congresso/` | 41 anos | | |
| `regulamentos/` | 16 anos | | |
| `leis-constitucionais/` | 5 anos (1938–1945) | | |
| `leis-delegadas/` | 2 anos (1962, 1992) | `ldl-<num>-<data>.md` | `leis-delegadas/1992/ldl-13-1992-08-27.md` |
| `constituicoes-historicas/` | 7 constituições (1824, 1891, 1934, 1937…) | | |
| `regimentos/` | Regimento Comum das Casas | `regimento-<casa>.md` | `regimento-camara.md`, `regimento-congresso.md` |
| `anexos/` | anexos de decretos | | |

`constituicao.md` na raiz = Constituição Federal de 1988, texto compilado do Planalto (único
arquivo do acervo sem cabeçalho).

## Cabeçalho dos arquivos

`titulo`, `tipo`, `numero`, `data`, `ementa`, `situacao`, `revogada`, `versao_texto`, `urn`,
`fonte`, `baixado_em` (+ `publicacao`/`data_publicacao` quando a fonte dá). `versao_texto` diz
se o texto é compilado vigente (`"compilada (texto vigente)"`) ou publicação original
(`"original"`). **O campo `fonte:` (normalmente normas.leg.br via URN LexML) é a referência
oficial a citar.**

O nome do arquivo usa a `data` da norma (sanção/promulgação); a publicação no DOU vem no
`publicacao:` e pode ser de dias depois.

## Limitações

- O COBERTURA.md do repo só contabiliza a base inicial (leis ordinárias, complementares,
  delegadas e decretos-lei); decretos, MPs, ECs, resoluções, regulamentos e decretos
  legislativos entraram em lotes posteriores. Os alcances da tabela acima são o estado
  observado em 2026-11-13 — confirme via contents API antes de concluir ausência.
- `federal/_falhas.jsonl` registra, linha por linha, o que não entrou no acervo e o motivo.
- OCR: parte do acervo veio de PDF escaneado e podem existir erros de reconhecimento (ordinais
  confundidos já foram corrigidos em lote). Em dúvida no texto, conferir a `fonte:`.

## Fontes oficiais de complemento

- **Planalto**: https://www.planalto.gov.br/legislacao — legislação compilada federal, texto
  vigente; `ccivil_03` para a coleção clássica (https://www.planalto.gov.br/ccivil_03/).
  Bloqueia user-agent não-navegador: usar user-agent de navegador em fetches.
- **normas.leg.br**: https://normas.leg.br/ — resolução de URN LexML; é o destino dos links
  `fonte:` do acervo.
- **Congresso Nacional**: https://www.congressonacional.leg.br/ — tramitação, MPs, comissões.
- **Senado**: https://www25.senado.leg.br/ — tramitação e legislação (a busca de legislação
  em www12.senado.leg.br responde 403 a fetches automatizados).
- **DOU**: https://www.in.gov.br/servicos/diario-oficial-da-uniao — publicação oficial; busca
  de matéria em https://www.in.gov.br/consulta/-/buscar/dou (usar user-agent de navegador).
