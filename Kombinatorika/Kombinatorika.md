>[!|hide]- Snov gimnazije
> 
> Če imamo $n$ predmetov in jih poskušamo razporediti na $n$ mest potem to lahko storimo na $n!$ načinov.
> Na prvo mesto lahko damo enega izmed $n$ predmetov, na drugo enega izmed $n-1$ in tako naprej. Temu pravimo permutacije.
> 
> $$P_{n} = n!$$
> 
> Če imamo $n$ predmetov in jih probamo postaviti na $k$ mest potem lahko število načinov izračunamo z
> 
> $$p_{k,n} = \frac{n!}{(n-k)!}$$
> 
> To lahko razložimo kot na vsako od k mest lahko damo $n, n-1, n-2,...,n-k+1$ elementov kar je natanko $\frac{n!}{(n-k)!}$, ker se preostalih znebimo tako da jih pokrajšamo.
> 
> Oziroma če si predstavljamo vseh $n!$ razporeditev. Recimo da imamo razporeditev 5 elemtnov na 3 mesta. Imamo lahko 12345 in 12354, kjer imamo razporeditev na prvih 3 mestih ponovljeno, in ker nas zanimajo le te moramo vse možne ponovitve zbrisati. Ker sta ostali le 2 mesti se lahko elementi na teh mestih razporedijo na $2!$ načinov, to jih da v grupe velikosti $2!$, da dobimo število grup verlikosti $2!$ pa moramo deliti z $2!$. 
> 
> Če imamo elemente ki se lahk ponovijo na $k$ mestih imamo
> 
> $$n^{k}$$
> 
> Če hočemo razporediti elemente kjer se nek elemente ki se ponovijo kjer se ponovijo $k_{1},...,k_m$ imamo
> 
> $$p^{n}_{k_{1},...,k_{n}} = \frac{n!}{k_{1}!k_{2}!...k_{n}!}$$
> 
> Spet delujemo po principu da dobimo $k_{1}!,...,k_{n}!$, kjer moramo deliti da dobimo pravilno število možnosti. Če imamo črke naprimer: $\text{BAN}_1\text{AN}_2$ in $\text{BAN}_2\text{AN}_1$ imamo spet $2!$ intako za vse možne črke.
> 
> Nato pa imamo če kombinacije, kjer iščemo samo vse množice velikosti  $k$ v množici z $n$ elementi.
> 
> $$_{n}C_{k} = \frac{n!}{k!(n-k)!}$$
> 
> Kar se dogaja je da gledamo vse razporeditve $n$ elementov na $k$ mestih nato pa še delimo z $k!$ se hočemo znebiti vseh permutacij teh elementov na $k$ mestih oz. vse permutacije istih elementov združimo v eno skupino.
> 
> Za kombinacije uporabljamo tudi binomski simbol.
> 
> $$\binom{\,n\,}{\,k\,}$$
> 
> Binomski simbol se pojavi tudi pri $n$-ti potenci dvočlenika kjer velja
> 
> $$(x+y)^{n} = \sum_{k = 0}^{n}\binom{\,n\,}{\,k\,}x^{n-k}y^{k}$$
> 
> Če pogledamo primer
> 
> $$(x+y)^{3} = (x+y)(x+y)(x+y)$$
> $$x^{3}+3x^{2}y + 3xy^{2}+y^{3}$$
> 
> je prva stvar ki jo opazimo da so vsi členi neka kombinacija $x$ in $y$. Nato pa je edina naslednja stvar še da opazimo da lahko do nekaterih kombinacij pridemo na več načinov kot do drugih saj vrstni red ni pomemben. Efektivno delamo računamo kombinacije obeh členov, kjer lahko do nekaterih členov pridemo na več načinov kot do drugih. Iz tega dobimo tudi Pascalov trikotnik.
> 
> **Kombinacije lahko gledamo tudi kot najprej permutacije, potem se omejimo na mesta na začetku in jih damo v skupine kjer je prvih $k$ elementov v enakem vrstnem redu, to se elementi te skupine, da ugotovimo koliko teh skupin je oz. koliko je permuatcij elementov na $k$ mestih moramo deliti s številom elementov v tej skupini - $\frac{n!}{(n-k)!}$, kar so permutacije ostalih elementov.**
> **Nato moramo še pogledati kje se elementi ponavljajo in dati vsa zaporedja ki vsebujejo iste elemente oz. so permutacije samih sebe v svojo skupino - in spet delimo s številom elementov v tej skupini da dobimo končno število kombinacij.**



## Osnovni problemi kombinatorike

###  Funkcija
Funkcija je definirana kot podmnožica kartezičnega produkta $A \times B$, kjer velja da za vsak $a \in A$ obstaja natanko en $b \in B$ tako da je $(a,b) \in  f$.

$$f: A \to B$$

$A$: **domena**
$B$: **kodomena**
$f(A)$: **slika**

> Funkcijo lahko zapišemo na različne načine:
> 
> **Eksplicitno za vsak element**
> $\{1,2,3\} \to \{a,b,c,d\}$; $f(1)=a, f(2)=a, f(3)=b$
> 
> **Predpis**
> $F: \mathbb{N} \to \mathbb{N}$; $F(n) = 2n$
> 
> **Rekurzivna**
> $F: \mathbb{Z} \to \mathbb{Z}$; $f(n) = f(n-1) + f(n-2)$ 

Funkcija ima lahko naslednje lastnosti
**Injektivnost**:
$$x \neq y \implies f(x) \neq f(y)$$
*Interpretacija:* v vsaki škatli je $\le 1$ kroglica.

**Surjektivnost**:
Slika funkcije je enaka $B$.
*Interpretacija:* vsaj ena kroglica v vsaki škatli.

**Bijektivnost**:
Je injektivna in surjektivna hkrati.

***

Za kombinatoriko pa so pomembne oznake

*   $[n] = \{1, \dots, n\}$; $|[n]| = n$. 
  Za $n=0 \implies \emptyset$. 
* $\mathbb{N} = \{0,1,2, \dots\}$.
*   $2^A$: **Potenčna množica** $\{X ; X \subseteq A\}$.
*   $\binom{A}{k} = \{B \in 2^A ; |B|=k\}$ (podmnožice s $k$ elementi).
*   $B^A :=$ množica vseh preslikav iz $A \vee B$.

***

 **Dirichletovo načelo**


$$f: A \to B \text{ je injektivna } \Rightarrow |A| \le |B|$$
$$\iff$$
$$|A| > |B| \implies \nexists \text{ inj. } F: A \to B$$

Za dokazovanje z **dirichletovim načelom** poskušamo najti neko karakterizacijo problema da lahko določimo množico z manj elementi kot imamo kroglic.

*Primer take uporabe je pri dokazovanju spodnjega problema kjer imamo podmnožico velikosti $n+1$ iz česar poskuismo ugotoviti ali v množici $[2n]$ lahko povlečemo množico z $n$ ali manj elementi tako da je aplikabilno za naš primer. ker imamo $2n$ elementov vemo da je notri natanko $n$ lihih števil nato pa lahko opazimo da je za deljivost uporaben zapis $2^{k} \cdot l$ kjer je $l$ liho število in lahko tako dokažemo da ni dovolj lihih števil kar pomeni da mora eno deliti drugo*

*Če damo $n$ kroglic v $k$ škatel in je $n > k$, potem je v vsaj eni škatli več kot 1 kroglica.*

