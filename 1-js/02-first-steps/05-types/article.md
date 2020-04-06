# Tipovi podataka

Varijabla u JavaScript-i može da sadrži bilo koje podatke. Varijabla u jednom trenutku može biti string, a u drugom broj:

```js
// nema greške
let message = "hello";
message = 123456;
```

Programski jezici koji dopuštaju takve stvari nazivaju se „dinamički kucano“, što znači da postoje tipovi podataka, ali varijable nisu vezane ni za jedan od njih.

<<<<<<< HEAD
Postoji sedam osnovnih tipova podataka u JavaScript-u. Ovde ćemo ih pokriti generalno, a u narednim ćemo poglavljima detaljno govoriti o svakom od njih.

## Broj
=======
There are eight basic data types in JavaScript. Here, we'll cover them in general and in the next chapters we'll talk about each of them in detail.

## Number
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

```js
let n = 123;
n = 12.345;
```

Tip *broj* predstavlja brojeve i brojeve sa pomičnim zarezom.

Postoji mnogo operacija za brojeve, npr. množenje `*`, dijeljenje `/`, sabiranje `+`, oduzimanje `-`, itd.

Pored regularnih brojeva, postoje i takozvane "posebne numeričke vrednosti" koje takođe pripadaju ovom tipu podataka: `Infinity`, `-Infinity` i `NaN`.

