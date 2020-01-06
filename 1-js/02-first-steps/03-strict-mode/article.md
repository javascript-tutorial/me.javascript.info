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

Uskoro ćemo naučiti funkcije (način za grupisanje komandi). Gledajući napred, uzmimo to u obzir `"use strict"` može se staviti na početak tela funkcije umesto celog skripta. To omogućava strogi režim samo u toj funkciji. Ali obično ga ljudi koriste za cijelu skriptu.


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
>>>>>>> 14e4e9f96bcc2bddc507f409eb4716ced897f91a
```

## Konzola pregledača

Kada za testiranje funkcija koristite konzolu pregledača za ubuduće, imajte na umu da to nema `use strict` podrazumijevano.

Ponekad, kada `use strict` čini razliku, dobićete pogrešne rezultate.

Možete da pokušate da pritisnete `taster:Shift+Enter` da unesete više redova i stavite „use strict“ na vrh, ovako:

```js
'use strict'; <Shift+Enter za novi red>
//  ...tvoj kod
<Enter za pokretanje>
```

Radi u većini pregledača, naime Firefox i Chrome.

Ako ne, najpouzdaniji način da to osigurate `use strict` bilo bi da unesete kod u konzolu ovako:

```js
(function() {
  'use strict';

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
