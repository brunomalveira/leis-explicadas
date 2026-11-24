# Estadual e municipal — ctresb/leis

## Estaduais

`estaduais/<UF>/<tipo>/<AAAA>/<arquivo>.md` — 27 UFs: AC, AL, AM, AP, BA, CE, DF, ES, GO, MA,
MG, MS, MT, PA, PB, PE, PI, PR, RJ, RN, RO, RR, RS, SC, SE, SP, TO.

Tipos por UF variam conforme a fonte. SP (verificado): `constituicao/`,
`constituicoes-historicas/`, `decretos/`, `decretos-legislativos/`, `decretos-lei/`,
`decretos-lei-complementares/`, `emendas-constitucionais/`, `leis-complementares/`,
`leis-ordinarias/`, `resolucoes/`. Outros (README do repo): `leis-promulgadas/` (AM, PB),
`leis-constitucionais/` (MG), `lei-organica/` e `emendas-lei-organica/` (DF).

**Nomenclatura com sufixo de fonte**: `lei-17616-2023-01-11-id206641.md` — o `-idNNNNN` é o
ID da norma no sistema de origem e **não é previsível**. Para montar a URL raw, liste a pasta
do ano via contents API primeiro:
`https://api.github.com/repos/ctresb/leis/contents/estaduais/<UF>/<tipo>/<AAAA>?ref=main`
(60 req/h sem token).

A coluna "Constituição" do [COBERTURA.md do repo](https://github.com/ctresb/leis/blob/main/COBERTURA.md)
diz por UF se a constituição estadual está no acervo — nem todas estão (ex.: CE, MA, PA não
têm constituição estadual no acervo).

## Municipais

`municipais/<UF>/<municipio>/<tipo>/…` — 35 UFs com municípios no acervo; município em
kebab-case (`adamantina`, `artur-nogueira`). SP tem 37 municípios (snapshot 2026-11-13).
A estrutura de tipos varia por município (ex.: `emendas-lei-organica/`, `resolucoes/`).

Municipal é fase em andamento no repo (5.570 fontes sem índice central) — não espere cobertura
ampla. Para município específico: listar via contents API
(`https://api.github.com/repos/ctresb/leis/contents/municipais/<UF>?ref=main`) e usar o portal
da câmara/prefeitura como complemento.

## Limitações por UF (principais lacunas)

Do COBERTURA.md e README do repo: PR e RJ nada coletado (WAF / Lotus Notes); AC só até 2009;
TO a partir de 2020; RN desde 1994; RS com 5.569 leis antigas sem texto na fonte; MG parou de
atualizar. Cada `_falhas.jsonl` de pasta registra o que não entrou e o motivo.

## Como citar a fonte oficial

O campo `fonte:` de cada arquivo aponta ao portal de origem da norma (SAPL da assembleia,
portal de legislação da Casa Civil etc.); o README do repo mantém a tabela de fonte por UF.
Para texto vigente estadual, preferir o portal do estado quando houver divergência.
