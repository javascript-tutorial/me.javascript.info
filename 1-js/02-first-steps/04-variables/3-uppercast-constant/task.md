važnost: 4

---

# Konstanta sa velikim slovima?

Ispitajte sledeći kod:

```js
const rođenje = '18.04.1982';

const godine = nekiKod(rođendan);
```

<<<<<<< HEAD
Ovđe imamo konstantu `rođenje` sa datumon i `godine` koje se računaju od `rođenje` uz pomoć nekog koda (nije predviđen za kratkoću i zato što ovđe nisu bitni detalji).
=======
Here we have a constant `birthday` for the date, and also the `age` constant.

The `age` is calculated from `birthday` using `someCode()`, which means a function call that we didn't explain yet (we will soon!), but the details don't matter here, the point is that `age` is calculated somehow based on the `birthday`.
>>>>>>> 540d753e90789205fc6e75c502f68382c87dea9b

Oće li biti u redu koristiti velika slova za `rođenje`? Za `godine`? Ili oboje?

```js
<<<<<<< HEAD
const ROĐENJE = '18.04.1982'; // velika slova?

const GODINE = nekiKod(ROĐENJE); // velika slova?
=======
const BIRTHDAY = '18.04.1982'; // make birthday uppercase?

const AGE = someCode(BIRTHDAY); // make age uppercase?
>>>>>>> 540d753e90789205fc6e75c502f68382c87dea9b
```
