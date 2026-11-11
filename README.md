# Portfólio – Alessandro Santos Oliveira

Site estático (HTML + CSS + JS puro), pronto para o GitHub Pages.

## Estrutura
```
index.html
css/style.css
js/data.js        <- TODO o conteúdo (textos, competências, certificados, currículos, contatos)
js/script.js      <- comportamento (não precisa mexer)
assets/
  images/         <- foto profissional (opcional)
  curriculos/     <- seus PDFs
  certificados/   <- imagens dos certificados (.webp)
```

## Adicionar um currículo
1. Coloque o PDF em `assets/curriculos/` (ex.: `curriculo-administrativo.pdf`; use minúsculas, sem espaços e sem acentos).
2. Em `js/data.js`, dentro de `curriculos: [ ... ]`, adicione:
```js
{ titulo: "Currículo Administrativo", descricao: "Perfil voltado a rotinas administrativas.", arquivo: "assets/curriculos/curriculo-administrativo.pdf" },
```
Cada objeto vira um card com os botões **Visualizar** e **Baixar**. Enquanto a lista estiver vazia, o site mostra um aviso com botões de e-mail e WhatsApp.

## Substituir ou remover
- **Substituir:** troque o PDF na pasta mantendo o mesmo nome (ou mude o `arquivo` em `data.js`).
- **Remover:** apague o objeto em `data.js` e o PDF da pasta.

## Certificados
As imagens já estão incluídas (recortadas, em WebP leve). Para trocar ou adicionar uma, salve-a em `assets/certificados/` com o nome do campo `file` (ex.: `jornada-python.webp`). O card só fica clicável quando a imagem existe.

## Foto e redes
- Foto: salve em `assets/images/` e preencha `foto: "assets/images/foto.webp"`.
- LinkedIn/GitHub: preencha `redes` em `data.js` (aparecem como botões no Contato).

## Testar localmente
PDFs e verificação de arquivos precisam de servidor local. Na pasta do projeto:
```
python -m http.server 8000
```
Abra http://localhost:8000. Confira: **Visualizar** abre o PDF (janela interna no computador, nova aba no celular), **Baixar** salva o arquivo. Se o caminho estiver errado, o card mostra "Arquivo não encontrado".

## Publicar no GitHub Pages
1. Crie um repositório no GitHub e envie todos os arquivos desta pasta (`index.html` na raiz).
2. Em **Settings → Pages**, em *Build and deployment*, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`, e salve.
3. Em alguns minutos o site fica em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.
4. Depois de publicar, adicione `og:url` e `og:image` no `<head>` do `index.html` para a prévia ao compartilhar.
