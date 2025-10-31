
V teoriji računljivosti uporabljamo idealiziran računalnik, imenovan **računski model** (*computational model*). Kot pri vsakem modelu v znanosti je lahko računski model natančen v nekaterih pogledih, v drugih pa morda ne. Zato bomo uporabljali več različnih računskih modelov, odvisno od lastnosti, na katere se želimo osredotočiti. Začnemo z najpreprostejšim modelom, imenovanim **končni avtomat** (*finite state machine* ali *finite automaton*).

***
**KONČNI AVTOMATI**

Končni avtomati so dobri modeli za računalnike z izjemno omejeno količino pomnilnika. Kaj lahko računalnik stori s tako majhnim pomnilnikom? Veliko koristnih stvari! Pravzaprav s takimi računalniki ves čas komuniciramo, saj so v središču različnih elektromehanskih naprav.

Krmilnik za avtomatska vrata je en primer take naprave. Pogosto jih najdemo na vhodih in izhodih supermarketov; avtomatska vrata se odprejo, ko krmilnik zazna, da se oseba približuje. Avtomatska vrata imajo podlogo...

Literatura Sipser razdelka 1.1 in 1.2 

**Kodiranje podatkov**

Če imamo abecedo $\Sigma$ lahko predstavimo nek matematični objekt s simboli.

$$X \rightarrow \Sigma^*$$

Iščemo neko funkcijo za katero velja da lahko predstavimo matematičen objekt iz $X$ v neko abecedo $\Sigma^{*}$ oz. hočemo funkcijo ki lahko preslika nek matematičen objekt v neke simbole.

$X$ je nabor objektov ki jih želimo kodirati.

$\Sigma$ je nabor simbolov

$\Sigma^{*}$ je nabor vseh možnih **končnih zaporedj** iz abecede $\Sigma$.

Funkciji pa pravimo **algoritem**.
***
Števila so oz. naravna števila lahko kodiramo ne več načinov.

$\mathbb{N} \rightarrow \Sigma^{*}$

**Eniško kodiranje**

$$n \rightarrow a^{n}$$

število $n$ je predstavljeno z $n$ ponovitvami enega simbola.

$\Sigma$ je abeceda z enim samim simbolom.

**Pozicijski številski sistem**

$$n \rightarrow s_{0}s_{1}...s_{m-1}$$
$$n = \sum_{i=0}^{m-1}k^{i}s_{i}$$

***

Govorimo tudi o zaporedjih števil, simbolično vpeljujemo ločila.

Pojem lahko razširimo na množice kot matematični objekt.

Grafe tudi lahko predstavimo kot zaporedje parov  števil (vozlišč.)

***

Kodo objekta $X$ zapišemo

$$\langle X \rangle$$

**Reševanje problemov**

Določanje ali nek string paše ali ne v množico rešitev $L$ (verjetno)

$$\langle x \rangle \in L$$

Hočemo nek avtomat / algoritem ki za nek objekt $\langle x \rangle$ vrne da ali ne.

