# Examples

Redux é distribuído com alguns exemplos em seu [código-fonte](https://github.com/reactjs/redux/tree/master/examples).

## Contador Vanilla

Rode o exemplo [Contador Vanilla](https://github.com/reactjs/redux/tree/master/examples/counter-vanilla) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/counter-vanilla
open index.html
```

Não necessita de um build de sistema ou um framework de view e existe para mostrar o Redux API puro usado com ES5.

## Contador

Rode o exemplo [Contador](https://github.com/reactjs/redux/tree/master/examples/counter) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/counter
npm install
npm start

open http://localhost:3000/
```

Esse é o exemplo mais básico usando Redux junto com React. Por questão de simplicidade, re-renderiza o componente React manualmente quando o store muda. Em projetos reais, ao invés disso você provavelmente vai querer usar os bindings do altamente performático  [React Redux](https://github.com/reactjs/react-redux).

Esse exemplo inclui testes.

## ToDos

Rode o exemplo [ToDos](https://github.com/reactjs/redux/tree/master/examples/todos) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/todos
npm install
npm start

open http://localhost:3000/
```

Este é o melhor exemplo para entender melhor como as atualizações de estado funcionam em conjunto com os componentes no Redux. Ele mostra como os reducers podem delegar ações de manipulação a outros reducers e como você pode usar o [React Redux](https://github.com/reactjs/react-redux) para gerar componentes de contêineres a partir de seus componentes de apresentação.

Este exemplo inclui testes.

## ToDos com Desfazer

Rode o exemplo [ToDos com Desfazer](https://github.com/reactjs/redux/tree/master/examples/todos-with-undo) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/todos-with-undo
npm install
npm start

open http://localhost:3000/
```

Essa é uma variação do exemplo anterior. É quase idêntico, mas adicionalmente mostra como encapsular seu reducer com [Redux Undo](https://github.com/omnidan/redux-undo) deixa você adicionar uma funcionalidade Desfazer/Refazer à sua aplicação com algumas linhas de código.

## ToDoMVC

Rode o exemplo [ToDoMVC](https://github.com/reactjs/redux/tree/master/examples/todomvc) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/todomvc
npm install
npm start

open http://localhost:3000/
```

Esse é o clássico exemplo [ToDoMVC](http://todomvc.com/) . Está aqui com o propósito de comparação, mas cobre os mesmos pontos que os exemplos ToDo.

Esse exemplo inclui testes.

## Carrinho de Compras

Rode o exemplo [Carrinho de Compras](https://github.com/reactjs/redux/tree/master/examples/shopping-cart) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/shopping-cart
npm install
npm start

open http://localhost:3000/
```

Esse exemplo mostra importantes padrões idiomáticos de Redux que se tornam importantes à medida que sua aplicação cresce. Em particular, mostra como armazenar entidades de maneira normalizada por seus IDs, como compôr reducers em muitos níveis, e como definir seletores ao lado dos reducers para que o conhecimento sobre a forma do estado seja encapsulado. Também demonstra logar com [Redux Logger](https://github.com/fcomb/redux-logger) e despacho condicional de ações com o middleware [Redux Thunk](https://github.com/gaearon/redux-thunk) .

## Visão de Árvore

Rode o exemplo [Visão de Árvore](https://github.com/reactjs/redux/tree/master/examples/tree-view) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/tree-view
npm install
npm start

open http://localhost:3000/
```

Esse exemplo mostra a rendereização de uma visão de árvore profundamente aninhada e representa seu estado em um formato normalizado para que seja fácil de atualizar a partir dos reducers. Um bom desempenho de renderização é obtido pelos componentes de contêiner que assinam granularmente apenas os nós de árvore que eles renderizam.

Esse exemplo inclui testes.

## Async

Rode o exemplo [Async](https://github.com/reactjs/redux/tree/master/examples/async) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/async
npm install
npm start

open http://localhost:3000/
```

Este exemplo inclui a leitura de uma API assíncrona, a busca de dados em resposta à entrada do usuário, a exibição de indicadores de carregamento, o armazenamento em cache da resposta e a invalidação do cache. Ele usa o middleware [Redux Thunk](https://github.com/gaearon/redux-thunk) para encapsular efeitos colaterais assíncronos.

## Universal

Rode o exemplo [Universal](https://github.com/reactjs/redux/tree/master/examples/universal) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/universal
npm install
npm start

open http://localhost:3000/
```

Essa é uma demonstração básica de [renderização no servidor](../recipes/ServerRendering.md) com Redux e React. Mostra como preparar o estado inicial do store no servidor, e passar para o cliente para que o store do cliente possa ser inicializado a partir de um estado existente.

## Mundo Real

Rode o exemplo [Mundo Real](https://github.com/reactjs/redux/tree/master/examples/real-world) :

```
git clone https://github.com/reactjs/redux.git

cd redux/examples/real-world
npm install
npm start

open http://localhost:3000/
```

Este é o exemplo mais avançado. É denso por design. Ele cobre a manutenção de entidades buscadas em um cache normalizado, implementando um middleware personalizado para chamadas de API, renderizando dados parcialmente carregados, paginação, respostas de armazenamento em cache, exibindo mensagens de erro e roteamento. Além disso, inclui Redux DevTools.

## Mais exemplos

Você pode encontrar mais exemplos em [Awesome Redux](https://github.com/xgrommx/awesome-redux).
