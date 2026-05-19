# Portal de Serviços Internos — Betina

Portal estático que centraliza o acesso aos sistemas operacionais da empresa.

## Objetivo

- Oferecer um ponto único de entrada para os serviços internos.
- Reduzir erros de navegação com links oficiais e padronizados.
- Manter uma interface simples, rápida e de baixa manutenção.

## Arquivo principal

- `/opt/betina/index.html`

## Serviços publicados no portal

1. **Cobranças**
   - URL: `https://betinalimpeza.ddns.net/atrasados/`
   - Função: acompanhamento de pedidos em atraso.
   - Ícone: `fa-money-bill-wave`

2. **Envio de Performance de Vendas**
   - URL: `https://betinalimpeza.ddns.net/performance/login`
   - Função: acesso ao login do serviço de performance para consolidação e envio periódico de dados de venda.
   - Ícone: `fa-chart-line`

3. **Gerador de Encartes**
   - URL: `https://betinalimpeza.ddns.net/gerador/`
   - Função: criação de encartes promocionais com geração de imagem final.
   - Ícone: `fa-images`

4. **Premiador**
   - URL: `https://betinalimpeza.ddns.net/premiador/login`
   - Função: cálculo de comissões, premiações e vales para vendedores.
   - Ícone: `fa-trophy`

## Uso

- Abra `index.html` em um navegador moderno.
- Clique no cartão do serviço desejado para redirecionamento.
- O cartão `Premiador` abre diretamente a tela de login do sistema de premiação.

## Padrões de manutenção

- Editar preferencialmente apenas `index.html` para ajustes de cards.
- Manter URLs em HTTPS e evitar links `localhost` no portal publicado.
- Alterar somente o cartão necessário para não impactar outros serviços.
- Em serviços com autenticação obrigatória, apontar o link para a rota de login.

## Como adicionar novo cartão

1. Localize a `<div class="grid">` em `index.html`.
2. Duplique um bloco `<a class="card">...</a>` existente.
3. Atualize `href`, ícone, nome e descrição.
4. Valide navegação clicando no novo cartão e nos demais cartões existentes.