>[!|]- Primeri:
> 13 ljudi $\implies$ potem imata vsaj 2 rojstni dan v istem mesecu.
> *   Kroglice: ljudje
> *   Škatle: meseci
> *   Preslikava: mesec rojstva. $|A|=13, |B|=12$.
> ***
> $n+1$ števil. Med njimi sta 2, ki imata razliko deljivo z $n$.
> *   Kroglice: izbrana števila ($n+1$)
> *   Škatle: ostanki pri deljenju z $n$ ($\{0, \dots, n-1\}$, teh je $n$)
> *   Preslikava: je ostanek pri deljenju z $n$. 
> Če imata dve števili isti ostanek $r$ $\Rightarrow x = k_{1}n+r \;,\; y=k_{2}n+r$ $\Rightarrow x-y = (k_{1}-k_{2})n$
>  $\Rightarrow n|x-y$
> ***
> $n$ ljudi, vsaka 2 se lahko poznata ali ne. Obstajata 2, ki poznata enako število ljudi.
> *   Kroglice: ljudje ($n$)
> *   Škatle: možna števila znancev $\{0, \dots, n-1\}$.
> *   *Opazka:* Škatli 0 (pozna nikogar) in $n-1$ (pozna vse ostale) ne moreta biti 'zasedeni' hkrati.
> *   $\implies$ imamo $n-1$ škatel na voljo za $n$ ljudi.
> ***
> $X \subseteq [100], |X|=10$. Dve disjunktni neprazni podmnožici $X$ morata imeti isto vsoto.
> *   Kroglice: neprazne podmnožice $X$; teh je $2^{10}-1 = 1023$.
> *   Škatle: možne vsote. Maksimalna vsota je $100+99+\dots+91 \approx 955$.
> *   Zaloga vrednosti (škatle) $\subseteq [955]$.
> *   $1023 > 955 \implies$ imamo dve različni podmnožici z isto vsoto $A, B \subseteq X$.
> *   Če nista disjunktni: vzemi $A \setminus (A \cap B)$ in $B \setminus (A \cap B)$. Še vedno imata isto vsoto in sta disjunktni.
> ***
> $X \subseteq [2n], |X|=n+1$. $\implies \exists x, x' \in X$, **tako da** $x | x'$ ali $x' | x$.
> *   Vsako število zapišemo kot $x = 2^a \cdot L$, kjer je $L$ lih del (lih faktor).
> *   Kroglice: $x \in X$ (teh je $n+1$).
> *   Škatle: liha števila v $[2n]$. To so $\{1, 3, 5, \dots, 2n-1\}$. Teh je $n$.
> *   Preslikava: $x \mapsto L$ (element preslikamo v njegov lihi del).
> *   Po Dirichletovem principu $\exists x, x' \in X$ z istim lihim delom $L$.
>     $x = 2^a \cdot L, \quad x' = 2^b \cdot L$.
>     Ker sta $x$ in $x'$ različna, sta tudi eksponenta $a$ in $b$ različna.
>     Če $a < b \implies x | x'$. (Sicer, če $b < a \implies x' | x$).

---

Pri kombinatoričnih problemih poznamo načelo vsote in produkta ki opisujeta koliko načinov imamo da izberemo nek element iz množic oz. koliko načinov imamo da tvorimo zaporedje izbir iz nekih množic.

**Načelo vsote**:

$$|A \cup B| = |A| + |B|,  \text{če sta } A \text{ in } B \text{ disjunktni.}$$

Splošno

$$|A \cup B| = |A| + |B| - |A \cap B|$$

*Uporabljamo ko imamo disjuntkne izbire -  ne moreta se zgoditi hkrati  - izbire se izključujejo - izberem lahko element iz množice $A$ ali element iz množice $B$*

**Načelo produkta**:

$$|A \times B| = |A| \cdot |B|$$

*Ko imamo izbire ki si sledijo ena drugi (recimo naprej izberemo element iz $A$ potem pa izberemo še element iz $B$) potem obstaja toliko zaporedij teh izbir kot je produkt moči $A$ in $B$.*

>[!|hide]- Primer
>  3 majice, 3 srajce (zgoraj 6 opcij); 4 hlače, 4 trenirke (spodaj 8 opcij).
Kombinacije: $(3+3) \cdot (4+4) = 6 \cdot 8 = 48$.
> 
> Izbiramo najprej med zgornjimi oblačili - $M + S$ potem pa kot naslednja izbira (v zaporedju) še med spodnjimi oblačil $H + T$.
> 
> $$M+S \cdot H+T$$

***

> Preslikav iz množice $N$ v $K$ je natanko $k^{n}$.
> Če  imamo $K^{N}$ imamo $k$ izbir za vsak element $n$.
> 
> Torej je $\underbrace{k \cdot k \cdot \dots \cdot k}_{n} = k^n$.
> 
> >[!|hide]- Dokaz bijekcije med podmnožicami in binarnimi zaporedji:
> > $|2^{[n]}| = |\{0,1\}^n| = 2^n$.
> > Iščemo bijekcijo iz $2^{[n]} v \{0,1\}^n = \{(\epsilon_1, \dots, \epsilon_n); \epsilon_i \in \{0,1\}\}$.
> > Preslikava s karakterističnim vektorjem:
> > $\Phi(A) = (\epsilon_1 \dots \epsilon_n)$, kjer $\epsilon_i = \begin{cases} 1; & i \in A \\ 0; & i \notin A \end{cases}$.
> > Inverz: $\Psi(\epsilon_1 \dots \epsilon_n) = \{ i \in [n] ; \epsilon_i = 1\}$.

> Če je $N$ končna in imamo $F \in  N^{N}$ potem velja naslednje
> 
> $F$ je inj. $\iff F$ je surjektivna $\iff F$ je bijektivna.

**Število injektivnih preslikav iz  $N \to K$**
Prvi element ima $k$ izbir, drugi $k-1$, ...

$$k(k-1)\dots(k-n+1) = k^{\underline{n}} = \frac{k!}{(k-n)!}$$

To označujemo kot **padajoča potenca** 

$$\large k^{\underline{\;\!\!n}} = k(k-1)\dots(k-n+1)$$

Obstaja tudi **naraščajoča potenca** 

$$\large k^{\overline{\;\!\!n}} = k(k+1)\dots(k+n-1)$$

Število bijekcij $N \to N$ oz. **permutacij**:

$$|N^N| = n! = n \cdot (n-1) \dots 2 \cdot 1$$


**Stirlingova aproksimacija**: $n! \sim \sqrt{2\pi n}(\frac{n}{e})^n$

>[!|hide]- 
>
> $$
> \ln(n!) = \ln(n) + \dots + \ln(1)
> $$
> $$
> \sum_{1}^{n} \ln(x) \approx \int_{1}^{n} \ln(x) dx
> $$
> $$
> \Big[ x\ln(x) - x \Big]_1^n \approx n\ln(n) - n
> $$
> $$
> \implies \ln(n!) \approx n \ln(n) - n
> $$
> $$
> n! \approx e^{n \ln(n) - n} = e^{\ln(n^n) - n}
> $$
> $$
> \approx n^n \cdot e^{-n} = \left(\frac{n}{e}\right)^n
> $$
***
> **Asimptotična enakost**: $a_{n}\sim b_{n}  := \lim \frac{a_n}{b_n} = 1$.
***
Posebni primeri (iz definicije preslikav med praznimi množicami):
*   $0! = 1$ (ena bijekcija $\emptyset \to \emptyset$).
*   $0^0 = 1$ (ena funkcija $\emptyset \to \emptyset$).
  
