# Ecossistema

O Redux é uma pequena biblioteca, mas seus contratos e APIs são cuidadosamente escolhidos para gerar um ecossistema de ferramentas e extensões.

Para uma extensa lista de tudo relacionado ao Redux, recomendamos [Awesome Redux](https://github.com/xgrommx/awesome-redux). Ele contém exemplos, boilerplates, middleware, bibliotecas de utilitários e muito mais.

Nesta página, apenas apresentaremos alguns deles que os mantenedores do Redux examinaram pessoalmente. Não deixe que isso te desencoraje de tentar o resto deles! O ecossistema está crescendo muito rápido e temos um tempo limitado para analisar tudo. Considere estas "escolhas da equipe" e não hesite em enviar um Pull Request se você tiver criado algo maravilhoso com o Redux.

## Aprendendo Redux

### Screencasts

* **[Getting Started with Redux](https://egghead.io/series/getting-started-with-redux)** — Aprenda o básico do Redux diretamente do seu criador (30 vídeos grátis)

### Apps de Exemplo

* [Exemplos Oficiais](Examples.md) — Alguns exemplos oficiais cobrindo diferentes técnicas de Redux
* [SoundRedux](https://github.com/andrewngu/sound-redux) — Um cliente SoundCloud construído com Redux

### Tutoriais e Artigos

* [Redux Tutorial](https://github.com/happypoulp/redux-tutorial) — Aprenda como usar Redux passo a passo
* [Redux Egghead Course Notes](https://github.com/tayiorbeii/egghead.io_redux_course_notes) — Notas sobre Redux [Egghead video course](https://egghead.io/series/getting-started-with-redux)
* [What the Flux?! Let’s Redux.](https://blog.andyet.com/2015/08/06/what-the-flux-lets-redux) — Uma introdução ao Redux
* [A cartoon intro to Redux](https://code-cartoons.com/a-cartoon-intro-to-redux-3afb775501a6) — Uma explicação visual do fluxo de dados do Redux
* [Understanding Redux](http://www.youhavetolearncomputers.com/blog/2015/9/15/a-conceptual-overview-of-redux-or-how-i-fell-in-love-with-a-javascript-state-container) — Aprenda os conceitos básicos do Redux
* [Handcrafting an Isomorphic Redux Application (With Love)](https://medium.com/@bananaoomarang/handcrafting-an-isomorphic-redux-application-with-love-40ada4468af4) — Um guia para criar uma aplicação universal com busca de dados e roteamento
* [Full-Stack Redux Tutorial](http://teropa.info/blog/2015/09/10/full-stack-redux-tutorial.html) — Um guia completo para desenvolvimento test-first (teste primeiro) com Redux, React, e Immutable
* [Secure Your React and Redux App with JWT Authentication](https://auth0.com/blog/2016/01/04/secure-your-react-and-redux-app-with-jwt-authentication/) — Aprenda como adicionar autenticação JWT a sua aplicação React e Redux
* [Understanding Redux Middleware](https://medium.com/@meagle/understanding-87566abcfb7a#.l033pyr02) — Guia detalhado para implementar o middleware Redux
* [Angular 2 — Introduction to Redux](https://medium.com/google-developer-experts/angular-2-introduction-to-redux-1cf18af27e6e) — Uma introdução aos conceitos fundamentais do Redux com um exemplo em Angular 2
* [Working with VK API (em Russo)](https://www.gitbook.com/book/maxfarseer/redux-course-ru/details) — Um tutorial em Russo que demonstra a criação de um app que consome VK API

### Talks

* [Live React: Hot Reloading and Time Travel](http://youtube.com/watch?v=xsSnOQynTHs) — Veja como as restrições impostas pelo Redux facilitam o recarregamento com viagens no tempo
* [Cleaning the Tar: Using React within the Firefox Developer Tools](https://www.youtube.com/watch?v=qUlRpybs7_c) — Aprenda a migrar gradualmente os aplicativos MVC existentes para o Redux
* [Redux: Simplifying Application State](https://www.youtube.com/watch?v=okdC5gcD-dM) — Uma introdução a arquitetura Redux

## Usando Redux

### Bindings

* [react-redux](https://github.com/gaearon/react-redux) — React
* [ng-redux](https://github.com/wbuchwalter/ng-redux) — Angular
* [ng2-redux](https://github.com/wbuchwalter/ng2-redux) — Angular 2
* [backbone-redux](https://github.com/redbooth/backbone-redux) — Backbone
* [redux-falcor](https://github.com/ekosz/redux-falcor) — Falcor
* [deku-redux](https://github.com/troch/deku-redux) — Deku

### Middleware

* [redux-thunk](http://github.com/gaearon/redux-thunk) — A maneira mais fácil de escrever criadores de ações assíncronas
* [redux-promise](https://github.com/acdlite/redux-promise) — [FSA](https://github.com/acdlite/flux-standard-action)-compliant promise middleware
* [redux-rx](https://github.com/acdlite/redux-rx) — Utilitários RxJS para Redux, incluindo um middleware para Observable
* [redux-logger](https://github.com/fcomb/redux-logger) — Logue toda ação Redux e o próximo estado
* [redux-immutable-state-invariant](https://github.com/leoasis/redux-immutable-state-invariant) — Avisos sobre mutações de estado em desenvolvimento
* [redux-analytics](https://github.com/markdalgleish/redux-analytics) — Analytics middleware para Redux
* [redux-gen](https://github.com/weo-edu/redux-gen) — Generator middleware para Redux
* [redux-saga](https://github.com/yelouafi/redux-saga) — Um modelo alternativo de efeito colateral para apps Redux

### Roteamento

* [react-router-redux](https://github.com/reactjs/react-router-redux) — Ligações impiedosamente simples para manter o React Router e Redux em sincronia

### Componentes

* [redux-form](https://github.com/erikras/redux-form) — Manter o estado do formulário React no Redux
* [react-redux-form](https://github.com/davidkpiano/react-redux-form) — Crie formulários facilmente em React with Redux

### Enhancers

* [redux-batched-subscribe](https://github.com/tappleby/redux-batched-subscribe) — Personalize as chamadas em lote (batch) e chamadas de debouncing para os assinantes da store
* [redux-history-transitions](https://github.com/johanneslumpe/redux-history-transitions) — Transições de histórico baseadas em ações arbitrárias
* [redux-optimist](https://github.com/ForbesLindesay/redux-optimist) — 
Aplicar de forma otimista ações que podem ser posteriormente confirmadas ou revertidas
* [redux-undo](https://github.com/omnidan/redux-undo) — Desfazer/refazer sem esforço e histórico de ações para seus reducers
* [redux-ignore](https://github.com/omnidan/redux-ignore) — Ignore ações de redux por array ou função de filtro
* [redux-recycle](https://github.com/omnidan/redux-recycle) — Redefinir o estado do Redux em certas ações
* [redux-batched-actions](https://github.com/tshelburne/redux-batched-actions) — Despachar várias ações com uma única notificação de assinante
* [redux-search](https://github.com/treasure-data/redux-search) — Indexar recursos automaticamente em um web worker e pesquisá-los sem bloquear
* [redux-electron-store](https://github.com/samiskin/redux-electron-store) — 
Armazenar enhancers que sincronizam os stores do Redux nos processos do Electron
* [redux-loop](https://github.com/raisemarketplace/redux-loop) — Efeitos da seqüência pura e naturalmente, retornando-os de seus reducers

### Utilidades

* [reselect](https://github.com/faassen/reselect) — Seletores de dados derivados eficientes inspirados pelo NuclearJS
* [normalizr](https://github.com/gaearon/normalizr) — Normalize as respostas de API aninhadas para facilitar o consumo dos reducers
* [redux-actions](https://github.com/acdlite/redux-actions) — Reduz o boilerplate em escrever reducers e criadores de ação
* [redux-act](https://github.com/pauldijou/redux-act) — Uma biblioteca opinativa para fazer reducers e criadores de ações
* [redux-transducers](https://github.com/acdlite/redux-transducers) — Utilitários Transducer para Redux
* [redux-immutable](https://github.com/gajus/redux-immutable) — Usado para criar uma função equivalente do Redux `combineReducers` que funciona com o estado do [Immutable.js](https://facebook.github.io/immutable-js/) .
* [redux-tcomb](https://github.com/gcanti/redux-tcomb) — Estado imutável e com verificação de tipo e ações para Redux
* [redux-mock-store](https://github.com/arnaudbenard/redux-mock-store) — Mock redux store para testar seu app

### DevTools

* [Redux DevTools](http://github.com/gaearon/redux-devtools) — Um logger de ações com UI de viagem no tempo, hot reloading e tratamento de erros para os reducers, [primeiro demo na React Europe](https://www.youtube.com/watch?v=xsSnOQynTHs)
* [Redux DevTools Extension](https://github.com/zalmoxisus/redux-devtools-extension) — Uma extensão do Chrome que encapsula o Redux DevTools e fornece funcionalidades adicionais

### DevTools Monitors

* [Log Monitor](https://github.com/gaearon/redux-devtools-log-monitor) — O monitor padrão para o Redux DevTools com uma visualização em árvore
* [Dock Monitor](https://github.com/gaearon/redux-devtools-dock-monitor) — Um dock redimensionável e móvel para monitores Redux DevTools
* [Slider Monitor](https://github.com/calesce/redux-slider-monitor) — Um monitor customizado para o Redux DevTools para reproduzir ações gravadas do Redux
* [Inspector](https://github.com/alexkuz/redux-devtools-inspector) — Um monitor personalizado para Redux DevTools que permite filtrar ações, inspecionar diffs e fixar caminhos profundos no estado para observar suas alterações
* [Diff Monitor](https://github.com/whetstone/redux-devtools-diff-monitor) — Um monitor para Redux Devtools que difere as mutações armazenadas no Redux entre ações
* [Filterable Log Monitor](https://github.com/bvaughn/redux-devtools-filterable-log-monitor/) — Monitor de exibição de árvore filtrável para Redux DevTools
* [Chart Monitor](https://github.com/romseguy/redux-devtools-chart-monitor) — Um monitor gráfico para Redux DevTools
* [Filter Actions](https://github.com/zalmoxisus/redux-devtools-filter-actions) — Redux DevTools monitor que pode ser composto com a capacidade de filtrar ações

### Convenções da Comunidade

* [Flux Standard Action](https://github.com/acdlite/flux-standard-action) — Um padrão amigável para objetos de ação Flux
* [Canonical Reducer Composition](https://github.com/gajus/canonical-reducer-composition) — Um padrão opinativo para composição de reducer aninhado
* [Ducks: Redux Reducer Bundles](https://github.com/erikras/ducks-modular-redux) — Uma proposta para agrupar redutores, tipos de ação e ações

### Traduções

* [中文文档](http://camsong.github.io/redux-in-chinese/) — Chinês
* [繁體中文文件](https://github.com/chentsulin/redux) — Chinês Tradicional
* [Redux in Russian](https://github.com/rajdee/redux-in-russian) — Russo

## Mais

[Awesome Redux](https://github.com/xgrommx/awesome-redux) é uma extensa lista de repositórios relacionados ao Redux.  
[React-Redux Links](https://github.com/markerikson/react-redux-links) é uma lista selecionada de artigos, tutoriais e conteúdo relacionado de alta qualidade para React, Redux, ES6 e muito mais.