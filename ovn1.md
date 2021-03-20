# Övning 1 grudat21
### Fredag 1/4 kl 15.00

- Gör (minst) en fil per uppgift och lägg filerna i katalogen <code>username-ovn1</code> i organisationen [grudat21 på KTH GitHub](https://gits-15.sys.kth.se/grudat21).
- Utgå från mallarna i [/grudat21/ovn0/](https://github.com/yourbasic/grudat21/tree/master/ovn0).
- Lösningar ska vara inlämnade före deadline.

Du väljer själv vilket av programspråken Python, Go eller Java du vill använda.
**Observera att all kod på den här kursen ska dokumenteras och testas.**

## Betyg G

### 1.1 Fakultet

- Implementera fakultetsfunktionen för heltal.

Utgå från en av mallarna

- [github.com/yourbasic/grudat21/blob/master/ovn0/uppg2.py](https://github.com/yourbasic/grudat21/blob/master/ovn0/uppg2.py)
- [github.com/yourbasic/grudat21/blob/master/ovn0/Uppg2.java](https://github.com/yourbasic/grudat21/blob/master/ovn0/Uppg2.java)
- [github.com/yourbasic/grudat21/blob/master/ovn0/uppg2.go](https://github.com/yourbasic/grudat21/blob/master/ovn0/uppg2.go)

[Tips och råd](https://www.youtube.com/watch?v=QRYvu1-H1xQ) (video)

### 1.2 Länkade listor

En **lista** (array), ett antal element ordnade i en linjär struktur, är den kanske enklaste och mest grundläggande datastrukturen.

En **länkad lista** är en sekvens av listelement förbundna av pekare.
En länkad lista med tre heltal <code>[2,&nbsp;2,&nbsp;1]</code> ser ut så här:

<pre><code>     ----------        ----------        ------------
    |     |    |      |     |    |      |     |      |
--->|  2  |  -------->|  2  |  -------->|  1  | null |
    |     |    |      |     |    |      |     |      |
     ----------        ----------        ------------
</code></pre>

(Nullpekaren har olika namn i olika programspråk: <code>None</code>, <code>nil</code> eller <code>null</code>.)

Listelementen kan implementeras som objekt med två instansvariabler,
en variabel som innehåller värdet och en variabel som pekar på nästa element i listan.
I **pseudokod**:

<pre><code># A list element that stores a value of type T.
private ListElement:
    data T
    next ListElement
</code></pre>


- Implementera en enkellänkad lista i form av en klass som innehåller funktionerna i följande **pseudokod**.
  Du får inte ändra klassens gränssnitt, dvs du får inte ändra **signaturerna** eller **dokumentationskommentarerna**
  på de  publika metoderna eller lägga till några andra publika metoder.

<pre><code># A singly linked list of elements of type T.
public LinkedList:
    private first ListElement # first element in list
    private last ListElement  # last element in list
    private size int          # number of elements in list
   
    # Create an empty list.
    public new() LinkedList

    # Insert the given element at the beginning of this list.
    public void addFirst(element T)

    # Insert the given element at the end of this list.
    public void addLast(element T)

    # Return the first element of this list.
    # Return null if the list is empty.
    public getFirst() T

    # Return the last element of this list.
    # Return null if the list is empty.
    public getLast() T

    # Return the element at the specified position in this list.
    # Return null if index is out of bounds.
    public get(index int) T

    # Remove and returns the first element from this list.
    # Return null if the list is empty.
    public removeFirst() T

    # Remove all elements from this list.
    public clear()

    # Return the number of elements in this list.
    public size() int

    # Return a string representation of this list.
    # The elements are enclosed in square brackets ("[]").
    # Adjacent elements are separated by ", ".
    public string() string
</code></pre>

- Beräkna den asymptotiska värstafallstiden för samtliga publika metoder i din implementation.
  Uttryck tiden som en funktion av antalet element&nbsp;<i>n</i> i listan.

- Skriv <b>utförlig testkod</b>. Alla publika metoder ska testas.
  Glöm inte att kontrollera att din kod fungerar även för den tomma listan.
  Jag rekommenderar att du skriver testkoden först.

#### Tips

Ditt program ska bestå av två klasser:

- <code>LinkedList</code> är den publika delen av programmet,
- <code>ListElement</code> är en privat hjälpklass som implementerar ett element i den länkade listan.

Titta gärna på exempelmallarna. De visar hur man kan skriva och testa en klass i Python, Java respektive Go:

- [github.com/yourbasic/grudat21/blob/master/ovn0/uppg3.py](https://github.com/yourbasic/grudat21/blob/master/ovn0/uppg3.py)
- [github.com/yourbasic/grudat21/blob/master/ovn0/Stack.java](https://github.com/yourbasic/grudat21/blob/master/ovn0/Stack.java)
- [github.com/yourbasic/grudat21/blob/master/ovn0/uppg3.go](https://github.com/yourbasic/grudat21/blob/master/ovn0/uppg3.go)

[Tips och råd](https://www.youtube.com/watch?v=SH72Eyelbs4) (video)

## Betyg VG

### 1.3 Mera testning

Det kan vara svårt att testa datastrukturer;
en metod kan returnera rätt svar men ändå göra fel.
Det händer till exempel om den lämnar efter sig instansvariabler
med felaktiga värden. En bra sätt att upptäcka den typen av fel
är att använda en testmetod som undersöker om listan befinner
sig i ett korrekt tillstånd:


<ul>
<li><code>size</code> måste vara lika med antalet <code>ListElement</code>.
</li>
<li>Om listan är tom så ska både <code>first</code> och <code>last</code>
    vara nullpekare, annars ska de peka på listelement.
</li>
<li>Om ett element ligger sist i listan så ska dess <code>next</code>-pekare
    vara null.
</li>
</ul>

Implementera en metod <code>healthy()</code> som kollar detta.
På lämpliga ställen, troligen ganska många, i din testkod ska du sedan
anropa <code>healthy()</code> för att kontrollera att listan inte har
gått sönder.