>[!|dokaz]- Dokaz:
> Funkcija $f: X \to Y$ je relacija $f \subseteq X \times Y$, ki mora izpolnjevati pogoj, da za vsak element $x \in X$ obstaja natanko en element $y \in Y$, na katerega ga funkcija preslika ($\forall x \in X, \exists ! y \in Y: (x, y) \in f$). $X = \emptyset$ in $Y = \emptyset$. V tem primeru je njun kartezični produkt $X \times Y$ prav tako prazen, $\emptyset \times \emptyset = \emptyset$.
> 
> Vsaka funkcija $f: \emptyset \to \emptyset$ mora biti podmnožica praznega produkta, torej $f \subseteq \emptyset$. Ker je edina podmnožica prazne množice sama prazna množica, obstaja samo ena takšna relacija: $f = \emptyset$. Sedaj moramo preveriti, ali ta prazna relacija ustreza strogim pogojem za funkcijo. Pogoj obstoja slike (totalnost), ki zahteva, da za vsak $x \in X$ obstaja slika, je trivialno resničen, saj ker je $X = \emptyset$, ne obstaja noben $x$. Ta univerzalna trditev o elementih prazne množice je avtomatično izpolnjena, saj ni nobenega nasprotnega primera, ki bi jo lahko ovrgel. Podobno je z enoličnostjo slike za vsak $x$: tudi ta pogoj je trivialno izpolnjen, ker ni nobenega elementa v domeni. Torej, funkcija $f: \emptyset \to \emptyset$ izpolnjuje vse zahteve in obstaja natanko ena – prazna funkcija $f = \emptyset$.
> 
> Ta rezultat je ključen pri razumevanju potenciranja v teoriji množic in kombinatoriki, kjer $a^b$ definiramo kot število vseh funkcij $f: B \to A$. Ko to definicijo uporabimo za moči praznih množic, kjer sta število elementov množic $A$ in $B$ enaka nič, dobimo izraz $0^0$. Ker smo dokazali, da obstaja natanko ena funkcija med dvema praznima množicama, matematična definicija določa, da je $0^0 = |\{f: \emptyset \to \emptyset\}|$, kar je enako 1.

---

## Permutacije

Bijekcija $A \to A$ je **permutacija** $A$. 

Množica vseh permutacij $A$ v $A$ je $S_A$.
Velikost: $|S_A| = |A|!$.

Za $[n]$ označimo $S_{[n]} = S_n$.

Notacije:
*   Dvovrstična: $\begin{pmatrix} 1 & 2 & \dots & n \\ \pi_1 & \pi_2 & \dots & \pi_n \end{pmatrix}$
*   Enovrstična: $\pi_1 \pi_2 \dots \pi_n$


**Ciklična notacija**:
Sledimo elementu: $1 \to \pi(1) \to \pi^2(1) \dots$ dokler se ne vrnemo.
Cikel zapišemo: $(i, \pi(i), \pi^2(i), \dots, \pi^{k-1}(i))$, kjer $\pi^k(i) = i$.

>Vsako permutacijo lahko zapišemo kot produkt disjunktnih ciklov.

>Cikle dolžine ena imenujemo **negibne točke**.

>Disjunktni cikli komutirajo.

## Načelo dvojnega štetja

Recimo da imamo $A$ in $B$ in relacijo $S \subseteq A \times B$.
Predstavljamo si lahko tabelo kjer imamo vrstico po $b$-jih in stolpec po $a$-jih.

$$\begin{bmatrix}(a_{1},b_{1}) & (a_{1},b_{2}) & ... &(a_{1},b_{n}) \\ (a_{2},b_{1}) & (a_{2},b_{2}) & ... &(a_{2},b_{n}) \\ ... & ...&...&...\\(a_{n},b_{1}) & (a_{n},b_{2}) & ...& (a_{n},b_{n})  \end{bmatrix}$$

Sedaj lahko za vrstico, nekega elementa $A$ zapišemo njeno vsoto:

$v_{i} = \text{št. } \checkmark \text{ v vrstici } a_{i} = |\{ (a_{i},b_{j}) \in S \,;\; j \in \{ 1,...,n\} \}|$

Oz. drugače povedano število relacij oz. parov $(a,b)$ ki pripadajo relaciji v vrstici.

$s_{j} = \text{št. } \checkmark \text{ v stolpcu } b_{j} = |\{ (a_{i},b_{j}) \in S \,;\; i \in \{ 1,...,n\} \}|$

Načelo dvojnega štetja pravi, da je skupno število kljukic enako, ne glede na način seštevanja:

$$\sum_{i=1}^{n} v_{i} = \sum_{j=1}^{n} s_{j} = |S| $$

>[!|hide]- Glaven primer
> 
> $$
> \sum_{1}^{n} k \binom{n}{k}
> $$
> 
> Iščemo kako bi lahko sešteli število podmožic velikosti $k$
> pomnoženih s številom elementov
> 
> $k \binom{n}{k}$ je lahko predsatvljen na naslednji način 
> $\qquad \qquad\quad \{1,2\}, \{2,3\}, \{1,3\}$
> $\qquad \qquad 1 \quad \checkmark \quad\quad\quad\qquad \quad \checkmark$
> $\qquad \qquad 2 \quad \checkmark \quad\quad\quad \checkmark \quad \qquad$
> $\qquad \qquad 3 \quad \quad\quad\quad \quad \checkmark \quad\quad \checkmark$
> kjer vidimo da če tvorimo tabelo kjer so  
> 
> podmnožce $\to$
> št. $[n] \downarrow$
> 
> potem naj bo relacija $(A, x)$ tako da velja $A R x$ če je $x \in A$.
> $\implies \sum_{1}^{n} \binom{n}{k} k$ sešteva po stolpcih
> 
> za $n 2^{n-1}$ pa seštevamo vrstice torej za vsako vrstico velja da je relacija tam kjer je element v podmnožici. $\implies$ recimo vrstica $2$ $-$ to pomeni da gledamo koliko je vseh podmnožic ki vsebujejo $2$. $\implies$ imamo $n-1$ el. ki so še lahko podmnožici
> $\implies 2^{n-1}$, ker je $n$ vrstic $\implies n 2^{n-1}$
> $$
> \implies \sum_{1}^{n} \binom{n}{k} k = n 2^{n-1}
> $$

