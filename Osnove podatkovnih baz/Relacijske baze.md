
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



**Razlika** med relacijama $R$ in $S$ vrne relacijo, ki vsebuje samo tiste $n$-terice (vrstice), ki so v $R$ in jih ni v $S$.

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

$$R \bowtie_F S$$


Predikat $F$ je oblike 

$$R.\text{atrR} \;\theta\; S.\text{atrS}$$

**Ekvistik** je theta stik omejen na enakost. *Če je atribut skupen se v tabeli pojavi dvakrat (Za obe relaciji)*

**Naravni stik** $R$ in $S$ je vrsta ekvistika prek skupnih atributov relacij $R$ in $S$.

$$R \bowtie S$$

*V stiku ostane le en primerek skupnega atributa.*

**Odprti stik** je stik kjer lahko prikažemo vrstice ki nimajo vrednosti v stičnem atributu.
Poznamo **levo odprti** in **desno odprti** stik.

$$ R \rtimes S $$
$$ R \ltimes S $$

**Levi odprti stik** je stik kjer so $n$-terice $R$ ki nimajo para v $S$ s stičnim atributom, vključene v rezultat.
**Desni stik** je enako le da so vključene $n$-terice iz $S$ ki nimajo para v $R$.

**Delni stik** je relacija ki vsebuje tiste $n$-terice $R$ ki nastopajo v stiku s $S$ po stolpcu $F$.

$$ R \triangleright_F S $$

>[!|hide]- Primer
> 
> **R=ARTIKEL**
> 
> | Šifra | Naziv | Skladišče | Dobavitelj | Zaloga |
> | :---: | :---: | :-------: | :--------: | :----: |
> | A10 | Telovadni copati Nike | LJ | Nike | 10 |
> | BC80 | Moška jakna QuickSilver | LJ | Karma | 1 |
> | X12 | Ženska jakna QuickSilver | GO | Karma | 0 |
> 
> **S=SKLADIŠČE**
> 
> | Šifra | Kraj |
> | :---: | :---: |
> | LJ | Ljubljana, Tržaška 33 |
> | MB | Maribor, Prešernov trg 2 |
> | GO | Nova Gorica, Cankarjeva 2 |
> 
> $$ $$
> $$ R \triangleright_{R.\text{Skladišče} = S.\text{Šifra}} (\sigma_{\text{Šifra} = \text{'LJ'}} (S)) $$
> $$ $$
> 
> | Šifra | Naziv | Skladišče | Dobavitelj | Zaloga |
> | :---: | :---: | :-------: | :--------: | :----: |
> | A10 | Telovadni copati Nike | LJ | Nike | 10 |
> | BC80 | Moška jakna QuickSilver | LJ | Karma | 1 |



**Količnik** med $R$ in $S$ vrne relacijo z atributi $C$ ki jo sestavljajo $n$-terice iz $R$, ki so v parih z vsemi vrednostmi iz $S$.

*Količnik se izvaja pod predpostavko da sta $R$ in $S$ razdeljena na dva dela. Če imamo atribute $A$ in $B$ potem so atributi $R$ enaki $A \cup B$, in atributi $S$ = $B$.*

$$R/S$$
$$\color{light} =\pi_{A}(R)-\pi_{A}((\pi_{A}(R) \times S)-R)$$

>[!|hide]- Postopek
> Najprej določimo množico vseh potencialnih subjektov (npr. Kupec ID, če je to naš $A$), ki se nahajajo v relaciji $R$. To so vsi subjekti, ki so sploh kadarkoli izvedli nakup.
>
> Nato izračunamo kratezični produkt med množico vseh potencialnih subjektov in celotno množico delitelja $S$ (npr. vsi obvezni artikli 'Karma'). To ustvari **idealno relacijo**, ki vsebuje *vse* kombinacije, ki bi morale obstajati, če bi vsak subjekt kupil vsak obvezni artikel.
> 
> Od idealne relacije (vseh teoretičnih kombinacij) odštejemo dejansko relacijo $R$ (dejanske nakupe). Rezultat te razlike so **manjkajoče povezave**.
> 
> Manjkajoče povezave iz projektiramo nazaj samo na atribute $A$ (Kupec ID). S tem dobimo seznam vseh subjektov, ki jim **manjka vsaj ena povezava** z obveznimi entitetami iz $S$ (torej, kupec ni kupil vsaj enega artikla 'Karma').
> 
> Nazadnje, od celotne množice potencialnih subjektov (Korak 1) odštejemo tiste subjekte, ki jim nekaj manjka. Ostanemo samo z naborom subjektov, ki so povezani **z VSEMI** entitetami v delitelju $S$.

