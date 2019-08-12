važnost: 4

---

# Konstanta sa velikim slovima?

Ispitajte sledeći kod:

```js
const rođenje = '18.04.1982';

const godine = nekiKod(rođendan);
```

Ovđe imamo konstantu `rođenje` sa datumon i `godine` koje se računaju od `rođenje` uz pomoć nekog koda (nije predviđen za kratkoću i zato što ovđe nisu bitni detalji).

Oće li biti u redu koristiti velika slova za `rođenje`? Za `godine`? Ili oboje?

```js
const ROĐENJE = '18.04.1982'; // velika slova?

const GODINE = nekiKod(ROĐENJE); // velika slova?
```