>[!|hide]- Primeri:
> 
> (1) 32 deklet, vsako dekle pozna 4 fante. Vsak fant pozna 8 deklet. Koliko je fantov?
> *   $A = \text{dekleta}, B = \text{fantje}$. Relacija "se poznata".
> *   Vsota po dekletih: $32 \cdot 4$.
> *   Vsota po fantih: $|B| \cdot 8$.
> *   $32 \cdot 4 = |B| \cdot 8 \implies 128 = 8|B| \implies |B| = 16$.
> 
> (2) Triangulacija grafa (dodajamo povezave dokler niso vsa lica trikotniki).
> *   Relacija med množico povezav $E$ in množico lic $F$. ($e_j$ je na robu lica $F_i$).
> *   Št. $\checkmark$ v vrstici $e_j$ (povezava): vsaka povezava meji na 2 lici.
> *   Št. $\checkmark$ v stolpcu $F_i$ (lice): vsako lice je trikotnik, ima 3 povezave.
> *   Dvojno štetje:
>     $$2 \cdot |E| = 3 \cdot |F|$$
> 
> (3) Koliko deliteljev imajo naravna št. "v povprečju"?
> *   Pogledamo na $[n]$ in vzamemo $n \to \infty$.
> *   Tabela velikosti $n \times n$. Vrstice: števila $i \in \{1 \dots n\}$, Stolpci: možni delitelji $d \in \{1 \dots n\}$.
> *   Relacija: $d$ deli $i$ ($d|i$).
> *   $v_r(i) = s_i$: število deliteljev števila $i$.
> *   $v_s(d)$: število števil v $[n]$, ki so večkratniki $d$. To je $\lfloor \frac{n}{d} \rfloor$.
> *   Vsota: $\sum_{i=1}^n s_i = \sum_{d=1}^n \lfloor \frac{n}{d} \rfloor$.
> *   Povprečje:
>     $$\frac{1}{n} \sum_{i=1}^n s_i = \frac{1}{n} \sum_{d=1}^n \lfloor \frac{n}{d} \rfloor \approx \frac{1}{n} \sum_{d=1}^n \frac{n}{d} = \sum_{d=1}^n \frac{1}{d} = H_n$$
>     $H_n$ (harmonično število) asimptotično raste kot $\ln n$.
> 
> (4) Dokaz
> $$
> \sum_{k=0}^{n} \binom{n}{k} = 2^n
> $$
> 
> $\text{el. } [n] \downarrow$ 
> podmnožice $\rightarrow$
> 
> 
> 
> $i \ R \ A \Leftrightarrow |A| = i$
> 
> Po stolpcih velja $2^n$ saj imamo v vsakem stolpcu eno relacijo - podmnožica ima eno velikost.
> 
> Po vrsticah velja da imamo toliko kljukic  v vrstici kolikor je podmnožic velikosti $i$.
> $$
> 1 + \binom{n}{1} + \binom{n}{2} + \dots + \binom{n}{n-1} + 1
> $$
> $$
> \Rightarrow \sum_{k=0}^{n} \binom{n}{k} = 2^n
> $$



### Podmnožice in načrti

**Binomski koeficient**


$$2^A = \{B \subset A\}$$

$$\binom{\,A\,}{\,k\,} = \{ B \subset A : |B| = k\}$$

>[!|hide]- Neka perspektiva
> *Recimo da imamo nekoga ki meče žogo v koš, in gledamo na koliko načinov lahko doseže 1 od 3 košev. Efektivno izbiramo iz množice 3 zadetkov a izberemo samo 2, kar definira tudi koliko zgrešitev bo.*
> *Taka stvar je isto pri binomskem izreku, $(x+y)^{n}$, kjer izbiramo med množico $x_{n}$ in izbiramo koliko $x_{i}$ za $k$-to potenco.*

Def:

$$\binom{\,n\,}{\,k\,} = \left| \binom{\,[n]\,}{\,k\,}\right|$$

oz. število k-elementnih podmnožic množice z $n$ elementi; število načinov da izberemo $k$ elementov iz množice z $n$ elementi.

$$\binom{\,[n]\,}{\,0\,} = \{ \emptyset\}$$
$$\binom{\,[n]\,}{\,1\,} = \{ \{ 1\},\{ 2\},...,\{ n\}\}$$
$$\binom{\,[n]\,}{\,n\,} = \{ [n]\}$$

$$\binom{\,n\,}{\,k\,}=0 \,;\; k < 0 \lor k > n$$

Binomski koeficient je simetričen

$$\binom{\,n\,}{\,k\,} = \binom{\,n\,}{\,n-k\,}$$
$$ $$
$$\phi: \binom{\,[n]\,}{\,k\,} \rightarrow \binom{\,[n]\,}{\,n-k\,}$$
$$\phi (A) = A^{C}$$
$$ $$

Rekurzivna zveza

$$ \binom{\,n\,}{\,k\,} = \binom{\,n-1\,}{\,k-1\,} + \binom{\,n-1\,}{\,k\,}$$

>[!|dokaz]- Dokaz:
> 
> Predpostavimo da damo nek element ven iz množice. Imamo $n-1$ elementov. Nato poiščemo vse podmnožice velikosti $k-1$ to so te ki bodo po dodajanju tega elementa vsebovale tudi le tega in bo velikost $k$.
> Nato pa lahko poiščemo še vse množice velikosti $k$ ki ne vsebujejo odstranjenega elementa in dobimo torej množice ki tako ali tako nimajo odstranjenega elementa torej so velikosti $k$. Ko dodamo odstranjen element nazaj v množico pa ga lahok dodamo še vsem množicam velikosti $k-1$, in dobimo podmnožice velikosti $k$ kar so potem vse podmnožice velikosti $k$.

> **Formula za binomski koeficient**
> 
> $$\binom{\,n\,}{\,k\,} = \frac{n^{\underline{k}}}{k!}$$
> 
> >[!|dokaz]- Dokaz:
> >Izberemo zaporedja $k$ elementov iz množice $n$ ampak ker smo šteli vse permutacije $k$ elementov moramo za vsako množico zaporedij z istimi elementi izločiti vse permutacije teh elementov - torej jih lahko damo po skupinah velikosti $k!$ - to pomeni da delimo s $k!$.



> $$1+2+...+n = \binom{\,n+1\,}{\,2\,}$$
> 
> >[!|dokaz]- Dokaz:
> > Z indukcijo in rekurzivno zvezo


**Pascalov trikotnik**


$$
\begin{array}{ccccccccccccc}
&&&&&& 1 &&&&&& \\
&&&&& 1 && 1 &&&&& \\
&&&& 1 && 2 && 1 &&&& \\
&&& 1 && 3 && 3 && 1 &&& \\
&& 1 && 4 && 6 && 4 && 1 && \\
& 1 && 5 && 10 && 10 && 5 && 1 & \\
1 && 6 && 15 && 20 && 15 && 6 && 1
\end{array}
$$

Kjer vsaka $i$-ta vrstica zaznamuje množico z $i$ elementi.
Vsak $j$-ti stolpec pa število $j$-elementnih podmnožic.

**Binomski izrek**

$$(x+y)^{n} = \sum_{0}^{n}\binom{\,n\,}{\,i\,}a^{i}b^{n-i}$$

Za to potrebujemo komutativni kolobar oz. da $a$ in $b$ komutirata in enoto če definiramo še $(a+b)^{0}$

>[!|dokaz]- Dokaz:
>1\. Način - indukcija po $n$-ju
>2\. Način - krajša ampak z idejo indukcije
>$$(a+b)^{n}=\sum_{k}^{}\binom{\,n\,}{\,k\,}a^{n-k}b^{k}$$
>$$(a+b)^{n} = (a+b)^{n-1}(a+b)$$
>$$= (\sum_{k}^{}\binom{\,n-1\,}{\,k\,}a^{n-1-k}b^{k})(a+b)$$
>$$\sum_{k}^{}\binom{\,n-1\,}{\,k\,}a^{n-k}b^{k} + \sum_{k}^{} \binom{\,n-1\,}{\,k\,}a^{n-1-k}b^{k+1}$$
>$$\sum_{k}^{}\binom{\,n-1\,}{\,k\,}a^{n-k}b_{k}+\sum_{k}^{}\binom{\,n-1\,}{\,k-1\,}a^{n-k}b^{k}$$
>$$\sum_{k}^{}(\binom{\,n-1\,}{\,k\,} + \binom{\,n-1\,}{\,k-1\,})a^{n-k}b^{k}$$
>3\. Način kombinatorični dokaz
>
>Kombinatorični dokaz Binomskega izreka, ki trdi, da je $(x+y)^n = \sum_{k=0}^{n} \binom{n}{k} x^{n-k} y^k$, se osredotoča na razumevanje, kako nastanejo posamezni členi v razširitvi produkta. Izraz $(x+y)^n$ predstavlja produkt $n$ enakih faktorjev $(x+y)$, torej $\underbrace{(x+y)(x+y)\cdots(x+y)}_{n \text{ faktorjev}}$. Ko ta produkt razširimo, vsak posamezni člen nastane z izbiro bodisi $x$ ali $y$ iz vsakega od $n$ oklepajev in nato pomnožitvijo teh izbranih elementov.
> 
> Oglejmo si splošni člen $x^{n-k}y^k$ v tej razširitvi, kjer $k$ predstavlja število faktorjev $y$ in $n-k$ število faktorjev $x$. Da bi dobili ta člen, moramo izbrati $y$ iz natanko $k$ oklepajev, medtem ko moramo iz preostalih $n-k$ oklepajev izbrati $x$. Ker je vrstni red izbire nepomemben, je ključno vprašanje, na koliko različnih načinov lahko izberemo teh $k$ oklepajev izmed vseh $n$ razpoložljivih oklepajev, iz katerih bomo vzeli $y$.
> 
> Število načinov za izbiro $k$ oklepajev iz množice $n$ oklepajev je natanko binomski koeficient $\binom{n}{k}$, kar je po definiciji število kombinacij brez ponavljanja. Vsak od teh $\binom{n}{k}$ načinov ustvari natanko en primerek člena $x^{n-k}y^k$. Ko se vsi ti primerki v končni vsoti seštejejo, je skupni koeficient pri členu $x^{n-k}y^k$ enak $\binom{n}{k}$. Ker ta logični argument velja za vsako vrednost $k$ od $0$ do $n$, s tem dokažemo, da je Binomski izrek resničen in da je celotna razširitev enaka vsoti teh členov: $(x+y)^n = \sum_{k=0}^{n} \binom{n}{k} x^{n-k} y^k$.


