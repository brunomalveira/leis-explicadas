# leis

### Instale este plugin no seu agente de IA e ele passa a responder perguntas de legislação brasileira com o texto oficial citado — em linguagem acessível.

**leis** é um plugin no padrão [Agent Skills](https://agentskills.io) (adotado por Claude,
Codex, Gemini CLI, Copilot, Cursor e outros) que dá rotas verificadas para buscar e citar a
legislação brasileira. Dado um assunto, o agente sabe onde procurar o texto oficial — no
acervo [ctresb/leis](https://github.com/ctresb/leis) (mais de 320 mil normas em Markdown,
busca 100% remota, sem clone) e nas fontes oficiais (Planalto, normas.leg.br, Congresso,
Senado, DOU) — e responde **citando a fonte publicada**, nunca só a conversão automática.

## O que ele faz

- 📖 **Respostas com base legal** — dado um assunto ("posso cancelar X?", "o que diz a lei Y?"),
  o agente localiza a norma, cita os dispositivos aplicáveis e explica em linguagem simples.
- 🔗 **Sempre com a fonte oficial** — toda resposta aponta a publicação oficial (normalmente
  normas.leg.br via URN LexML). O acervo é conversão automática e não substitui o DOU.
- 🗺️ **Rotas verificadas por domínio** — federal (leis, decretos, MPs, ECs), reguladores
  (ANVISA, CONTRAN, RFB…), jurisprudência (STF, STJ, TST), estadual/municipal e tratados,
  carregadas sob demanda — sem gastar tokens com o que o assunto não pede.
- ⚡ **Zero dependências** — busca remota via URL raw + API do GitHub; sem clone, sem índice
  local, sem chave de API.

## Instalação

### Claude Code

```text
/plugin marketplace add brunomalveira/leis
/plugin install leis@leis-br
```

### claude.ai (Pro/Max)

Baixe o zip da pasta `skills/legislacao-brasileira/` e envie em
**Configurações › Recursos › Skills**.

### Outros agentes (Codex, Cursor, Gemini CLI, Copilot, Hermes…)

Copie `skills/legislacao-brasileira/` para o diretório de skills do seu agente — o formato é
o [open standard Agent Skills](https://agentskills.io). Em qualquer agente que leia
`AGENTS.md`, apontar para este repositório também funciona: a AGENTS.md direciona ao
`SKILL.md`.

## Aviso

O plugin fornece **informações educativas e orientações gerais** baseadas em legislação
publicada. Não substitui a consulta a advogado (OAB), contador (CRC) ou outro profissional
habilitado. O texto do acervo é conversão automática das fontes oficiais (com OCR de
documentos escaneados) e não substitui a publicação no Diário Oficial — toda resposta do
agente traz a fonte oficial citada e, em caso de divergência, prevalece a oficial.

## Na comunidade

Outros projetos que acessam a legislação brasileira por IA:

- [mazulo/leis-mcp](https://github.com/mazulo/leis-mcp) — servidor MCP sobre o mesmo acervo
  ctresb/leis, com índice SQLite local
- [cristianoaredes/mcp-camara](https://github.com/cristianoaredes/mcp-camara) — MCP da API de
  Dados Abertos da Câmara dos Deputados
- [AlissonSantos1/brasil-legal-skills](https://github.com/AlissonSantos1/brasil-legal-skills) —
  plugin consultivo de direito brasileiro com calculadoras

## Licença

[MIT](LICENSE)
