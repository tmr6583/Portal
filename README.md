# Portal de Serviços Internos — Betina

Portal estático que centraliza o acesso aos sistemas internos da Betina Soluções em Limpeza.

## Objetivo

- Oferecer um ponto único de entrada para os serviços internos.
- Reduzir erros de navegação com links oficiais e padronizados.
- Manter uma interface simples, rápida e de baixa manutenção.

## Estrutura do repositório

| Arquivo | Função |
|---|---|
| `index.html` | Página inteira: HTML, CSS inline e cards dos serviços. Não há JavaScript. |
| `Logo_Azul.webp` | Logo do cabeçalho e favicon da página. |
| `Logo_Azul.jpg` | Versão JPG do logo, mantida como cópia de referência. |
| `README.md` | Esta documentação. |
| `.gitattributes` | Configuração de final de linha do Git. |

Não há etapa de build, dependências locais, testes automatizados nem pipeline de CI/CD no repositório.

## Dependências externas

Carregadas diretamente pelo navegador a partir de `index.html`:

- **Google Fonts**: fonte Inter (pesos 300 a 700).
- **Font Awesome 6.5.0** (cdnjs): ícones dos cards.

## Serviços publicados no portal

Todos os links usam o domínio `https://betinalimpeza.com.br`.

1. **Cobranças** (card com destaque amarelo)
   - URL: `https://betinalimpeza.com.br/atrasados`
   - Função: acompanhamento de pedidos em atraso.
   - Ícone: `fa-money-bill-wave`

2. **Envio de Performance de Vendas**
   - URL: `https://betinalimpeza.com.br/performance`
   - Função: consolidação e envio periódico de dados mensais de venda.
   - Ícone: `fa-chart-line`

3. **Gerador de Encartes**
   - URL: `https://betinalimpeza.com.br/gerador/`
   - Função: criação de encartes promocionais com geração de imagem.
   - Ícone: `fa-images`

4. **Premiador** (card com destaque amarelo)
   - URL: `https://betinalimpeza.com.br/premiador`
   - Função: cálculo de comissões, premiações e vales para a equipe de vendas.
   - Ícone: `fa-trophy`

5. **Catálogo** (card com múltiplos links)
   - Não é um link único. O card é um `<div>`, porque um `<a>` não pode conter outros links. Cada catálogo aparece como um botão em formato de pílula dentro do card:
     - Geral: `https://betinalimpeza.com.br/catalogo/`
     - Adriana: `https://betinalimpeza.com.br/catalogo/adriana`
     - Simone: `https://betinalimpeza.com.br/catalogo/simone`
     - Silvana: `https://betinalimpeza.com.br/catalogo/silvana`
     - Maria Eduarda: `https://betinalimpeza.com.br/catalogo/mariaeduarda`
   - Ícone: `fa-book-open`

## Cabeçalho

- O logo no topo da página é um link para `https://betinalimpeza.com.br/`.
- O subtítulo "Portal de Serviços Internos" é apenas texto.

## Layout e responsividade

Os cards ficam em uma grade definida na classe `.grid` de `index.html`:

| Largura da tela | Colunas |
|---|---|
| Acima de 1100px | 5 (todos os cards na mesma linha) |
| 601px a 1100px | 3 |
| 381px a 600px | 2 |
| Até 380px | 1 |

A largura útil do conteúdo é de no máximo 1600px (`main { max-width: 1600px }`).

Em telas entre 1100px e 1300px, os cards ficam estreitos, e o texto pode quebrar em mais linhas.

## Uso

- Abra `index.html` em um navegador moderno.
- Clique no cartão do serviço desejado para ser redirecionado.
- No Catálogo, clique no botão do catálogo desejado (Geral ou de cada vendedora).

## Padrões de manutenção

- Editar somente `index.html` para ajustes de cards e layout.
- Manter URLs em HTTPS e evitar links `localhost` no portal publicado.
- Alterar somente o cartão necessário para não impactar os outros serviços.
- Cores, bordas e sombras são definidas como variáveis em `:root`. Para ajustar a paleta, altere essas variáveis.
- Ao publicar, valide cada link manualmente. Os endereços atuais não usam mais a rota `/login`. Se algum sistema exigir login e abrir uma tela de autenticação de forma errada, ajuste o link para a rota correta.

## Como adicionar um novo cartão

Para um cartão com link único:

1. Localize a `<div class="grid">` em `index.html`.
2. Duplique um bloco `<a class="card">...</a>` existente.
3. Atualize `href`, ícone, nome e descrição.
4. Como a grade tem 5 colunas em telas largas, confira o resultado nas larguras de 1100px, 600px e 380px.
5. Valide a navegação clicando no novo cartão e nos demais.

Para um cartão com vários links:

1. Use `<div class="card">`, e não `<a>`.
2. Coloque os links dentro de `<div class="card-links">`, usando `<a class="card-link">` para cada um.

## Pontos em aberto

- O caminho de deploy do arquivo no servidor não está confirmado neste repositório. Uma versão anterior deste README citava `/opt/betina/index.html`, mas esse caminho não aparece em nenhum outro lugar do projeto e não foi possível verificá-lo a partir do código. Confirme com quem administra o servidor antes de documentá-lo novamente.
- Os links de Performance e Premiador não usam mais `/login`. Confirme se esses sistemas abrem a tela de login diretamente nesses endereços.
