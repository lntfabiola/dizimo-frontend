# Frontend — Sistema de Dízimo (Paróquia São Miguel Arcanjo)

Um único arquivo HTML (com CSS e JavaScript embutidos) — não precisa instalar Node, npm, nem
nenhuma ferramenta de build. Funciona tanto no celular do tesoureiro (mobile) quanto no
computador da secretaria (desktop), com telas adaptadas pra cada perfil de usuário.

## Como usar

1. Abra o arquivo `index.html` num editor de texto e ajuste a primeira linha do `<script>`:

   ```js
   const API_BASE = "http://localhost:8000";
   ```

   Troque pela URL do backend:
   - **Testando local**: deixe `http://localhost:8000` (com o backend rodando via
     `python -m uvicorn app.main:app --reload`, como já validamos)
   - **Em produção**: troque pela URL do backend no Render (algo como
     `https://dizimo-api.onrender.com`)

2. Para testar localmente, é só abrir o `index.html` direto no navegador (duplo-clique).

3. Para publicar de verdade (acessível pelo celular de qualquer tesoureiro), suba esse arquivo
   num serviço de hospedagem estática — Render Static Site, GitHub Pages, Netlify ou Vercel
   funcionam bem e são gratuitos pra esse tipo de site.

## O que tem em cada visão

**Tesoureiro** (login vinculado a uma comunidade):
- **Dízimo**: busca de dizimista por nome/código, cadastro de novo dizimista (incluindo data de
  nascimento), lançamento de contribuição (cadastrada ou avulsa)
- **Ofertório**: lançamento da coleta da missa (dinheiro + Pix separados) e histórico recente
- **Aniversários**: lista de aniversariantes da semana ou do mês, da própria comunidade

**Secretaria/pároco** (acesso geral):
- **Consolidado**: relatório financeiro por mês, geral e por comunidade
- **Aniversariantes**: mesma lista, mas de todas as comunidades, com o nome da comunidade
  aparecendo ao lado de cada pessoa
- **Importar histórico**: upload da planilha preenchida (modelo
  `planilha-importacao-historico.xlsx`) — mostra quantos registros foram criados/atualizados e
  os avisos de qualquer linha que não pôde ser importada

## Testado

Esse app foi testado de ponta a ponta (login nos dois perfis, cadastro, busca, lançamentos,
aniversariantes e relatório) antes de ser entregue.

## Próximos passos possíveis

- Transformar em PWA (permite "instalar" na tela inicial do celular sem loja de app)
- Modo offline (fase 2, conforme os requisitos)