Pogosto pišemo tudi 

$$(1+x)^{n} = \sum_{0}^{n}\binom{\,n\,}{\,k\,}x^{k}$$

***
### Izbori

Imamo $n$ oštevilčenih kroglic in izberemo $k$ kroglic.

Razlikujemo med tem ali je **vrstni red pomemben** ali ne in ali lahko izbiro vračamo nazaj oz. so **dovoljene ponovitve**.


| | **Ponovitve so Dovoljene (DA)** | **Ponovitve niso Dovoljene (NE)** |
| :---: | :---: | :---: |
| **Vrstni red je Pomemben (DA)** | **Variacije s ponavljanjem** | **Variacije (Permutacije) brez ponavljanja** |
| | $$n^k$$ | $$\frac{n!}{(n-k)!}$$ |
| **Vrstni red ni Pomemben (NE)** | **Kombinacije s ponavljanjem** | **Kombinacije brez ponavljanja** |
| | $$\binom{n+k-1}{k}$$ | $$\binom{n}{k} = \frac{n!}{k!(n-k)!}$$ |

**Kombinacije s ponavljanjem**

Če imamo $n$ elementov ki se lahko ponavljajo in jih hočemo razporediti na $k$ mest.

Ker vrstni red ni pomemben lahko vse kombinacije kjer ponavljamo elemente preuredimo v zaporedje kjer so vsi elementi ki so se ponovili skupaj. To naj bo predstavnik te kombinacije - torej lahko vse kombinacije s ponavljanjem predstavimo z zaporedjem kjer so vsi ponovljeni elementi drug za drugim.

Sedaj lahko vpeljemo element pregrade ki stojijo med skupinami. Torej če imamo neke $x,y,z$ elemente ki se lahko ponavljajo na $k$ mestih jih lahko grupiramo in vidimo da jih lahko ločimo z $2$ pregradama oz. če imamo $n$ različnih elementov jih lahko ločimo z $n-1$ pregradami.

Če dodamo našim $k$ prostim mestom še mesta za pregrade dobimo $k + n-1$ mest. Opazimo da je s postavitvijo pregrad že definirana kombinacija saj ostane $k$ mest kjer so po skupinah ločeni elementi.

Vidimo da je v resnici izbira $n-1$ mest za pregrade iz $k+n-1$ vseh mest - za pregrade  in elemente $n-1 + k$.

Torej je enačba

$$\binom{\,k+n-1\,}{\,n-1\,}$$

Kar je enako

$$\binom{\,k+n-1\,}{\,k\,}$$

***

### Kompozicije

Kompozicija števila $n$ je $k$-terica $\lambda_{i}$, kjer velja $\lambda_{i} \in [n]$

$$\sum_{i}^{}\lambda _{i} = n$$

$\lambda_{i}$ so členi kompozicije
$l$ je dolžina kompozicije
$n$ je velikost kompozicije

Za $n = 9$:
Kompozicije si lahko predstavljamo kot kombinacije s ponavljanjem 9 elementov na 9 mestih. Predstavljamo si 9 različnih enk kjer če se neka enka ponavlja tvori večje število. To pomeni da imamo 8 pregrad torej 17 mest iz katerih izbiramo 8 mest za pregrado.

Posplošeno imamo kombinacije s ponavljanjem $n$ elementov na $n$ mestih - $n$ različnih enk. Imamo $n-1$ pregrad oz. $n-1$ mest za pregrado kjer jo lahko postavimo ali ne.

*Mest je $n-1$ ker mora biti vsako število večje ali enako 1, kar pomeni da vsilimo med vsako enko mesto za pregrado potem pa se odločimo ali jo postaivmo ali ne.*

Tako imamo skupno število kompozicij enako

$$2^{n-1}$$

Za 0 velja da ima eno kompozicijo - prazno kompozicijo.

Št kompozicij števila $n$ dolžine $k$ da imamo $n-1$ aktivnih mest a lahko izberemo le $k-1$ mest za pregrado.

$$\binom{\,n-1\,}{\,k-1\,}$$
***
**Šibka kompozicija** števila $n$ je $\lambda = (\lambda_{1},...,\lambda_{n}) \,;\; \lambda_{i}\geq 0$.

Koliko je šibkih kompozicijnekega števila $n$ dolžine $k$.

>[!|dokaz]- Dokaz:
> 1\. Način
> Imamo neko šibko kompozicijo $0+0+3+1+0+2+0+0+1$ kar je 7.
> 
> $$||***|*||**|||*$$
> 
> Imamo $n+k-1$ objektov in jih dajemo na $k-1$ mest kamor damo pregrade.
> 
> $$\binom{\,n+k-1\,}{\,k-1\,}$$
> 
> 2\. Način
> 
> $$\lambda_{1}+...+\lambda_{k} = n \,;\; \lambda_{i} \geq 0$$
> 
> $$\mu_{i}= \lambda_{i}+1$$
> $$\mu_{1}+...+\mu_{k}=n+k$$
> $$\binom{\,n+k-1\,}{\,k-1\,}$$

Šibke kompozicije so spet določene s pregradami in različnimi enkami ki jih lahko grupiramo.
Razlika je da ne določimo vnaprej $n-1$ mest kjer so lahko pregrade ali ne. Mi imamo $n$ tipov enk ki sestavijo število $n$ ki jih lahko ponavljamo in grupiramo. Postavljamo pregrade. Ker imamo $n$ elementov jih razdelimo z $n-1$ pregradami. Če imamo $k$ mest pomeni da imamo $k+n-1$ prostih mest kjer definiramo šibko kompozicijo s postavitvijo pregrad nakar ostane $k$ mest kamor damo ostale enke. To pomeni da med $k+n-1$ mesti izbiramo $n-1$ mest za pregrade.

Kombinacije s ponavljanjem je natanko šibka kompozicija št $n$ dolžine $k$.

***

### Multinomski koeficienti

**Multimnožica** je množica kjer se elementi lahko ponavljajo.

$$A = \{ 1,1,1,2,2,3,3\} = \{ 1^{3}, 2^{2}, 3^{2}\}$$