>[!|hide]- Primer
> $\pi_{\text{Šifra, Kupec}}$
> 
> | Šifra | Kupec |
> | :---: | :---: |
> | A10 | K1 |
> | A12 | K1 |
> | BC80 | K2 |
> | X12 | K3 |
> | A10 | K3 |
> | BC80 | K3 |
> | BC80 | K4 |
> | X12 | K4 |
> | A12 | K5 |
> 
> $\pi_{\text{Šifra artikla}} (\sigma_{\text{dobavitelj} = \text{'Karma'}} (S))$
> 
> | Šifra |
> | :---: |
> | BC80 |
> | X12 |
> 
> 
> $\pi_{\text{Šifra, Kupec}} (R) / \pi_{\text{Šifra artikla}} (\sigma_{\text{dobavitelj} = \text{'Karma'}} (S))$
> 
> | Kupec |
> | :---: |
> | K3 |
> | K4 |


***

**Agregatne operacije**

$$\Gamma_{AL}(R)$$

Agregat $\Gamma_{AL}$ aplicira seznam agregatnih funkcij $AL$ na relaciji $R$ in vrne agregirano relacijo.

$AL$ vsebuje enega ali več parov
$(\text{<agregatna funkcija>}, \text{<atribut>})$

Poznamo $\text{COUNT, SUM, AVG, MIN, MAX}$

>[!|hide]- Primer
> $$ \rho_R(\text{AvgCena}) \Gamma_{\text{AVG Cena}} (\sigma_{\text{Zaloga} > 0} (R)) $$
> 
> **R**
> 
> | Šifra | Naziv | Skladišče | Cena | Zaloga |
> | :---: | :---: | :-------: | :----: | :----: |
> | A10 | Telovadni copati Nike | LJ | 17.990 | 10 |
> | A12 | Trenerka Bali | MB | 6.750 | 4 |
> | BC80 | Moška jakna QuickSilver | LJ | 14.290 | 1 |
> | X12 | Ženska jakna QuickSilver | GO | 14.290 | 0 |
> 
> **Rezultat**
> 
> | AvgCena |
> | :-----: |
> | 13.010 |

***

**Zruževalne operacije**

$$\text{GA }\Gamma_{AL}(R) = $$

Relacijo ko jo dobimo vsebuje atribute $GA$ ter vrednosti ki jih dobim z agregati $AL$ kjer se združijo po istih vrednostih atributov iz $GA$.
***

**Preimenovanje** je operacije ki poeimenuje atributi ki ga dobimo z operacijami $\text{Op}$ nad relacijo $R$ z imenom $\text{Ime}$.

$$\rho_{R}(\text{AvgCena})\Gamma_{\text{AVG}Cena} (\sigma_{\text{Zaloga}>0}(R))$$

***

### SQL

Imamo operacije vrste **DML** oz. **Data manipulation langauge**, in **DDL** oz. **Data definition language**.

Pod DML spadajo **select, insert, update, delete**, namanjeni neposrednemu delu s podatki znotraj tabel. medtem ko pod DDL spadajo create, alter, set transaction, ki služijo definiranju in upravljanju strukture baze in njenih objektov.

**SQL**je enostaven, nepostopkoven, večnamenski, in je uveljaven kot standardni jezik za delo z relacijskimi bazami.
***
**DML skupine**

- SELECT, 
- UPDATE, 
- INSERT, 
- DELETE
***
**SELECT**

```sql
SELECT [DISTINCT|ALL]
{*|[columnExpression[AS newName]][,...]}
FROM table-name [alias][,...]
[WHERE condition]
[GROUP BY columnList] 
[HAVING condition]
[ORDER BY columnList]
```

`SELECT` določa stolpce ki naj se pojavijo v izhodni relaciji.
`FROM` določa tabele za poizvedbo
`WHERE` filtrira vrstice
`GROUP BY` Združuje vrstice po vrednostih izbranih stolpcev
`HAVING` Filtrira skupine glede na določene pogoje
`ORDER BY` Določa vrstni red vrstic na izhodu

Vrstnega reda sklopov ni možno spreminjati, obvezna pa sta le `SELECT` in `FROM` sklopa.

SQL izrazi so **neobčutljivi** na velikost črk.

Rezervirane besede SQL ne smemo uporabljati za definicije.

```sql
select * from table-name;
//Izbere vse stolpce iz tabele.

select col1, col2 from table-name;
//Izbere stolpca col1 in col2 iz tabele.

select distinct atr-name from table-name;
//Izpiše vse distinktne vrednosti ki nastopajo v stolpcu.

select first_name, last_name, birth_date, hire_date, DATEDIFF(hire_date, birth_date)/365 as 'Starost ob zaposlitvi' from employees;
//ali
select first_name, last_name, YEAR(hire_date)-YEAR(birth_date) as 'Starost ob zaposlitvi' from employees;
//Izpiše starost ob zaposlitvi
```

Primeri funkcij v mySQL SUPB


