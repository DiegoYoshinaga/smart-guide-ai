# SmartGuideAI

## Frontend

O MVP web está em `frontend/` e usa HTML, CSS e JavaScript sem frameworks ou dependências de build. Para testar, sirva essa pasta com um servidor HTTP local (por exemplo, `python -m http.server 5500 --directory frontend`) e abra `http://localhost:5500`.

O frontend consulta a API Spring Boot em `http://localhost:8080`. As rotas esperadas estão centralizadas em `frontend/js/api.js`: `GET /api/produtos`, `GET /api/produtos/{id}`, `GET /api/categorias`, `POST /api/chat`, `GET /api/mapa/produto/{id}` e `POST /api/lista-compras`. O backend precisa permitir CORS para a origem local usada no desenvolvimento. Se a API de produtos estiver indisponível, as páginas de catálogo, assistente e mapa informam explicitamente que estão usando os dados locais de demonstração; respostas da API não são substituídas por esses dados.

A lista de compras é compartilhada entre as páginas e armazenada no `localStorage` do navegador. O envio da lista ao backend permanece preparado, mas a persistência usada pelo MVP é local.