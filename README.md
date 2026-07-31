# Dashboards · Almoxarifado Central — Grupo GBS

Vitrine de dashboards do setor, hospedada gratuitamente via GitHub Pages.

## Arquivos
- `index.html` — página principal com os cards de cada dashboard
- `dashboards.html` — modo TV: rodízio automático entre os dashboards (para deixar rodando num monitor do setor)

## Como publicar do zero

### 1. Criar o repositório no GitHub
1. Acesse [github.com](https://github.com) e faça login (ou crie uma conta gratuita).
2. Clique em **New repository**.
3. Nome sugerido: `dashboards-almoxarifado` (pode ser qualquer nome, sem espaços).
4. Marque como **Public** (necessário para o GitHub Pages gratuito) e clique em **Create repository**.

### 2. Subir os arquivos
Sem usar linha de comando (mais simples):
1. Dentro do repositório recém-criado, clique em **Add file → Upload files**.
2. Arraste `index.html` e `dashboards.html`.
3. Clique em **Commit changes**.

Ou via Git, se preferir:
```bash
git init
git add index.html dashboards.html README.md
git commit -m "Primeira versão da vitrine de dashboards"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/dashboards-almoxarifado.git
git push -u origin main
```

### 3. Ativar o GitHub Pages
1. No repositório, vá em **Settings → Pages**.
2. Em **Source**, selecione a branch `main` e a pasta `/ (root)`.
3. Clique em **Save**.
4. Em alguns segundos o GitHub mostra o link, algo como:
   `https://SEU_USUARIO.github.io/dashboards-almoxarifado/`

### 4. Pegar os links dos dashboards no Power BI
1. Abra o dashboard no Power BI Service (app.powerbi.com).
2. **Arquivo → Inserir relatório → Publicar na web (público)**.
   - Atenção: isso torna o relatório acessível a qualquer pessoa com o link. Não use para dados sensíveis/confidenciais — para uso interno restrito, prefira "Publicar na organização" com autenticação, ou embutir via um portal interno em vez do GitHub Pages público.
3. Copie o link gerado (algo como `https://app.powerbi.com/view?r=eyJrIjoi...`).
4. Cole esse link no lugar de `SEU_LINK_AQUI_1`, `SEU_LINK_AQUI_2` etc. em `index.html` e `dashboards.html`.

### 5. Editar os cards
Em `index.html`, cada card é um bloco `<a class="card" href="...">`. Para adicionar um novo:
1. Copie um bloco `<a class="card">...</a>` inteiro.
2. Troque o `href` pelo link do Power BI.
3. Troque o título, a descrição e o emoji do `card-thumb`.
4. Marque o status como `ativo` (mostra "Acessar") ou `construcao` (mostra "Em Construção").

Em `dashboards.html`, adicione/remova itens na lista `dashboards` no topo do `<script>`.

### 6. Atualizações futuras
Sempre que quiser trocar algo, edite o arquivo direto pelo GitHub (ícone de lápis no arquivo) ou suba a nova versão via **Upload files**. O site atualiza sozinho em ~1 minuto.

## Nota sobre segurança
"Publicar na Web" no Power BI deixa o relatório público na internet (qualquer pessoa com o link acessa, sem login). Para dados internos sensíveis (custos, fornecedores, valores), considere hospedar essa vitrine em um SharePoint/intranet interno em vez do GitHub Pages, ou usar embed com autenticação Azure AD.
