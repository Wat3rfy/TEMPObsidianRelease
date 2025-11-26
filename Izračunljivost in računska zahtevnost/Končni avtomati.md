
V teoriji računljivosti uporabljamo idealiziran računalnik, imenovan **računski model** (*computational model*). 

Obstaja jih več odvisno od potrebovanih lastnosti.

Začnemo z najpreprostejšim modelom - **končni avtomat** (*finite state machine* ali *finite automaton*).

**Končni avtomat** je model račnunalnika z močno omejenim pomnilnikom.

Končni avtomat lahko predstavimo z diagramom stanj. Sestavljen je iz začetnih stanj, vmesnih stanj in končnih oz sprejemnih stanj. Med njimi so puščice - prehodi.

Če dobimo nek vhod kot je 1101 dobimo izhod kot je sprejetost ali zavrnitev. Pravimo da je izhod tipe ja/ne. Ko pridemo do konca pogledamo če smo v končnem stanju - če smo vrnemo ja drugače ne.


Končni avtomat definiramo kot 5-terico $M = (Q,\Sigma, \delta, q_{0}, F)$, kjer so
- $Q \text{ : končna množica vseh stanj}$
- $\Sigma : \text{ končna množica simbolov oz. vhodna abeceda}$
- $\delta : Q \times \Sigma \rightarrow Q : \text{prehodna funkcija}$
- $q_{0} \in Q : \text{ začetno stanje}$
- $F \subset  Q : \text{ množica končnih stanj}$

Lahko uprabljamo tudi notacijo $\langle \text{objekt}\rangle$, kjer to predstavlja nek simbol iz abecede.

Iz vskaega stanja pelje natanko ena puščica za vsak simbol iz abecede. Torej mora biti v DKA Točno $|Q| \cdot |\Sigma|$.

Če je $A$ jezik ki jih avtomat $M$ sprejme pravimo da je $A$ jezik $M$ oz. $L(M) = A$.
Avtomat vedno sprejeme natanko en jezik.

> Imamo $M  = (Q, \Sigma, \delta, q_{0}, F)$ in $w = w_{1}...w_{n}$ je  niz sestavljen iz abecede $\Sigma$. $M$ sprejme $w$ če velja da obstaja zaporedje stanj $r_{0},...,r_{n}$ v $Q$ da velja
> 
> $$r_{0} = q_{0}$$
> $$\delta(r_{i},w_{i+1}) = r_{i+1} \,;\; \forall i \in \{ 0,...n-1\}$$
> $$r_{n} \in F$$
> 
> Pravimo da $M$ sprejme jezik $A$ če je $A = \{ w \,;\; M \text{ sprejme } w\}$


> Definirajmo funkcije $\delta' : Q \times \Sigma^* \to Q$
> 
> 1. ${\delta'}(q, \varepsilon) = q$
> 2. ${\delta'}(q, xa) = \delta({\delta'}(q, x), a) ; a \in \Sigma, x \in \Sigma^*$
> 
> Jezik končnega avtomata pa bo tako
> 
> $$L(M) = \{ w \in \Sigma^{*} \,;\; \delta' (q_{0},w) \in  F\}$$

Jezik je **regularen** če obstaja končni avtomat ki ga sprejme.

Konstrukcija končnega avtomata temelji na prepoznavanju nekih končno mnogih stanj med katerimi moramo razločevati npr. sodost lihost simbola, ostanek pri deljenju simbola, kateri so trenutni končni znaki, pojavitev števila zaporednih črk,...

Nad ragularnimi jeziki definiramo regularne operacije **unija, konkatenacija in zvezda**:
- $A \cup B = \{ x \;;\; x \in A \lor x \in B\}$
- $A \circ B = \{ xy \;;\; x \in A \land y \in  B \}$
- $A^{*} = \{ x_{1}x_{2}...x_{k} \,;\;k \geq 0 \land x_{i}\in A\}$

Poleg teh operacij ohranjajo regularnost tudi
- Presek $L_{1} \cap L_{2}$
- Komplement $L^{C}$
- Razlika $L_{1}\backslash L_{2}$
- Obrat $L^{R}$
- Homomorfizem $f(L)$

$A^{*}$ vedno vsebuje $\varepsilon$.

>Unija, konkatenacija in zvezda so zaprte operacije za regularne jezike.
>>[!|dokaz]+ Dokaz:
>> Za dokaz uporabimo nedeterministične končne avtomate, kjer rečemo da za $L_{1}$ in $L_{2}$ obstajata avtomata $M_{1}$ in $M_{2}$.
>> Za unijo lahko definiramo novo začetno stanje in povežemo preko $\varepsilon$ z začetnimi stanji $M_1$ in $M_{2}$. 
>> Za konkatenacijo vzamemo $M_1$ in iz vsakega končnega stanja dodamo $\varepsilon$ prehod v začetno stanje $M_{2}$. Sedaj so sprejemna stanja le še $M_2$.
>> Za zvezdo ustvarimo novo začetno stanje ki je hkrati sprejemno, dodamo epsilon prehod iz novega začetnega tanja v staro začetno stanje $M_{1}$ in iz vbseh starih sprejemnih stanj dodamo $\varepsilon$ prehod v staro začetno stanje $M_{1}$.

**Nedeterministični končni avtomati** so avtomati kjer velja da lahko iz vsakega stanja gremo v več stanj za nek vhod. Za sprejemanje besede mora veljati da obstaja vsaj 1 pot do končnega stanja, teh je lahko več, dopuščamo pa tudi $\varepsilon$-prehode kar so prehodi brez vhoda.

Velja da je NKA 5-terica $M = (Q, \Sigma, \delta, q_{0}, F)$
kjer velja vse enako kot pri DKA le da je 
$\delta : Q \times \Sigma   \rightarrow P\{ Q\}$

$\delta$ lahko vrne prazno množico kot izhod kar ne pomeni da smo sprejeli stanje temveč da je pot umrla.

NKA $N = (Q, \Sigma, \delta, q_{0}, F)$ sprejme $w = y_{1}...y_{n}, y_{i} \in \Sigma_\varepsilon$ natanko tedaj ko velja da je 
- $r_{0} = q_0$
- $r_{i+1}\in  \delta(r_{i} , y_{i+1}) \,;\; i \in \{ 0,...,n-1\}$ 
- $r_{n} \in  F$

Pravimo da je prehodna funkcija oblika

1. $$\delta' (q,\varepsilon) = \{ q\}$$
2. $$\delta' (q,xa) = \bigcup_{p \in  \delta'(q,x)} \delta(p,a)$$