>[!|hide]- 
>Seveda, tukaj gre za temeljne koncepte **Teorije izračunljivosti (Computational Theory)** in **Teorije formalnih jezikov (Theory of Formal Languages)**, ki predstavljata matematični temelj računalništva in določata, kaj je sploh mogoče izračunati oziroma avtomatizirati.
> 
> ### Razlaga konceptov
> 
> #### 1. Notacija: Kodna beseda objekta ($\langle X \rangle$)
> 
> Zapis $\langle X \rangle$ je standardna matematična notacija v teoriji izračunljivosti. Pomeni:
> 
> *   **Kodna beseda (Encoding):** Označuje konkreten **niz simbolov** (string) iz abecede $\Sigma^*$, ki služi kot reprezentacija (koda) za abstraktni matematični objekt $X$.
> *   **Objekt $X$:** Je lahko karkoli: število, graf, funkcija, Turingov stroj, algoritem, drugi formalni jezik, itd.
> *   **Vloga:** Zagotavlja matematični most med *abstraktnimi* objekti in *konkretnimi* vhodnimi podatki (nizi, stringi), ki jih lahko obdela avtomat ali algoritem.
> 
> **Primer:** Če je $X$ Turingov stroj $M$, potem je $\langle M \rangle$ niz ničel in enic, ki je opis samega stroja.
> 
> #### 2. Reševanje problemov in Množica rešitev ($L$)
> 
> Tu se osredotočimo na **odločitvene probleme (Decision Problems)**: to so problemi, na katere je mogoče odgovoriti zgolj z **DA** ali **NE**.
> 
> *   **Jezik $L$ (Množica rešitev):** V teoriji formalnih jezikov se množica vseh kodnih besed $\langle x \rangle$, ki ustrezajo pozitivnemu odgovoru na problem, imenuje **jezik $L$**.
>     *   $L$ je torej formalna definicija problema. Vsebuje natanko tiste nize (kodi), ki "rešijo" problem.
>     *   **Zapis $\langle x \rangle \in L$:** To pomeni, da za dani vhod $\langle x \rangle$ rešitev problema pravi **DA**.
> 
> *   **Primer problema (Je število $x$ praštevilo?):**
>     *   $X = \mathbb{N}$ (naravna števila).
>     *   $L$ je množica vseh kod $\langle x \rangle$, ki predstavljajo praštevila (npr. $\langle 2 \rangle, \langle 3 \rangle, \langle 5 \rangle, \dots$).
>     *   Če je $\langle x \rangle = \langle 7 \rangle$, je $\langle 7 \rangle \in L$ (DA). Če je $\langle x \rangle = \langle 4 \rangle$, potem $\langle 4 \rangle \notin L$ (NE).
> 
> #### 3. Avtomat/Algoritem (Model izračuna)
> 
> Iščemo mehanizem, ki bo za vsak vhodni niz izvedel to odločitev (preveril, ali je niz v jeziku $L$).
> 
> *   **Avtomat/Algoritem:** Je matematični model za izvajanje izračunov (računalnik). Najbolj splošen model je **Turingov stroj (Turing Machine)**.
> *   **Cilj:** Želimo algoritem $A$ (ali Turingov stroj $M$), ki za vhod $\langle x \rangle$ vrne:
>     *   **DA (Sprejmi):** če $\langle x \rangle \in L$.
>     *   **NE (Zavrni):** če $\langle x \rangle \notin L$.
> 
> #### Ključni pojmi, povezani s tem
> 
> 1.  **Odločljivost (Decidability):** Problem je **odločljiv**, če obstaja algoritem (Turingov stroj), ki se **vedno ustavi** za vsak vhod $\langle x \rangle$ in pravilno vrne DA ali NE.
> 2.  **Sprejemljivost (Recognizability) ali Rekurzivna števnost:** Problem je **sprejemljiv**, če obstaja algoritem, ki se **ustavi in vrne DA** za vse $\langle x \rangle \in L$, vendar pa se za $\langle x \notin L \rangle$ morda **ne ustavi** (lahko teče v neskončnost).
> 3.  **Neodločljivost (Undecidability):** Problem je **neodločljiv**, če zanj **ne obstaja** algoritem (Turingov stroj), ki bi se *vedno* ustavil in dal pravilen odgovor (DA/NE). Klasičen primer je **Problem ustavljanja (Halting Problem)**, ki je dokazano neodločljiv.
> 
> **Skratka:** Vaša vprašanja vas vodijo neposredno v osrčje **Teorije računanja**, ki se ukvarja z ugotavljanjem:
> a) Kaj je sploh mogoče avtomatizirati (izračunljivost)?
> b) Kako učinkovito (hitro in z malo spomina) je to mogoče storiti (teorija kompleksnosti - P/NP)?

***

**Deterministični končni avtomati** 
*Deterministic final automata*

| Stanje $Q$ | 0 |  1 |
| :---: | :---: | :---: |
| **$q_0$** | $q_0$ | $q_1$ |
| **$q_1$** | $q_2$ | $q_1$ |
| **$q_2$** | $q_0$ | $q_1$ |

iz tega lahko z nekim stringom kot za vhod $w = 011011$ določimo neko sled izvajanja

>[!|hide]- Potek
| Korak | Trenutno stanje | Vhodni simbol | Naslednje stanje (iz tabele) |
| :---: | :---: | :---: | :---: |
| **Start** | $q_0$ | | |
| **1.** | $q_0$ | **0** | $q_0$ ($\delta(q_0, 0) = q_0$) |
| **2.** | $q_0$ | **1** | $q_1$ ($\delta(q_0, 1) = q_1$) |
| **3.** | $q_1$ | **1** | $q_1$ ($\delta(q_1, 1) = q_1$) |
| **4.** | $q_1$ | **0** | $q_2$ ($\delta(q_1, 0) = q_2$) |
| **5.** | $q_2$ | **1** | $q_1$ ($\delta(q_2, 1) = q_1$) |
| **6.** | $q_1$ | **1** | $q_1$ ($\delta(q_1, 1) = q_1$) |
| **KONEC** | $q_1$ | | |

$$q_0 \xrightarrow{0} q_0 \xrightarrow{1} q_1 \xrightarrow{1} q_1 \xrightarrow{0} q_2 \xrightarrow{1} q_1 \xrightarrow{1} q_1$$

**Formalna definicija**

$$M = (Q, \Sigma, q_{0}, F, \delta)$$

