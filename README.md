# Apuração por região · Presidente · 2º turno 2026

Painel que acompanha a apuração do 2º turno presidencial agrupada por região (Norte, Nordeste,
Centro-Oeste, Sudeste, Sul e exterior), com mapa, placar por região, saldo de votos e detalhe por estado.

Os dados vêm dos arquivos públicos do TSE (`resultados.tse.jus.br`, eleição 6258), lidos direto pelo
navegador. Não há servidor nem build: é só o `index.html` e a malha estadual do IBGE (`brasil-ufs.json`).
A página atualiza sozinha a cada 60 s.

**Projeção:** em cada UF, os votos que faltam seguem o padrão já apurado nela (proporcional ao
eleitorado ainda não apurado). Região e Brasil são a soma das UFs. Se a capital apurar antes do
interior (ou o contrário), a projeção erra.

## Rodar localmente

```
python -m http.server 8000
```

Depois abra http://localhost:8000. Abrir o `index.html` direto do disco não funciona, porque o navegador
bloqueia a leitura do `brasil-ufs.json`.

## Publicar no GitHub Pages

Settings → Pages → Build and deployment → Source: **Deploy from a branch** → branch `main`, pasta `/ (root)`.
