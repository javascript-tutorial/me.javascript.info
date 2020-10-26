# Varijable

Većinu vremena JavaScript aplikacija treba da radi sa informacijama. Evo dva primjera:
1. Internet shop -- informacije mogu sadržavati robu koja se prodaje i kolica za kupovinu.
2. Aplikaciaj za čatovanje -- informacije mogu obuhvatati korisnike, poruke i još mnogo toga.

Varijable se koriste za čuvanje ovih informacija.

## varijabla

[Varijabla](https://en.wikipedia.org/wiki/Variable_(computer_science)) je "imenovana memorija" za podatke. Možemo da koristimo varijable za čuvanje stvari, posetilaca i drugih podataka.

Da biste kreirali promenljivu u JavaScript, koristi se `let` riječ.

<<<<<<< HEAD
Iskaz ispod kreira varijablu sa imenom "poruka":
=======
The statement below creates (in other words: *declares*) a variable with the name "message":
>>>>>>> 2d5be7b7307b0a4a85e872d229e0cebd2d8563b5

```js
let poruka;
```

Sada možemo u nju ubaciti neke podatke koristeći operatora jednakosti `=`:

```js
let poruka;

*!*
poruka = 'Zdravo'; // čuva string
*/!*
```

String je sada sačuvan u memorijskoj oblasti koja je povezana sa varijablom. Pristupamo mu koristeći naziv varijable:

```js run
let poruka;
poruka = 'Zdravo!';

*!*
alert(poruka); // Prikazuje sadržaj varijable
*/!*
```

Da budemo sažeti, možemo kombinovati deklaraciju varijable i dodeljivanje u jedan red:

```js run
let poruka = 'Zdravo!'; // definišite varijablu i dodijelite vrijednost

alert(poruka); // Zdravo!
```

Takođe možemo deklarisati više varijabli u jednom redu:

```js no-beautify
let korisnik = 'Veljko', godine = 20, poruka = 'Zdravo';
```

To može izgledati kraće, ali ne preporučujemo. Radi bolje čitljivosti, koristite jedan red po varijabli.

višelinijska varijanta je malo duža, ali je lakša za čitanje:

```js
let korisnik = 'Veljko';
let godine = 20;
let poruka = 'Zdravo';
```

Neki ljudi takođe definišu više varijabli u ovom multilinijskom stilu:
```js no-beautify
let korisnik = 'Veljko',
  godine = 20,
  poruka = 'Zdravo';
```

...Ili čak u stilu "zarez-prvi":

```js no-beautify
let korisnik = 'Veljko'
  , godine = 20
  , poruka = 'Zdravo';
```

Tehnički, sve ove varijante rade istu stvar. Dakle, to je stvar ličnog ukusa i estetike.

<<<<<<< HEAD

````smart header="`var` umjesto `let`"
U starijim skriptama možete naći i drugu ključnu reč: `var` umjesto `let`:
=======
````smart header="`var` instead of `let`"
In older scripts, you may also find another keyword: `var` instead of `let`:
>>>>>>> 2d5be7b7307b0a4a85e872d229e0cebd2d8563b5

```js
*!*var*/!* poruka = 'Zdravo';
```

`var` ključna reč je *skoro* isto što i `let`. Takođe deklariše varijablu, ali na nešto drugačiji, „old-school“ način.

Postoje suptilne razlike između `let` i `var`, ali za nas to još uvek nije važno. Detaljno ćemo ih opisati u ovom poglavlju
 <info:var>.
````

## Realna analogija

Pojam „varijable“ lako možemo da shvatimo ako je zamislimo kao „kutiju“ za podatke, sa jedinstveno imenovanom nalepnicom na sebi.

Na primer, varijabla `poruka` može se zamisliti kao okvir s natpisom` `message '' sa sadržajem '' Zdravo! '' u njoj:

![](variable.svg)

U kutiji možemo staviti bilo koji sadržaj.

Takođe ga možemo promeniti onoliko puta koliko želimo:
```js run
let poruka;

poruka = 'Zdravo!';

poruka = 'Svijete!'; // promijenjen sadržaj

alert(poruka);
```

Kada se sadržaj promeni, stari podaci se uklanjaju od varijable:

![](variable-change.svg)

Takođe možemo proglasiti dvije varijable i kopirati podatke iz jedne u drugu.

```js run
let zdravo = 'Zdravo svijete!';

let poruka;

*!*
// kopira 'Zdravo svijete' sa varijable pod imenom 'zdravo' sadržaj u sadržaj
poruka = 'Zdravo svijete';
*/!*

// sada dvije varijable sadrže iste podatke
alert(zdravo); // Zdravo svijete!
alert(poruka); // Zdravo svijete!
```

<<<<<<< HEAD
```smart header="Funkcionalni jezici"
Zanimljivo je primijetiti da postoje [funkcionalni](https://en.wikipedia.org/wiki/Functional_programming) programski jezici, kao [Scala](http://www.scala-lang.org/) ili [Erlang](http://www.erlang.org/) koje zabranjuju promenu vrednosti varijabli.
=======
````warn header="Declaring twice triggers an error"
A variable should be declared only once.

A repeated declaration of the same variable is an error:

```js run
let message = "This";

// repeated 'let' leads to an error
let message = "That"; // SyntaxError: 'message' has already been declared
```
So, we should declare a variable once and then refer to it without `let`.
````

```smart header="Functional languages"
It's interesting to note that there exist [functional](https://en.wikipedia.org/wiki/Functional_programming) programming languages, like [Scala](http://www.scala-lang.org/) or [Erlang](http://www.erlang.org/) that forbid changing variable values.
>>>>>>> 2d5be7b7307b0a4a85e872d229e0cebd2d8563b5

U takvim jezicima, jednom kada se vrijednost čuva „u kutiji“, to je zauvjek. Ako treba da spremimo nešto drugo, jezik nas prisiljava da stvorimo novi okvir (deklarišemo novu varijablu). Ne možemo ponovo da koristimo staru.

Iako na prvi pogled djeluju pomalo čudno, ovi jezici su prilično sposobni za ozbiljan razvoj. Pored toga, postoje oblasti poput paralelnih izračunavanja gde ovo ograničenje daje određene koristi. Proučavanje takvog jezika (čak i ako ga uskoro ne planirate upotrebljavati) preporučuje se za širenje uma.
```

## Imenovanje varijable [#imenovanje-varijable]

Postoje dva ograničenja za imena varijabli u JavaScript-i:

1. Ime mora da sadrži samo slova, cifre ili simbole `$` i `_`.
2. Prvi znak ne smije da bude cifra.

Primeri važećih imena:

```js
let korisničkoIme;
let test123;
```

Kada ime sadrži više riječi, [camelCase](https://en.wikipedia.org/wiki/CamelCase) se obično koristi. Odnosno: riječi idu jedna za drugom, a svaka riječ osim što prvo započinje velikim slovom: `mojePunoIme`.

Šta je zanimljivo -- znak dolar `'$'` i donja crta `'_'` takođe se može koristiti u imenima. Oni su redovni simboli, baš kao i slova, bez posebnog značenja.

Ova imena su validna:

```js run untrusted
let $ = 1; // deklarisana promenljivu sa imenom "$"
let _ = 2; // a sada varijabla sa imenom "_"

alert($ + _); // 3
```

Primeri pogrešnih imena varijabli:

```js no-beautify
let 1a; // ne može početi sa brojem

let moje-ime; // crtice - nisu dozvoljene u imenu
```

```smart header="Slučaj je bitan"
Varijable nazvane `apple` i` AppLE` su dve različite varijable.
```

````smart header="Nelatinična slova su dozvoljena, ali se ne preporučuju"
Moguće je koristiti bilo koji jezik, uključujući ćirilična slova ili čak hijeroglife, poput ovog:

```js
let назив = '...';
let имя = '...';
let 我 = '...';
```

<<<<<<< HEAD
Tehnički, ovde nema greške, takva su imena dozvoljena, ali postoji međunarodna tradicija da se engleski koriste u imenima varijabli. Čak i ako pišemo malu skriptu, pred nama je možda dug život. Ljudi iz drugih zemalja možda će trebati da je pročitaju neko vreme.
=======
Technically, there is no error here. Such names are allowed, but there is an international convention to use English in variable names. Even if we're writing a small script, it may have a long life ahead. People from other countries may need to read it some time.
>>>>>>> 2d5be7b7307b0a4a85e872d229e0cebd2d8563b5
````

````warn header="Rezervisana imena"
Ovđe je [lista rezervisanih imena](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords), koja se ne mogu koristiti kao imena varijabli jer ih koristi sam jezik.

Na primjer: `let`, `class`, `return`, and `function` su rezervisana.

Donji kod daje grešku u sintaksi:

```js run no-beautify
let let = 5; // ne može imenovati varijablu "let", greška!
let return = 5; // takođe se ne može imenovati "return", greška!
```
````

````warn header="Zadatak bez `use strict`"

Obično moramo definisati varijablu prije nego što je koristimo. Ali u starim vremenima tehnički je bilo moguće kreirati varijablu pukim dodeljivanjem vrednosti bez korišćenja „let“. Ovo i dalje funkcioniše ako u svoje skripte ne stavimo „use strict“ za održavanje kompatibilnosti sa starim skriptama.

```js run no-strict
// primijeti: nema "use strict" u ovom primjeru

broj = 5; // varijabla "broj" je kreirana , ako je uopšte nije bilo

alert(broj); // 5
```

Ovo je loša praksa i moglo bi izazvati grešku u strogom režimu:

```js
"use strict";

*!*
broj = 5; // greška: 'broj' nije definisan
*/!*
```
````

## Konstante

Da se deklariše konstantna (nepromjenjiva) varijabla, koristi `const` umjesto `let`:

```js
const mojRođendan = '18.04.1982';
```

<<<<<<< HEAD
Varijable deklarisane pomoću `const` nazivaju se" konstante ". Oni se ne mogu promeniti. Pokušaj da to učinite izazvao bi grešku:
=======
Variables declared using `const` are called "constants". They cannot be reassigned. An attempt to do so would cause an error:
>>>>>>> 2d5be7b7307b0a4a85e872d229e0cebd2d8563b5

```js run
const mojRođendan = '18.04.1982';

mojRođendan = '01.01.2001'; // greška, ne može ponovo dodeliti konstantu!
```

Kada je programer siguran da se varijabla nikada neće promeniti, oni to mogu proglasiti „const“ kako bi garantovali i jasno preneli tu činjenicu svima.



### Konstante sa velikim slovima

Postoji raširena praksa da se konstante koriste kao pseudonimi za teško pamtljive vrednosti koje su poznate prije izvršenja.

Takve konstante su imenovane velikim slovima i donjim crtama.

Na primer, napravimo konstante za boje u takozvanom "web" (heksadecimalnom) formatu:

```js run
const BOJA_CRVENA = "#F00";
const BOJA_ZELENA = "#0F0";
const BOJA_PLAVA = "#00F";
const BOJA_NARANDŽASTA = "#FF7F00";

// ...kada trebamo odabrati boju
let boja = BOJA_NARANDŽASTA;
alert(boja); // #FF7F00
```

Benefiti:

- `BOJA_NARANDŽASTA` mnogo je lakše zapamtiti nego `"#FF7F00"`.
- Mnogo je lakše pogrešno uneti tekst `"#FF7F00"` nego `COLOR_ORANGE`.
- Kada čitate kod, `BOJA_NARANDŽASTA` mnogo je značajnija od `#FF7F00`.

Kada trebamo stalno upotrebljavati velika slova i kada to treba normalno imenovati? Da razjasnimo.

Biti „konstanta“ samo znači da se vrednost varijable nikada ne menja. Ali postoje konstante koje su poznate prije izvršenja (poput heksadecimalne vrednosti za crveno) i postoje konstante koje se *izračunavaju* u toku rada, za vreme izvršenja, ali se ne menjaju nakon početnog podešavanja.

Na primjer:
```js
const vrijemeUčitavanjaStranice = /* vreme koje je stranica uzela za učitavanje */;
```

Vrijednost `vrijemeUčitavanjaStranice` nije poznato prije učitavanja stranice, pa se normalno naziva. Ali to je i dalje konstanta jer se nakon zadatka ne mijenja.

Drugim rečima, konstante sa velikim slovima koriste se samo kao pseudonimi za "teško kodirane" vrednosti. 

## Imenujte stvari kako treba

Kada govorimo o varijablama, postoji još jedna izuzetno važna stvar.

<<<<<<< HEAD
Ime varijable trebalo bi da ima čisto, očigledno značenje, opisuje podatke koje pohranjuje.
=======
A variable name should have a clean, obvious meaning, describing the data that it stores.
>>>>>>> 2d5be7b7307b0a4a85e872d229e0cebd2d8563b5

Imenovanje varijable je jedna od najvažnijih i najkompleksnijih vještina u programiranju. Brzi pogled na imena varijabli može otkriti koji je kod napisao početnik nasuprot iskusnom programeru.

U stvarnom projektu se najviše vremena provodi na modifikovanju i proširivanju postojeće baze koda, a ne na pisanje nečega potpuno odvojenog od nule. Kada se vratimo na neki kod nakon što neko vreme uradimo nešto drugo, mnogo je lakše pronaći informacije koje su dobro označene. Ili drugim rečima kada varijable imaju dobra imena.

Molimo vas da potrošite vreme razmišljajući o pravom imenu varijable prije nego što je proglasite. Ako to učinite, lepo će vam se plaćati.

Nekoliko dobrih pravila su:

- Koristite razumljiva imena kao što su `korisničkoIme` or `šopingKolica`.
- Držite se dalje od skraćenica ili kratkim imenima poput "a", "b", "c", osim ako zaista ne znate šta radite.
- Napravite imena maksimalno opisna i sažetka. Primeri loših imena su „podaci“ i „vrednost“. Takva imena ne govore ništa. Koristite ih samo ako kontekst koda čini izuzetno očiglednim na koje se podatke ili vrednosti odnosi varijabla.
- Dogovorite se oko uslova svog tima i po sopstvenom umu. Ako se posetilac web lokacije naziva "korisnik", trebalo bi da imenujemo srodne varijable "trenutniKorisnik" ili "noviKorisnik" umesto "trenutniPosjetilac" ili "noviUGradu".

Zvuči jednostavno? Zaista jeste, ali stvaranje opisnih i sažetih imena varijabli u praksi nije. Samo napred.

```smart header="Iskoristi ponovo ili napravi novu?"
I poslednja bilješka. Postoje neki lijeni programeri, koji umesto da deklarišu nove varijable, imaju tendenciju da ponovo koriste postojeće.

Kao rezultat toga, njihove varijable su poput kutija u koje ljudi bacaju različite stvari bez menjanja nalepnica. Šta je sada u kutiji? Ko zna? Moramo se približiti i provjeriti.

Takvi programeri štede malo na deklaraciji varijable, ali gube deset puta više na uklanjanju pogrešaka.

Dodatna varijabla je dobro, a ne zlo.

Savremeni JavaScript minifieri i pregledači dovoljno optimizuju kod, tako da neće stvarati probleme sa performansama. Korištenje različitih varijabli za različite vrijednosti može čak pomoći motoru da optimizira vaš kod.
```

## Rezime

Možemo deklarisati varijable za čuvanje podataka koristeći ključne reči `var`,` let` ili `const`.

- `let` -- je moderna deklaracija varijable.
- `var` -- je deklaracija promenljive u staroj školi. Obično ga uopšte ne koristimo, ali pokrit ćemo suptilne razlike od „let“ u poglavlju <info: var>, samo u slučaju da su vam potrebni.
- `const` -- je kao `let`, ali vrednost varijable se ne može promeniti.

Varijable bi trebalo da budu imenovane na način koji nam omogućava da lako razumijemo šta se nalazi unutar njih.
