# Algoritmer med mere
### Læringsmål
Efter første uge er det meningen at:

- du kan anvende debuggeren i Netbeans
- du kan forklare hvordan Java håndterer *variable*, *felter* og `this` referencen på kaldsstakken og på heap.
- du skal kunne skrive junit tests for metoder på enkeltstående klasser.
- Du kan forklare hvordan HashMap fungerer, specielt hvordan man håndterer kollisioner og udvidelse.


Efter anden uge er det meningen at:

- Du kan redegøre for et binært søgetræ
- Du kan redegøre for hvordan et binært søgetræ kan bruges til sortering
- Du kan implementere quicksort algoritmen
- Du anvende kompleksitetsmåletet "store O" på løkker, metoder og algoritmer.
- Du kan vælge en passende datastruktur fra Java's klasse biblioteker

#### Erhvervskompetencer
Efter disse to uger er det meningen at du skal kunne:

- Bruge og forstå en debugger og ikke fylde din kode med `System.out.println` som en anden begynder...
- Kunne skrive unit tests istedet for at have main metoder til test
- Forstå og anvende ArrayList og Hashmap samt vide hvordan sorteringer udføres effektivt.

De algoritmiske ting bag ArrayList, HashMap og sortering vil I ikke komme til at skrive selv (de ligger i Java bibliotekerne). Men jeres chef og kollegaer forventer at man ved hvordan de virker.

## Uge 1
Det er meningen I skal arbejde sammen selvstændigt med emnerne. Vi mødes mandag, onsdag og fredag. 

### Mandag er vigtig
og vil være "klassisk dag", altså alle tilstæde i klassen med en blanding af oplæg, demo, og øvelser.

Denne dag er semesterets første dag, og vi vil prøve at give det overordnede billede af hvad der kommer til at ske resten af semesteret, og præsentere Thomas og Kasper som er de to undervisere I kommer til at arbejde med.

Onsdag og Fredag vil vi mødes 2 grupper af gangen (4 personer) i 30 min, så vi kan følge op på om der er problemer med opgaverne og læsestoffet.

### Læsestof og opgaver til onsdag

