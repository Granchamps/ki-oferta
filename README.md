# Ki-Oferta

> **Projeto em construção.** Este repositório está em desenvolvimento ativo como projeto de estudos (FATEC) e ainda não representa uma versão final.

## Sobre o projeto

O Ki-Oferta é um modelo de aplicação criado com duas frentes de aprendizado em mente:

1. **Desenvolvimento web moderno** — uso de ferramentas atuais de build e um fluxo de trabalho baseado em módulos JavaScript (ES Modules), organização de código em componentes/páginas e boas práticas de estruturação de projeto front-end.
2. **Conceitos de desenvolvimento de aplicativos** — o mesmo código-fonte web é empacotado como um aplicativo mobile nativo (Android/iOS) usando o [Capacitor](https://capacitorjs.com/), permitindo estudar como uma aplicação web se transforma em um app instalável, com acesso a APIs nativas do dispositivo (câmera, splash screen, etc.).

A ideia é usar um único projeto para explorar, ao mesmo tempo, o "mundo web" e o "mundo mobile", entendendo onde as duas abordagens se encontram e onde elas divergem.

## Padrão utilizado

O projeto segue uma estrutura simples de **SPA (Single Page Application) em JavaScript puro (vanilla JS)**, sem frameworks como React, Vue ou Angular. Os principais pontos do padrão são:

- **Roteamento por hash**: a navegação entre telas é controlada pelo hash da URL (`#buscar`, `#mapa`, `#enviar`, etc.), interceptado pelo evento `hashchange` em [src/js/main.js](src/js/main.js).
- **Páginas como módulos**: cada tela vive em seu próprio arquivo dentro de [src/js/paginas/](src/js/paginas/) e exporta um objeto com sua `url` e uma função `pagina()` responsável por renderizar o conteúdo dentro do elemento `#app`.
- **Mapa de rotas central**: [src/js/rotas/rotas.js](src/js/rotas/rotas.js) reúne todas as páginas disponíveis em uma lista única, usada tanto pelo roteador quanto pela navbar.
- **Navbar dinâmica**: o componente em [src/js/navbar/navbar.js](src/js/navbar/navbar.js) é montado a partir do mesmo mapa de rotas, evitando duplicação entre navegação e páginas.
- **Build com Vite**: o [Vite](https://vitejs.dev/) cuida do bundling e do servidor de desenvolvimento, gerando a pasta `dist/` que o Capacitor usa como `webDir` para empacotar o app nativo.

## Como rodar o projeto

### Pré-requisitos

- [Node.js](https://nodejs.org/) instalado (recomendado LTS mais recente)
- npm (instalado junto com o Node.js)

### Passo a passo

1. Clone o repositório e acesse a pasta do projeto:

   ```bash
   git clone https://github.com/faustinopsy/ki-oferta
   cd ki-oferta
   ```

2. Instale as dependências:

   ```bash
   npm install
   ```

3. Rode o projeto em modo de desenvolvimento (abre no navegador, com hot reload):

   ```bash
   npm run dev
   ```

4. Para gerar a versão de produção (usada também pelo Capacitor):

   ```bash
   npm run build
   ```

5. Para pré-visualizar o build de produção localmente:

   ```bash
   npm run preview
   ```

### Rodando como app nativo (Capacitor)

Este projeto usa o [`@capacitor/create-app`](https://github.com/ionic-team/create-capacitor-app) como base. Para sincronizar o build web com os projetos nativos (Android/iOS), consulte a [documentação do Capacitor](https://capacitorjs.com/docs) — em resumo, após o `npm run build`, é necessário adicionar a plataforma desejada e sincronizar os arquivos web com o projeto nativo antes de rodar em um emulador ou dispositivo.

## Status

Este é um projeto didático em construção. Funcionalidades, estrutura de pastas e padrões podem mudar conforme o aprendizado avança.


## Atividade Bônus [1-3]

Membros do Grupo:
    • Allan Granchamps Fernandes Vieira
    • João Vitor Gomes de Vasconcelos
    • Thiago do Espirito Santo Corrêa

1. O que é o framework e qual abordagem ele segue?
Foi escolhido o framework Bootstrap, que atua no CSS e oferece classes e componentes prontos para facilitar a criação e organização de páginas web. Esse framework tem uma abordagem baseada em classes e componentes e também usa um sistema de grid responsivo para organizar os elementos na página.

2. Como você incluiu o framework na página?
O Bootstrap foi incluído na página utilizando o próprio link disponibilizado na documentação oficial através de um arquivo CSS externo. Com isso as classes podem ser usadas diretamente nos elementos HTML. 

3. Cite três benefícios que você percebeu ao usar, não apenas os que o site do framework anuncia.
Pudemos perceber que o uso do framework facilita muito a criação da estrutura da página, especialmente por ter classes para espaçamento, alinhamento e organização dos elementos. Ficou mais fácil montar uma estrutura visual sem precisar escrever todas as regras de CSS do zero. O fato de poder consultar exemplos prontos na documentação do Bootstrap e fazer as adequações conforme necessário também facilita bastante o processo.

4. Cite duas limitações ou desvantagens.
Para quem não está muito acostumado com o framework, ter que aprender os nomes e funções das classes pode gerar uma barreira inicial de aprendizagem. Outra desvantagem é que os componentes usam um estilo próprio e se o projeto quiser usar outro estilo, pode ser necessário criar um CSS próprio para modificar esses estilos.

5. Abra o CSS do framework (ou inspecione um elemento no DevTools F12). Ele estiliza usando classes ou IDs? Por que você acha que frameworks preferem um dos dois?
O Bootstrap usa principalmente as classes para aplicar seus estilos. Acreditamos que os frameworks preferem classes porque elas podem ser reutilizadas em diferentes elementos da página, possibilitando combinações conforme necessário. Já um ID normalmente identifica um elemento específico.

6. Fontes
    • Bootstrap Documentation — Bootstrap Documentation
https://getbootstrap.com/docs/
Data de acesso: 17/09/2026. 
    • MDN Web Docs — CSS selectors
https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Selectors
Data de acesso: 17/09/2026.
