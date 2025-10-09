
**SUPB oz. sistem za upravljanje s podatkovnimi bazami** je vmesnik med podatkovno bazo in uporabnikom.

### Relacijske baze

**Relacijska baza** je tip podatkovne baze ki shranjuje in organizira podatke po relacijskem modelu.

Za njih velja da so:
- **enostavne** - podatki so shranjeni v tabelah
- **foramlno definirane** - osnovane na matematični definiciji relacij
- **ločeni od fizične implementacije**
- **močni poizvedovalni jeziki**

**Relacija** je implementiranja kot tabela, predstavlja trenutno stanje podatkov. 
Če se tabela spremeni je to nova relacija.

Je množica **$n$-teric** ki so predstalvjene kot vrstice v tabeli - relaciji.

Vsak element v $n$-terici pripada nekemu **atributu** relacije. Atributi so deifnirani na svoji **domeni** - množici možnih vrednosti ki jih nek atribut lahko zazvame.

Tako lahko implementacijo primerjamo z relacijo z matematično definicijo.

Relacija predstavlja podmnožico kartezičnega produkta domen atributov.

Recimo da imamo relacijo `oseba` z atributi `starost`, `ime`, `priimek`, ki naj bodo definirane na domeni $A_{1}=\{ 0,...,200\}, A_{2}=\{\text{a},...,\text{ž}\}, A_{3}=\{\text{a},...,\text{ž}\}$.

Sedaj velja da je množica  $O :=$ `oseba` definirana kot

$$O \subseteq  A_{1} \times  A_{2} \times A_{3}$$

kjer je vsak element $O$ $n-terica$ kartezičnega produkta, kar predstavimo kot vrstica v tabeli.

**Stopnja relacije** je kot pri matematični definiciji število množic ki sestavljajo kartezični produkt oz. število elementov v $n$-terici oz. **stopnja $n$-terice**

**Števnost relacije** je kot pri matematiki - števnost oz. cardinality množice, število elementov v relaciji $R$ - torej **število vrstic**.

***

Relacijska shema je zapis ki semantično predstavlja relacijo.

Za osebo predstalvjeno z imenom in starostjo bi napisali kot
```
oseba(ime:char(20), starost:integer)
```

Splošno zgleda kot
```
ime-relacije(ime-atributa:data-type,...)
```

***

Lastnosti relacij
- **ime relacije, imena atributov** in **vsaka n-terica** so enolične
- vrednosti atributov so iz **iste domene**
- vsaka celica vsebuje natanko eno **atomarno vrednost**
- **vrstni red atributov in n-teric** ni pomemben

**Atomarna vrednost** je predvidoma taka vrednost ki bi ob nadalnji členitvi izgubila smisel.

***

**Funkcionalna odvisnost** je princip kjer je neka množica atributov odvisna od druge. 

Če je $Y$ funkcionalno odvisen od $X$ potem velja da lahko za vsak element v $Y$ dobimo enoličen element iz $X$ a to ne velja obratno.

Torej če vzamemo dva elementa iz $X$ lahko imata oba isto pripadajočo vrednost iz $Y$.

$$\begin{array}\\
1 & A\\
2 & A\\
3 & B
\end{array}$$

vidimo da lahko za vsako številko nedvoumno ugotovimo katera črka ji pripada. Za črko $A$ pa ne moremo ugotoviti ali ji pripada 1 ali 2.

Velja da lahko množico funckionalnih odvisnost ki velja med atributi sheme $R$ označimo s $F$.

$$\begin{array}\
X \rightarrow Y \in F \\ 
\Leftrightarrow \\
\forall r (\text{Sh}(r) = R \Rightarrow \forall t,u \in r (t.X = u.X \Rightarrow t.Y = u.Y))
\end{array}$$

**Množica atributov je lahko funckionalno odvisna od množice atributov** ni omejeno na to da je samo en atribut odvisen od drugega.

***

Atributi $X$ so ključ relacijske sheme oz. pripadajočih relacij če velja
- Vsi atributi ki niso v $X$ so funkcionalno odvisni od $X$
- Ne obstaja podmnožica $X$ ki bi tudi funkcionalno določala vse atribute.

