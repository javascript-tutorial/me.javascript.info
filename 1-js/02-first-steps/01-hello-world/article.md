# Zdravo Svijete!

Ovaj deo udžbenika govori o jezgru JavaScripta, samom jeziku.

Ali potrebno nam je radno okruženje za pokretanje naših skripti i budući da je ova knjiga na mreži, pregledač je dobar izbor. Smanjićemo količinu naredbi specifičnih za pregledač (poput „upozorenja“) na minimum tako da na njih ne trošite vreme ako se planirate koncentrisati na drugo okruženje (poput Node.js). Usredsredićemo se na JavaScript u pregledaču u [sledećem delu] (/ ui) udžbenika.

Prvo, da vidimo kako prikačiti skriptu na web stranicu. Za okruženja na strani poslužitelja (poput Node.js), možete izvršavati skriptu pomoću naredbe poput `"node my.js"`.


## "script" tag

<<<<<<< HEAD
JavaScript programi se mogu ubaciti u bilo koji deo HTML dokumenta uz pomoć `<script>` taga.
=======
JavaScript programs can be inserted almost anywhere into an HTML document using the `<script>` tag.
>>>>>>> d4b3c135ccf80914f59677803e64ebc832d165e3

Na primjer :

```html run height=100
<!DOCTYPE HTML>
<html>

<body>

  <p>Prije skripte...</p>

*!*
  <script>
    alert( 'Zdravo Svijete!' );
  </script>
*/!*

  <p>...posle skripte.</p>

</body>

</html>
```

```online
Primer možete pokrenuti klikom na dugme „Play“ u gornjem desnom uglu gornjeg okvira.
```

`<script>` tag sadrži JavaScript kod koji se automatski izvršava kada pregledač obrađuje oznaku.


## Moderno označavanje

`<script>` tag ima nekoliko atributa koji se danas retko koriste, ali se još uvek mogu naći u starom kodu:

<<<<<<< HEAD
`type` atribut: <code>&lt;script <u>type</u>=...&gt;</code>
: Stari HTML standard, HTML4, zahtevao je skriptu da sadrži `type`. Obično je to bilo `type="text/javascript"`. To više nije potrebno. Takođe, savremeni HTML standard potpuno je promenio značenje ovog atributa. Sada se može koristiti za JavaScript module. Ali to je napredna tema; razgovaraćemo o modulima u drugom delu udžbenika.
=======
The `type` attribute: <code>&lt;script <u>type</u>=...&gt;</code>
: The old HTML standard, HTML4, required a script to have a `type`. Usually it was `type="text/javascript"`. It's not required anymore. Also, the modern HTML standard totally changed the meaning of this attribute. Now, it can be used for JavaScript modules. But that's an advanced topic, we'll talk about modules in another part of the tutorial.
>>>>>>> d4b3c135ccf80914f59677803e64ebc832d165e3


`language` atribut: <code>&lt;script <u>language</u>=...&gt;</code>
: Ovaj atribut je trebalo da pokaže jezik skripte. Ovaj atribut više nema smisla jer je JavaScript zadani jezik. Nema potrebe da se koristi.

Komentari pre i posle skripte.
: U zaista 'drevnim' knjigama i vodičima možete pronaći komentare unutar `<script>` taga, ovako:

    ```html no-beautify
    <script type="text/javascript"><!--
        ...
    //--></script>
    ```

<<<<<<< HEAD
    Ovaj trik se ne koristi u savremenom JavaScript-u. Ovi komentari su sakrili JavaScript kod od starih pretraživača koji nisu znali kako da to obrade `<script>` tag. Budući da pregledači objavljeni u poslednjih 15 godina nemaju ovaj problem, ova vrsta komentara može vam pomoći da identifikujete zaista stari kod.
=======
    This trick isn't used in modern JavaScript. These comments hide JavaScript code from old browsers that didn't know how to process the `<script>` tag. Since browsers released in the last 15 years don't have this issue, this kind of comment can help you identify really old code.
>>>>>>> d4b3c135ccf80914f59677803e64ebc832d165e3


## Spoljne skripte

Ako imamo puno JavaScript koda, možemo ga staviti u odvojenu datoteku.

Datoteke skripta su u HTML-u priložene atributom `src`

```html
<script src="/put/do/skripta.js"></script>
```

Ovdje , `/put/do/skripta.js` je apsolutni put do skripte iz korena mesta. Takođe se može pružiti relativna putanja od trenutne stranice. Na primer, `src="skripta.js"` značilo bi da fajl `"script.js"` je u trenutnom folderu.

Takođe možemo dati punu URL adresu. Na primer:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js"></script>
```

Da biste dodali nekoliko skripti, koristite više tagova:

```html
<script src="/js/skripta1.js"></script>
<script src="/js/skripta2.js"></script>
…
```

```smart
Po pravilu, u HTML se ubacuju samo najjednostavnije skripte. Složenije se nalaze u odvojenim fajlovima.

Prednost odvojene datoteke je u tome što će je pregledač preuzeti i sačuvati u svojoj [keš memoriji](https://en.wikipedia.org/wiki/Web_cache).

Ostale stranice koje se pozivaju na isti skript uzimaće ga iz keša umesto da ga preuzmu, tako da se datoteka zapravo preuzima samo jednom.


To smanjuje promet i brže stvara stranice.
```

````warn header="Ako je `src` postavljeno, sadržaj skripte se ignoriše." Pojedinačna oznaka `<script>` ne može imati atribut `src` i kod unutra.

Ovo neće raditi:

```html
<script *!*src*/!*="file.js">
  alert(1); // sadržaj se ignoriše jer je podešen src
</script>
```

Moramo odabrati `<script src="…">` ili regularno `<script>` sa kodom.

Gornji primer može se podeliti na dve skripte za rad:

```html
<script src="fajl.js"></script>
<script>
  alert(1);
</script>
```
````

## Rezime

- Možemo koristiti `<script>` tag kako bi dodali JavaScript kod na stranici.
- `type` i `language` atributi nisu potrebni.
- Skripta u odvojenom fajlu se prikači sa `<script src="put/do/skripte.js"></script>`.


Postoji mnogo više da se nauči o skriptama pretraživača i njihovoj interakciji sa web stranicom. Ali imajmo na umu da je ovaj deo udžbenika posvećen JavaScript jeziku, tako da ne bismo smeli da odvlačimo pažnju pomoću njegovih pretraživača. Koristićemo pretraživač kao način pokretanja JavaScripta, što je vrlo dobro za čitanje putem interneta, ali samo jedan od mnogih.
