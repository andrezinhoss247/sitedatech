# Site da D. A Tech

Site institucional estático da **D. A Tech Tecnologia e Empreendimentos**, pronto para ser publicado no GitHub Pages.

## Arquivos

- `index.html` - estrutura e conteúdo da página.
- `style.css` - todo o visual e a responsividade.
- `CNAME` - domínio personalizado `www.datechnology.com.br`.
- `README.md` - este guia.

Não há framework, banco de dados, build ou dependências. É HTML + CSS puro, então o GitHub Pages consegue servir os arquivos diretamente.

## 1. Baixar o repositório

No terminal:

```bash
git clone https://github.com/andrezinhoss247/sitedatech.git
cd sitedatech
```

Confira em qual branch você está:

```bash
git branch --show-current
```

## 2. Colocar os arquivos do site no repositório

Extraia o pacote que recebeu e copie `index.html`, `style.css`, `CNAME` e `README.md` para a raiz do repositório `sitedatech`.

Depois confira o que mudou:

```bash
git status
```

## 3. Fazer commit e push

```bash
git add index.html style.css CNAME README.md
git commit -m "Publica site da D. A Tech"
git push origin main
```

Se sua branch principal tiver outro nome, troque `main` pelo nome mostrado em `git branch --show-current`.

## 4. Ativar o GitHub Pages

No GitHub, abra:

`andrezinhoss247/sitedatech` → **Settings** → **Pages**

Em **Build and deployment**:

1. Source: **Deploy from a branch**.
2. Branch: **main** (ou a branch principal do repositório).
3. Folder: **/ (root)**.
4. Clique em **Save**.

Antes do domínio próprio, o endereço padrão do projeto será semelhante a:

`https://andrezinhoss247.github.io/sitedatech/`

## 5. Configurar o domínio no GitHub

Ainda em **Settings → Pages**, em **Custom domain**, informe:

`www.datechnology.com.br`

e salve.

O arquivo `CNAME` deste projeto já contém esse mesmo endereço. Mesmo assim, o domínio deve ser configurado também nas opções do GitHub Pages.

## 6. Configurar o DNS na Cloudflare

Na Cloudflare, abra `datechnology.com.br` → **DNS** → **Records**.

Para o endereço `www.datechnology.com.br`, use:

| Tipo | Nome | Destino |
| --- | --- | --- |
| CNAME | `www` | `andrezinhoss247.github.io` |

Durante a configuração inicial, deixe o registro como **DNS only** (nuvem cinza) para simplificar a validação.

Se já existir um CNAME chamado `www` apontando para outro serviço, ele deve ser substituído pelo destino do GitHub. Um nome não deve ter dois CNAME concorrentes.

Importante: o CNAME do GitHub aponta para `andrezinhoss247.github.io`, **sem** `/sitedatech` no final.

## 7. HTTPS

Depois que o DNS for reconhecido pelo GitHub, volte a **Settings → Pages** e habilite **Enforce HTTPS** quando a opção estiver disponível.

O GitHub informa que a emissão/ativação do HTTPS pode levar algum tempo depois da configuração do domínio.

## Testar localmente antes do push

Você pode simplesmente abrir `index.html` no navegador. Para simular um servidor local, também pode executar, dentro da pasta:

```bash
python3 -m http.server 8000
```

e acessar `http://localhost:8000`.

## Referências oficiais

- GitHub Pages - fonte de publicação: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- GitHub Pages - domínio personalizado: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- GitHub Pages - HTTPS: https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https