Jezik NKA potem definiramo
$$L(M) = \{ w \in \Sigma^{*} \,;\; \delta'(q_{0},w) \cap F \neq \emptyset\}$$



Če definiramo še $\varepsilon$-NKA kot NKA kjer v abecedo vključimo še prazen niz.

Definirajmo še $\varepsilon$ zaprtje nekega stanja kot množica vseh stanj ki jih lahko dosežemo iz nekega stanja preko $\varepsilon$ prehodov oz. preko praznih nizov.

Za vsako stanje velja da preko praznega niza pridemo nazaj vanj oz. je implicitno.

> Velja, da za vsak NKA obstaja ekvivalenten DKA. To dosežemo s **podmnožično konstrukcijo**, kjer množico trenutnih stanj NKA obravnavamo kot eno stanje DKA. Če ima NKA $n$ stanj, jih ima DKA v najslabšem primeru $2^n$.
>>[!|dokaz]- Dokaz:
> > **Smer DKA $\Rightarrow$ NKA:** Trivialno, saj je vsak DKA le poseben primer NKA (brez nedeterminizma in $\epsilon$-prehodov).
> >
> > **Smer NKA $\Rightarrow$ DKA:**
> > Konstruiramo DKA $M$ iz NKA $N$:
> > 1. **Stanja:** Množica stanj $M$ je **potenčna množica** stanj $N$ (oznaka $2^{Q_N}$). Vsako stanje v DKA torej predstavlja *množico* stanj iz NKA.
> > 2. **Začetno stanje:** Vsebuje začetno stanje $N$ in vsa stanja, dosegljiva z $\epsilon$-prehodi ($\epsilon$-zaprtje).
> > 3. **Prehodi:** Za stanje $R = \{q_i, \dots\}$ (ki je množica stanj NKA) in simbol $a$ je prehod unija vseh možnih prehodov v NKA:
> >    $$\delta_{M}(R, a) = \bigcup_{q \in R} \delta_{N}(q, a)$$
> > 4. **Končna stanja:** So tiste podmnožice v $M$, ki vsebujejo **vsaj eno** končno stanje iz $N$.
> >
> > Tak DKA simulira izvajanje NKA tako, da sledi vsem možnim potem hkrati. Beseda je sprejeta, če se simulacija konča v množici, ki vsebuje končno stanje.

Jezik je regularen natanko tedaj, ko ga prepozna nek nedeterministični končni avtomat.

***

**Regularni izrazi**

$R$ je **regularni izraz** če velja da je $R$
- $a$ za nek $a$ v $\Sigma$
- $\varepsilon$
- $\emptyset$
- $R_{1} + R_{2}$
- $R_{1}R_{2}$
- $R_{1}^{*}$
  
Potem pa lahko še definiramo $R^{+}$ kot $RR^{*}$ in $R^{k}$ kot staknjenje $k$ $R$-jev.

Veljajo naslednje identitete:
- $R + \emptyset = R$
- $R \varepsilon = R$
- $R + \varepsilon$ je nova množica ki bsebuje vse nize iz jezika $R$ in prazen niz
- $R \emptyset = \emptyset$ je uničvelen element

Za naslednji izrek potrebujemo PNKA oz. posplošen nedeterminističen končni avtomat kjer lahko za prehodne funkcije uporabljamo regularne izraze kot vhodne spremenljivke.

>Jezik je regularen natanko tedaj ko je jezik regularnega izraza. 
>>[!|dokaz]- Dokaz:
> > 
> >Smer ($\Leftarrow$): Vsak regularni izraz opisuje regularen jezik
> >
> > **Cilj:** Če imamo regularni izraz $R$, moramo dokazati, da obstaja končni avtomat, ki sprejme $L(R)$.
> > 
> > **Dokaz (z indukcijo po zgradbi izraza - Thompsonova konstrukcija):**
> > Dokazujemo, da za vsak regularni izraz lahko zgradimo $\epsilon$-NKA (nedeterministični končni avtomat z $\epsilon$-prehodi). Ker vemo, da je $\epsilon$-NKA enakovreden DKA (determinističnemu avtomatu), je jezik regularen.
> > 
> > 2.  **Osnovni primeri:**
> >     *   $\emptyset, \epsilon, a$ (kjer je $a \in \Sigma$): Za vsakega od teh je trivialno zgraditi preprost avtomat.
> > 2.  **Induktivni korak:** Predpostavimo, da za izraza $R_1$ in $R_2$ že imamo avtomata $M_1$ in $M_2$.
> >     *   **Unija ($R_1 + R_2$):** Zgradimo nov avtomat z novim začetnim stanjem, ki ima $\epsilon$-prehod na začetni stanji $M_1$ in $M_2$.
> >     *   **Stik ($R_1 R_2$):** Povežemo končna stanja $M_1$ z začetnim stanjem $M_2$ preko $\epsilon$-prehodov.
> >     *   **Kleenejeva zvezdica ($R_1^*$):** Dodamo $\epsilon$-prehode iz končnih stanj $M_1$ nazaj na začetek in omogočimo "preskok" celotnega avtomata (za prazno besedo).
> > 
> > **Zaključek:** Ker lahko za vsak operater zgradimo $\epsilon$-NKA, je jezik regularnega izraza regularen.
> > 
> > ---
> > 
> > Smer ($\Rightarrow$): Vsak regularen jezik se da opisati z regularnim izrazom
> > **Cilj:** Če je jezik $L$ regularen (torej ga sprejme nek DKA), zanj obstaja regularni izraz.
> > 
> > **Dokaz (metoda eliminacije stanj ali GNFA):**
> > Ker je $L$ regularen, obstaja DKA $A$, ki ga prepozna. Ta DKA pretvorimo v regularni izraz s postopkom posplošenega NKA (GNFA), kjer so prehodi označeni z regularnimi izrazi namesto s črkami.
> > 
> > 1.  **Priprava:** DKA pretvorimo v GNFA tako, da dodamo novo začetno stanje (z $\epsilon$-prehodom v staro) in novo končno stanje (z $\epsilon$-prehodi iz vseh starih končnih stanj).
> > 2.  **Eliminacija:** Izbiramo stanja $q_{k}$ (ki niso začetno ali končno) in jih odstranjujemo enega za drugim.
> > 3.  **Posodobitev prehodov:** Ko odstranimo stanje $q_{k}$, moramo ohraniti poti, ki so tekle skozi njega. Če imamo prehod iz stanja $q_i$ v $q_j$ skozi $q_k$, posodobimo neposredni prehod $q_i \to q_j$ po formuli:
> >     $$R_{ij}' = R_{ij} + R_{ik} (R_{kk})^* R_{kj}$$
> >     *(Pomen: Stara pot ali (pot do k, zanka na k kolikokrat želimo, pot iz k)).*
> > 4.  **Rezultat:** Na koncu ostaneta le začetno in končno stanje z enim samim prehodom med njima. Oznaka na tem prehodu je iskani regularni izraz.
> > 
> > **Zaključek:** Za vsak DKA obstaja ekvivalenten regularni izraz.
> > 
> > ---
> > 
> > **Končni sklep:** Ker veljata obe smeri, je jezik regularen natanko tedaj, ko ga opiše regularni izraz.


Definirajmo še PNKA kot 5-terico $M = (Q, \Sigma , \delta, q_{\text{start}}, q_\text{accept})$, kjer je 
- $Q$ končna množica vseh stanj
- $\Sigma$ je vhodna abeceda
- $\delta : (Q- \{ q_\text{accept}\}) \times (Q - \{ q_\text{start} \}) \rightarrow R$ : je prehodna funkcija, kjer je $R$ množica vseh regulranih izrazov nad $\Sigma$
- $q_\text{start}$ je začetno stanje
- $q_\text{end}$ je končno stanje

PNKA sprejme besedo natanko tedaj ko velja da obstaja zaporedje stanj $q_{0},...,q_{n}$ tako da za besedo $w = w_{1}...w_{n}$ velja
- $q_{0}  = q_\text{start}$
- $q_{k} = q_\text{accept}$
- za vsak $i$ je $w_{i} \in  L(R_{i})$, kjer je $R_{i}=\delta(q_{i-1}, q_{i})$ oz. z drugimi besedami $R_{i}$ je izraz puščici med $q_{i-1}$ in $q_{i}$ 

$w_{i}$ je lahko prezen niz


**Neregularni jeziki**

**Neregularni jeziki** so jeziki ki jih ne moremo izraziti s končnimi avtomati. Ponavadi izhajajo iz dejstva da rabimo slediti neskončno stanjem

Velja par ključnih trditev
- Komplement ohranja neregularnost
- Unija ni nujno neregularna $A \cup A^{C}$ kjer je $A$ neregularen da regularni jezik vseh nizov.
- Presek ni zaprt ker lahko dobimo prazno množico kar je regularen jezik.
- **Če mešamo regularen in neregularen jezik preko unije potem je neregularen.**

>**Lema o napihovanju**
>$$\exists n \geq 1 : \forall w \in L , |w| \geq n $$ $$ \exists xyz = w , |xy| \leq n, |y| \geq 1 : \forall i\geq 0 : xy^{i}z \in L$$
>Predpostavimo DKA ki sprejme $L$. Potem lahko za $n$ vzamemo število stanj v avtomatu.
>
>Pokažemo da je vsaka beseda velikosti vsaj $n$ lahko razdeljena in napihnjena
>
>Če nobena beseda ni velikosti $n$ potem velja da ne obstaja taka beseda in izrek postane prazno izpolnjen, ker pogoji oz. trditve veljajo za vse te besede - ki jih ni.
>
>Če je beseda dolžine vsaj $n$ recimo $N$ potem vemo da mora iti čez $N+1$ stanj kjer je zadnje sprejemno. Ker je $N+1 \geq n$ mora veljati da se je neko stanje ponovilo *(Dirichletovo načelo)*. 
>Naj bo $q$ stanje ki se ponovi. Besedo razdelimo na $x$ del besede ki pride do $q$, $y$ del besede s katerim pridemo nazaj v $q$ (ker se $q$ ponovi je $|y| \geq 1$ $\Rightarrow$ ker imamo $n$ stanj moramo do prve ponovitve stanja priti v največ $n$ korakih (od prvega do $n$ v $n-1$ $+ 1$ prva ponovitev preko $y$) : $|xy| \leq n$), $z$ del besede s katerim pridemo v končno stanje. Ker je $y$ del ki nas iz $q$ pripelje v $q$ ga lahko spustimo ali pa ponovimo poljubnokrat. Torej velja $xy^{i}z \in L; \forall i$

Definiramo relacijo 

$$L \subset  \Sigma^{*}$$ 
$$  x,y \in \Sigma^{*}$$
$$x \sim_{L} y \Leftrightarrow \forall z \in \Sigma^{*} : xz \in L \Leftrightarrow yz \in L$$ 

ki pravi da sta $x$ in $y$ ekvivalentna saj za vsak $z$ velja da sta še vedno v jeziku. 

Iz nje lahko določimo pripadaoče ekvivalenčne razrede oz. množice vseh nizov ki so v relaciji. Iz množice lahko izberemo nek element in ga vzamemo kot predstavnika - zapišemo $[x]$.

*Ekvivalenčne razrede razlikujemo po nizih $z$ za katere dobimo različne izide sprejemanje/zavračanje.*

>**Myhill-Nerode izrek**
>Jezik je regularen natanko tedaj ko je število ekvivalenčnih razredov relacije končno.
>Število končnih stanj v minimalnem DKA je enako številu ekvivalenčnih razredov.
Tukaj je dokaz izreka Myhill-Nerode v obliki zveznega besedila.
> >[!|dokaz]+ Dokaz:
> >
> > 
> > Oznaka $[x]$ v predstavlja ekvivalenčni razred niza $x$ glede na relacijo $\sim_L$.
> > 
> > **Dokaz smeri ($\Rightarrow$): Če je $L$ regularen, je število ekvivalenčnih razredov končno**
> > 
> > Predpostavimo, da je jezik $L$ regularen. To pomeni, da obstaja deterministični končni avtomat (DKA) $A = (Q, \Sigma, \delta, q_0, F)$, ki prepozna ta jezik. Na podlagi tega avtomata lahko vpeljemo novo relacijo $\sim_A$, kjer sta dva niza $x$ in $y$ v relaciji, če nas branje obeh nizov iz začetnega stanja pripelje v isto stanje avtomata, torej $\delta(q_0, x) = \delta(q_0, y)$. Ker je množica stanj $Q$ končna, ima relacija $\sim_A$ končno mnogo ekvivalenčnih razredov, in sicer največ toliko, kolikor je stanj v avtomatu.
> > 
> > Pokazati moramo povezavo z relacijo $\sim_L$. Če sta niza $x$ in $y$ v relaciji $\sim_A$, se avtomat po branju obeh nahaja v istem stanju $q$. Če na to stanje dodamo poljuben niz $z$, bo avtomat za vhoda $xz$ in $yz$ končal v istem stanju $\delta(q, z)$. To končno stanje je bodisi sprejemno bodisi nesprejemno, kar pomeni, da niz $xz$ pripada jeziku $L$ natanko tedaj, ko jeziku $L$ pripada niz $yz$. Po definiciji to pomeni, da velja $x \sim_L y$. Ugotovimo torej, da relacija $\sim_A$ implicira relacijo $\sim_L$, kar pomeni, da so ekvivalenčni razredi relacije $\sim_A$ vsebovani v razredih relacije $\sim_L$. Posledično je število ekvivalenčnih razredov $\sim_L$ manjše ali enako številu razredov $\sim_A$. Ker je slednje končno, je tudi število ekvivalenčnih razredov $\sim_L$ končno.
> > 
> > **Velja da je število ekvivalenčnih razredov manjše ali enako številu stanj oz. je število stanj večje ali enako številu ekv. razredov.** Sedaj moramo dokazati le še minimalnost oz. da obstaja DKA s številom stanj kot je ekvivalenčnih razredov in ker je to spodnja meja za število stanj mora biti to minimalni avtomat. 
> > 
> > **Dokaz smeri ($\Leftarrow$): Če je število ekvivalenčnih razredov končno, je $L$ regularen**
> > 
> > Za dokaz v drugo smer predpostavimo, da ima relacija $\sim_L$ končno število ekvivalenčnih razredov. Konstruiramo lahko DKA, kjer so stanja ravno ti ekvivalenčni razredi. Množico stanj $Q'$ definiramo kot množico vseh razredov $\{[x] \mid x \in \Sigma^{*}\}$. Začetno stanje je razred, ki vsebuje prazen niz, $[\epsilon]$. Množica končnih stanj $F'$ pa vsebuje tiste razrede $[x]$, za katere velja $x \in L$. Ta definicija končnih stanj je smiselna, saj iz definicije relacije sledi: če je $x \in L$ in $x \sim_L y$, potem je tudi $y \in L$ (če vzamemo $z=\epsilon$).
> > 
> > Prehodno funkcijo definiramo s predpisom $\delta'([x], a) = [xa]$. Da je ta definicija veljavna, moramo preveriti neodvisnost od izbire predstavnika. Če velja $x \sim_L y$, mora veljati tudi $xa \sim_L ya$. To lastnost imenujemo desna invariantnost in sledi neposredno iz definicije relacije $\sim_L$: če sta $x$ in $y$ nerazločljiva glede na poljuben podaljšek $z$, sta nerazločljiva tudi, če je prvi znak tega podaljška $a$. Avtomat je tako dobro definiran. Z indukcijo je enostavno videti, da avtomat po branju niza $w$ konča v stanju $[w]$. Ker smo končna stanja definirali kot tista, ki vsebujejo nize iz $L$, avtomat sprejme niz $w$ natanko tedaj, ko je $w \in L$. Ker smo uspeli konstruirati končni avtomat, je jezik $L$ regularen.
> > 
> > *Prehodna funkcija ($\delta'$): $\delta'([x], a) = [xa]$.*
> >     *Moramo preveriti, ali prehod ni odvisen od izbire predstavnika $x$.*
> >     *Če $x \sim_L y$, ali velja $xa \sim_L ya$?*
> >     *$$ x \sim_L y \implies \forall z: (xz \in L \iff yz \in L) $$*
> >     *Preverimo za $xa$ in $ya$ s poljubnim $w$:*
> >     *$$ (xa)w \in L \iff x(aw) \in L \iff y(aw) \in L \iff (ya)w \in L $$*
> >     *Ker to velja za vsak $w$, je $xa \sim_L ya$. Relacija je **desno invariantna**, zato je prehodna funkcija dobro definirana.*
> > 
> > **Dokaz o minimalnosti avtomata**
> > 
> > Izrek trdi tudi, da je število stanj v minimalnem DKA enako številu ekvivalenčnih razredov relacije $\sim_L$. V drugem delu dokaza smo konstruirali avtomat, ki ima natanko toliko stanj, kot je ekvivalenčnih razredov $\sim_L$, kar nam da zgornjo mejo za velikost minimalnega avtomata. V prvem delu dokaza pa smo videli, da za vsak poljuben avtomat, ki prepozna $L$, velja, da je število njegovih stanj večje ali enako številu ekvivalenčnih razredov $\sim_L$. To pomeni, da noben avtomat ne more imeti manj stanj od števila ekvivalenčnih razredov. Sledi, da je avtomat, zgrajen na ekvivalenčnih razredih, minimalen.

***

**Konetkstno neodvisna gramatika**

Množica jezikov ki se da zapisati s KNG imenujemo kontekstno neodvisni jeziki. Vsebujejo vse regularne jezike in druge.

Gramatika je zgrajena iz **pravil nadomeščanja** oz. **produkcij**. Sestavljeno je iz simbola, puščice in niza. Simbol je **spremenljivka**, niz pa je sestalvjen iz spremenljivk in drugih simbolov imenovani **terminali**.
Ena spremenljivka je določena kot **začetna spremenljivka**.

Vsi nizi generirani s produkcijami so jezik gramatike. Vsak jezik ga lahko generira KNG se imenuje **kontekstno neodvisen jezik**.

**Kontekstno neodvisna gramtika** je $G = (V, \Sigma, R, S)$ kjer 
- $V$ je končna množica spremenljivk
- $\Sigma$ je končna množica terminalov disjuktna z $V$
- $R$ je končna množica pravil sestavljenih iz spremenljivke in niza spremenljivk in terminalov
- $S \in  V$ je začetna spremenljivka

Če so $u,v,w$ nizi spremenljivk in terminalov in je $A \rightarrow w$ pravilo gramatike pravimo da $uAv$ daje $uwv$. 

Pravimo da se $u$ izpelje v $v$ zapisano $u \stackrel{*}{\Rightarrow} v$, če velja $u = v$ ali če obstaja zaporedje $u_1, u_2, \dots, u_k$ za $k \ge 0$, tako da velja:
$$u \Rightarrow u_1 \Rightarrow u_2 \Rightarrow \dots \Rightarrow u_k \Rightarrow v.$$

**Jezik gramatike** je $\{w \in \Sigma^* \mid S \stackrel{*}{\Rightarrow} w\}$.

Če lahko gramatika generira nek niz na vsaj dva načina rečemo da je **dvoumna**. Natančneje najprej definiramo **levo izpeljavo** za katero velja da na vsakem koraku izpeljave niza $w$ v neki gramatiki $G$ nadomestimo najbolj levo spremenljivko.
Niz $w$ je izpeljan **dvoumno** če ima vsaj 2 različni levi izpeljavi.
Gramatika je **dvoumna** če je nek niz generiran **dvoumno**.

Ponavadi lahko pretvorimo dvoumno gramatiko v nedvoumno ampak nekatere so lahko le **dvoumne**. Tem pravimo **izhodiščno dvoumne**.

Poznamo Chomskyjevo normalno obliko kjer je vsako pravilo oblike
$$A \rightarrow BC$$
$$A \rightarrow a$$
Dovolimo $A \rightarrow \varepsilon$ če je $A$ začetna spremenljivka. $B,c$ ne smeta biti začetni.


Seveda, tukaj so dodatni zapiski, ki pokrivajo vsebino s priloženih slik (Skladovni avtomati in njihova ekvivalenca s kontekstno neodvisnimi gramatikami), napisani v istem stilu kot tvoji obstoječi zapiski.

Dodaj to na konec svojih zapiskov (po razdelku o Context-Free Grammars in dvoumnosti).

***

**Skladovni avtomati (Pushdown Automata)**

Skladovni avtomati (PDA) so nov računski model, ki je podoben nedeterminističnemu končnemu avtomatu, vendar ima dodatno komponento: **sklad** (*stack*).

Sklad omogoča avtomatu neomejen dodaten pomnilnik, ki deluje po principu "zadnji noter, prvi ven" (LIFO - Last In, First Out). To omogoča prepoznavanje jezikov, ki niso regularni (npr. $\{0^n 1^n \mid n \ge 0\}$), saj si lahko avtomat na sklad shrani število prebranih ničel in jih kasneje "poparčka" z enkami.

Skladovni avtomat lahko na sklad **potisne** (*push*) simbol ali pa z njega **vzame** (*pop*) simbol. Dostop je mogoč le do vrhnjega simbola.


Formalno je **skladovni avtomat** definiran kot 6-terica $P = (Q, \Sigma, \Gamma, \delta, q_0, F)$, kjer so:
- $Q$: končna množica stanj,
- $\Sigma$: vhodna abeceda,
- $\Gamma$: **skladovna abeceda** (lahko vsebuje simbole, ki niso v $\Sigma$),
- $\delta : Q \times \Sigma_\varepsilon \times \Gamma_\varepsilon \rightarrow \mathcal{P}(Q \times \Gamma_\varepsilon)$: prehodna funkcija,
- $q_0 \in Q$: začetno stanje,
- $F \subseteq Q$: množica sprejemnih stanj.

Opomba: $\Sigma_\varepsilon = \Sigma \cup \{\varepsilon\}$ in $\Gamma_\varepsilon = \Gamma \cup \{\varepsilon\}$.

Prehodna funkcija $\delta(q, a, x)$ vzame trenutno stanje $q$, naslednji vhodni simbol $a$ in vrhnji simbol na skladu $x$. Vrne množico parov $(r, y)$, kjer je $r$ novo stanje in $y$ simbol, ki zamenja $x$ na skladu (če je $y=\varepsilon$, se $x$ izbriše - *pop*; če je $x=\varepsilon$, se $y$ doda - *push*).

**Nedeterminizem** je pri skladovnih avtomatih ključen. Deterministični skladovni avtomati (DPDA) so šibkejši in ne prepoznajo vseh kontekstno neodvisnih jezikov. Mi se osredotočamo na nedeterministične.



Vhod $w$ sprejme, če lahko $w$ zapišemo kot $w = w_1 w_2 \dots w_m$, kjer je vsak $w_i \in \Sigma_{\varepsilon}$, in če obstajata zaporedje stanj $r_0, r_1, \dots, r_m \in Q$ ter zaporedje nizov $s_0, s_1, \dots, s_m \in \Gamma^*$, ki zadoščajo naslednjim trem pogojem. Nizi $s_i$ predstavljajo zaporedje vsebine sklada, ki ga ima $M$ na sprejemajoči veji računanja.

1.  $r_0 = q_0$ in $s_0 = \varepsilon$. Ta pogoj pomeni, da $M$ začne pravilno, v začetnem stanju in s praznim skladom.
2.  Za $i = 0, \dots, m - 1$ velja $(r_{i+1}, b) \in \delta(r_i, w_{i+1}, a)$, kjer je $s_i = at$ in $s_{i+1} = bt$ za neka $a, b \in \Gamma_{\varepsilon}$ in $t \in \Gamma^*$. Ta pogoj pravi, da se $M$ premika pravilno glede na stanje, sklad in naslednji vhodni simbol.
3.  $r_m \in F$. Ta pogoj pravi, da se na koncu vhoda pojavi sprejemno stanje.


***

**Ekvivalenca med KNG in PDA**


>**Izrek:** Jezik je kontekstno neodvisen natanko tedaj, ko ga prepozna nek skladovni avtomat.

Dokazujemo dve smeri:

**1. Smer (KNG $\Rightarrow$ PDA):**
Če je jezik $L$ kontekstno neodvisen, zanj obstaja KNG $G$. Konstruiramo PDA $P$, ki simulira izpeljave te gramatike.

*Ideja:*
PDA na svojem skladu hrani vmesne nize izpeljave. Začne z začetno spremenljivko.
- Če je na vrhu sklada **spremenljivka** $A$, PDA nedeterministično izbere eno od pravil za $A$ (npr. $A \to w$) in na skladu zamenja $A$ z $w$.
- Če je na vrhu sklada **terminal** $a$, PDA prebere znak z vhoda. Če se ujemata, terminala "odšteje" (pop s sklada). Če se ne ujemata, se veja izvajanja prekine (zavrne).
- Če je sklad prazen in smo prebrali celoten vhod, sprejmemo.

**2. Smer (PDA $\Rightarrow$ KNG):**
Če PDA $P$ prepozna jezik, zanj obstaja KNG $G$.
Ta smer je težja. Želimo zgraditi gramatiko, ki generira vse nize, ki avtomat $P$ pripeljejo iz enega stanja v drugega s praznim skladom.

*Postopek:*
1. Najprej poenostavimo PDA, da ima le eno sprejemno stanje, da sprazni sklad pred sprejetjem in da vsak prehod bodisi doda simbol bodisi ga odvzame (ne oboje hkrati).
2. Definiramo spremenljivke gramatike oblike $A_{pq}$.
   Spremenljivka $A_{pq}$ generira vse nize, ki avtomat pripeljejo iz stanja $p$ (s praznim skladom) v stanje $q$ (s praznim skladom).
3. Pravila gramatike:
   - Za vsak $p$ dodamo $A_{pp} \to \varepsilon$ (v 0 korakih ostanemo v istem stanju).
   - Za poti, kjer se sklad vmes ne sprazni: Če avtomat iz $p$ preide v $r$ (push $u$), nato iz $r$ pride v $s$ (vmesno dogajanje) in iz $s$ v $q$ (pop $u$), dodamo pravilo:
     $$A_{pq} \to a A_{rs} b$$
     kjer sta $a$ in $b$ vhodna simbola pri prvem in zadnjem koraku.
   - Za poti, kjer se sklad vmes sprazni v nekem stanju $r$:
     $$A_{pq} \to A_{pr} A_{rq}$$

S tem dokažemo, da so jeziki, ki jih prepozna PDA, natanko tisti, ki jih generira KNG.





***



>[!|hide]- Naloge iz skladovnih avtomatov
> ### Napredne naloge: Skladovni avtomati (Težavnost 9/10)
> 
> **1. Komplement enakosti (The "Anti-Copy" Language)**
> Zapišite **nedeterministični** skladovni avtomat za jezik:
> $$L_1 = \{ w \in \{a, b\}^* \mid w \neq uu \text{ za poljuben } u \in \{a, b\}^* \}$$
> *(Opomba: To je jezik vseh nizov, ki **niso** oblike $ww$. To vključuje nize lihe dolžine in nize sode dolžine, kjer se prva polovica razlikuje od druge.)*
> 
> **2. Dvojna neenakost**
> Zapišite skladovni avtomat za jezik:
> $$L_2 = \{ a^i b^j c^k \mid i \neq j \lor j \neq k \}$$
> *(Namig: Neenakost ($i \neq j$) pomeni ($i < j \lor i > j$). Naloga zahteva konstrukcijo, ki pokriva unijo štirih različnih primerov.)*
> 
> **3. Aritmetika na skladu s spremembo smeri**
> Zapišite **deterministični** skladovni avtomat (DPDA) za jezik:
> $$L_3 = \{ a^n b^m c^k \mid n + k = m; \ n,m,k \ge 1 \}$$
> *(Izziv: Sklad morate uporabiti tako, da najprej beležite $a$-je, nato jih "uničite" z $b$-ji, presežek $b$-jev pa shranite, da jih kasneje "uničite" s $c$-ji. Vse mora biti deterministično.)*
> 
> **4. Razmerja v poljubnem vrstnem redu**
> Zapišite skladovni avtomat za jezik:
> $$L_4 = \{ w \in \{a, b\}^* \mid 2 \cdot \#_a(w) \neq 3 \cdot \#_b(w) \}$$
> *(Izziv: Simboli so premešani (ni nujno $a^n b^m$). Avtomat mora preverjati razmerje 2:3. Ker gre za neenakost ($\neq$), morate zgraditi vejo za "manj kot" in vejo za "več kot".)*
> 
> **5. "Almost" Palindromi**
> Zapišite skladovni avtomat za jezik:
> $$L_5 = \{ w \in \{a, b\}^* \mid w = w^R \text{ in } \#_a(w) = \#_b(w) \}$$
> *(Izziv: To je presek dveh kontekstno neodvisnih jezikov (palindromi in enakim številom a/b). Ali je to sploh mogoče s skladovnim avtomatom? Če ni, utemeljite. Če je, narišite. Za težavnost 9/10 poskusite raje to variacijo, ki **je** mogoča: $L = \{xcx^R \mid x \in \{a,b\}^*\} \cup \{ a^n b^n \mid n \ge 1 \}$.) *
> 
> ---
> 
> ### Namigi in rešitve (zakaj so to 9/10 naloge)
> 
> Če želite te naloge rešiti, morate razmišljati "izven okvirjev" običajnega štetja $a^n b^n$. Tukaj je logika za najtežji dve:
> 
> **Analiza naloge 1 (Komplement $ww$):**
> To je klasičen "težek" problem teorije. Jezik $L = \{ww\}$ ni kontekstno neodvisen (ne morete ga prepoznati s SA). Njegov komplement pa **je**.
> *   **Strategija:** Avtomat nedeterministično ugane eno od dveh možnosti:
>     1.  Niz je lihe dolžine (lahko preverimo).
>     2.  Niz je sode dolžine $2n$, vendar obstaja nek indeks $k$ (kjer $1 \le k \le n$), da se $k$-ti simbol niza razlikuje od $(n+k)$-tega simbola.
>     *   Avtomat mora "uganiti" ta indeks $k$, si zapomniti simbol na tem mestu, preskočiti $n-1$ znakov in preveriti, če se simbol na $n+k$ razlikuje. To zahteva zapleteno manipulacijo sklada za štetje dolžine.
> 
> **Analiza naloge 2 (Dvojna neenakost):**
> Logični pogoj je $P_1 \lor P_2$, kjer je $P_1: (i < j \lor i > j)$ in $P_2: (j < k \lor j > k)$.
> *   To pomeni, da mora vaš avtomat na začetku z $\epsilon$-prehodom nedeterministično skočiti v eno izmed štirih stanj, ki preverjajo:
>     1.  $i < j$ (in ignorira $k$)
>     2.  $i > j$ (in ignorira $k$)
>     3.  $j < k$ (ignorira $i$, nato preveri $j < k$)
>     4.  $j > k$ (ignorira $i$, nato preveri $j > k$)
> *   Težavnost je v pravilnem "ignoriranju" delov niza, ki niso relevantni za izbrano neenakost, hkrati pa zagotavljanju, da je sklad prazen na koncu.




***






![[Screenshot 2025-11-23 165815.png]]

![[Screenshot 2025-11-23 165732.png]]

![[Screenshot 2025-11-23 165740.png]]

![[Screenshot 2025-11-23 165749.png]]

![[Screenshot 2025-11-23 165810.png]]