**Superključ** je vrsta ključa ki izpolnjuje le prvo točko - torej ima odvečne atribute.

**Kandidatni kjuč** je množica atributov ki izpolnjuje oba pogoja.

**Primarni ključ** je izbrana množica atributov izmed kandidatnih ključev.

**Tuji ključ** je uporabljen za vzpostavljanje povezave med tabelami. *Če imamo tabelo $A$ ki ima primarni ključ in hočemo referncirati n-terica iz $A$ v neki relaciji $B$ potem moramo uporabiti njen primarni ključ kateremu v relaciji $B$ pravimo tuji ključ.*

***

**Za kakovost in celovitost podatkov** vpeljemo **omejitve** nad podatki. Poznamo več vrst.

**Omejitve domene** določajo katere vrednosti so dovoljene za nek atribut.

**Pravila za celovitost podatkov** so pravila s katerimi skrbimo za doslednost baze.
- **Celovitost entitet** pravi da primarni ključ nobene entitete ne sme biti prazen
- **Celovitost povezav** pa pravi da mora tuji ključ zazvemati veljavne vrednosti oz. obstoječe zapise ali pa je NULL (če je to dopuščeno).

**Števnost** specificira kako sta dve entiteti povezani. Poznamo 1:1, 1:n, n:m, kjer predstalvjajo kolikokrat nastopa neka entiteta v drugi.

**Tuji ključi** morajo zavzameti veljavne vrednosti ali biti v celoti NULL (če je to dovoljeno).

Knjižnica ima več knjig ;-; knjiga : knjižnica - n : 1
Knjiga ima en ISBN ;-; knjiga : ISBN - 1 : 1
...
**Splošne omejitve** so poljubna pravila določena naknadno s strani organizacije oz. uporabnika npr. NOT NULL, UNIQUE, CHECK,...

***

**NULL** je vrednost atributa ki je trenutno neznana - gre za nepopolne podatke.

V osnovni relaciji ne sme noben atribut ki je del ključa biti NULL.

***

**View** je način predstavitve podatkovne baze brez ogrožanja varnosti podatkov. Prilagojen dostopu uporabnikov. Izvaja preko poizvedovalnih jezikov.
***
### Relacijska algebra

**Relacijska algebra je postopkovni jezik** kjer navajamo potek pridobivanja zahtevanih informacij.

**Relacijsko popoln jezik** je tak s katerim je mogoče izvesti vsako operacijo ki jo je mogoče izvesti z relacijsko algebro ki presdtavlja izhodišče. *Temelji na selekciji, projekciji, kartezičnem produktu, uniji, razliki.*

**Vhod in izhod** so **relacije**. Vhodne relacije se ne spreminjajo.

**Selekcija** deluje na enojni relaciji $R$ in vrne relacijo ki vsebuje samo tiste $n$-terice ki zadoščajo predikatu $\theta$ - določenem pogoju.
$$\sigma_\theta (R)$$

**Projekcija** deluje na enojni relaciji $R$ in vrne relaicjo ki vsebuje samo tiste atribute ki so določeni s seznamom $s_1,...,s_n$

$$\pi_{s_{1},...,s_{n}} (R) $$

>[!|hide]- Primer
>Vzemimo relacijo (tabelo) **ZAPOSLENI**:
> 
> | Id | Ime | Oddelek | Plača |
> | :---: | :---: | :---: | :---: |
> | 101 | Ana | IT | 3500 |
> | 102 | Marko | Prodaja | 3200 |
> | 103 | Petra | IT | 4100 |
> | 104 | Luka | Prodaja | 3200 |
> 
> $$\sigma_{\text{Oddelek = ' IT '}} (\text{ZAPOSLENI})$$
> 
> | Id | Ime | Oddelek | Plača |
> | :---: | :---: | :---: | :---: |
> | 101 | Ana | IT | 3500 |
> | 103 | Petra | IT | 4100 |
> 
> $$\pi_{\text{Plača}} (\text{ZAPOSLENI})$$
> 
> | Plača |
> | :---: |
> | 3500 |
> | 3200 |
> | 4100 |


