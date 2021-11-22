# Uvod u JavaScript

<<<<<<< HEAD
Pogledajmo šta je tako posebno u JavaScriptu, šta možemo postići sa njim i koje druge tehnologije se sa njim dobro 'igraju'.
=======
Let's see what's so special about JavaScript, what we can achieve with it, and what other technologies play well with it.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425

## Šta je JavaScript ?

<<<<<<< HEAD
*JavaScript* je prvobitno kreiran kako bi *"oživio web stranice"*.
=======
*JavaScript* was initially created to "make web pages alive".
>>>>>>> a82915575863d33db6b892087975f84dea6cb425

Programi na ovom jeziku se nazivaju *skripte*. Mogu se napisati pravo u HTML-u veb stranice i pokrenuti automatski kada se stranica učita.

Skripte se pružaju i izvode u obliku običnog teksta. Za pokretanje im nisu potrebne posebne pripreme ili kompilacije.

U ovom aspektu, JavaScript se veoma razlikuje od drugog jezika koji se zove [Java](https://en.wikipedia.org/wiki/Java_(programming_language)).

<<<<<<< HEAD
```smart header="Zašto <u>Java</u>Script?"
Kada je kreiran JavaScript, u početku je imao drugo ime: "LiveScript". Ali Java je u to vreme bila veoma popularna, pa je odlučeno da će pozicioniranje novog jezika Java-ovog „mlađeg brata“
=======
```smart header="Why is it called <u>Java</u>Script?"
When JavaScript was created, it initially had another name: "LiveScript". But Java was very popular at that time, so it was decided that positioning a new language as a "younger brother" of Java would help.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425

Ali kako se razvijao, JavaScript je postao potpuno nezavisan jezik sa sopstvenom specifikacijom [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript), a sada uopšte nema veze sa Javom.
```

Danas JavaScript može da se izvršava ne samo u pregledaču, već i na serveru, ili zapravo na bilo kom uređaju koji ima poseban program koji se zove [the JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine).

Preglednik ima ugrađeni motor koji se ponekad naziva i „JavaScript virtuelna mašina“.

Različite mašine imaju različita "kodna imena". Na primer:

<<<<<<< HEAD
- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- u Chrome-u i Opera.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- u Firefox-u.
- ... Postoje i druga kodna imena poput "Trident" i "Chakra" za različite verzije IE-a, "ChakraCore" za Microsoft Edge, "Nitro" i "SkuirrelFish" za Safari, itd.

Gore navedene pojmove dobro je zapamtiti jer se koriste u člancima za programere na Internetu. Koristićemo i njih. Na primer, ako „odliku X podržava V8“, ona verovatno funkcioniše u Chrome-u i Operi.
=======
- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- in Chrome, Opera and Edge.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- in Firefox.
- ...There are other codenames like "Chakra" for IE, "JavaScriptCore", "Nitro" and "SquirrelFish" for Safari, etc.

The terms above are good to remember because they are used in developer articles on the internet. We'll use them too. For instance, if "a feature X is supported by V8", then it probably works in Chrome, Opera and Edge.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425

```smart header="Kako rade mašine ?"

Motori su komplikovani. Ali osnove su jednostavne.

1. Motor (ugrađen ako je pretraživač) čita („analizira“) skriptu.
2. Zatim pretvara ("kompajlira") skriptu u mašinski jezik.
3. A onda mašinski kod radi prilično brzo.

<<<<<<< HEAD
Motor primenjuje optimizacije na svakom koraku procesa. Čak posmatra sastavljenu skriptu dok radi, analizira podatke koji prolaze kroz nju i primenjuje optimizacije na mašinskom kodu na osnovu tog znanja. Kada je gotov, skripte se pokreću prilično brzo.
=======
The engine applies optimizations at each step of the process. It even watches the compiled script as it runs, analyzes the data that flows through it, and further optimizes the machine code based on that knowledge.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425
```

## Šta JavaScript u internet pretraživaču može da radi?

Savremeni JavaScript je "siguran" programski jezik. Ne pruža pristup memoriji ili CPU-u nižeg nivoa, jer je prvobitno kreiran za pregledače koji to ne zahtevaju.

Mogućnosti JavaScript-a u velikoj meri zavise od okruženja u kome se nalazi. Na primjer [Node.js](https://wikipedia.org/wiki/Node.js) podržava funkcije koje omogućuju JavaScriptu da čita / piše proizvoljne datoteke, izvršava mrežne zahteve itd.

JavaScript u pretraživaču može učiniti sve što se odnosi na manipulaciju web stranicama, interakciju sa korisnikom i web serverom.

Na primer, JavaScript u pregledaču može:

- Dodajte novi HTML na stranicu, promenite postojeći sadržaj, izmenite stilove.
- Reaguje na akcije korisnika, pokretanje određene radnje klikom miša, pokretanje pokazivača, klik na tasteru.
- Slanje zahteva preko mreže udaljenim serverima, preuzimanje i učitavanje datoteka (takozvani [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) i [COMET](https://en.wikipedia.org/wiki/Comet_(programming)) tehnologije).
- Dobijajte i postavljajte kolačiće, postavljajte pitanja posetiocu, pokažite poruke.
- Zapamtite podatke na strani klijenta ("lokalna memorija").

## Šta NE MOŽETE u JavaScript pretraživaču?

<<<<<<< HEAD
Mogućnosti JavaScripta u pretraživaču su ograničene zbog bezbednosti korisnika. Cilj je sprečiti zlo veb stranici da pristupi privatnim podacima ili našteti korisnikovim podacima.
=======
JavaScript's abilities in the browser are limited for the sake of a user's safety. The aim is to prevent an evil webpage from accessing private information or harming the user's data.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425

Primeri takvih ograničenja uključuju:

<<<<<<< HEAD
- JavaScript na veb stranici možda ne može čitati / pisati proizvoljne datoteke na hard disku, kopirati ih ili izvršavati programe. Nema direktan pristup funkcijama sistema OS.
=======
- JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS functions.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425

    Savremeni pregledači omogućavaju mu da radi sa datotekama, ali je pristup ograničen i pruža se samo ako korisnik izvrši određene radnje, poput „puštanja“ datoteke u prozor pregledača ili izbora pomoću „<input>“ taga.

    Postoje načini za interakciju s kamerom / mikrofonom i drugim uređajima, ali za njih je potrebno izričito odobrenje korisnika. Dakle, stranica sa omogućenim JavaScriptom možda ne dozvoljava da večno omogućuju veb kameru, posmatrajte okolinu i šaljite informacije na [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
    
- Različiti tabovi / prozori uglavnom ne znaju jedni o drugima. Ponekad to urade, na primer kada jedan prozor koristi JavaScript da otvori drugi. Ali čak i u ovom slučaju, JavaScript s jedne stranice možda ne može pristupiti drugoj ako dolaze sa različitih veb lokacija (sa drugog domena, protokola ili porta).

    To se naziva „Politika istog porekla“. Da biste to rešili, * obe stranice * moraju se složiti za razmenu podataka i sadržavati poseban JavaScript kod koji njime rukuje. Doći ćemo i do toga tutorijala.

    Ovo ograničenje je, opet, zbog bezbednosti korisnika. Stranica sa `http: // anisite.com` koju je korisnik otvorio ne smije biti u mogućnosti da pristupi drugoj kartici pregledača sa URL-om `http://gmail.com` i krade informacije odatle.
    
- JavaScript može lako da komunicira preko mreže sa serverom odakle je došla trenutna stranica. Ali njegova sposobnost da prima podatke sa drugih lokacija / domena je osakaćena. Iako je moguće, zahteva izričit dogovor (izražen u HTTP zaglavima) sa udaljene strane. Još jednom, to je sigurnosno ograničenje.

![](limitations.svg)

Takva ograničenja ne postoje ako se JavaScript koristi izvan pregledača, na primer na serveru. Savremeni pregledači takođe dozvoljavaju dodatak / proširenja koji mogu tražiti proširenja dozvola.

## Po čemu je JavaScript jedinstven?

Postoje najmanje *tri* sjajne stvari o JavaScript-i :

```compare
<<<<<<< HEAD
+ Potpuna integracija sa HTML-om/CSS-om.
+ Jednostavne stvari se rade jednostavno.
+ Podrška svih glavnih pregledača i omogućena podrazumijevano.
=======
+ Full integration with HTML/CSS.
+ Simple things are done simply.
+ Supported by all major browsers and enabled by default.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425
```
JavaScript je jedina tehnologija pretraživača koja kombinuje ove tri stvari.

To čini JavaScript jedinstvenim. Zato je to najrasprostranjeniji alat za kreiranje interfejsa pretraživača.

Uz to, JavaScript takođe omogućava kreiranje servera, mobilnih aplikacija itd.

## Jezici "preko" JavaScript-e

Sintaksa JavaScript ne odgovara svačijim potrebama. Različiti ljudi žele različite karakteristike.

To je očigledno, jer su projekti i zahtevi za svakoga različiti.

Tako se nedavno pojavila mnoštvo novih jezika koji su * prevedeni * (pretvoreni) u JavaScript pre nego što se pokrenu u pretraživaču.

Savremeni alati čine transpilaciju veoma brzom i preglednom, ustvari omogućavajući programerima da kodiraju na drugom jeziku i automatski ga pretvaraju "pod haubom".

Primeri takvih jezika:

<<<<<<< HEAD
- [CoffeeScript](http://coffeescript.org/) je "sintaktički šećer" za JavaScript. Uvodi kraću sintaksu, omogućavajući nam pisanje jasnijeg i preciznijeg koda. Obično se Ruby programerima sviđa.
- [TypeScript](http://www.typescriptlang.org/) koncentrisana je na dodavanje „strogog unosa podataka“ radi pojednostavljenja razvoja i podrške složenih sistema. Razvio ga je Microsoft.
- [Flow](http://flow.org/) takođe dodaje podatke za unos podataka, ali na drugačiji način. Razvijen od strane Facebook-a.
- [Dart](https://www.dartlang.org/) je samostalan jezik koji ima svoj motor koji radi u okruženjima koja nisu u pretraživaču (poput mobilnih aplikacija), ali takođe se može prevesti u JavaScript. Razvio Google.
=======
- [CoffeeScript](http://coffeescript.org/) is a "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](http://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Flow](http://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.
- [Brython](https://brython.info/) is a Python transpiler to JavaScript that enables the writing of applications in pure Python without JavaScript.
- [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) is a modern, concise and safe programming language that can target the browser or Node.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425

Postoji više. Naravno, čak i ako koristimo jedan od prevedenih jezika, trebalo bi da znamo i JavaScript da bismo zaista razumeli šta radimo.

## Rezime

<<<<<<< HEAD
- JavaScript je u početku kreiran kao jezik samo za pregledač, ali se sada koristi i u mnogim drugim okruženjima.
- Danas JavaScript ima jedinstvenu poziciju kao najšire prihvaćeni jezik pregledača sa potpunom integracijom sa HTML-om / CSS-om.
- Postoji mnogo jezika koji se "prevode" u JavaScript i pružaju određene funkcije. Preporučuje se da ih sagledate, bar na kratko, nakon savladavanja JavaScripta.
=======
- JavaScript was initially created as a browser-only language, but it is now used in many other environments as well.
- Today, JavaScript has a unique position as the most widely-adopted browser language, fully integrated with HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
>>>>>>> a82915575863d33db6b892087975f84dea6cb425
