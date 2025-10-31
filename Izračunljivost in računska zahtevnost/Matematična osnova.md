**Množica** je skupina **edinstvenih** matematičnih objektov katerim pravimo **elementi** množice.

**Podmnožica** je taka množica katere elementi so vsi tudi elementi **nadmnožice**.

**Prava podmnožica** je podmnožica ki ni enaka nadmnožici.

Množice nimajo ponavljajočih se elementov torej je $\{ 7,7,7\}$ enaka $\{ 7\}$. Če hočemo upoštevati število ponovljenih elementov govorimo o **multimnožicah**.

**Neskončna množica** vsebuje neskončno vrednosti. Pišemo $\mathbb{N} = \{ 1,2,...\}, \mathbb{Z} = \{ ...,-2,-1,0,1,2,...\}$. Množica brez elementov je **prazna množica** $\emptyset$. Množica z enim elementom je **singelton**. in množica z dvema elementom je **neurejen par**.

Poznamo **presek, unijo, komplement, razliko, in simetrično razliko**, kot operacije nad množicami.

**Zaporedje** objektov je urejen seznam - $(7,10,11)$. Vrstni red in ponavljanje elementov v množici nista pomembna medtem ko v zaporedju sta.

**Končno** zaporedje $n$ elementov kličemo **$n$-terica**. *- $n$-tuple*

**Potenčna množica** je množica vseh podmnožic.

**Krartezični produkt** množic je množica vseh urejenih parov množic.

**Funkcija** je pravilo ki slika elemente iz ene množice v elemente druge množice - element ne more imeti več slik.

$f: A \rightarrow B$

**Rigorozno:** 

Funkcija z domeno $X$ in kodomeno $Y$ je binarna relacija $R$ med $X$ in $Y$, ki zadovoljuje naslednja pogoja:

*   Za vsak $x$ v $X$ obstaja $y$ v $Y$ tako, da je $(x, y) \in R$.
*   Če velja $(x, y) \in R$ in $(x, z) \in R$, potem je $y = z$.

$A$ je domena in $B$ je kodomena $f$.
$f(A)$ je slika $f$ in velja $f(A) \subset B$.

Če $f$ slika vsak element iz $A$ v originalen element v $B$ potem je injektivna.

Če je $f(A) = B$ potem je $f$ **surjektivna**.

$f$ je **bijektivna** če je oboje hkrati.

Če je funkcija surjektivna pravimo tudi da slika **na** B.

Če imamo za vhod funkcije neko $n$-terico $(a_{1},...,a_{n})$ potem so $a_{i}$ argumenti $f$ in imamo funckijo $n$ spremenljivk. Tako imamo unarne in binarne funckije kot najpogostejše.

Nekatere binarne funckije pišemo z medponskim zapisom $+(a,b) := a + b$ namesto predponskim.

**Predikat** oz. **lastnost** je funkcija katere kodomena je $\{ \text{TRUE}, \text{FALSE}\}$. Primer je enakost - $\text{equal}(A \times B) = \{ \text{TRUE, FALSE}\}$. Funkcija ki ovrednosti neke elemente glede na trditev predikata.

$$S(x,y) = x\text{ je enak }y$$

***

**Grafi**

Neusmerjen graf oz. graf je množica točk in povezav.
Definiran je kot par množice vozlišč in povezav.

$$(V, E)$$

Število povezav ki pripadajo vozlišču rečemo stopnja vozlišča.

**Dovoljujemo povezavo samo nase oz. zanko.**

Neusmerjene povzeave predstavljamo z $(i,j)$ kjer sta $i$ in $j$ povezani vozlišči.

Podgraf je graf za katerega velja da je $V' \subset V$ in $E' \subset E$.

Pot je zaporedje vozlišč ki so povezani. Enostavna pot ne ponavlja vozlišč.

Graf je **povezan** če med vsakima vozliščema obstaja pot.

Enostavna pot je **cikel** če se začne in konča v istem vozlišču.

Grafu rečemo **drevo** če velja da je povezan in ne vsebuje nobnih ciklov.

**List** imenujemo vozlišča drevesa stopnje 1.

**Usmerjen graf** ima puščice namesto črt in za vsako vozlišče vsebuje vstopno stopnjo in izhodno stopnjo. 
Povezavo v usmerjenem grafu predstavimo kot par $(i,j)$.

Pot kjer vse puščice kažejo v isto smer kot njeni koraki imenujemo **usmerjena pot**. Le-ta je **močno povezan** če usmerjena pot povezuje vsaki dve vozlišči.

