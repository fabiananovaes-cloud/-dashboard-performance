Dashboard de Performance — Google Ads
Backend Python (Flask) que conecta à Google Ads API e serve métricas
para o dashboard de marketing de performance.
Configuração local
1. Instalar dependências
```bash
pip install -r requirements.txt
```
2. Criar o arquivo .env
Copie o arquivo de exemplo e preencha com suas credenciais:
```bash
copy .env.example .env
```
Edite o `.env` e preencha:
`REFRESH_TOKEN` — gerado no OAuth Playground
`DEVELOPER_TOKEN` — da Central da API no Google Ads
3. Rodar localmente
```bash
python app.py
```
Acesse: http://localhost:5000/api/health
4. Testar as métricas
```
http://localhost:5000/api/metrics?days=30
```
Deploy no Render.com
Suba este repositório no GitHub
No Render: New Web Service → conectar repositório
Em "Environment Variables", adicione todas as variáveis do `.env`
(nunca suba o arquivo .env para o GitHub)
O Render detecta o `Procfile` e inicia com gunicorn automaticamente
Endpoints
Endpoint	Descrição
`GET /api/health`	Verifica se o servidor está rodando
`GET /api/metrics?days=30`	Retorna todas as métricas (7, 14, 30 ou 90 dias)
