# Três Princípios

Redux pode ser descrito em três princípios fundamentais:

### Única fonte de verdade

**O [estado](../Glossary.md#state) (state) de todo o aplicativo é armazenado em uma árvore de objetos em um único [armazenamento](../Glossary.md#store) (store).**

Isso facilita a criação de aplicativos universais, já que o estado do servidor pode ser serializado e hidratado no cliente sem nenhum esforço extra de codificação. Uma única árvore de estado também facilita a depuração ou a introspecção de uma aplicação; Ele também permite que você persista o estado do seu aplicativo no desenvolvimento, para um ciclo de desenvolvimento mais rápido. Algumas funcionalidades que têm sido tradicionalmente difíceis de implementar - Desfazer / Refazer, por exemplo - podem subitamente tornar-se triviais de implementar, se todo o seu estado estiver armazenado em uma única árvore.

```js
console.log(store.getState())

/* Prints
{
  visibilityFilter: 'SHOW_ALL',
  todos: [
    {
      text: 'Consider using Redux',
      completed: true,
    },
    {
      text: 'Keep all state in a single tree',
      completed: false
    }
  ]
}
*/
```

### Estado é somente leitura

**A única maneira de alterar o estado é emitir uma [ação](../Glossary.md#action) (action), um objeto descrevendo o que aconteceu.**

Isso garante que nem as views nem os retornos de chamada (callbacks) da rede jamais serão gravados diretamente no estado. Em vez disso, eles expressam a intenção de mudar. Como todas as mutações são centralizadas e acontecem uma a uma em uma ordem estrita, não há condições sutis de corrida a serem observadas. Como as ações são apenas objetos simples, elas podem ser registradas, serializadas, armazenadas e, posteriormente, reproduzidas para fins de depuração ou teste.

```js
store.dispatch({
  type: 'COMPLETE_TODO',
  index: 1
})

store.dispatch({
  type: 'SET_VISIBILITY_FILTER',
  filter: 'SHOW_COMPLETED'
})
```

### As alterações são feitas com funções puras

**Para especificar como a árvore de estados é transformada por ações, você escreve [redutores](../Glossary.md#reducer) (reducers) puros.**

Redutores são apenas funções puras que tomam o estado anterior e uma ação, e retornam o próximo estado. Lembre-se de retornar objetos de novo estado, em vez de alterar o estado anterior. Você pode começar com um único reducer e, à medida que seu aplicativo cresce, divida-o em reducers menores que gerenciam partes específicas da árvore de estados. Como os redutores são apenas funções, você pode controlar a ordem na qual eles são chamados, passar dados adicionais ou até mesmo fazer reducers reutilizáveis ​​para tarefas comuns, como paginação.

```js

function visibilityFilter(state = 'SHOW_ALL', action) {
  switch (action.type) {
    case 'SET_VISIBILITY_FILTER':
      return action.filter
    default:
      return state
  }
}

function todos(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ]
    case 'COMPLETE_TODO':
      return state.map((todo, index) => {
        if (index === action.index) {
          return Object.assign({}, todo, {
            completed: true
          })
        }
        return todo
      })
    default:
      return state
  }
}

import { combineReducers, createStore } from 'redux'
let reducer = combineReducers({ visibilityFilter, todos })
let store = createStore(reducer)
```

É isso aí! Agora você sabe o que é Redux.