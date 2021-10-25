# Savremeni mod, "use strict"

Dugo vremena je JavaScript evoluirao bez problema sa kompatibilnošću. Jeziku su dodate nove funkcije dok se stara funkcionalnost nije promenila.

To je imalo koristi od toga što nikada nije prekršilo postojeći kod. Ali, nedostatak je bio da se bilo kakva greška ili nesavršena odluka koju su doneli JavaScript kreatori zauvek zaglavi u jeziku.

Tako je bilo sve do 2009. godine kada se pojavio ECMAScript 5 (ES5). Jeziku je dodao nove funkcije i modifikovao neke od postojećih. Da bi stari kod radio, većina takvih modifikacija je podrazumevano isključena. Morate ih izričito omogućiti posebnom direktivom: `"use strict"`.

## "use strict"

Direktiva izgleda kao string: `"use strict"` ili `'use strict'`. Kada se nalazi na vrhu skripte, ceo skript deluje na "moderan" način.

Na primjer:

```js
"use strict";

// ovaj kod deluje na savremen način
...
```

<<<<<<< HEAD
Uskoro ćemo naučiti funkcije (način za grupisanje komandi). Gledajući napred, uzmimo to u obzir `"use strict"` može se staviti na početak tela funkcije umesto celog skripta. To omogućava strogi režim samo u toj funkciji. Ali obično ga ljudi koriste za cijelu skriptu.

=======
Quite soon we're going to learn functions (a way to group commands), so let's note in advance that `"use strict"` can be put at the beginning of a function. Doing that enables strict mode in that function only. But usually people use it for the whole script.
>>>>>>> 3699f73b4ccb2a57ac5ef990d2687bf31ccf564c

````warn header="Obezbijedi da je \"use strict\" na vrhu"
Obavezno proverite da li se „use strict“ nalazi na vrhu vaše skripte, jer u suprotnom strogi režim možda neće biti omogućen.


Strogi režim ovde nije omogućen:

```js no-strict
alert("neki kod");
// "use strict" ispod se ignoriše-- mora biti na vrhu

"use strict";

// strogi režim nije omogućen
```

Gore se mogu pojaviti samo komentari `"use strict"`.
````

```warn header="Nema načina da otkažete `use strict`"
Ne postoji takva direktiva `"no use strict"` koja vraća motor na staro ponašanje.

<<<<<<< HEAD
Jednom kada uđemo u strogi režim, nema povratka.
=======
Once we enter strict mode, there's no going back.
>>>>>>> 3699f73b4ccb2a57ac5ef990d2687bf31ccf564c
```

## Konzola pregledača

<<<<<<< HEAD
Kada za testiranje funkcija koristite konzolu pregledača za ubuduće, imajte na umu da to nema `use strict` podrazumijevano.
=======
When you use a [developer console](info:devtools) to run code, please note that it doesn't `use strict` by default.
>>>>>>> 3699f73b4ccb2a57ac5ef990d2687bf31ccf564c

Ponekad, kada `use strict` čini razliku, dobićete pogrešne rezultate.

<<<<<<< HEAD
Možete da pokušate da pritisnete `taster:Shift+Enter` da unesete više redova i stavite „use strict“ na vrh, ovako:
=======
So, how to actually `use strict` in the console?

First, you can try to press `key:Shift+Enter` to input multiple lines, and put `use strict` on top, like this:
>>>>>>> 3699f73b4ccb2a57ac5ef990d2687bf31ccf564c

```js
'use strict'; <Shift+Enter za novi red>
//  ...tvoj kod
<Enter za pokretanje>
```

Radi u većini pregledača, naime Firefox i Chrome.

<<<<<<< HEAD
Ako ne, najpouzdaniji način da to osigurate `use strict` bilo bi da unesete kod u konzolu ovako:
=======
If it doesn't, e.g. in an old browser, there's an ugly, but reliable way to ensure `use strict`. Put it inside this kind of wrapper:
>>>>>>> 3699f73b4ccb2a57ac5ef990d2687bf31ccf564c

```js
(function() {
  'use strict';

<<<<<<< HEAD
  // ...tvoj kod...
})()
```

## Uvjek "use strict"

Moramo još da pokrijemo razlike između strogog načina rada i "uobičajenog" režima.

U sledećim poglavljima, dok učimo jezičke karakteristike, primetićemo razlike između strogog i zadanog načina rada. Srećom, nema ih mnogo i oni nam zapravo poboljšavaju život.

Za sada je dovoljno znati o tome uopšte:

1. `"use strict"` direktiva prebacuje motor u „moderan“ mod, menjajući ponašanje nekih ugrađenih funkcija. Detalje ćemo videti kasnije u vodiču.
2. trogi režim je omogućen postavljanjem `"use strict"` na vrhu skripte ili funkcije. Nekoliko jezičnih funkcija, poput „klase“ i „modula“, automatski omogućuju strogi režim.
3. Strogi režim podržavaju svi moderni pregledači.
4. Preporučujemo uvek pokretanje skripti sa `"use strict"`. Svi primjeri u ovom vodiču pretpostavljaju strogi način rada, osim ako (vrlo rijetko) nije drugačije određeno.
=======
  // ...your code here...
})()
```

## Should we "use strict"?

The question may sound obvious, but it's not so.

One could recommend to start scripts with `"use strict"`... But you know what's cool?

Modern JavaScript supports "classes" and "modules" - advanced language structures (we'll surely get to them), that enable `use strict` automatically. So we don't need to add the `"use strict"` directive, if we use them.

**So, for now `"use strict";` is a welcome guest at the top of your scripts. Later, when your code is all in classes and modules, you may omit it.**

As of now, we've got to know about `use strict` in general.

In the next chapters, as we learn language features, we'll see the differences between the strict and old modes. Luckily, there aren't many and they actually make our lives better.

All examples in this tutorial assume strict mode unless (very rarely) specified otherwise.
>>>>>>> 3699f73b4ccb2a57ac5ef990d2687bf31ccf564c