Multimnžica $M$ je definirana kot par množice elementov $S$ in preslikave ki slika vsak element množice $S$ v število ponovitev v multimnožici.

$$M = (S, \varphi)$$

$S$ je množica, $\varphi: S \rightarrow \mathbb{N}$

$$A = (S, \varphi)$$
$$S = [4], \varphi(1)=3, \varphi(2)=1,...$$

Naj bo permutacija multimnožice mešanje elementov, kjer ne ločimo med istimi elementi.
To pomeni da ko imamo $a_{1}a_{2}b_{1}$ je enako kot $a_{2}a_{1}b_{1}$.

**Primer**

$$11223,12123,11322,...$$ 

Dobimo jih lahko z izbiranjem mest za iste elemente torej 2 mesti izberemo od 5 za enke, 2 za dvojke in 1 za trojke:

Za enke imamo $\binom{\,5\,}{\,2\,}$ za dvojek $\binom{\,3\,}{\,2\,}$ za trojek $\binom{\,1\,}{\,1\,}$.

$$\binom{\,5\,}{\,2\,} \binom{\,3\,}{\,2\,} \binom{\,1\,}{\,1\,} = 30$$

Lahko pa ugotovimo da so to vse permutacije ki jih lahko grupiramo po temu da ugotovimo koliko elementov je v skupini kjer so elementi med katerimi ne razlikujemo pomešani, kar so njegove permutacije. V taki skupini jih je natanko $k!$, kjer je element ponovljen $k$-krat. Torej delimo s številom členov v tej skupini da dobimo število dejanskih različnih skupin.

Imamo $5!$ načinov ampak se znebimo permutacij enk in dvojk, torej 

$$\frac{5!}{2!2!}$$
***
Imamo $M = \{ 1^{a}, 2^{a_{2}},...,k^{a_{k}}\}$

Elemente lahko premešamo na več načinov

**1\. Način:** 
Naprej izberemo mesta za enke $\binom{\,n\,}{\,a_{1}\,}$ potem izberemo mesta za dvojke $\binom{\,n-a_{1}\,}{\,a_{2}\,}$, potem trojke $\binom{\,n-a_{1}-a_{2}\,}{\,a_{3}\,}$ in tako naprej do$\binom{\,a_{k}\,}{\,a_{k}\,}$

$$\binom{\,n\,}{\,a_{1}\,}\binom{\,n-a_{1}\,}{\,a_{2}\,}...\binom{\,a_{k}\,}{\,a_{k}\,}$$
$$\frac{n!}{a_{1}(n-a_{1})!}\frac{(n-a_{1})!}{a_{2}!(n-a_{1}-a_{2})!}...$$

Vse se pokrajša in dobimo $$\frac{n!}{a_{1}!...a_{k}!}$$

**2\. Način** 
$1_{1},...,1_{a_{1}},2_{1},...,2_{a_{2}},...,k_{1},...,k_{a_{k}}$

$n!$ permutacij, izbrišemo vsako permutacijo multimnožice dobimo

$a_{1}!a_{2}!...a_{k!}$-krat

$$\binom{\,n\,}{\,a_1,...,a_{k}\,}:=\frac{n!}{a_{1}!...a_{k}!}$$

kjer je 

$$a_{1}+...+a_{k} = n$$

Temu pravimo **multinomski koeficient**.

$$\binom{\,a_{1}+a_{2}\,}{\,a_{1},a_{2}\,} = \binom{\,a_{1}+a_{2}\,}{\,a_{1}\,} = \binom{\,a_{1}+a_{2}\,}{\,a_{2}\,}$$
$$\binom{\,n\,}{\,k\,} = \binom{\,n\,}{\,k,n-k\,}$$

**Multinomski izrek**

$$(x_{1}+...+x_{k})^{n} = \sum_{a_{1}+...+a_{k} = n} \binom{\,n\,}{\,a_{1},...,a_{k}\,} x_{1}^{k_{1}}...x_{k}^{k_{k}}$$


***




**Načelo vključitev izključitev** *Principle of inclusion and exclusion*

$$
\left| \bigcup_{i=1}^{n} A_i \right| = $$ 
$$ \sum_{i} |A_i| - \sum_{i < j} |A_i \cap A_j| + \sum_{i < j < k} |A_i \cap A_j \cap A_k| - \cdots + (-1)^{n-1} \left| \bigcap_{i=1}^{n} A_i \right|$$

Kot vidimo seštevamo in odštevamo vedno večje preseke množic. Indeksi zaznamujejo vse kombinacije množic $A_{i}$ ki jih imamo. Torej če imamo $n$ množic - $A_{1,...,n}$ bomo seštevali moči množic katerih indeksi bojo neka podmnožica indeksov. Torej pri odštevanju preseka 2 množic bomo imeli $A_{i}\cap A_{j} \,;\; \{ i,j\}\subset [n]$ torej $\sum_{I \subset [n], |I| = 2}^{}|A_{i}\cap A_{j}|$. 

To bomo počeli za za vsako podmnožico indeksov vseh velikosti, vse kar se spremnija je le predznak zato lahko zapišemo




$$ \left| \bigcup_{i=1}^{n} A_i \right| = \sum_{\emptyset \ne I \subseteq \{1, \dots, n\}} (-1)^{|I|-1} \left| \bigcap_{i \in I} A_i \right| $$

Če definiramo presek 

$$A_{I}:=\{ a \in A:a \in A_{i} , \forall i \in I\}$$

Dobimo formulo

$$ \left| \bigcup_{i=1}^{n} A_i \right| = \sum_{\emptyset \ne I \subseteq \{1, \dots, n\}} (-1)^{|I|-1} \left| A_{I} \right| $$

**Dokaz: todon**



**Ekvivalentno lahko uporabimo deMorganove zakone**

Vedno predpostavljamo da je $A_{1},...,A_{n} \subset A$, da lahko definiramo komplement $A_{i}^{C}$ kot $A - A_{i}$.

$$A_{I}=\{ a \in A:a \in A_{i} \forall i \in I\}$$

$$A_{\emptyset}= \{ a \in A:a \in A, \forall i \in \emptyset\} = A$$
$$|A_{\emptyset}| = A$$
$$|\emptyset| = 0$$

Velja

$$
\left|\bigcup A_{i}\right| = \left|\left(\bigcap A_{i}^{c}\right)^{c}\right|
$$
$$
\left|\bigcup A_{i}\right| = |A| - \left|\bigcap A_{i}^{c}\right|
$$
$$
\left|\bigcap A_{i}^{c}\right| = |A| - \left|\bigcup A_{i}\right|
$$
$$
= |A| - \sum_{\emptyset \neq I \subseteq [n]} (-1)^{|I|-1} |A_{I}|
$$

Ker je $|A|$ definiran kot $|A_\emptyset|$ ga lahko vključimo v vsoto in razširimo mejo $I \subset [n]$. Prej pa še minus izpred vsote damo v vsoto in dobimo $(-1)^{|I|}$.


$$
= |A| + \sum_{\emptyset \neq I \subseteq [n]} (-1)^{|I|} |A_{I}|
$$
$$
= \sum_{I \subseteq [n]} (-1)^{|I|} |A_{I}|
$$

$$\Rightarrow$$
$$\left|\bigcap_{i=1}^{n} A^{C}_{i}\right| = \sum_{I \subset [n]}^{}(-1)^{|I|}\left|\bigcap_{i \in I} A_{i} \right| $$

Velja da je torej komplement unije enak preseku komplementov $A_{i}$ kar je enako vsoti kombinacij presekov.

