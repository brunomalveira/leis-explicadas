---
name: legislacao-brasileira
description: Consulta legislação brasileira (leis, decretos, MPs, emendas, súmulas, jurisprudência): busca o texto oficial no acervo ctresb/leis e em fontes oficiais (Planalto, normas.leg.br, Senado, DOU), cita a fonte e explica em linguagem acessível. Use em qualquer pergunta que exija base legal brasileira.
---

# Legislação brasileira

Dado um assunto ou uma norma, busque o texto oficial, cite a fonte publicada e explique em
linguagem acessível. Baseie a resposta apenas em fatos oficiais publicados — nunca em
conhecimento de memória sem confirmação. Não substitui a fonte oficial nem profissional
habilitado (OAB/CRC); é consulta.

## Quando usar

- Pergunta sobre leis, decretos, MPs, emendas, súmulas ou jurisprudência brasileira ("posso X?", "o que diz a lei Y?", "qual o prazo de Z?")
- Pedido para citar o texto oficial de uma norma
- Pergunta que exige base legal (consumidor, trabalho, trânsito, tributos, previdência, LGPD…)

## Ordem de consulta

1. **Acervo [ctresb/leis](https://github.com/ctresb/leis)** (busca remota, sem clone) — como
   buscar na seção abaixo; rotas por domínio em `references/`.
2. **Fontes oficiais** — para o que o acervo não tem e para confirmar a fonte citada:
   [Planalto](https://www.planalto.gov.br/legislacao) ·
   [normas.leg.br](https://normas.leg.br/) ·
   [Congresso Nacional](https://www.congressonacional.leg.br/) ·
   [Senado](https://www25.senado.leg.br/) ·
   [DOU](https://www.in.gov.br/servicos/diario-oficial-da-uniao)

## Como buscar no acervo (busca 100% remota)

- Sabendo **tipo + número + data** → URL raw direta:
  `https://raw.githubusercontent.com/ctresb/leis/main/<caminho>/<arquivo>.md`
  (padrões de nomeação por domínio nas referências abaixo).
- Sem nomenclatura previsível → contents API na pasta:
  `https://api.github.com/repos/ctresb/leis/contents/<caminho>?ref=main`
  **Sem token: 60 requisições/hora por IP** — navegue pasta a pasta, não varra o acervo.
  Estourado o limite, o raw continua funcionando.
- **Nunca clone** (~8,6 GB, atualização constante) e **não use busca por código** do GitHub
  (exige login e não é caminho para resposta citável).
- O nome do arquivo usa a **data da norma** (sanção/promulgação), não a publicação no DOU —
  leis publicadas no dia seguinte têm o nome com a data da sanção.
- **O tipo importa**: a CLT é Decreto-Lei (`decretos-lei/1943/del-5452-1943-05-01.md`), não Lei.
- 404 na `main` pode ser pasta nova ou nomeação diferente — confirme na pasta do ano/tipo
  antes de concluir que a norma não está no acervo.
- Rotas rápidas: Constituição Federal = `constituicao.md` (raiz) · CDC =
  `federal/leis-ordinarias/1990/lei-8078-1990-09-11.md` · Código Civil =
  `federal/leis-ordinarias/2002/lei-10406-2002-01-10.md` · CLT =
  `federal/decretos-lei/1943/del-5452-1943-05-01.md`

## Referências por domínio (leia a que o assunto pedir)

| Arquivo | Quando ler |
| --- | --- |
| `references/federal.md` | Leis, decretos, MPs, ECs, resoluções — tabela de tipos e padrões de arquivo |
| `references/reguladores.md` | Atos de ANVISA, CONTRAN, RFB e outros reguladores (90 órgãos) |
| `references/jurisprudencia.md` | Súmulas STF/STJ/TST, teses vinculantes, repercussão geral, controle concentrado |
| `references/estaduais-municipais.md` | Constituições e leis por UF; legislação municipal |
| `references/tratados.md` | Bitributação, direitos humanos, convenções OIT |

## Regra de citação (obrigatória)

- O acervo é conversão automática das fontes oficiais (com OCR de documentos escaneados) e
  **não substitui a publicação oficial** — aviso do próprio repo.
- Toda resposta cita a **fonte oficial publicada**: o campo `fonte:` do frontmatter da norma
  no acervo (normalmente normas.leg.br via URN LexML) ou o site oficial onde encontrou.
- A conversão é o ponto de partida para **encontrar** a norma, não a autoridade citada.
- Se o texto do acervo divergir da fonte oficial, **prevalece a oficial**; reporte a divergência.

## Como responder (linguagem acessível)

Estrutura, sem juridiquês:

1. **Resposta direta** (1–2 frases) — o que a norma diz sobre a pergunta, em linguagem simples.
2. **O que a norma diz** — os dispositivos aplicáveis com a citação pronta (art., parágrafo,
   inciso) e o texto fiel: parafraseie simples e traga o trecho literal entre aspas quando o
   texto exato importa.
3. **Base legal** — nome da norma, número e data, e o link oficial (`fonte:` do frontmatter ou
   o site oficial).
4. **Avisos** — revogada (e por qual lei), se o texto é compilado vigente ou publicação
   original (`versao_texto:`), limitação do acervo (OCR, cobertura).

Regras:

- **Nunca invente** número de lei, artigo, inciso ou data. Não encontrou: diga que não
  encontrou e aponte a fonte oficial para busca manual.
- Traduza o juridiquês na primeira menção: "ementa" → resumo do assunto da norma;
  "revogada" → não vale mais; "súmula" → entendimento fixo do tribunal; "infralegal" →
  abaixo da lei. Mantenha o termo original entre parênteses.
- Não dê conselho jurídico personalizado: apresente o que a norma diz e recomende
  profissional habilitado (OAB/CRC) para decisão concreta.

## Limitações

- O acervo está em atualização constante e a cobertura é desigual por órgão, UF e município —
  confirme via contents API antes de concluir ausência.
- OCR pode conter erros de reconhecimento; em dúvida no texto, confira a `fonte:`.
- Municipal é fase em andamento no repo — não espere cobertura ampla.
