# Tipovi podataka

Varijabla u JavaScript-i može da sadrži bilo koje podatke. Varijabla u jednom trenutku može biti string, a u drugom broj:

```js
// nema greške
let message = "hello";
message = 123456;
```

Programski jezici koji dopuštaju takve stvari nazivaju se „dinamički kucano“, što znači da postoje tipovi podataka, ali varijable nisu vezane ni za jedan od njih.

Postoji sedam osnovnih tipova podataka u JavaScript-u. Ovde ćemo ih pokriti generalno, a u narednim ćemo poglavljima detaljno govoriti o svakom od njih.

## Broj

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

## String

String u JavaScript moraju biti između znakova navodnika.

```js
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed ${str}`;
```

U JavaScript, postoje 3 vrste navodnika.

1. Dupli navodnici: `"Hello"`.
2. Pojedinačni navodnici: `'Hello'`.
3. Zatvoreni jendostruki navodnik: <code>&#96;Hello&#96;</code>.

Dupli i pojedinačni navodnici su "jednostavni" citati. Nema razlike među njima u JavaScript-u.

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

```smart header="Nema tip *karaktera*."
U nekim jezicima postoji poseban tip „karaktera“ za jedan karakter. Na primjer, na jeziku C i na Javi to je `char`.

U JavaScript-u ne postoji takva vrsta. Postoji samo jedna vrsta: `string`. String se može sastojati od samo jednog znaka ili više njih.
```

## Boolean (logički tip podatka)

Boolean tip podatka ima samo dvije vrijednosti: `true` i `false`.

Ovaj tip podatka se najčešće koristi da čuva da/ne vrijednosti: `true` znači "da, tačno", a `false` znači "ne, netačno".

Na primjer:

```js
let nameFieldChecked = true; // da, polje za ime je čekirano
let ageFieldChecked = false; // ne, polje za godine nije čekirano
```

Boolean vrijednosti takođe dolaze kao rezultat poređenja:

```js run
let isGreater = 4 > 1;

alert( isGreater ); // true (rezultat poređenja je "da")
```

Boolean ćemo raditi detaljnije u poglavlju <info:logical-operators>.

## "null" vrijednost

Specijalna vrijednost `null` ne pripada niti jednom tipu koje je gore opisan.

Formirati se posebni tip koji sadrži samo `null` vrijednost:

```js
let age = null;
```

Kod JavaScript-a, `null` nije "referenca na nepostojeći objekat" ili "null pokazivač" kao u nekim drugim programskim jezicima.

To je samo specijalna vrijednost koja predstavlja "ništa", "prazno" ili "nepoznatu vrijednost".

Gornji kod navodi da je varijabla `age` nepoznata ili prazna iz nekog razloga.

## "undefined" vrijednost

Specijalna vrijednost `undefined` se takođe nezavisno razmatra. Sama po sebi je tip, isto kao `null`.

Značenje `undefined` je "vrijednost nije dodijeljena".

Ako je varijabla deklarisana, ali joj vrijednost nije dodijeljena, onda je vrijednost te varijable `undefined`:

```js run
let x;

alert(x); // prikazuje "undefined"
```

Tehnički, moguće je dodijeliti `undefined` bilo kojoj varijabli:

```js run
let x = 123;

x = undefined;

alert(x); // "undefined"
```

...Ali to nije preporučljivo da se radi. Najčešće, koristimo `null` da dodijelimo "praznu" ili "nepoznatu" vrijednost varijabli, a `undefined` koristimo za provjeru da li je vrijednsot nekoj varijabli dodijeljena.

## Objekti i Simboli and Symbols

Tip `object` je specijalni tip.

Svi ostali tipovi se zovu "primitivni" zbog toga što su vrijednosti kod tih tipova sadrže samo jednu stvar (bio to string ili broj ili štagod). U kontrastu, objekti se koriste da čuvaju kolekciju podataka i kompleksije entitete. Njima ćemo se baviti kasnije u poglavlju <info:object> nakok što naučimo nešto više o primitivnim tipovima podataka.

Tip `symbol` se koristi za kreiranje jedinstvenih identifikatora za objekte. Ovdje ga spominjemo radi cjelovitosti, ali ćemo ga proučiti nakon objekata.

## Operator typeof [#type-typeof]

Operator `typeof` vraća tip argumenta. Korisno je kada želimo različito obraditi vrijednosti različitih tipova podataka ili samo želimo napraviti brzu provjeru.

Podržana su dva oblika sintakse:

1. Kao operator: `typeof x`.
2. Kao funkcija: `typeof(x)`.

Drugim riječima, radi sa zagradama ili bez zagrada. Rezultat je isti.

Poziv `typeof x` vraća string sa nazivom tipa:

```js
typeof undefined // "undefined"

typeof 0 // "number"

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

Poslednje tri linije možda trebaju dodatno objašnjenje:

1. `Math` je ugrađeni (built-in) objekat koji omogućava matematičke operacije. Učićemo o njemu u poglavlju <info:number>. Ovdje, služi samo kao primjer za objekte.
2. Rezultat `typeof null` je `"object"`. Ovo je pogrešno. Zvanično ovo predstavlja grešku za `typeof`, ali se ovako čuva radi kompatibilnosti. Naravno, `null` nije objekat. To je specijalna vrijednost sa posebnim vlastitim tipom. Ponovo da napomenemo, ovo je greška u jeziku.
3. Rezultat `typeof alert` je `"function"`, jer `alert` jeste funcika. O funkcijama ćemo učiti u narednom poglavlju gdje ćemo isto vidjeti da ne postoji specijalni tip "function" u JavaScript-u. Funkcije pripradaju tipu object. Ali `typeof` ih tretira drugačije, vraćajući `"function"`. Ovo nije sasvim ispravno, ali je vrlo zgodno u praksi.


## Sažetak

Postoji 7 osnovnih tipova podataka kod JavaScript-a.

- `number` za bilo kakve brojeve: cijele ili floating-point.
- `string` za strings. String može da sadrži jedan ili više karatkera, ne postoji poseban tip za stringove koji imaju jedan karakter.
- `boolean` za `true`/`false`.
- `null` za nepoznate vrijednost -- zasebni tip koji ima samo jednu vrijednost `null`.
- `undefined` za nedodijeljene vrijednosti -- zasebni tip koji ima samo jednu vrijednost `undefined`.
- `object` za kompleksije strukture podataka.
- `symbol` za jedinstvene identifikatore.

Oeprator `typeof` omogućava da vidimo koji tip vrijednosti se čuva u varijabli.

- Dvije forme: `typeof x` ili `typeof(x)`.
- Vraća naziv tipa, npr. `"string"`.
- Za `null` vraća `"object"` -- ovo je greška u jeziku, u stvari i nije objekat.
U narednim poglavljima, koncentrisaćemo se na primitivne vrijednosti i kada ih dovoljno upoznamo, preći ćemo na objekte.