- $Q$ je **končna** množica stanj
- $\Sigma$ je **končna** abeceda
- $q_{0} \in Q$ je začetno stanje
- $F \subset Q$ je množica končnih stanj
- $\delta: Q \times \Sigma$ je **totalna** funkcija prehodov
  
  
**Totalna** pomeni da je definirana za poljuben simbol abecede v poljubnem stanju

Tipično jih definiramo **grafično**. **Dvojno obkrožen krog je končno stanje oz. je del $F$.**

Končne avtomate podajamo z diagrami prehodov, tabelami, zapisi delta funckije.

Izvajanje $\delta' : Q \times  \Sigma^{*} \rightarrow Q$

1. $\delta'(q, \varepsilon) = q$
2. $\delta'(q,xa) = \delta(\delta'(q,x),a); a \in \Sigma, x \in \Sigma^{*}$

$\delta'$ je funkcija ki prebere celoten niz znakov, $\delta$ pa samo enega.

$\delta'$ formalizira celotno sled izvajanja.

Da predstavimo jezik ki ga sprejme avtomat $M$ zapišemo

$L(M) = \{ w \in \Sigma^{*} ; \delta'(q_{0},w) \in F\}$

kjer je $M$ jezik avtomata - podmnožica nizov ($\Sigma^{*}$).
Vsi nizi ki pridejo do nekega končenga stanja v množici $F$.

Torej je $L$ množica vseh nizov ki avtomat $M$ pripeljejo iz začetnega stanja v neko končno stanje. 

Če ni se niz zavrže in ni del jezika avtomata.

Poglejmo primere - vedno naj bo $\Sigma = \{ 0,1\}$

**Primer 1**

$$L = \emptyset$$

$$F = \{ \}$$

**Primer 2**

$$L = \Sigma^{*}$$
$$F = \{ q_{0}\}$$
q0: 1 : q0, 0 : q0

**Primer 3**

$$L = \{ 01, 10, 0001\}$$
$$...$$

**Primer 4**

$$L = \{ w \,;\; \text{število 0 je sodo, število 1 je liho}\}$$
$$\text{npr. 00111} - \text{sodo 0 in liho 1}$$


**Primer 5**

$$L = \{ w \in \{ 0,1\}^{*} \,;\; \text{beseda predstavlja število v dvojiškem sistemu deljivo s 3}\}$$

*Gleda se po ostankih*

***

**Nedeterminizem**

Končne avtomate delimo na **deterministične** in **nedeterministične**.

Nedeterminizem pomeni da za dano stanje in vhodni simbol avtomat **nima nujno samo ene** poti v naslednje stanje.

Avtomat lahko ima **več kot en prehod**, **nič možnih prehodov**, prehod prek **praznega niza**.

**Formalna razlika**

$$\delta: Q \times (\Sigma \cup \{ \varepsilon\}) \rightarrow 2^{Q}$$

Prehod se lahko zgodi brez da bi prebral vhodni simbol - $\varepsilon$-prehodi.

Ker dovoljujemo prehod v več stanj je NDA po prebranem vhodnem nizu sočasno v **množici stanj** $2^{Q}$

Niz $w$ je sprejet če **obstaja vsaj ena pot** iz začetnega stanja $q_{0}$ ki vodi v eno od končnih stanj $F$.

$\varepsilon$-prehod spremeni stanje brez da preberemo vhodni znak.

$$\delta'(q,\varepsilon) = \{ q\}$$
$$\delta'(q,xa) = \bigcup_{p \,\in\, \delta'(q,x)} \delta(p,a)$$

Jezik NKA