***

**Nizi in jeziki**

Definiramo **abecedo** kot katero koli neprazno končno množico. 
Člani abecede so **simboli** abecede. 
Za označevanje abeced običajno uporabljamo velike grške črke $\Sigma$ in $\Gamma$ ter pisavo tipkovnice (typewriter font) za simbole iz abecede. 

Nekaj primerov abeced.

$$\Sigma_1 = \{0, 1\}$$
$$\Sigma_2 = \{a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z\}$$
$$\Gamma = \{0, 1, x, y, z\}$$

**Niz nad abecedo** je končno zaporedje simbolov iz te abecede, običajno zapisanih drug poleg drugega in brez vejic. 
Če je $\Sigma_1 = \{0, 1\}$, je $01001$ niz nad $\Sigma_1$. 
Če je $\Sigma_2 = \{a, b, c, \ldots, z\}$, je $abracadabra$ niz nad $\Sigma_2$. 
Če je $w$ niz nad $\Sigma$, je **dolžina** niza $w$, zapisana $|w|$, število simbolov, ki jih vsebuje. 
Niz z dolžino nič se imenuje **prazni niz** in se zapiše $\epsilon$. 
Prazni niz igra vlogo $0$ v številskem sistemu.

Če ima $w$ dolžino $n$, lahko zapišemo $w = w_1 w_2 \ldots w_n$, kjer je vsak $w_i \in \Sigma$. 
**Obrat** niza $w$, zapisan $w^R$, je niz, dobljen z zapisom $w$ v obratnem vrstnem redu (tj. $w_n w_{n-1} \ldots w_1$).

Niz $z$ je **podniz** niza $w$, če se $z$ pojavi zaporedoma znotraj $w$. Na primer, $cad$ je podniz niza $abracadabra$.

Če imamo niz $x$ dolžine $m$ in niz $y$ dolžine $n$, je **konkatenacija** $x$ in $y$, zapisana $xy$, niz, dobljen z dodajanjem $y$ na konec $x$, kot v $x_1 \ldots x_m y_1 \ldots y_n$. 
Za konkatenacijo niza samega s seboj večkrat uporabljamo nadpisno notacijo $x^k$, ki pomeni

$$ \underbrace{xx \cdots x}_{k} $$

Leksikografski vrstni red nizov je enak znanemu vrstnemu redu slovarja. 
Občasno bomo uporabili spremenjen leksikografski vrstni red, imenovan **shortlex vrstni red** ali preprosto **vrstni red nizov**, ki je enak leksikografskemu, razen da krajši nizi vedno predhodijo daljšim. Tako je vrstni red vseh nizov nad abecedo $\{0, 1\}$:

$$(\epsilon, 0, 1, 00, 01, 10, 11, 000, \ldots).$$

Rečemo, da je niz $x$ **predpona** niza $y$, če obstaja niz $z$, za katerega velja $xz = y$, in da je $x$ **prava predpona** niza $y$, če poleg tega velja $x \neq y$. 

**Jezik** je množica nizov. Jezik je **brez predpon** (*prefix-free*), če noben član ni prava predpona drugega člana.

---

**DEFINICIJE, TEOREMI IN DOKAZI**

**Definicije** opisujejo objekte in pojme, ki jih uporabljamo. 

Ko definiramo različne objekte in pojme, običajno izjavimo **matematične trditve** o njih. 
Značilno je, da trditev izraža, da ima objekt določeno lastnost. 
Trditev je lahko resnična ali napačna; Dvomljivost glede njenega pomena ni dovoljena.

**Dokaz** je prepričljiv logični argument, da je trditev resnična.

**Teorem** je matematična trditev, ki je dokazano resnična. Na splošno to besedo uporabljamo za trditve posebnega pomena. Občasno dokazujemo trditve, ki so zanimive samo zato, ker pomagajo pri dokazovanju druge, pomembnejše trditve. Takšne trditve se imenujejo **leme**. Včasih nam teorem ali njegov dokaz omogoča, da z lahkoto sklepamo, da so resnične tudi druge, povezane trditve. Te trditve se imenujejo **posledice** teorema.

Za dokazovanje uporabljamo par popularnih strategij kot so **dokaz s protislovjem kot najsplošnejšo, dokaz z indukcijo, dokaz s konstrukcijo.**

Če dokazujemo enako moč množic lahko najdemo bijekcijo ali pa pokažemo da je ena podmnožica druge kot tudi da je druga podrmnožica prve.