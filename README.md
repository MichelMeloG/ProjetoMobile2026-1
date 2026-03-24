# MapS2 - Inicio Completo

Este projeto tem duas paginas:

- `index.html`: painel que mostra locais em tempo real e mapa por iframe.
- `rastreador.html`: pagina para celular enviar GPS para o Firestore.

## 1) Configurar Firebase (uma vez)

1. Entre no Firebase Console e abra o projeto `maps2-6bf71`.
2. Abra Firestore Database e crie o banco, caso ainda nao exista.
3. Na aba Rules, cole o conteudo de `firestore.rules.txt` e publique.

## 2) Testar localmente no computador

1. Abra `index.html` no navegador.
2. Verifique se a colecao `nomeDoLocal` existe no Firestore.

## 3) Enviar GPS do celular

1. Abra `rastreador.html` no celular (via site publicado em HTTPS).
2. Informe um `ID do documento` unico (ex.: `celular-joao`).
3. Clique em `Iniciar envio` e permita a localizacao.
4. A cada mudanca de posicao, o documento sera atualizado no Firestore.

Campos gravados automaticamente:

- `nomeDoLocal`
- `latitude`
- `longitude`
- `precisao`
- `atualizadoEm`

## 4) Ver no painel em tempo real

1. Abra `index.html` no computador.
2. O painel atualiza sozinho por `onSnapshot`.
3. Clique em `Ver no mapa` para focar um local no iframe.

## 5) Deploy no GitHub Pages

1. Suba estes arquivos para um repositorio GitHub.
2. Em Settings > Pages, selecione branch principal e pasta raiz.
3. Acesse a URL do Pages no computador e no celular.

Observacoes:

- Geolocation no celular exige HTTPS.
- GitHub Pages ja fornece HTTPS.
- Se tiver erro `permission-denied`, revise as regras do Firestore.