$$L(M) = \{ w \in \Sigma^{*} \,;\;\delta'(q_{0} ,w) \cap F \neq \emptyset\}$$

**Primer 1**

$$L = \{ aab, abb,aaaa\}$$


**Eno uro sm spustu kle ampak mislm da je blo o avtomatih naprej al neki**

*Poljuben reulgarni izraz lahko zapišemo s končnim avotmatom in obranto*

***


**Regularni izrazi in avtomati, neregularnost**


**Posplošeni nedeterminirani končni avtomati (PNKA)** imajo namesto prehodnih simbolov, kar regularne izraze, torej so prehodi med stanji označeni z regulranimi izrazi.

Sedaj bo vedno samo ena puščica med dvema stanjema.

Obstaja neka **posebna oblika** - obstaja samo eno začetno stanje in samo eno končno stanje.
Nimamo prehodov v začetno stanje, brz prehodov iz končnega stanja.
Med vsakim ostalim parom stanj pa obstaja prehod - torej vsak je povezan z vsakim.

Le-ta se uporablja za dokaz ekvivalence med reg. izrazi in končnimi avtomati.

Če začnemo z nekim končnim avtomatom ga hočemo spremeniti v PNKA.

Ker nočemo povezav vzačetno stanje naredimo novo začetno stanje in prehod v nasldnje označimo z $\varepsilon$, kot naredimo tudi novo končno stanje in povezavo $\varepsilon$ v njega.

Med vsakima dvema stanjema $q_i$ in $q_j$ (razen iz $q_{accept}$ in v $q_{start}$) mora obstajati natančno en prehod, označen z regularnim izrazom. Če med $q_i$ in $q_j$ ni prehoda, ga označimo s praznim jezikom ($\emptyset$). Če med njima obstaja več prehodov, jih združimo z operacijo unije ($\cup$).

PNKA definiramo z 

$$M =\langle Q,\Sigma, \delta ,q_{s},q_{e} \rangle$$

$$\delta: (Q\backslash \{ q_{e}\}) \times (Q\backslash \{ q_{s}\}) \rightarrow RI $$

$RI$ so regulratni izrazi
Funkcija delta slika med vsemi stanji razen začetnim in končnim, funkcija pa so regularn izrazi.

Jezik PNKA

$$L(M) = \{ w=w_{1}...w_{n} \,;\;\exists q_{s}q_{1}...q_{e},w_{i} \in L(\delta(q_{i-1},q_{i}))\}$$

$$q_{0}= q_{s}$$

$$ q_{n}= q_{e}$$

$w$ je sprejemni niz če obstaja pot iz $q_s$ v $q_{e}$, del besede $w_{i}$ se mora ujemati z nekim izrazom na prehodu $\color{light}w_{i}\in L(\delta(q_{i-1},q_{i} ))$




	
Dokaz se nadaljuje z zmanjševanjem števila notranjih stanj. V vsakem koraku odstranimo eno notranje stanje $q_{x}$ in ustrezno posodobimo regularne izraze na vseh prehodih, ki so šli skozi $q_{x}$.

**Za vsak par stanj $q_i$ in $q_j$ (ki nista $q_{x}$):**

Prehod $q_i \to q_j$ se posodobi z regularnim izrazom, ki zajame poti, ki so prej šle:
1.  **Direktno** iz $q_i$ v $q_j$
2.  Iz $q_i$ v $q_{x}$, poljubno število zank v $q_{x}$, in nato iz $q_{x}$ v $q_j$.

**Formalna posodobitev prehoda:**

$$R'_{ij} = R_{ij} \cup (R_{i, x} (R_{x, x})^* R_{x, j})$$

Kjer:
*   $R'_{ij}$ je nov regularni izraz med $q_i$ in $q_j$.
*   $R_{ij}$ je stari regularni izraz med $q_i$ in $q_j$.
*   $R_{i, x}$ je izraz iz $q_i$ v $q_{x}$.
*   $(R_{x, x})^*$ je Kleenejeva zvezda za zanko na $q_{x}$.
*   $R_{x, j}$ je izraz iz $q_{x}$ v $q_j$.

>Izrek
>$$\forall G \in \text{PNKA} : L(G) = L(\text{convert}(G))$$
>Hočemo da je jezik originalnega avtomata enak jeziku avtomata z eliminiranimi stanji.

>[!|dokaz]- Dokaz:
> Hočemo dokazati da če vzamemo poljubno stanje $q_{x}$ potem se ohranja jezik oz. je jezik novega $G'$ enak jeziku $G$.
>Pri število stanj je $|Q| = 2$ je trivialno in drži.
>Indukcijski korak:
>Predpostavimo da izrek drži za $k-1$ stanj in pokažimo da držu tudi za $G$,
> torej moramo pokazati
>$$w \in L(G) \Leftrightarrow w \in L(G')$$
>$\Rightarrow$
>$q_{s}q_{1}...q_{e}$ je zaporedje ki sprejema $w$ v avtomatu $G$ in $w_{1}w_{2}...w_{n}$ je pripadajoče razbitje beede $w$.
>*Predpostavljamo da je $L(G') = L(\text{convert}(L(G')))$*
>a) $q_x$ ni v tem zaporedju, potem isto zaporedje sprejema $w$ v $G'$.
>b) $q_x$ je v tem zaporedju, potem odstranimo vse pojavitve $q_x$ iz zaporedja (pripadajoče besede staknemo) in dobimo veljavno zaporedje stanj.
>...
>vrjetn lahko z ai



**Lema o napihovanju**

Za vsak regularni jezik $L$ obstaja konstanta $n$ da za vsako besedo $w \in L$ ki je daljša od $n$ lahko razbijemo na 3 komponente:

$w = xyz$

za katere velja

$|y| > 0$
$|xy| \leq n$
$\forall i \geq 0 : xy^{i}z \in  L$





