- [Slides fra mandag](https://efif.sharepoint.com/sites/cph/Lyngby/_layouts/15/guestaccess.aspx?guestaccesstoken=WuJRvpgtBdKAgs2RfTv7Jqnu9QHBd5aOQvW7m0YeNKM%3d&docid=2_0e12cd4b1d59642b59d9ffb3aa386f7f4&rev=1)
- [Tavle](tavle20170821.pdf)
- [Note om hvordan Java bruger stak og heap](RuntimeJava.md)
- [Note om Netbeans debuggeren](DebuggingAndArraylist.md)
- [Kode der bruges i Sem2ArrayList](https://github.com/DAT2Sem2017E/Modul1Sem2ArrayList)

Når vi mødes onsdag vil jeg gerne have en demo af hvordan I kan sætte breakpoints og forklare mig hvordan debuggeren virker. Det betyder at I skal have lavet jeres ArrayList så I kan vise det til mig.

Forventninger:

Niveau | Demo
---|---
Grøn | Det forventes at I har fået arraylist programmet op at køre i netbeans, og kan forklare mig hvordan vi i debuggeren kan se kaldsstak, this pointeren og parametere til metoden `add` når der er sat et breakpoint i linje 33 i `Sem2ArrayList.java`. Det forventes også at I ved hvad fejlen er i denne linje.
Gul | Der skal laves en metode `Coordinate removeLast()` der fjerner det sidste element (og returnerer det). Hvis der ikke er noget element skal der returneres null. I kan eventuelt også lave det sådan at hvis kun 25% af elementerne i array bruges, så kopieres de resterende elementer over i et mindre array (halv størrelse af det gamle). I skal så vise et eksempel hvor der er et breakpoint som stopper ligefør arrayet gøres mindre.
Rød | For de særligt nysgerrige vil jeg foreslå at I forbereder en forklaring på hvad der sker i konstruktøreren og hvorfor den mon hedder `<init>` i både pythontutor og i debuggeren. Hint - prøv at flytte noget af initialiseringen ud af konstruktøren og over i felterne.


### Læsestof og opgaver til fredag

De næste par dage skal vi se på hvordan man i Java kan teste sine programmer. Det bliver først interessant hvis programmerne er lidt komplicerede, så vores eksempel vil være at lave vores egen udgave af et HashMap.

- [Note om HashMap](HashMap.md)
- [Note om test (af HashMap)](JUnitAndHashMap.md)
- [Kode der bruges i Sem2HashMap](https://github.com/DAT2Sem2017E/Modul1Sem2HashMap)

Når vi mødes fredag vil jeg gerne have en demo af jeres HashMap (eller det i er nået). Hvis I ikke er færdig til fredag, så skal I vise hvad I har og hvorfor I er gået i stå.

Forventninger:

Niveau | Demo
---|---
Grøn | Jeg forventer i kan demo et hashmap med tests. Det behøver *ikke* at håndtere kollisioner, men I skal have en test der viser at den ikke kan - altså en test der fejler pga. kollision.
Gul | Jeg forventer at I kan håndtere kollisioner og at der er en test der viser at det kan I. Jeg forventer *ikke* at jeres HashMap kan udvides. Der skal være en test der fejler fordi den ikke kan udvides.
Rød | Jeg forventer I har implementeret at jeres HashMap udvides når det begynder at blive fuldt. Der skal være tests der viser at det kan det.



## Uge 2
Vi skal i denne uge kikke på et emne der kaldes "søgning og sortering".

Vi kommer til at bruge den første del af ugen på det der kaldes et "binært søge træ". Søgetræer er en klassisk måde at gemme data på. Søgetræer fungerer ligesom HashMap ved at man gemmer en værdi under en nøgle.

Dernæst skal vi kikke på en af de måder at sortere på som er mest udbredt, nemlig *quicksort*. 

Endelig skal vi fredag se på hvordan man vælger hvilken type collection man skal bruge til hvilken opgave.

### Mandag
Mandag bliver "klassisk dag", altså alle tilstæde i klassen med en blanding af oplæg, demo, og øvelser. Jeg vil gennemgå ugens emner

- Tirsdag skal i arbejde selvstændigt (2 mands grupper) med at implementere søgetræet

### Onsdag
Vi mødes vi 2 grupper af gangen (4 personer) for at I kan give en demo af søgetræet I har implementeret.

#### Læsestof & opgaver
- [PDF af tavlen](tavle20170828.pdf)
- [Note om søgetræer](BinarySearchTree.md) (inkl opgaver til onsdag)


Forventninger:

Niveau | Demo
---|---
Grøn | Jeg regner med at I har kan demo løsningerne til opgaverne i Noten om søgetræer (dem der *ikke* er markeret avanceret)
Gul | Jeg regner med at I selv har kikket på det med at fjerne elementer fra søgetræet, og hvis I ikke har fået det til at virke, at I så i det mindste har fået skrevet nogle tests der fejler men kan oversættes.
Rød | Jeg regner med at I enten har fået det balancerede søgetræ til at virke, eller har nogle ret klare spørgsmål for at afklare jeres problemer.

- Torsdag skal i arbejde med at implementere quicksort, og løse nogle "store O" opgaver.

### Fredag 
I skal demo (i grupper) jeres løsninger af quicksort algoritmen, og jeres løsninger på store O opgaverne og det at vælge en collection

#### Læsestof og opgaver
- [Note om quicksort & "store O"](QuicksortAndBigO.md) (inkl opgaver til fredag)
- [Note om at vælge en collection](ChoosingACollection.md)
- [Vejledende løsning](https://github.com/DAT2Sem2017E/Modul1TreeAndSort/tree/solution)

Forventninger:

Niveau | Demo
---|---
Grøn | Jeg regner med at I kan demo quicksort og har test at I kan sortere både nul, et og 10 elementer, og en test der viser at I kan sortere noget der allerede er sorteret, samt noget der er i omvendt rækkefølge. Desuden regner jeg med at vi kan snakke om løsningen på opgaverne omkring store O og det at vælge en datastruktur.
Gul | Jeg regner med at I kan forklare *hvorfor* man får *log<sub>2</sub>(n)* opførsel på søgning i søgetræ, og hvorfor man får *n·log<sub>2</sub>(n)* opførsel på quicksort.
Rød | Jeg vil foreslå at I kikker på den algoritme der hedder "MergeSort", og prøver at implementere den. Hvis I ikke kommer igennem med det, så prøv at indkredse hvad ved algoritmen I ikke forstår.
