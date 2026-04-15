====================================================================
PORTAL DE SERVIÇOS INTERNOS - BETINA SOLUÇÕES EM LIMPEZA
====================================================================

Visão Geral
-----------
Este projeto é o portal central de acesso aos serviços e sistemas 
internos da Betina Soluções em Limpeza. Ele funciona como uma 
página inicial (hub) que direciona os usuários para as diversas 
ferramentas operacionais da empresa.

Arquivo principal do portal:
- /opt/betina/index.html

Serviços Atuais
---------------
O portal atualmente integra os seguintes sistemas:

1. Cobranças
   - URL: https://betinalimpeza.ddns.net/atrasados/
   - Descrição: Sistema para acompanhamento de pedidos em atraso.
   - Ícone: fa-money-bill-wave

2. Envio de Performance de Vendas
   - URL: https://betinalimpeza.ddns.net/performance/login
   - Descrição: Acesso direto à página de login do serviço de Performance para consolidação e envio periódico de dados mensais de venda.
   - Ícone: fa-chart-line

3. Gerador de Encartes
   - URL: https://betinalimpeza.ddns.net/gerador/
   - Descrição: Criação de encartes promocionais com geração de imagem final.
   - Ícone: fa-images

Para Usuários
-------------
Você pode acessar o portal por uma destas formas:
- Abrindo o arquivo "index.html" em navegador web moderno (Chrome, Firefox, Edge).
- Publicando este mesmo arquivo por servidor HTTP interno/externo.

Navegação:
- Clique no cartão desejado para redirecionamento automático.
- O cartão "Envio de Performance de Vendas" abre diretamente a tela de login do serviço Performance.
- O cartão "Gerador de Encartes" abre o sistema de criação de encartes.

Para Desenvolvedores
--------------------
O portal foi desenvolvido como uma página estática pura (HTML + CSS) 
para máxima performance e facilidade de manutenção.

- Arquivo Principal: index.html
- Estilização: CSS embutido no `<head>` usando variáveis nativas (:root)
  para as cores da marca (Azul e Amarelo).
- Ícones: Utiliza a biblioteca Font Awesome (via CDN).
- Fontes: Inter (Google Fonts).

Padrão de links dos cartões:
- Preferir URL pública HTTPS do serviço.
- Evitar links locais (localhost) no portal publicado.
- Em serviços com autenticação obrigatória, apontar diretamente para a rota de login.

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

Checklist de revisão antes de publicar alteração no portal:
1. Confirmar se cada `href` aponta para o ambiente correto (produção/homologação).
2. Confirmar se nenhum link de outro serviço foi alterado sem necessidade.
3. Validar se título, descrição e ícone representam corretamente o serviço.
4. Abrir o index.html no navegador e clicar em todos os cartões.
