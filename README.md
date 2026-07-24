# meu-hub — site de sistemas GameMaker Studio 2

Site estático (HTML/CSS/JS puro), sem back-end e sem custo de hospedagem ou domínio.

## Estrutura

```
index.html            → página inicial
docs.html              → visualizador de documentação (lê arquivos .md)
biblioteca.html        → lista de downloads (lê library-manifest.json)
social.html            → suas redes sociais
style.css              → todo o visual do site
docs/                  → seus arquivos .md de documentação
  manifest.json        → lista quais docs aparecem na aba Docs
library-manifest.json  → lista quais sistemas aparecem na Biblioteca
sitemap.xml / robots.txt → ajudam o Google a indexar o site
```

## Como adicionar um novo sistema (pelo Painel — recomendado)

O site tem uma página `admin.html` (link "painel" no rodapé de qualquer página) onde você publica sistemas sem mexer em nenhum arquivo.

1. Suba o arquivo do sistema (`.yymps` exportado do GameMaker) em uma *Release* do seu repositório: no GitHub, aba **Releases → Create a new release**, anexe o arquivo, publique, e copie o link de download do arquivo.
2. Abra `admin.html` no seu site publicado.
3. Na seção **1. Configuração**, faça uma única vez:
   - Crie um token em [github.com/settings/personal-access-tokens/new](https://github.com/settings/personal-access-tokens/new), limitado só ao seu repositório, com permissão **Contents: Read and write** (o passo a passo completo já está descrito na própria página do painel).
   - Preencha usuário, nome do repositório e cole o token. Clique em **Salvar configuração**. Isso fica guardado só no seu navegador.
4. Na seção **2. Publicar um sistema novo**, preencha nome, versão, descrição, link de download e (opcional) a documentação em markdown. Clique em **Publicar sistema**.
5. Pronto — o painel já salva tudo direto no seu repositório. Em ~1 minuto o GitHub Pages atualiza e o sistema aparece na Biblioteca e (se você preencheu a documentação) na aba Docs.

Você também pode remover um sistema publicado na lista no final do painel.

> O token fica salvo só no `localStorage` do navegador que você usou — se abrir o painel em outro computador, precisa configurar de novo. Nunca compartilhe esse token com ninguém, ele dá acesso de escrita ao seu repositório.

## Como adicionar um novo sistema manualmente (alternativa)

Se preferir editar os arquivos você mesmo:

1. **Documentação:** crie um arquivo `docs/nome-do-sistema.md` (markdown normal, com imagens `![alt](caminho)`, código, tabelas etc). Depois adicione uma entrada em `docs/manifest.json`:
   ```json
   { "id": "nome-do-sistema", "title": "Nome do Sistema", "file": "docs/nome-do-sistema.md" }
   ```
2. **Download:** adicione uma entrada em `library-manifest.json`:
   ```json
   {
     "title": "Nome do Sistema",
     "version": "v1.0.0",
     "description": "Descrição curta.",
     "size": "50 KB",
     "docId": "nome-do-sistema",
     "downloadUrl": "https://github.com/SEU-USUARIO/SEU-REPO/releases/download/v1.0.0/arquivo.yymps"
   }
   ```

## Como publicar de graça (GitHub Pages)

1. Crie uma conta no [github.com](https://github.com) (grátis).
2. Crie um repositório novo (público), ex: `meu-hub`.
3. Suba todos os arquivos desta pasta para o repositório (pelo site do GitHub: "Add file" → "Upload files", ou usando o Git no seu PC).
4. No repositório, vá em **Settings > Pages**.
5. Em "Source", escolha a branch `main` e a pasta `/ (root)`. Salve.
6. Em 1-2 minutos seu site estará no ar em:
   `https://SEU-USUARIO.github.io/meu-hub/`
7. Troque os textos `SEU-USUARIO` e `SEU-REPO` nos arquivos `sitemap.xml`, `robots.txt` e `library-manifest.json` pelo endereço real do seu site.

Alternativas igualmente gratuitas, sem domínio pago: **Netlify** (arraste a pasta em app.netlify.com/drop) ou **Cloudflare Pages**.

## Como aparecer no Google

1. Acesse [Google Search Console](https://search.google.com/search-console).
2. Adicione sua propriedade usando o endereço do seu GitHub Pages (`https://SEU-USUARIO.github.io/meu-hub/`), método "prefixo de URL".
3. Verifique a propriedade (o Search Console vai te dar um arquivo HTML ou meta tag para colocar no site — basta subir o arquivo na raiz do repositório e confirmar).
4. Em "Sitemaps", envie a URL: `https://SEU-USUARIO.github.io/meu-hub/sitemap.xml`.
5. Peça indexação manual de cada página em "Inspeção de URL" → "Solicitar indexação" para acelerar (o processo natural pode levar alguns dias).

## Testar localmente antes de publicar

Como o site usa `fetch()` para carregar os `.md` e `.json`, abrir o `index.html` direto no navegador (`file://`) pode bloquear esses carregamentos. Para testar localmente, rode dentro da pasta:

```bash
python3 -m http.server 8000
```

E acesse `http://localhost:8000` no navegador.
