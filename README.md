# JavaScript Style Guide() {

_Style guide simplificado para o Grupo 4 do PI Mentora-me para Digital House_

> Adaptado do [Airbnb StyleGuide](https://github.com/airbnb/javascript)

## Conteúdo:

1. [VS Code](#VScode)
1. [Variables/Variáveis](#variaveis)
1. [Objects/Objetos](#objects)
1. [Arrays/Vetores](#arrays)
1. [Functions/Funções](#functions)
1. [Classes & Constructors](#classes--constructors)
1. [Properties/Propriedades](#properties)
1. [Comparison Operators & Equality/Operadores de Comparação & Equidade](#comparison-operators--equality)
1. [Comentários](#comments)
1. [Naming Conventions/Nomeação](#naming-conventions)
1. [Git Commits](#git-commits)

## VS Code

<a name="vs-code"></a><a name="1.1"></a>

- [1.1](#vs-code) Use a extensão Prettier para formatação automática no VS Code.

## Variables/Variáveis

<a name="variaveis"></a><a name="2.1"></a>

- [2.1](#variaveis) Use apenas `const` ou `let`.

  ```javascript
  const a = 1;

  // só use let se o valor da variável for mudar posteriormente.
  let count = 1;
  if (true) {
    count += 1;
  }
  ```

- [2.2](#variables--const-let-group) Agrupe os `const`s and os `let`s.

  > É mais fácil de localizar a variável dessa forma.

  ```javascript
  // não:
  let i;
  const items = getItems();
  let dragonball;
  const goSportsTeam = true;
  let len;

  // sim:
  const goSportsTeam = true;
  const items = getItems();
  let dragonball;
  let i;
  let length;
  ```

**[⬆ voltar ao início](#table-of-contents)**

## Objects/Objetos

<a name="objects--no-new"></a><a name="3.1"></a>

- [3.1](#objects--no-new) Use a notação literal para criar objetos.

  ```javascript
  // não:
  const item = new Object();

  // sim:
  const item = {};
  ```

- [3.2](#objects--quoted-props) Só utilizar aspas em propriedades que tem identificadores inválidos.

  ```javascript
  // não:
  const bad = {
    foo: 3,
    bar: 4,
    "data-blah": 5,
  };

  // sim:
  const good = {
    foo: 3,
    bar: 4,
    "data-blah": 5,
  };
  ```

**[⬆ voltar ao início](#table-of-contents)**

## Arrays/Vetores

<a name="arrays--literals"></a><a name="4.1"></a>

- [4.1](#arrays--literals) Use a notação literal para criar arrays.

  ```javascript
  // não:
  const items = new Array();

  // sim:
  const items = [];
  ```

- [4.2](#es6-array-spreads) Use o spread operator `...` para copiar um array.

      ```javascript
      const itemsCopy = [...items];
      ```

**[⬆ voltar ao início](#table-of-contents)**

## Strings

<a name="strings--quotes"></a><a name="5.1"></a>

- [5.1](#strings--quotes) Use aspas duplas `""` para strings.

  ```javascript
  const name = "Capt. Janeway";
  ```

- [5.2](#es6-template-literals) Use template literal para criar strings sem concatenação.

  ```javascript
  // não:
  function sayHi(name) {
    return "Olá, " + name + "!";
  }

  // sim:
  function sayHi(name) {
    return `Olá, ${name}!`;
  }
  ```

**[⬆ voltar ao início](#table-of-contents)**

## Functions/Funções

<a name="functions--declarations"></a><a name="6.1"></a>

- [6.1](#functions--declarations) Declare as funções dentro de uma variável `const`.

  ```javascript
  // sim:
  const short = function myNewFunction() {
    // ...
  };
  ```

**[⬆ voltar ao início](#table-of-contents)**

## Properties/Propriedades

<a name="properties--dot"></a><a name="7.1"></a>

- [7.1](#properties--dot) Use `.` para acessar propriedades.

  ```javascript
  const luke = {
    jedi: true,
    age: 28,
  };

  // não:
  const isJedi = luke["jedi"];

  // sim:
  const isJedi = luke.jedi;
  ```

- [7.2](#properties--bracket) Use chaves `[]` para acessar propriedades com uma variável.

  ```javascript
  const luke = {
    jedi: true,
    age: 28,
  };

  function getProp(prop) {
    return luke[prop];
  }
  const isJedi = getProp("jedi");
  ```

**[⬆ voltar ao início](#table-of-contents)**

## Comparison Operators & Equality/Operadores de Comparação e Equidade

<a name="comparison--eqeqeq"></a><a name="8.1"></a>

- [8.1](#comparison--eqeqeq) Dê preferência ao uso de `===` e `!==` ao invés de `==` e `!=`.

**[⬆ voltar ao início](#table-of-contents)**

## Comentários

<a name="comments--multiline"></a><a name="9.1"></a>

- [9.1](#comments--multiline) Use `/** ... */` para comentar várias linhas.
- [9.2](#comments--singleline) Use `//` para comentários de uma linha só, sempre na linha acima do que você gostaria de comentar.

  ```javascript
  // não:
  const active = true; // is current tab

  // sim:
  // is current tab
  const active = true;

  // sim:
  function getType() {
    console.log("fetching type...");

    // set the default type to 'no type'
    const type = this.type || "no type";

    return type;
  }
  ```

- [9.3](#comments--spaces) Inicie todos os comentários com um espaço para facilitar a leitura.

  ```javascript
  // não:
  //is current tab
  const active = true;

  // sim:
  // is current tab
  const active = true;
  ```

- [9.4](#comments--actionitems) Use `FIXME` ou `TODO` para ajudar o resto da equipe a identificar mais rápido onde é necessário trabalhar.

- [9.5](#comments--fixme) Use `// FIXME:` para identificar problemas.

  ```javascript
  class Calculator extends Abacus {
    constructor() {
      super();

      // FIXME: não usar variável global aqui
      total = 0;
    }
  }
  ```

- [9.6](#comments--todo) Use `// TODO:` para comentar a solução de um problema.

  ```javascript
  class Calculator extends Abacus {
    constructor() {
      super();

      // TODO: o total deve ser configurado por options param
      this.total = 0;
    }
  }
  ```

**[⬆ voltar ao início](#table-of-contents)**

## Naming Conventions/Nomeação

<a name="naming--descriptive"></a><a name="10.1"></a>

- [10.1](#variaveis-ingles) Utilize inglês preferencialmente.
- [10.2](#naming--descriptive) Evitar nomes não-descritivos.

  ```javascript
  // não:
  function q() {
    // ...
  }

  // sim:
  function query() {
    // ...
  }
  ```

- [10.3](#naming--camelCase) Use camelCase para nomear objects, functions, e instances.

  ```javascript
  // não:
  const OBJEcttsssss = {};
  const this_is_my_object = {};
  function c() {}

  // sim:
  const thisIsMyObject = {};
  function thisIsMyFunction() {}
  ```

- [10.4](#naming--PascalCase) Use PascalCase para nomear constructors e classes.

  ```javascript
  class User {
    constructor(options) {
      this.name = options.name;
    }
  }

  const good = new User({
    name: "João",
  });
  ```

- [10.5](#naming--filename-matches-export) Arquivos devem ter exatamente o mesmo nome do seu default export.

  ```javascript
  import CheckBox from "./CheckBox"; // PascalCase export/import/filename
  import fortyTwo from "./fortyTwo"; // camelCase export/import/filename
  import insideDirectory from "./insideDirectory";
  ```

**[⬆ voltar ao início](#table-of-contents)**

## Git Commits

<a name="git-commits"></a><a name="11.1"></a>

- [11.1](#git-commits) Os commits no github devem ser escritos preferencialmente começando com um verbo no passado.

  ```
  // não:
  git commit -m "adicionando novo server"
  ```

  ```
  // sim:
  git commit -m "Adicionado novo server"
  ```

  **[⬆ voltar ao início](#table-of-contents)**

# };
