# Konzola za programere

Kod je sklon greškama. Verovatno ćete pogrešiti ... Oh, o čemu govorim? * Apsolutno ćete grešiti, barem ako ste čovek, a ne čovek [robot](https://en.wikipedia.org/wiki/Bender_(Futurama)).

Ali u pretraživaču korisnici ne vide greške prema zadanim postavkama. Dakle, ako nešto pođe po zlu u scenariju, nećemo videti šta je slomljeno i ne možemo to da popravimo.

Da biste videli greške i dobili puno drugih korisnih informacija o skriptama, „alati za programere“ ugrađeni su u pregledače.

Većina programera za razvoj se naginje na Chrome ili Firefox jer ti pregledači imaju najbolje alate za programere. Ostali pregledači takođe nude alate za programere, ponekad i posebne funkcije, ali obično se igraju „nadoknadu“ za Chrome ili Firefok. Tako većina programera ima "omiljeni" pregledač i prelaze na druge ako je problem specifičan za pretraživač.

Alati za programere su snažni; imaju mnogo funkcija. Za početak ćemo naučiti kako da ih otvorimo, pogledati greške i pokrenuti JavaScript komande.

## Gugl Chrome

Otvorite stranicu [bug.html](bug.html).

Postoji greška u JavaScript kodu. Sakriven je od očiju redovnog posetioca, pa otvorimo programe za razvojne programere da bismo ih videli.

Pretisni `taster:F12` ili, ako si na Mac računaru, onda `taster:Cmd+Opt+J`.

Alatke za programere će se podrazumevano otvoriti na kartici konzola.

Izgleda nekako ovako:

![chrome](chrome.png)

Tačan izgled alata za programere zavisi od verzije Chrome-a. Povremeno se menja, ali bi trebalo da bude slično.

- Ovde možemo videti poruku o grešci u crvenoj boji. U ovom slučaju, skripta sadrži nepoznatu komandu "lalala".
- Sa desne strane postoji veza na koju se može kliknuti na izvor `bug.html: 12` sa brojem linije na kojoj je došlo do greške.

<<<<<<< HEAD
Ispod poruke o grešci nalazi se plavi simbol ">". Označava „komandnu liniju“ u koju možemo otkucati JavaScript komande. Pretisni `taster:Enter` da ih pokreneš (`taster:Shift+Enter` za unos višerednih komandi).
=======
Below the error message, there is a blue `>` symbol. It marks a "command line" where we can type JavaScript commands. Press `key:Enter` to run them.
>>>>>>> 4d01fc20d4d82358e61518a31efe80dec9bb2602

Sada možemo videti greške, a to je dovoljno za početak. Kasnije ćemo se vratiti alatima za razvojne programere i detaljnije ćemo pokloniti pogrešku u ovom poglavlju <info:debugging-chrome>.

```smart header="Multi-line input"
Usually, when we put a line of code into the console, and then press `key:Enter`, it executes.

To insert multiple lines, press `key:Shift+Enter`. This way one can enter long fragments of JavaScript code.
```

## Firefox, Edge, i ostali

Većina pretraživača koristi `taster:F12` za otvaranje alata za programere.

Izgled i osećaj kod njih prilično su slični. Kada znate kako da koristite jedan od ovih alata (možete početi sa Chrome-om), lako možete preći na drugi.

## Safari

Safari (Mac pretraživač, nije podžan od strane Windows/Linux) je malo poseban ovde. Prvo moramo da omogućimo „Developer meni“.

Otvorite Postavke i idite na okno „Napredno“. Na dnu je potvrdni okvir:

![safari](safari.png)

Sada `taster:Cmd+Opt+C` može prebaciti konzolu. Takođe, imajte na umu da se pojavila nova stavka gornjeg menija pod nazivom „Develop“. Ima mnogo komandi i opcija.

<<<<<<< HEAD
```smart header="Više-linijski ulaz"
Obično kada stavimo liniju koda u konzolu, a zatim pritisnemo `taster: Enter`, izvršava se.

Da biste umetnuli više linija, pritisnite `taster:Shift+Enter`. Na ovaj način se mogu uneti dugi fragmenti JavaScript koda.
```

## Rezime
=======
## Summary
>>>>>>> 4d01fc20d4d82358e61518a31efe80dec9bb2602

- Alatke za programere omogućavaju nam da vidimo greške, izvršavamo komande, ispitujemo promenljive i još mnogo toga.
- Mogu se otvoriti sa `taster:F12` za većinu pregledača u operativnom sistemu Windows. Chrome za Mac treba `taster:Cmd+Opt+J`, Safari: `taster:Cmd+Opt+C` (prvo treba da se omogući).

Sad je spremno okruženje. U sledećem odeljku preći ćemo na JavaScript.