$$ \left|\left(\bigcup A_{i}\right)^{C} \right| = \left|\bigcap_{i=1}^{n} A^{C}_{i}\right| = \sum_{I \subset [n]}^{}(-1)^{|I|}\left|\bigcap_{i \in I} A_{i} \right|$$

*Še kle rabm dokaz*

**Kronickerjeva delta**

$$\delta_{ij} = \begin{cases}
1: i = j \\
0: i \neq j \\
\end{cases}$$

Primer uporabe

$$0^{n} = \delta_{0n}$$

*Vedno je enaka 0 razen pri $0^{0} = 1$.*

$$\delta_{0m} = \sum_{k=0}^{m}\binom{\,m\,}{\,k\,}(-1)^{k}$$

>[!|dokaz]- Dokaz:
> 
> $$ \left| \bigcup_{i=1}^{n} A_i \right| = \sum_{i} |A_i| - \sum_{i < j} |A_i \cap A_j| + \sum_{i < j < k} |A_i \cap A_j \cap A_k| - \cdots + (-1)^{n-1} \left| \bigcap_{i=1}^{n} A_i \right| $$
> 
> ---
> 
> ## Dokaz Principa Vključevanja in Izključevanja (PVII) za $n$ Množic
> 
> Dokaz temelji na preštevanju, kolikokrat je poljuben element $x$, ki pripada uniji, prispeval k vsoti na desni strani enačbe (DSE).
> 
> **Cilj dokaza:** Pokazati, da vsak element $x$, ki pripada vsaj eni množici $A_i$ (tj. $x \in \bigcup_{i=1}^{n} A_i$), prispeva k DSE natanko **enkrat**.
> 
> ### 1. Definicija elementa in število njegovih pojavitev
> 
> Vzemimo poljuben element $x$ iz unije $\bigcup_{i=1}^{n} A_i$.
> 
> Naj bo $m$ **število množic $A_i$, ki vsebujejo element $x$**. Ker je $x$ v uniji, vemo, da je $m \ge 1$.
> $$1 \le m \le n$$
> 
> ### 2. Prispevek elementa $x$ k desni strani enačbe (DSE)
> 
> Preštejmo, kolikokrat $x$ prispeva k posameznim vsotam v PVII:
> 
> #### Korak 1: Vsota enojnih množic (Sum $\sum |A_i|$)
> Element $x$ je vključen v $m$ množic. Zato prispeva k prvi vsoti $m$-krat.
> $$\text{Prispevek: } \binom{m}{1}$$
> 
> #### Korak 2: Vsota dvojnih presekov (Sum $\sum |A_i \cap A_j|$)
> Element $x$ se pojavi v preseku dveh množic $A_i \cap A_j$ samo, če sta $A_i$ in $A_j$ med tistimi $m$ množicami, ki vsebujejo $x$.
> Število parov množic, izbranih iz $m$ množic, je $\binom{m}{2}$.
> $$\text{Prispevek: } \binom{m}{2}$$
> 
> #### Korak $k$: Vsota $k$-terih presekov (Sum $\sum |A_{i_1} \cap \dots \cap A_{i_k}|$)
> Element $x$ prispeva k vsoti $k$-terih presekov, če je izbran $k$-terice množic, ki vsebujejo $x$. To je mogoče le, če izberemo $k$ množic izmed tistih $m$ množic, ki element $x$ vsebujejo.
> $$\text{Prispevek: } \binom{m}{k}$$
> 
> #### Korak $n$: $n$-kratni presek
> Ker je $x$ prisoten v le $m$ množicah, in $m \le n$, prispeva k $n$-kratnemu preseku le, če je $m=n$, torej $\binom{n}{n}$. Na splošno je prispevek $\binom{m}{n}$ (kar je 0, če je $m < n$).
> 
> ### 3. Skupni prispevek elementa $x$
> 
> Skupni prispevek elementa $x$ k desni strani enačbe (DSE) je alternirajoča vsota teh prispevkov (upoštevajoč predznake v PVII):
> 
> $$\text{DSE prispevek}(x) = \binom{m}{1} - \binom{m}{2} + \binom{m}{3} - \cdots + (-1)^{m-1} \binom{m}{m} + \cdots + (-1)^{n-1} \binom{m}{n}$$
> 
> Ker je $\binom{m}{k} = 0$, če je $k > m$, se vsota ustavi pri $k=m$:
> 
> $$\text{DSE prispevek}(x) = \binom{m}{1} - \binom{m}{2} + \binom{m}{3} - \cdots + (-1)^{m-1} \binom{m}{m}$$
> 
> ### 4. Uporaba Binomske formule
> 
> Zdaj uporabimo splošno znano identiteto, ki izhaja iz razvoja $(1-1)^m = 0$. Iz binomskega izreka vemo:
> 
> $$(1 + y)^m = \sum_{k=0}^{m} \binom{m}{k} y^k$$
> 
> Vstavimo $y = -1$:
> 
> $$(1 + (-1))^m = \sum_{k=0}^{m} \binom{m}{k} (-1)^k$$
> 
> $$0 = \binom{m}{0} (-1)^0 + \binom{m}{1} (-1)^1 + \binom{m}{2} (-1)^2 + \cdots + \binom{m}{m} (-1)^m$$
> 
> $$0 = \binom{m}{0} - \binom{m}{1} + \binom{m}{2} - \binom{m}{3} + \cdots + (-1)^m \binom{m}{m}$$
> 
> Ker vemo, da je $\binom{m}{0} = 1$, lahko preuredimo enačbo:
> 
> $$1 = \binom{m}{1} - \binom{m}{2} + \binom{m}{3} - \cdots + (-1)^{m-1} \binom{m}{m}$$
> 
> ### 5. Zaključek
> 
> Ugotovili smo, da je skupni prispevek poljubnega elementa $x$ k desni strani enačbe (DSE) natanko:
> 
> $$\text{DSE prispevek}(x) = 1$$
> 
> Ker vsak element $x$ v uniji prispeva k DSE natanko 1-krat, je vsota na DSE natanko enaka številu elementov v uniji.
> 
> $$\left| \bigcup_{i=1}^{n} A_i \right| = \text{Število elementov } x \text{ v uniji} \times 1$$
> 
> To dokazuje Princip vključevanja in izključevanja za $n$ množic.


*Računanje vseh surjekcij iz $A$ v $B$*


Število surjekcij $N_{\text{sur}}$ je:

$$ N_{\text{sur}} = \sum_{k=0}^{m} (-1)^k \binom{m}{k} (m-k)^n $$

**Razlaga formule:**
1. **$k=0$ (Vsi):** $\binom{m}{0} m^n$. To je skupno število vseh funkcij.
2. **$k=1$ (Odštejemo, kjer manjka 1 element):** $\binom{m}{1} (m-1)^n$. Izberemo $k=1$ element, ki ga funkcija ne doseže, in preštejemo vse funkcije, ki preslikajo $A$ v preostalih $m-1$ elementov.
3. **$k=2$ (Prištejemo nazaj, kjer manjkata 2 elementa):** $\binom{m}{2} (m-2)^n$. To so funkcije, ki ne dosežejo dveh izbranih elementov. Te so bile dvakrat odštete prej, zato jih moramo prišteti nazaj.
4. **... do $k=m$:** $\binom{m}{m} (m-m)^n = 1 \cdot 0^n$ (če je $n \ge 1$; če je $n=0$, je 1).

### Končna formula za število surjekcij

$$ \text{Število surjekcij } (n \to m) = m! \cdot S(n, m) = \sum_{k=0}^{m} (-1)^k \binom{m}{k} (m-k)^n $$