| Name | Description | Example SQL Usage | Example Result (Based on hypothetical input) |
| :--- | :--- | :--- | :--- |
| **ADDDATE()** | Add time values (intervals) to a date value | `SELECT ADDDATE('2024-06-01', INTERVAL 5 DAY);` | `2024-06-06` |
| **ADDTIME()** | Add time | `SELECT ADDTIME('10:00:00', '01:30:00');` | `11:30:00` |
| **CONVERT\_TZ()** | Convert from one timezone to another | `SELECT CONVERT_TZ('2024-06-01 10:00:00', 'UTC', 'EST');` | `2024-06-01 06:00:00` |
| **CURDATE()** | Return the current date | `SELECT CURDATE();` | `2024-10-27` (Current Date) |
| **CURRENT\_DATE(),** | Synonyms for CURDATE() | `SELECT CURRENT_DATE;` | `2024-10-27` (Current Date) |
| **CURRENT\_TIME(),** | Synonyms for CURTIME() | `SELECT CURRENT_TIME();` | `14:35:50` (Current Time) |
| **CURRENT\_TIMESTAMP()** | Synonyms for NOW() | `SELECT CURRENT_TIMESTAMP;` | `2024-10-27 14:35:50` (Current Datetime) |
| **CURTIME()** | Return the current time | `SELECT CURTIME();` | `14:35:50` (Current Time) |
| **DATE\_ADD()** | Add time values (intervals) to a date value | `SELECT DATE_ADD('2024-01-01', INTERVAL 3 MONTH);` | `2024-04-01` |
| **DATE\_FORMAT()** | Format date as specified | `SELECT DATE_FORMAT(NOW(), '%W, %M %D, %Y');` | `Sunday, October 27th, 2024` |
| **DATE\_SUB()** | Subtract a time value (interval) from a date | `SELECT DATE_SUB('2024-06-30', INTERVAL 1 WEEK);` | `2024-06-23` |
| **DATE()** | Extract the date part of a date or datetime expression | `SELECT DATE('2024-10-27 15:45:00');` | `2024-10-27` |
| **DATEDIFF()** | Subtract two dates (returns difference in days) | `SELECT DATEDIFF('2024-07-01', '2024-06-01');` | `30` |
| **DAY()** | Synonym for DAYOFMONTH() | `SELECT DAY('2024-11-15');` | `15` |
| **DAYNAME()** | Return the name of the weekday | `SELECT DAYNAME('2024-11-15');` | `Friday` |


**Iskalni kriteriji**

Izpiši vse zaposlene, ki so moškega spola in so rojeni pred 1953. 

```sql
select * from employees 
where YEAR(birth_date)<1953 and gender = 'M';
```

Uporaba logičnih operatorjev kot so and, or, not, =, <, <=, != pri `where`.

Posebnejši: 
- between (preverja vrednosti v intervalu), 
- like(preverja po nekeme vzorcu npr. `A%`), 
- in (preverja vrednosti v podanem seznamu), 
- is null, 
- is not null, 
- **all**, 
- **any**, 
- **exists**

kjer so all, any in exists uporabljeni pri poizvedbi na drugi tabeli.

**All** - gledamo ali je cena večja od vseh v drugi tabeli.

```sql
SELECT ime_izdelka, cena FROM Izdelki 
WHERE cena > ALL ( 
SELECT cena FROM Izdelki 
WHERE oddelek = 'Oblačila' );
```

**Any** - gledamo ali je cena večja od vsaj ene v drugi tabeli

**Exsists** - gledamo če je 

```sql
SELECT id_izdelka, ime_izdelka FROM Izdelki I WHERE EXISTS ( SELECT 1 FROM Narocila N WHERE N.id_izdelka = I.id_izdelka );
```

*Select 1 je sintaksa kjer pri njeni uporabi preverjamo le obstoj vrstice in ne zaravljamo časa z branjem in prenašanjem dejanskih podatkov ampak preverjam le obstoj vrstice; 1 je le standardna konstanta, lahko bi pisalo tudi selet NULL, select  'A'...*

**Leta** so shranjena po `YYYY-MM-DD`, **čas** je srhanjen kot `HH:MM:SS`, **datetime** pa kot `YYYY-MM-DD HH:MM:SS`.

Obstaja tudi `CAST`: 
```sql 
SELECT CAST('2025-10-27' AS DATE);
```

Primer iskanja po članstvu v množici

```sql
select * from titles 
where title in ('Staff', 'Senior Staff');
```


Primer iskanja z vzorcem

```sql
select * from employees 
where last_name like 'B%' and birth_date like '__6_____01';
//Imena ki se začnenjo na B in rojeni prvega v mesecu v šestedesetih
```

Iskanje z NULL

```sql
select * from employees 
where hire_date is null;
```

**Sortiranje vrstic**

```sql
select emp_no, last_name, birth_date from employees 
order by last_name, birth_date desc;
```

**Agregiranje podatkov**

ISO standard definira pet agregarnih operacij
- `COUNT` - število vrednosti
- `SUM` - seštevek vrednosti
- `AVG` - povprečje vrednosti
- `MIN` - minimalna vrednost
- `MAX` - največja vrednost

Vse delujejo samo na enem stolpcu.
`COUNT, MIN, MAX` se uporabljajo z numeričnimi in nenumeričnimi vrednostmi,
`SUM, AVG` zahtevata na numerične vrednosti

Vse operacije razen `COUNT(*)` najprej odstranijo vrstice `NULL`  po katerem agregirajo.



