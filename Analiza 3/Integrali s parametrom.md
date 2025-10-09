# Integrali s parametrom

> Namesto funckijske vrste vepljemo vsoto čez realna števila neke funkcije preko parametra $r$:
> $$\int_{a}^{b}f(x,t)dt$$
> Velja da lahko zgornjo funkcijo zapišemo kot
> $$G(a,b,x) = \int_{a}^{b}f(x,t)dt$$

>[!|hide]- Podrobno
> Če imamo funkcijsko zaporedje $f_{n}$ si ga lahko predstavljamo kot funkcijo $g(x,n)$, kjer je za vsak $n \in \mathbb{N}$ neka druga funkcija - torej funkcijsko zaporedje. 
> 
> Predstava: https://www.math3d.org/kMoS6mej9a
> 
> Sedaj naredimo iz tega funkcijsko vrsto ampak hočemo seštevati ne samo čez naravna števila - torej kako se spremnija za vsak $n \in \mathbb{N}$ ampak za vsa realna števila $n \in \mathbb{R}$.
> 
> Z operatorjem vsote to ne gre več ampak poznamo operator za seštevanje funkcijskih vrednosti od ene meje do druge kar je integral.
> 
> Pomembno je da vemo da kot pri funkcijskih vrstah predpotavljamo da je $x$ pritrjen oz. deluje kot konstanta - mi ne gledamo kako se spremnija vrednost funkcijse po $x$ ampaka kako se funkcija spreminja glede na $n \in \mathbb{R}$.
> 
> Da bo jasneje pišimo $t := n \in \mathbb{R}$
> 
> Če hočemo sedaj sešteti vse funkcije glede na $t$ kot neko vsoto $f_{t}$ vpeljemo funkcijo $g(x,t) = f_{t}(x)$, kjer lahko uporabimo integral kot operator vsote in dobimo
> 
> $$\int_{a}^{b}g(x,t)dt$$
> 
> kjer je ključno da vemo da integriramo po $t$, meje za seštevanje pa so podane z $a,b$. $x$ pa se kot pri vrstah obravnava kot konstanta oz. kot da je pritrjen.
> 
> Tehnično gledano lahko za to vpeljemo še funkcijo
> 
> $$G(a,b,t) = \int_{a}^{b}g(x,t)dt$$
> 
> ker lahko spreminjamo meji integrala.
***
Množica  $A \in \mathbb{R}^n$ je **lokalno zaprta** če velja da za vsako točko v množici velja da obstaja zaprt interval okoli nje ki je popolnoma vsebovan v $\mathbb{R}$.

> Če je monžica odprta ali zaprta je lokalno zaprta.
> Če je neka množica presek odprte in zaprte je lokalno zaprta

Racionalna števila $\mathbb{Q}$ so primer ne lokalno zaprte množice.

***

