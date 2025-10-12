## Ponovitev z gimnazije


Če imamo $n$ predmetov in jih poskušamo razporediti na $n$ mest potem to lahko storimo na $n!$ načinov.
Na prvo mesto lahko damo enega izmed $n$ predmetov, na drugo enega izmed $n-1$ in tako naprej. Temu pravimo permutacije.

$$P_{n} = n!$$

Če imamo $n$ predmetov in jih probamo postaviti na $k$ mest potem lahko število načinov izračunamo z

$$p_{k,n} = \frac{n!}{(n-k)!}$$

To lahko razložimo kot na vsako od k mest lahko damo $n, n-1, n-2,...,n-k+1$ elementov kar je natanko $\frac{n!}{(n-k)!}$, ker se preostalih znebimo tako da jih pokrajšamo.

Oziroma če si predstavljamo vseh $n!$ razporeditev. Recimo da imamo razporeditev 5 elemtnov na 3 mesta. Imamo lahko 12345 in 12354, kjer imamo razporeditev na prvih 3 mestih ponovljeno, in ker nas zanimajo le te moramo vse možne ponovitve zbrisati. Ker sta ostali le 2 mesti se lahko elementi na teh mestih razporedijo na $2!$ načinov, to jih da v grupe velikosti $2!$, da dobimo število grup verlikosti $2!$ pa moramo deliti z $2!$. 

Če imamo elemente ki se lahk ponovijo na $k$ mestih imamo

$$n^{k}$$

Če hočemo razporediti elemente kjer se nek elemente ki se ponovijo kjer se ponovijo $k_{1},...,k_m$ imamo

$$p^{n}_{k_{1},...,k_{n}} = \frac{n!}{k_{1}!k_{2}!...k_{n}!}$$

Spet delujemo po principu da dobimo $k_{1}!,...,k_{n}!$, kjer moramo deliti da dobimo pravilno število možnosti. Če imamo črke naprimer: $\text{BAN}_1\text{AN}_2$ in $\text{BAN}_2\text{AN}_1$ imamo spet $2!$ intako za vse možne črke.

Nato pa imamo če kombinacije, kjer iščemo samo vse množice velikosti  $k$ v množici z $n$ elementi.

$$_{n}C_{k} = \frac{n!}{k!(n-k)!}$$

Kar se dogaja je da gledamo vse razporeditve $n$ elementov na $k$ mestih nato pa še delimo z $k!$ se hočemo znebiti vseh permutacij teh elementov na $k$ mestih oz. vse permutacije istih elementov združimo v eno skupino.

Za kombinacije uporabljamo tudi binomski simbol.

$$\binom{\,n\,}{\,k\,}$$

Binomski simbol se pojavi tudi pri $n$-ti potenci dvočlenika kjer velja

$$(x+y)^{n} = \sum_{k = 0}^{n}\binom{\,n\,}{\,k\,}x^{n-k}y^{k}$$

Če pogledamo primer

$$(x+y)^{3} = (x+y)(x+y)(x+y)$$
$$x^{3}+3x^{2}y + 3xy^{2}+y^{3}$$

je prva stvar ki jo opazimo da so vsi členi neka kombinacija $x$ in $y$. Nato pa je edina naslednja stvar še da opazimo da lahko do nekaterih kombinacij pridemo na več načinov kot do drugih saj vrstni red ni pomemben. Efektivno delamo računamo kombinacije obeh členov, kjer lahko do nekaterih členov pridemo na več načinov kot do drugih. Iz tega dobimo tudi Pascalov trikotnik.





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

Za kombinatoriko pa so pomembne naslednje oznake

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

Pri kombinatoričnih problemih poznamo načelo vsote in produkta ki opisujeta koliko načinov imamo izberemo nek element iz množic oz. koliko načinov imamo da tvorimo zaporedje izbir iz nekih množic.

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
> $k \binom{n}{k}$ je lahko predsatvljen na naslednji način $\qquad \qquad\quad \{1,2\}, \{2,3\}, \{1,3\}$
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