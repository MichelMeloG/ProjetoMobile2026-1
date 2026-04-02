# MapS2 - Inicio Completo

https://michelmelog.github.io/ProjetoMobile2026-1/rastreador.html

https://michelmelog.github.io/ProjetoMobile2026-1/

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



cores ibmec:

**Cores Neutras (Textos e Fundos base)**
* **Escuros:** `#121212` (Dark Pure / Foco principal), `#424242` (Dark Low), `#A3A3A3` (Dark High)
* **Claros:** `#FFFFFF` (Light Pure / Branco), `#F5F5F5` (Light High), `#E0E0E0` (Light Low)

**Cores de Ação (Botões, Links e Destaques)**
* **Ação Primária (Azul/Marinho):** `#002555` (Pure), `#00122A` (Low), `#BFC8D4` (High)
* **Ação Secundária (Amarelo/Mostarda):** `#F5AC00` (Pure), `#7A5600` (Low), `#FCEABF` (High / Hover de botões)

**Cores de Feedback (Alertas, Sucessos e Erros)**
* **Positivo (Verde):** `#54D073` (Pure), `#1C662E` (Low), `#CFF2D8` (High)
* **Negativo (Vermelho):** `#FF8771` (Pure), `#991700` (Low), `#FFDAD3` (High)
* **Aviso/Warning (Laranja):** `#FFAA33` (Pure), `#8C4400` (Low), `#FFEAC1` (High)

**Cores de Fundo (Backgrounds)**
* **Sistema (Cinzas e Grafites):** `#B5B3B3` (Pure), `#454444` (Low), `#E4E4E4` (High)
* **Público 01 (Ciano/Azul Claro):** `#39C1EC` (Pure), `#1F6C87` (Low), `#BBECFC` (High - também usado como a cor de tema do navegador no `<meta name="theme-color">`)
* **Público 02 (Azul Escuro/Vivo):** `#1245FF` (Pure), `#092380` (Low - usado no fundo do rodapé), `#C4D0FF` (High)

**Outros (Transparência / Sombras)**
* Fundo principal com opacidade: `rgba(18, 18, 18, 0.62)`
