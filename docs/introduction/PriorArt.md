# Técnica Anterior

Redux tem uma herança mista. É semelhante a alguns padrões e tecnologias, mas também é diferente deles de maneiras importantes. Exploraremos algumas das semelhanças e as diferenças abaixo.

### Flux

Redux pode ser considerado uma implementação de [Flux](https://facebook.github.io/flux/) ?  
[Sim](https://twitter.com/fisherwebdev/status/616278911886884864), e [não](https://twitter.com/andrestaltz/status/616270755605708800).

(Não se preocupe, [os criadores do Flux](https://twitter.com/jingc/status/616608251463909376) [aprovam isso](https://twitter.com/fisherwebdev/status/616286955693682688), se isso é tudo que você queria saber.)

O Redux foi inspirado por várias qualidades importantes do Flux. Como o Flux, o Redux prescreve que você concentre sua lógica de atualização de modelo em uma certa camada de sua aplicação (“stores” no Flux, “reducers” no Redux). Em vez de permitir que o código do aplicativo sofra uma mutação direta dos dados, ambos dizem para você descrever cada mutação como um objeto simples chamado de “action”.

Ao contrário do Flux, **o Redux não possui o conceito de um Dispatcher**. Isso ocorre porque ele depende de funções puras em vez de emissores de eventos, e funções puras são fáceis de compor e não precisam de uma entidade adicional para gerenciá-las. Dependendo de como você vê o Flux, você pode ver isso como um desvio ou um detalhe de implementação. Flux tem sido frequentemente [descrito como `(state, action) => state`](https://speakerdeck.com/jmorrell/jsconf-uy-flux-those-who-forget-the-past-dot-dot-dot-1). Nesse sentido, o Redux é fiel à arquitetura Flux, mas torna-se mais simples graças a funções puras.

Outra diferença importante do Flux é que **o Redux assume que você nunca muta seus dados**. Você pode usar objetos simples e arrays para o seu estado muito bem, mas mutá-los dentro dos redutores é fortemente desencorajado. Você deve sempre devolver um novo objeto, o que é fácil com a proposta do [operador de propagação de objetos](../recipes/UsingObjectSpreadOperator.md), ou com uma biblioteca como [Immutable](https://facebook.github.io/immutable-js).

Embora seja tecnicamente *possível* [escrever reducers impuros](https://github.com/reactjs/redux/issues/328#issuecomment-125035516) que alterem os dados para casos de desempenho, nós ativamente desencorajamos você a fazer isso. Os recursos de desenvolvimento, como viagem no tempo, gravação/reprodução ou hot reloading serão interrompidos. Além disso, não parece que a imutabilidade apresenta problemas de desempenho na maioria dos aplicativos reais, porque, como o [Om](https://github.com/omcljs/om) demonstra, mesmo se você perder a alocação de objetos, você ainda ganha evitando re-renderizações e recálculos caros, pois você sabe exatamente o que mudou graças à pureza do reducer.

### Elm

[Elm](http://elm-lang.org/) é uma linguagem de programação funcional inspirada em Haskell e criada por [Evan Czaplicki](https://twitter.com/czaplic). Ele impõe uma [arquitetura de “model view update”](https://github.com/evancz/elm-architecture-tutorial/), na qual a atualização possui a seguinte assinatura: `(action, state) => state`. Os “atualizadores” (updaters) do Elm servem o mesmo propósito que os reducers no Redux.

Ao contrário do Redux, o Elm é uma linguagem, por isso é capaz de se beneficiar de muitas coisas como pureza forçada, tipagem estática, imutabilidade imediata e correspondência de padrão (usando a expressão `case`). Mesmo que você não planeje usar o Elm, leia a arquitetura do Elm e brinque com ela. Existe um [playground de biblioteca JavaScript interessante implementando idéias semelhantes](https://github.com/paldepind/noname-functional-frontend-framework). Devemos procurar inspiração aqui no Redux! Uma forma de nos aproximarmos da tipagem estática de Elm é [usando uma solução de digitação gradual como o Flow](https://github.com/reactjs/redux/issues/290).

### Immutable

[Immutable](https://facebook.github.io/immutable-js) é uma biblioteca JavaScript que implementa estruturas de dados persistentes. É de alto desempenho e tem uma API JavaScript idiomática.

Immutable e bibliotecas mais semelhantes são ortogonais ao Redux. Sinta-se à vontade para usá-los juntos!

**O Redux não se importa *como* você armazena o estado - pode ser um objeto simples, um objeto Immutable ou qualquer outra coisa.** Você provavelmente desejará um mecanismo de (des)serialização para criar aplicativos universais e hidratar o estado deles a partir do servidor, mas, além disso, é possível usar qualquer biblioteca de armazenamento de dados, *desde que ela ofereça suporte à imutabilidade*. Por exemplo, não faz sentido usar o Backbone para o state do Redux, porque os modelos de Backbone são mutáveis.

Observe que, mesmo que sua biblioteca imutável ofereça suporte a cursores, você não deve usá-los em um aplicativo do Redux. Toda a árvore de estados deve ser considerada somente leitura, e você deve usar o Redux para atualizar o estado e assinar as atualizações. Portanto, escrever via cursor não faz sentido para o Redux. **Se seu único caso de uso para cursores é separar a árvore de estados da árvore da interface do usuário e refinar gradualmente os cursores, você deve procurar os seletores.** Seletores são funções getter que podem ser compostas. Veja [reselect](http://github.com/faassen/reselect) para uma implementação realmente ótima e concisa de seletores que podem ser compostos.

### Baobab

[Baobab](https://github.com/Yomguithereal/baobab) é outra biblioteca popular que implementa API imutável para atualizar objetos JavaScript simples. Embora você possa usá-lo com o Redux, há pouco benefício em usá-los juntos.

A maior parte da funcionalidade fornecida pelo Baobab está relacionada à atualização dos dados com cursores, mas o Redux impõe que a única maneira de atualizar os dados é despachar uma ação. Portanto, eles resolvem o mesmo problema de maneira diferente e não se complementam.

Ao contrário do Immutable, o Baobab ainda não implementa nenhuma estrutura de dados eficiente especial, portanto, você não ganha nada mesmo usando o Redux. É mais fácil usar apenas objetos simples nesse caso.

### Rx

[Reactive Extensions](https://github.com/Reactive-Extensions/RxJS) (e suas revisões [reescritas modernas](https://github.com/ReactiveX/RxJS)) são uma excelente maneira de gerenciar a complexidade dos aplicativos assíncronos. Na verdade, [há um esforço para criar uma biblioteca que modela a interação humano-computador como um observador interdependente](http://cycle.js.org).

Faz sentido usar o Redux junto com o Rx? Certo! Eles trabalham muito bem juntos. Por exemplo, é fácil expor um repositório Redux como um observável:

```js
function toObservable(store) {
  return {
    subscribe({ onNext }) {
      let dispose = store.subscribe(() => onNext(store.getState()))
      onNext(store.getState())
      return { dispose }
    }
  }
}
```

Da mesma forma, você pode compor diferentes fluxos assíncronos para transformá-los em ações antes de supri-los para `store.dispatch()`.

A questão é: você realmente precisa do Redux se já usa o Rx? Talvez não. Não é difícil [reimplementar o Redux no Rx](https://github.com/jas-chen/rx-redux). Alguns dizem que é um método de duas linhas usando o método Rx `.scan()`. Pode muito bem ser!

Se você estiver em dúvida, confira o código-fonte do Redux (não há muita coisa acontecendo), bem como o ecossistema (por exemplo, [as ferramentas de desenvolvedor](https://github.com/gaearon/redux-devtools)). Se você não se importar muito com isso e quiser ir com o fluxo de dados reativo até o fim, talvez queira explorar algo como o [Cycle](http://cycle.js.org), ou até combiná-lo com o Redux. Deixe-nos saber como vai!
