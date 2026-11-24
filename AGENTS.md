# AGENTS.md — leis

Plugin de legislação brasileira para agentes de IA: dado um assunto, o agente sabe onde
buscar o texto oficial e como chegar nele, e responde citando a fonte oficial publicada.

## Onde buscar (leia primeiro)

- **`skills/legislacao-brasileira/SKILL.md`** — entrada para agentes: ordem de consulta,
  como buscar no acervo [ctresb/leis](https://github.com/ctresb/leis) (busca remota, sem
  clone), regra de citação e guia de resposta em linguagem acessível. Rotas por domínio em
  `skills/legislacao-brasileira/references/`.

## Regra de citação

Cite sempre a fonte oficial publicada — o campo `fonte:` do frontmatter da norma no acervo
ou o site oficial onde encontrou. A conversão do acervo não substitui a publicação no DOU.

## Estrutura

```
.claude-plugin/                     plugin.json + marketplace.json (o repo é o marketplace)
skills/legislacao-brasileira/       SKILL.md + references/ (rotas por domínio, sob demanda)
assets/                             banner do README
README.md                           instalação e uso
docs/                               workspace local do autor (gitignored — não faz parte do plugin)
```

## Ambiente local (do autor)

`docs/` fica fora do git: intenções confirmadas em `docs/intent/`, skills importadas em
`docs/skills/` (índice em `docs/skills/README.md`). Nada daqui é necessário para usar o
plugin. O conteúdo de `docs/referencias/` foi movido para `skills/legislacao-brasileira/`
(SKILL.md + references/) — atualize as rotas por lá.

## Convenções

- Docs em PT-BR.
- O acervo ctresb/leis é consultado remotamente — nunca clonar (~8,6 GB, atualização constante).
