# Polymarket Paper Pilot — Dashboard

Dashboard do piloto paper no Polymarket. **Paper only — sem dinheiro real.**

## O que é

Acompanha as posições paper do piloto: estimativas do estimador Jev vs preços
do mercado, P&L, Brier score e calibração ao longo das resoluções.

## Estrutura

- `index.html` — dashboard estático (tema escuro, sem dependências externas)
- `data.json` — dados gerados do ledger (não editar à mão)
- `../sync.py` — gera `data.json` a partir de `runs/paper_positions.jsonl`

## Atualizando

```bash
cd ~/workspace/polymarket-scout
python3 dashboard/sync.py   # regenera dashboard/data.json
```

Depois suba o `data.json` atualizado para este repo (o `index.html` lê o
arquivo relativamente — funciona no GitHub Pages sem backend).

## Regras do piloto

- Banca paper: $1.000 · size 2–5% por edge · edge mínimo 5pp
- Máx 3 posições abertas · sem martingale · stop -20% = pausa e revisão
- Toda posição resolve até o fim; Brier score vs baseline 0,25