>**Izrek o zveznosti integrala s parametrom**
>1. Naj bo **$I = [a,b]$** in **$X \subset \mathbb{R}^n$ lokalno zaprta množica**. 
>2. Naj bo **$f: I \times X \to \mathbb{R}$ zvezna funkcija**. 
>
>Potem je funkcija $G: X \times I \times I \to \mathbb{R}$, definirana s formulo
$$G(x,u,w) = \int_u^w f(t,x)dt$$
zvezna.
>*Kjer je $x$ lahko spremenljivka v $\mathbb{R}^n$*
>>[!|dokaz]- Dokaz:
> > Naj bo $(x_0, u_0, w_0) \in X \times I \times I$ poljubna točka in naj bo $\varepsilon>0$.
> >
> > Ker je $X$ lokalno zaprta, obstaja kompaktna okolica $K \subset X$ točke $x_0$. Ker je tudi interval $I$ kompakten, je produkt $I \times K$ kompaktna množica. Zvezna funkcija $f$ je na kompaktni množici $I \times K$ **enakomerno zvezna**. Zato obstaja $\delta_1>0$, da za vsak $x \in K$ z $\|x - x_0\| < \delta_1$ velja $|f(t, x) - f(t, x_0)| < \frac{\varepsilon}{2(b-a)}$ za vse $t \in I$.
> >
> > Razliko ocenimo z uporabo trikotniške neenakosti:
> > $$|G(x, u, w) - G(x_0, u_0, w_0)| = \left|\int_{u}^{w} f(t, x) d t - \int_{u_0}^{w_0} f(t, x_0) d t\right|$$
> > $$= \left|\int_{u}^{w} f(t, x) d t - \int_{u}^{w} f(t, x_0) d t + \int_{u}^{w} f(t, x_0) d t - \int_{u_0}^{w_0} f(t, x_0) d t\right|$$
> > $$\leq \left|\int_{u}^{w} (f(t, x) - f(t, x_0)) d t\right| + \left|\int_{u}^{w} f(t, x_0) d t - \int_{u_0}^{w_0} f(t, x_0) d t\right|$$
> > $$ \leq \int_{\min(u,w)}^{\max(u,w)} |f(t, x) - f(t, x_0)| d t + \left|\int_{u_0}^{u} f(t, x_0) d t + \int_{w_0}^{w} f(t, x_0) d t\right|$$
> >
> > Za $x \in K$ z $\|x - x_0\| < \delta_1$ je prvi člen manjši od:
> > $$\int_{\min(u,w)}^{\max(u,w)} \frac{\varepsilon}{2(b-a)} dt = \frac{\varepsilon}{2(b-a)}|w-u| \leq \frac{\varepsilon}{2(b-a)}(b-a) = \frac{\varepsilon}{2}.$$
> >
> > Funkcija $t \mapsto f(t, x_0)$ je zvezna na kompaktnem intervalu $I$, zato je omejena. Obstaja $M>0$, da je $|f(t, x_0)| \leq M$ za vse $t \in I$. Drugi člen lahko zato ocenimo z:
> > $$ \left|\int_{u_0}^{u} f(t, x_0) d t\right| + \left|\int_{w_0}^{w} f(t, x_0) d t\right| \leq M|u-u_0| + M|w-w_0|. $$
> > Izberimo $\delta_2 = \frac{\varepsilon}{4M}$ (če je $M>0$). Za $|u-u_0| < \delta_2$ in $|w-w_0| < \delta_2$ je ta izraz manjši od $M\delta_2 + M\delta_2 = \varepsilon/2$. Če je $M=0$, je izraz enak 0 in pogoj trivialno izpolnjen.
> >
> > Izberimo $\delta = \min(\delta_1, \delta_2)$ (in $\delta$ mora biti dovolj majhen, da je $x \in K$). Potem za vse $(x, u, w)$, ki zadoščajo $\|x-x_0\|<\delta$, $|u-u_0|<\delta$ in $|w-w_0|<\delta$, velja:
> > $$|G(x,u,w) - G(x_0,u_0,w_0)| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon.$$
> > Torej je $G$ zvezna funkcija.

>**Posplošitev**
>Če je $f$ zvezna funkcija spremenljivk $x$ in $t$ posebej, je $G$, dana s predpisom
> 
> $$G(x,u,w) = \int_u^w f(t,x)dt,$$
> 
> tudi zvezna funkcija spremenljivk $(x,u,w)$.


> **Posledica**
> Naj bo $X \subset \mathbb{R}^n$ lokalno zaprta množica in $f : [a, b] \times X \to \mathbb{R}$
> zvezna. 
> 
> Tedaj je $F$, dana s predpisom
> $$
> F(x) = \int_a^b f(t, x) dt,
> $$
> zvezna funkcija na $X$.

***

> **Izrek o odvajanju integrala s parametrom** 
> 
> Naj bo **$J \subset \mathbb{R}$ odprt interval** in $f : [a, b] \times J \to \mathbb{R}$ **zvezna funkcija**. 
> 
> Naj za vsak $(t, x) \in [a, b] \times J$ obstaja $\frac{\partial f}{\partial x}(t, x)$ in naj bo **$\frac{\partial f}{\partial x}(t,x)$ zvezna funkcija** na $[a, b] \times J$. Tedaj velja
> ***
>**1\.** Funkcija $F$, dana s predpisom
> $$
> F(x) = \int_a^b f(t, x) dt,
> $$
> je zvezno odvedljiva na $J$ in velja
> $$
> F'(x) = \int_a^b \frac{\partial f}{\partial x}(t, x) dt,
> $$
> za $x \in J$.
> ***
> **2\.** Za poljubni **zvezno odvedljivi** funkciji $\alpha, \beta : J \to [a, b]$ je funkcija $G$
> $$
> G(x) = \int_{\alpha(x)}^{\beta(x)} f(t, x) dt,
> $$
> zvezno odvedljiva na $J$ in velja
> $$
> G'(x) = f(\beta(x), x) \beta'(x) - f(\alpha(x), x) \alpha'(x) + \int_{\alpha(x)}^{\beta(x)} \frac{\partial f}{\partial x}(t, x) dt.
> $$