**Unija** deluje na dveh relacijah in vrne relacijo ki vsebuje vse $n$-terice relaije $R$ in $S$.
Eliminira duplikate.

Mora veljati **unijska združljivost** - ujemanje po **številu atributov** in **podatkovnem tipu domen**. 

>[!|hide]- Primer 
> $R$
> | Ime | Mesto |
> | :---: | :---: |
> | Peter | Ljubljana |
> | Ana | Maribor |
> | Maja | Celje |
> 
> $S$
> | Ime | Mesto |
> | :---: | :---: |
> | Maja | Celje |
> | Jure | Koper |
> 
> $$R \cup S$$
> 
> | Ime | Mesto |
> | :---: | :---: |
> | Peter | Ljubljana |
> | Ana | Maribor |
> | Maja | Celje |
> | Jure | Koper |



**Razlika** med relacijama $R$ in $S$ ($R - S$) vrne relacijo, ki vsebuje samo tiste $n$-terice (vrstice), ki so v $R$ in jih ni v $S$.

Za izvedbo operacije je potrebna **unijska združljivost**.

>[!|hide]- Primer
>
> $R$
> | Ime | Mesto |
> | :---: | :---: |
> | Peter | Ljubljana |
> | Ana | Maribor |
> | Maja | Celje |
>
> $S$
> | Ime | Mesto |
> | :---: | :---: |
> | Maja | Celje |
> | Jure | Koper |
>
> $$R - S$$
>
> **Rezultat:**
>
> | Ime | Mesto |
> | :---: | :---: |
> | Peter | Ljubljana |
> | Ana | Maribor |
> *(Vrstica 'Maja, Celje' je izključena, ker je prisotna v $S$.)*

**Presek** deluje na dveh relacijah in je v resnici kompozitska operacija.

$$R \cap S = R \backslash (R \backslash S)$$

Ker je sestavljena iz razlike potrebujemo **unijsko združljivost.**

**Kartezični produkt** je operacija na dveh relacijah in vrne relacijo z vsemi možnimi kombinacijami med vrsticami obeh relacij.


>[!|hide]- Primer
>
> $R$ = `ARTIKEL`
> 
> | Šifra | Naziv | Zaloga |
> | :---: | :---: | :---: |
> | A10 | Telovadni copati Nike | 10 |
> | A12 | Trenerka Bali | 4 |
> | BC80 | Moška jakna QuickSilver | 1 |
> | X12 | Ženska jakna QuickSilver | 0 |
>
> $S$ = `RAČUN`
> 
> | Račun | Šifra artikla | Količina |
> | :---: | :---: | :---: |
> | 15/05 | A10 | 1 |
> | 15/05 | X12 | 1 |
>
> $R \times S$
>
> | Šifra | Naziv | Šifra artikla | Količina |
> | :---: | :---: | :---: | :---: |
> | A10 | Telovadni copati Nike | A10 | 1 |
> | A10 | Telovadni copati Nike | X12 | 1 |
> | A12 | Trenerka Bali | A10 | 1 |
> | A12 | Trenerka Bali | X12 | 1 |
> | BC80 | Moška jakna QuickSilver | A10 | 1 |
> | BC80 | Moška jakna QuickSilver | X12 | 1 |
> | X12 | Ženska jakna QuickSilver | A10 | 1 |
> | X12 | Ženska jakna QuickSilver | X12 | 1 |

**Stik** je operacija ki združi kartezični produkt in selekcijo. Ena izmed bolj časovno kompleksnih operacij.

Obstaja več vrst stika:
- **Theta stik**
- **Ekvistik**
- **Naravni stik**
- **Odprti stik**
- **Delni stik**

**Theta stik** med $R$ in $S$ vrne vrstice ki zadoščajo predikatu $F$ kartezičnega produkta $R \times S$.

Predikat $F$ je oblike 

$$R.\text{atrR} \;\theta\; S.\text{atrS}$$

**Ekvistik** je theta stik omejen na enakost. 