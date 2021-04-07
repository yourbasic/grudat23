# Övning 3 grudat21
### Fredag 23/4 kl 13.00

**Vid övningen ska du vara beredd att muntligt presentera och diskutera dina lösningar och din programkod.**

- Gör (minst) en fil per uppgift och lägg filerna i katalogen <code>username-ovn3</code> i organisationen [grudat21 på KTH GitHub](https://gits-15.sys.kth.se/grudat21).
- Utgå från mallarna i [/grudat21/ovn0/](https://github.com/yourbasic/grudat21/tree/master/ovn0).
- Lösningar ska vara inlämnade före deadline.

Du väljer själv vilket av programspråken Python, Go eller Java du vill använda.
**Observera att all kod på den här kursen ska dokumenteras och testas.**

## Betyg G

### 3.1 Fakultet i repris

Skriv en rekursiv fakultetsfunktion och bevisa att den är korrekt med hjälp av induktion.

Utöver beviset ska du som vanligt skriva testkod.

> Beware of bugs in the above code; I have only proved it correct, not tried it.

&ndash; Donald Knuth

[Video om induktion](https://www.youtube.com/watch?v=x8dmvJIF-MI)

### 3.2 Typvärde

[Typvärdet](https://sv.wikipedia.org/wiki/Typv%C3%A4rde) (mode)
i ett statistiskt datamaterial är det värde som förekommer flest gånger.

- Skriv en funktion som beräknar typvärdet för en vektor med heltal.
  Om flera värden är lika vanliga skall funktionen ge det minsta av dem.
- Tidskomplexiteten för din algoritm ska vara *O*(*n*&nbsp;log&nbsp;*n*).

Det är fritt fram att använda de datastrukturer och algoritmer
som finns i standardbiblioteken för Python, Java eller Go.
Det är bra att kunna sitt standardbibliotek och det är bra praxis att använda en färdig vältestad funktion
snarare än att skriva den själv.

Med det sagt, så får man inte använda https://docs.python.org/3/library/statistics.html#statistics.multimode,
som ju nästan löser uppgiften direkt.
Observera också att det inte framgår av Python-dokumentationen vilken tidskomplexitet denna funktion har.

### 3.3 Negativt och positivt

- Skriv en funktion som ändrar ordningen på en vektor med tal så att de negativa talen kommer först.
  Vektorn ska inte sorteras, du behöver endast samla alla negativa tal för sig.
- Skriv en **loopinvariant** som förklarar hur koden fungerar.
- Räkna också ut tidskomplexiteten för din algoritm.

Algoritmen ska vara **in-place** ([Wikipedia: In-place algorithm](https://en.wikipedia.org/wiki/In-place_algorithm)),
dvs använda högst *O*(1) extra utrymme. *Du får inte använda någon sorteringsalgoritm.*

[Video om loopinvarianter](https://www.youtube.com/watch?v=vVdDyI1PIUU)

## Betyg VG

För betyg VG ska du göra samma uppgifter som för betyg G,
men med det extra kravet att algoritmerna i **uppgift 3.2 och 3.3** ska ha *O*(*n*) tidskomplexitet.
Det räcker med förväntad (expected) tid, men värstafall går förstås också bra. (Linjär värstafallstid är svårt men inte helt omöjligt.)

På engelska skiljer man på **average** time complexity där man väger samman tiderna för alla möjliga indata och  **expected** time complexity där algoritmen använder sig av slump för att göra värstafallsbeteendet extremt osannolikt. Vi har sett två exempel på expected time hittils i kursen: hashtabeller och treapar. På svenska finns det tyvärr ingen tydlig och bra terminologi.

Så här skriver Wikipedia om [Average-case complexity](https://en.wikipedia.org/wiki/Average-case_complexity):

> Average-case analysis requires a notion of an "average" input to an algorithm,
> which leads to the problem of devising a probability distribution over inputs.
> Alternatively, a randomized algorithm can be used.
> The analysis of such algorithms leads to the related notion of an expected complexity.

