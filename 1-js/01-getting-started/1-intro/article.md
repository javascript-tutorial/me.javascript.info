# Uvod u JavaScript

<<<<<<< HEAD
Pogledajmo šta je tako posebno u JavaScriptu, šta možemo postići sa njim i koje druge tehnologije se sa njim dobro 'igraju'.
=======
Let's see what's so special about JavaScript, what we can achieve with it, and what other technologies play well with it.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

## Šta je JavaScript ?

<<<<<<< HEAD
*JavaScript* je prvobitno kreiran kako bi *"oživio web stranice"*.
=======
*JavaScript* was initially created to "make web pages alive".
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

Programi na ovom jeziku se nazivaju *skripte*. Mogu se napisati pravo u HTML-u veb stranice i pokrenuti automatski kada se stranica učita.

Skripte se pružaju i izvode u obliku običnog teksta. Za pokretanje im nisu potrebne posebne pripreme ili kompilacije.

U ovom aspektu, JavaScript se veoma razlikuje od drugog jezika koji se zove [Java](https://en.wikipedia.org/wiki/Java_(programming_language)).

<<<<<<< HEAD
```smart header="Zašto <u>Java</u>Script?"
Kada je kreiran JavaScript, u početku je imao drugo ime: "LiveScript". Ali Java je u to vreme bila veoma popularna, pa je odlučeno da će pozicioniranje novog jezika Java-ovog „mlađeg brata“
=======
```smart header="Why is it called <u>Java</u>Script?"
When JavaScript was created, it initially had another name: "LiveScript". But Java was very popular at that time, so it was decided that positioning a new language as a "younger brother" of Java would help.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

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
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

```smart header="Kako rade mašine ?"

Motori su komplikovani. Ali osnove su jednostavne.

<<<<<<< HEAD
1. Motor (ugrađen ako je pretraživač) čita („analizira“) skriptu.
2. Zatim pretvara ("kompajlira") skriptu u mašinski jezik.
3. A onda mašinski kod radi prilično brzo.

Motor primenjuje optimizacije na svakom koraku procesa. Čak posmatra sastavljenu skriptu dok radi, analizira podatke koji prolaze kroz nju i primenjuje optimizacije na mašinskom kodu na osnovu tog znanja. Kada je gotov, skripte se pokreću prilično brzo.
=======
1. The engine (embedded if it's a browser) reads ("parses") the script.
2. Then it converts ("compiles") the script to machine code.
3. And then the machine code runs, pretty fast.

The engine applies optimizations at each step of the process. It even watches the compiled script as it runs, analyzes the data that flows through it, and further optimizes the machine code based on that knowledge.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e
```

## Šta JavaScript u internet pretraživaču može da radi?

<<<<<<< HEAD
Savremeni JavaScript je "siguran" programski jezik. Ne pruža pristup memoriji ili CPU-u nižeg nivoa, jer je prvobitno kreiran za pregledače koji to ne zahtevaju.
=======
Modern JavaScript is a "safe" programming language. It does not provide low-level access to memory or the CPU, because it was initially created for browsers which do not require it.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

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
JavaScript's abilities in the browser are limited to protect the user's safety. The aim is to prevent an evil webpage from accessing private information or harming the user's data.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

Primeri takvih ograničenja uključuju:

<<<<<<< HEAD
- JavaScript na veb stranici možda ne može čitati / pisati proizvoljne datoteke na hard disku, kopirati ih ili izvršavati programe. Nema direktan pristup funkcijama sistema OS.
=======
- JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS functions.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

    Savremeni pregledači omogućavaju mu da radi sa datotekama, ali je pristup ograničen i pruža se samo ako korisnik izvrši određene radnje, poput „puštanja“ datoteke u prozor pregledača ili izbora pomoću „<input>“ taga.

<<<<<<< HEAD
    Postoje načini za interakciju s kamerom / mikrofonom i drugim uređajima, ali za njih je potrebno izričito odobrenje korisnika. Dakle, stranica sa omogućenim JavaScriptom možda ne dozvoljava da večno omogućuju veb kameru, posmatrajte okolinu i šaljite informacije na [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
    
- Različiti tabovi / prozori uglavnom ne znaju jedni o drugima. Ponekad to urade, na primer kada jedan prozor koristi JavaScript da otvori drugi. Ali čak i u ovom slučaju, JavaScript s jedne stranice možda ne može pristupiti drugoj ako dolaze sa različitih veb lokacija (sa drugog domena, protokola ili porta).

    To se naziva „Politika istog porekla“. Da biste to rešili, * obe stranice * moraju se složiti za razmenu podataka i sadržavati poseban JavaScript kod koji njime rukuje. Doći ćemo i do toga tutorijala.

    Ovo ograničenje je, opet, zbog bezbednosti korisnika. Stranica sa `http: // anisite.com` koju je korisnik otvorio ne smije biti u mogućnosti da pristupi drugoj kartici pregledača sa URL-om `http://gmail.com` i krade informacije odatle.
    
- JavaScript može lako da komunicira preko mreže sa serverom odakle je došla trenutna stranica. Ali njegova sposobnost da prima podatke sa drugih lokacija / domena je osakaćena. Iako je moguće, zahteva izričit dogovor (izražen u HTTP zaglavima) sa udaljene strane. Još jednom, to je sigurnosno ograničenje.

![](limitations.svg)

Takva ograničenja ne postoje ako se JavaScript koristi izvan pregledača, na primer na serveru. Savremeni pregledači takođe dozvoljavaju dodatak / proširenja koji mogu tražiti proširenja dozvola.
=======
    There are ways to interact with the camera/microphone and other devices, but they require a user's explicit permission. So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
- Different tabs/windows generally do not know about each other. Sometimes they do, for example when one window uses JavaScript to open the other one. But even in this case, JavaScript from one page may not access the other page if they come from different sites (from a different domain, protocol or port).

    This is called the "Same Origin Policy". To work around that, *both pages* must agree for data exchange and must contain special JavaScript code that handles it. We'll cover that in the tutorial.

    This limitation is, again, for the user's safety. A page from `http://anysite.com` which a user has opened must not be able to access another browser tab with the URL `http://gmail.com`, for example, and steal information from there.
- JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is severely limited. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that's a safety limitation.

![](limitations.svg)

Such limitations do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugins/extensions which may ask for extended permissions.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

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
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e
```
JavaScript je jedina tehnologija pretraživača koja kombinuje ove tri stvari.

To čini JavaScript jedinstvenim. Zato je to najrasprostranjeniji alat za kreiranje interfejsa pretraživača.

<<<<<<< HEAD
Uz to, JavaScript takođe omogućava kreiranje servera, mobilnih aplikacija itd.
=======
That said, JavaScript can be used to create servers, mobile applications, etc.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

## Jezici "preko" JavaScript-e

Sintaksa JavaScript ne odgovara svačijim potrebama. Različiti ljudi žele različite karakteristike.

To je očigledno, jer su projekti i zahtevi za svakoga različiti.

<<<<<<< HEAD
Tako se nedavno pojavila mnoštvo novih jezika koji su * prevedeni * (pretvoreni) u JavaScript pre nego što se pokrenu u pretraživaču.
=======
So, recently a plethora of new languages appeared, which are *transpiled* (converted) to JavaScript before they run in the browser.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

Savremeni alati čine transpilaciju veoma brzom i preglednom, ustvari omogućavajući programerima da kodiraju na drugom jeziku i automatski ga pretvaraju "pod haubom".

Primeri takvih jezika:

<<<<<<< HEAD
- [CoffeeScript](http://coffeescript.org/) je "sintaktički šećer" za JavaScript. Uvodi kraću sintaksu, omogućavajući nam pisanje jasnijeg i preciznijeg koda. Obično se Ruby programerima sviđa.
- [TypeScript](http://www.typescriptlang.org/) koncentrisana je na dodavanje „strogog unosa podataka“ radi pojednostavljenja razvoja i podrške složenih sistema. Razvio ga je Microsoft.
- [Flow](http://flow.org/) takođe dodaje podatke za unos podataka, ali na drugačiji način. Razvijen od strane Facebook-a.
- [Dart](https://www.dartlang.org/) je samostalan jezik koji ima svoj motor koji radi u okruženjima koja nisu u pretraživaču (poput mobilnih aplikacija), ali takođe se može prevesti u JavaScript. Razvio Google.

Postoji više. Naravno, čak i ako koristimo jedan od prevedenih jezika, trebalo bi da znamo i JavaScript da bismo zaista razumeli šta radimo.
=======
- [CoffeeScript](https://coffeescript.org/) is "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](https://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Flow](https://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.
- [Brython](https://brython.info/) is a Python transpiler to JavaScript that enables the writing of applications in pure Python without JavaScript.
- [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) is a modern, concise and safe programming language that can target the browser or Node.

There are more. Of course, even if we use one of these transpiled languages, we should also know JavaScript to really understand what we're doing.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e

## Rezime

<<<<<<< HEAD
- JavaScript je u početku kreiran kao jezik samo za pregledač, ali se sada koristi i u mnogim drugim okruženjima.
- Danas JavaScript ima jedinstvenu poziciju kao najšire prihvaćeni jezik pregledača sa potpunom integracijom sa HTML-om / CSS-om.
- Postoji mnogo jezika koji se "prevode" u JavaScript i pružaju određene funkcije. Preporučuje se da ih sagledate, bar na kratko, nakon savladavanja JavaScripta.
=======
- JavaScript was initially created as a browser-only language, but it is now used in many other environments as well.
- Today, JavaScript has a unique position as the most widely-adopted browser language, fully integrated with HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
>>>>>>> 725653fd99b19d42195e837ac3bb23c1784f8f6e