- `Infinity` predstavlja matematičku [beskonačnost](https://en.wikipedia.org/wiki/Infinity) ∞. To je posebna vrednost veća od bilo kog broja.

    To možemo dobiti kao rezultat podjele na nulu:

    ```js run
    alert( 1 / 0 ); // Infinity
    ```

    Ili direktnim navođenjem:

    ```js run
    alert( Infinity ); // Infinity
    ```
- `NaN` predstavlja grešku u računanju. Na primjer, rezultat je pogrešne ili nedefinisane matematičke operacije:

    ```js run
    alert( "not a number" / 2 ); // NaN, such division is erroneous
    ```

    `NaN` je ljepljiv. Svako sledeća operacija na `NaN` vraća `NaN`:

    ```js run
    alert( "not a number" / 2 + 5 ); // NaN
    ```

    Dakle, ako negde u matematičkom izrazu postoji `NaN`, on se širi ka celokupnom rezultatu.

```smart header="Matematičke operacije su sigurne"
Bavljenje matematikom je u JavaScriptu sigurno. Možemo učiniti bilo šta: podeliti na nulu, tretirati ne numeričke nizove kao brojeve itd.

Skripta nikada neće prestati sa fatalnom greškom ("umreti"). U najgorem slučaju dobićemo `NaN` kao rezultat.
```

Posebne numeričke vrednosti formalno pripadaju vrsti „broj“. Naravno da to nisu brojevi u zdravom smislu ove reči.

Više ćemo videti o radu sa brojevima u ovom poglavlju <info:number>.

<<<<<<< HEAD
=======
## BigInt

In JavaScript, the "number" type cannot represent integer values larger than <code>2<sup>53</sup></code> (or less than <code>-2<sup>53</sup></code> for negatives), that's a technical limitation caused by their internal representation. That's about 16 decimal digits, so for most purposes the limitation isn't a problem, but sometimes we need really big numbers, e.g. for cryptography or microsecond-precision timestamps.

`BigInt` type was recently added to the language to represent integers of arbitrary length.

A `BigInt` is created by appending `n` to the end of an integer literal:

```js
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```

As `BigInt` numbers are rarely needed, we devoted them a separate chapter <info:bigint>.

```smart header="Compatability issues"
Right now `BigInt` is supported in Firefox and Chrome, but not in Safari/IE/Edge.
```

>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622
## String

String u JavaScript moraju biti između znakova navodnika.

```js
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```

U JavaScript, postoje 3 vrste navodnika.

1. Dupli navodnici: `"Hello"`.
2. Pojedinačni navodnici: `'Hello'`.
3. Zatvoreni jendostruki navodnik: <code>&#96;Hello&#96;</code>.

<<<<<<< HEAD
Dupli i pojedinačni navodnici su "jednostavni" citati. Nema razlike među njima u JavaScript-u.
=======
Double and single quotes are "simple" quotes. There's practically no difference between them in JavaScript.
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

Zatvoreni jednostruki navodnici su navodnici "proširene funkcionalnosti". Omogućuju nam da uklopimo varijable i izraze u niz omotajući ih, na primer, „$ {…}“

```js run
let name = "John";

// embed a variable
alert( `Hello, *!*${name}*/!*!` ); // Hello, John!

// embed an expression
alert( `the result is *!*${1 + 2}*/!*` ); // the result is 3
```

Ekspresija unutar `$ {...}` se procjenjuje i rezultat postaje deo niza. Tamo možemo staviti bilo šta: varijablu poput „name“ ili aritmetički izraz poput „1 + 2“ ili nešto složenije.

Imajte na umu da se to može učiniti samo jednostrukom navodnicima. Ostale ponude nemaju ovu funkciju ugradnje!
```js run
alert( "Rezultat je ${1 + 2}" ); // Rezultat je ${1 + 2} (Dupli navodnici ne rade ništa)
```

Detaljnije ćemo prikazati stringove u ovom poglavlju <info:string>.

<<<<<<< HEAD
```smart header="Nema tip *karaktera*."
U nekim jezicima postoji poseban tip „karaktera“ za jedan karakter. Na primjer, na jeziku C i na Javi to je `char`.
=======
```smart header="There is no *character* type."
In some languages, there is a special "character" type for a single character. For example, in the C language and in Java it is called "char".
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

U JavaScript-u ne postoji takva vrsta. Postoji samo jedna vrsta: `string`. String se može sastojati od samo jednog znaka ili više njih.
```

## Boolean (logical type)

The boolean type has only two values: `true` and `false`.

This type is commonly used to store yes/no values: `true` means "yes, correct", and `false` means "no, incorrect".

For instance:

```js
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
```

Boolean values also come as a result of comparisons:

```js run
let isGreater = 4 > 1;

alert( isGreater ); // true (the comparison result is "yes")
```

We'll cover booleans more deeply in the chapter <info:logical-operators>.

## The "null" value

The special `null` value does not belong to any of the types described above.

It forms a separate type of its own which contains only the `null` value:

```js
let age = null;
```

In JavaScript, `null` is not a "reference to a non-existing object" or a "null pointer" like in some other languages.

It's just a special value which represents "nothing", "empty" or "value unknown".

The code above states that `age` is unknown or empty for some reason.

## The "undefined" value

The special value `undefined` also stands apart. It makes a type of its own, just like `null`.

The meaning of `undefined` is "value is not assigned".

If a variable is declared, but not assigned, then its value is `undefined`:

```js run
let x;

alert(x); // shows "undefined"
```

Technically, it is possible to assign `undefined` to any variable:

```js run
let x = 123;

x = undefined;

alert(x); // "undefined"
```

...But we don't recommend doing that. Normally, we use `null` to assign an "empty" or "unknown" value to a variable, and we use `undefined` for checks like seeing if a variable has been assigned.

## Objects and Symbols

The `object` type is special.

All other types are called "primitive" because their values can contain only a single thing (be it a string or a number or whatever). In contrast, objects are used to store collections of data and more complex entities. We'll deal with them later in the chapter <info:object> after we learn more about primitives.

The `symbol` type is used to create unique identifiers for objects. We mention it here for completeness, but we'll study it after objects.

## The typeof operator [#type-typeof]

The `typeof` operator returns the type of the argument. It's useful when we want to process values of different types differently or just want to do a quick check.

It supports two forms of syntax:

1. As an operator: `typeof x`.
2. As a function: `typeof(x)`.

In other words, it works with parentheses or without them. The result is the same.

The call to `typeof x` returns a string with the type name:

```js
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

*!*
typeof Math // "object"  (1)
*/!*

*!*
typeof null // "object"  (2)
*/!*

*!*
typeof alert // "function"  (3)
*/!*
```

The last three lines may need additional explanation:

1. `Math` is a built-in object that provides mathematical operations. We will learn it in the chapter <info:number>. Here, it serves just as an example of an object.
2. The result of `typeof null` is `"object"`. That's wrong. It is an officially recognized error in `typeof`, kept for compatibility. Of course, `null` is not an object. It is a special value with a separate type of its own. So, again, this is an error in the language.
3. The result of `typeof alert` is `"function"`, because `alert` is a function. We'll study functions in the next chapters where we'll also see that there's no special "function" type in JavaScript. Functions belong to the object type. But `typeof` treats them differently, returning `"function"`. That's not quite correct, but very convenient in practice.

## Summary

There are 8 basic data types in JavaScript.

- `number` for numbers of any kind: integer or floating-point, integers are limited by ±2<sup>53</sup>.
- `bigint` is for integer numbers of arbitrary length.
- `string` for strings. A string may have one or more characters, there's no separate single-character type.
- `boolean` for `true`/`false`.
- `null` for unknown values -- a standalone type that has a single value `null`.
- `undefined` for unassigned values -- a standalone type that has a single value `undefined`.
- `object` for more complex data structures.
- `symbol` for unique identifiers.

The `typeof` operator allows us to see which type is stored in a variable.

- Two forms: `typeof x` or `typeof(x)`.
- Returns a string with the name of the type, like `"string"`.
- For `null` returns `"object"` -- this is an error in the language, it's not actually an object.

In the next chapters, we'll concentrate on primitive values and once we're familiar with them, we'll move on to objects.