***
**Preštevanje premestitev**: premutacije brez negibne točke : torej $\pi(i) \neq i$.
>[!|hide]-  
> Predstavljeni izpisek natančno opisuje prve korake uporabe **Principa vključitve in izključitve (PIE)** za izračun števila **deranžmajev** ($D_n$).
> 
> Deranžma je posebna vrsta permutacije, pri kateri noben element ni preslikan sam vase (tj. nima fiksne točke).
> 
> Spodaj je podrobna razlaga posameznih korakov in izpeljave formule.
> 
> ---
> 
> ## B) Preštevanje deranžmajev (Permutacije brez fiksne točke)
> 
> **Cilj:** Izračunati število permutacij $D_n$ množice $\{1, 2, \dots, n\}$, za katere velja, da je $\pi(i) \neq i$ za vsak $i \in \{1, \dots, n\}$.
> 
> Za izračun uporabimo Princip vključitve in izključitve.
> 
> ### 1. Določitev Univerzalne Množice ($U$)
> 
> **Naj bo $U$ množica vseh permutacij.**
> *   Velikost univerzalne množice je:
>     $$|U| = n!$$
> *   To je celotno število možnih razporeditev $n$ elementov.
> 
> ### 2. Določitev "Slabih" Lastnosti (Množice $A_i$)
> 
> **Naj bo $A_i$ množica vseh permutacij, ki imajo fiksno točko $i$.**
> *   To pomeni, da je za $\pi \in A_i$ izpolnjeno: $\pi(i) = i$.
> *   $A_i$ predstavlja "slabe" permutacije, saj kršijo pogoj, da noben element ni fiksna točka.
> *   Cilj je izračunati: $$D_n = |U| - |\bigcup_{i=1}^n A_i|$$
>     (Število deranžmajev je število vseh permutacij minus število tistih, ki imajo vsaj eno fiksno točko).
> 
> ### 3. Izračun Velikosti Posameznega Preseka
> 
> Po Principu vključitve in izključitve moramo izračunati vsote velikosti presekov $k$ množic, imenovanih $S_k$. Najprej določimo velikost posameznega preseka $k$ množic.
> 
> **Obravnavamo presek $A_{i_1} \cap A_{i_2} \cap \dots \cap A_{i_k}$:**
> *   Ta presek predstavlja množico permutacij, ki imajo fiksne točke na *natančno določenih* $k$ mestih: $i_1, i_2, \dots, i_k$.
> *   Ker so ta mesta fiksirana ($\pi(i_j) = i_j$), preostalih $n - k$ elementov lahko poljubno preuredimo med preostalimi $n - k$ mesti.
> *   Število načinov preureditve $n-k$ elementov je **$(n-k)!$**.
> *   Torej, velikost katerega koli določenega preseka $k$ množic je:
>     $$|A_{i_1} \cap \dots \cap A_{i_k}| = (n-k)!$$
> 
> ### 4. Izračun Vsote Presekov ($S_k$)
> 
> $S_k$ je vsota velikosti vseh možnih presekov, ki vključujejo *točno $k$* množic $A_i$.
> 
> *   **Število možnih presekov $k$ množic:** Ker nas ne zanimajo, kateri elementi so fiksne točke, temveč le koliko jih je ($k$), moramo izbrati $k$ indeksov izmed $n$ možnosti. To storimo na $\binom{n}{k}$ načinov.
>     $$\text{Število presekov} = \binom{n}{k}$$
> *   **Izračun $S_k$:** Ker je velikost vsakega takšnega preseka $(n-k)!$, je vsota vseh $k$-presekov produkt števila možnosti in velikosti posameznega preseka:
>     $$S_k = \sum_{1 \le i_1 < \dots < i_k \le n} |A_{i_1} \cap \dots \cap A_{i_k}| = \binom{n}{k} (n-k)!$$
> 
> **Poenostavitev $S_k$:**
> Uporabimo definicijo binomskega koeficienta $\binom{n}{k} = \frac{n!}{k!(n-k)!}$:
> $$S_k = \frac{n!}{k!(n-k)!} \cdot (n-k)!$$
> $$S_k = \frac{n!}{k!}$$
> 
> ---
> 
> ### Končna Formula za Deranžmaje ($D_n$)
> 
> S pomočjo $S_k$ in Principa vključitve in izključitve lahko sedaj izračunamo število deranžmajev ($D_n$).
> 
> Število permutacij, ki imajo vsaj eno fiksno točko, je:
> $$|\bigcup_{i=1}^n A_i| = S_1 - S_2 + S_3 - \dots + (-1)^{n-1} S_n = \sum_{k=1}^n (-1)^{k-1} S_k$$
> 
> Število deranžmajev $D_n$ je torej:
> $$D_n = |U| - |\bigcup_{i=1}^n A_i| = n! - \sum_{k=1}^n (-1)^{k-1} S_k$$
> 
> Če vstavimo izračun za $S_k = \frac{n!}{k!}$:
> $$D_n = n! - \sum_{k=1}^n (-1)^{k-1} \frac{n!}{k!}$$
> 
> Lahko preoblikujemo tako, da vključimo $k=0$ člen (ki je $S_0 = |U| = n!$):
> $$D_n = n! + \sum_{k=1}^n (-1)^{k} \frac{n!}{k!} = \sum_{k=0}^n (-1)^{k} \frac{n!}{k!}$$
> 
> **To je končna formula za število deranžmajev $D_n$.**


***

**Eulerjeva funkcija**

$$\varphi(n) = |\{ i \in [n] \,;\;i \perp n\}|$$

Razstavimo število na prafaktorje

$$n = p_{1}^{e_{1}}...p_{k}^{e_{k}}$$

Hočemo prešteti števila ki niso deljiva z nobenim od teh prafaktorjev, in njihovo število odštejemo od $n$.

Imamo $[n] \Rightarrow |[n]| = n$

Naj bo $A_{i}$ množica števil ki so deljiva z s prafaktorjem $p_{i}$.

Če odštejemo presek vseh $A_{i}$ smo lahko na primer število $p_{1}p_{2} \leq n$ odšteli dvakrat zato uporabimo princip o vključitvi in izključitvi.

Iščemo torej komplement unije $A_{i}$.

$$A_{i}=\{ m \in [n]; p_{i}|m\}$$

Velja da je $|A_{i}| = \frac{n}{p_{i}}$

$$A_{i} \cap A_{j} = \{ m \in [n]; p_{i}p_{j}|m\}$$

Kot tudi da je $|A_{i} \cap A_{j}| = \frac{n}{p_{i}p_{j}}$

$$A_{I} = \{ m \in [k];  \prod_{i \in I} p_{i} |m\}$$

Torej velja

$$|A_{I}| = \frac{n}{\prod_{i \in I}\,p_{i}}$$

Če vzamemo unijo vseh množic kjer so števila deljiva z nekim prafaktorskim razcepom $n$ in vzamem njen komplement potem dobim vse števila ki so si tuja.

$$\left(\bigcup_{I \subset [n]} A_{I} \right)^{C}= \bigcap_{I \subset [n]} A_{I}^{C}$$

$$\sum_{I \subset [k]}^{}(-1)^{|I|} \cdot  n \cdot  \frac{1}{\prod_{i \in I}p_{i}}$$


$$= n \cdot \prod_{p|n}(1-\frac{1}{p})$$

***

### Načrti in t-načrti

*Neka motivacija
Podjetje izdeluje več inačic nekega produtka
Radi bi jih testirali na strankah.
hočemo da je vsaka enačica enakokrat testiranaa in da ima vsaka stranka enako števil oenačic za preizkusitw*