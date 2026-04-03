====================================================================
PORTAL DE SERVIÇOS INTERNOS - BETINA SOLUÇÕES EM LIMPEZA
====================================================================

Visão Geral
-----------
Este projeto é o portal central de acesso aos serviços e sistemas 
internos da Betina Soluções em Limpeza. Ele funciona como uma 
página inicial (hub) que direciona os usuários para as diversas 
ferramentas operacionais da empresa.

Serviços Atuais
---------------
O portal atualmente integra os seguintes sistemas:

1. Cobranças
   - URL: http://localhost:3000/
   - Descrição: Sistema para acompanhamento de pedidos em atraso.
   - Ícone: fa-money-bill-wave

2. Envio de Performance de Vendas
   - URL: http://localhost:3200/
   - Descrição: Consolidação e envio periódico de dados mensais de venda.
   - Ícone: fa-chart-line

Para Usuários
-------------
Para acessar o portal, basta abrir o arquivo "index.html" em qualquer 
navegador web moderno (Chrome, Firefox, Edge). 
Clique no serviço desejado para ser redirecionado automaticamente.

Para Desenvolvedores
--------------------
O portal foi desenvolvido como uma página estática pura (HTML + CSS) 
para máxima performance e facilidade de manutenção.

- Arquivo Principal: index.html
- Estilização: CSS embutido no `<head>` usando variáveis nativas (:root)
  para as cores da marca (Azul e Amarelo).
- Ícones: Utiliza a biblioteca Font Awesome (via CDN).
- Fontes: Inter (Google Fonts).

Como adicionar um novo serviço:
1. Abra o arquivo index.html.
2. Localize a tag `<div class="grid">`.
3. Copie o bloco de um cartão existente (`<a class="card">...</a>`).
4. Altere o `href` para a URL do novo serviço.
5. Atualize o ícone `<i class="fa-solid ...">` (consulte fontawesome.com).
6. Altere o título (`<div class="card-name">`) e a descrição (`<div class="card-desc">`).

Nota sobre Estilos de Cartão:
- Use `class="card"` para o estilo padrão (azul).
- Use `class="card accent"` para o estilo de destaque (amarelo), como 
  usado no módulo de Cobranças.
