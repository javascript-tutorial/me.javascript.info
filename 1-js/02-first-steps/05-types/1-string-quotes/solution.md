
Navodnici dodaju izraz koji se nalazi između `${...}` u izraz.

```js run
let name = "Ilya";

// izraz je broj 1
alert( `hello ${1}` ); // hello 1

// izraz je string "name"
alert( `hello ${"name"}` ); // hello name

// izraz je varijabla, dodaj je
alert( `hello ${name}` ); // hello Ilya
```
