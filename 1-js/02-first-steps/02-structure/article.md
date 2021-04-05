# Struktura koda

Prvo što ćemo proučiti pisanje blokova koda.

## Iskazi

Iskazi su sintaksne konstrukcije i naredbe koje izvode akcije.

Već smo viđeli iskaz, `alert('Zdravo svijete!')`, koja prikazuje poruku "Zdravo svijete!".

U kodu možemo imati onoliko iskaza koliko želimo. Iskazi se mogu odvojiti tačkom sa zarezom.

Na primer, ovde smo podelili "Zdravo svijete!" na dva upozorenja:

```js run no-beautify
alert('Zdravo'); alert('svijete!');
```

Iskazi se obično pišu u novim linijama kako bi se kod učinio čitljivijim:

```js run no-beautify
alert('Zdravo');
alert('svijete!');
```

## Tačka-zarez [#tackazarez]

Tačka-zarez može biti izostavljena u većini slučajeva kada postoji prekid linije.

Ovo bi takođe funkcionisalo:

```js run no-beautify
alert('Zdravo')
alert('svijete')
```

Ovde JavaScript interpretira proboj prelom linija kao "implicitni" tačka-zarez. To se naziva [automatsko umetanje tačake-zareza]
(https://tc39.github.io/ecma262/#sec-automatic-semicolon-insertion).

**U većini slučajeva novi red podrazumeva tačku sa zarezom. Ali "u većini slučajeva" ne znači "uvjek"!**

Postoje slučajevi kada nova linija ne znači tačka-zarez. Na primjer:

```js run no-beautify
alert(3 +
1
+ 2);
```

Kod ispisuje `6`, jer JavaScript ovde ne ubacuje tačku-zarez. Intuitivno je očigledno da ako se linija završava sa plus "+" `, onda je to" nepotpun izraz ", pa tačka-zarez nije obavezna. I u ovom slučaju to radi onako kako je planirano.


**Ali postoje situacije u kojima JavaScript „ne uspijeva“ da pretpostavi tačku-zarez tamo gde je stvarno potrebno.
**

Greške koje se dešavaju u takvim slučajevima je stvarno teško otkriti i ispraviti.

````smart header="Primjer greške"
Ako ste radoznali da vidite konkretan primer takve greške, pogledajte ovaj kod:

```js run
[1, 2].forEach(alert)
```

Još nije potrebno razmišljati o značenju zagrada `[]` i `forEach`. Kasnije ćemo ih proučiti. Za sada se samo sjetite rezultata koda: prikazuje "1", a zatim "2".

Sada, dodajmo upozorenje prije koda i *ne* završimo tačkom-zarezom:

```js run no-beautify
alert("Ovđe će doći do greške")

[1, 2].forEach(alert)
```

Sada ako pokrenemo kod, prikazuje se samo prvo `upozorenje` i tada imamo grešku!

Ali opet je sve u redu ako nakon `upozorenja` dodamo tačku-zarez:
```js run
alert("Sad je sve u redu!");

[1, 2].forEach(alert)  
```

Sada imamo poruku "Sve u redu", a zatim slijede "1" i "2".


Do greške u varijanti koja nije pod tačkom-zarezom događa se jer JavaScript ne podrazumeva tačku sa zarezom ispred uglastih zagrada `[...]`.

Dakle, jer tačka-zarez nije automatski umetnuto, kod u prvom primeru se tretira kao jedna stavka. Evo kako motor to vidi:


```js run no-beautify
alert("Ovđe će doći do greške!")[1, 2].forEach(alert)
```

Ali to bi trebalo biti dva odvojena iskaza, ne jedan. Takvo spajanje u ovom slučaju je upravo pogrešno, otuda i greška. To se može dogoditi i u drugim situacijama.
````

Preporučujemo stavljanje tačke-zareza između izjava, čak i ako su razdvojene novim linijama. Ovo pravilo široko prihvata zajednica. Napomenimo još jednom - *moguće je* izostavljati tačku-zarez većinu vremena. Ali sigurnije je - posebno za početnike - koristiti ih.

<<<<<<< HEAD
## Komentari
=======
## Comments [#code-comments]
>>>>>>> 7b76185892aa9798c3f058256aed44a9fb413cc3

Kako vrijeme prolazi, programi postaju sve složeniji. Potrebno je dodati *komentare* koji opisuju šta kod radi i zašto.

Komentari se mogu staviti na bilo koje mesto skripte. Oni ne utiču na njegovo izvršenje jer ih motor jednostavno ignoriše.

**Jednolinijski komentari počinju sa dvije prednje kose crte `//`.**

Ostatak linije je komentar. Može zauzeti punu liniju ili slediti iskaz.

Kao što je ovđe:
```js run
// Ovaj komentar zauzima sopstvenu liniju
alert('Zdravo');

alert('Svijete'); // Ovaj komentar prati iskaz
```

**Višelinijski komentari počinju sa jednom prednjom kosom crtom i zvjezdicom <code>/&#42;</code> i završavaju se sa zvjezdicom i prednjom kosom crtom <code>&#42;/</code>.**

Kao što je ovo:

```js run
/* Primjer sa dvije poruke
Ovo je višelinijski komentar
*/
alert('Zdravo');
alert('Svijete');
```

Sadržaj komentara se ignoriše, pa ako stavimo kod unutra <code>/&#42; ... &#42;/</code>, neće se izvršavati.

Ponekad je korisno privremeno deaktivirati deo koda:
```js run
/* Komentarisanje koda
alert('Zdravo');
*/
alert('Svijete');
```

<<<<<<< HEAD
```smart header="Korišćenje tastera za prečice!"
U većini urednika koda se može komentarisati pritiskom na `taster:Ctrl+/` za jednolinijski komentar i nešto slično `taster:Ctrl+Shift+/` -- za komentare sa više linija (izaberite deo koda i pritisnite taster). Probajte za Mac računare `taster:Cmd` umjesto `taster:Ctrl`.
=======
```smart header="Use hotkeys!"
In most editors, a line of code can be commented out by pressing the `key:Ctrl+/` hotkey for a single-line comment and something like `key:Ctrl+Shift+/` -- for multiline comments (select a piece of code and press the hotkey). For Mac, try `key:Cmd` instead of `key:Ctrl` and `key:Option` instead of `key:Shift`.
>>>>>>> 7b76185892aa9798c3f058256aed44a9fb413cc3
```

````warn header="Uneseni komentari nisu podržani!"
Ne može biti `/*...*/` u `/*...*/`.

Takav kod bit će uništen greškom

```js run no-beautify
/*
  /* komentar u komentar ?!? */
*/
alert( 'Svijet' );
```
````

Ne ustručavajte se da komentarišete svoj kod.

Komentari povećavaju ukupni trag koda, ali to uopšte nije problem. Postoji mnogo alata koji minimiziraju kod prije objavljivanja na proizvodnom serveru. Oni uklanjaju komentare, tako da se ne pojavljuju u radnim skriptama. Stoga komentari uopšte nemaju negativne efekte na proizvodnju.

Kasnije će u udžbeniku biti poglavlja <info:code-quality> to takođe objašnjava kako napisati bolje komentare.
