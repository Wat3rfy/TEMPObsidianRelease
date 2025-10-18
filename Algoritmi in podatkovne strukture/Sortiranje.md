
Random sort
premutation sort
selection sort
insertion sort
bubble sort

merimo čas izvajanja
št operacij

kje mermimo 

najboljši, nasjabši povprečni primer
velikost pod./primerov

Računska zahtevnost ( kompleksnost)
- časovna (koliko operacij izvajamo)
- prostorska (koliko pomnilnika)

asimptotična računska zahtevnost

zogrnja meja - simptotočna časovna zahtevnost - notacija $O(n), O(n^2)$ $n \rightarrow \infty$

$$f(n) = O(n^{2}) \Rightarrow \exists C \ni: \lim_{n \to \infty} f(n) < Cn^{2}$$

$$\lim_{n \to \infty}\frac{f(n)}{g(n)} < \infty$$


$$f(n) = \frac{1}{2}(n-1)(n+2)\log{n} + \sqrt[]{n}$$

v katerem $O(n)$ je

glavne:
- $O(1)$
- $O(\log n)$
- $O(n)$
- $O(n \log n)$
- $O(n^{2})$
- $O(n^c)$ - polinomska
- $O(k^{n})$
- $O(\sqrt[]{n})$


Če imamo funkcije z več spremenljivkami lahko dobimo
$n^{2}\log m$

Primeri

$100 + 2n + 3n^{2} =(n^{2})$
$3n \cos\,\! 2\pi n + \frac{n}{\log n} + 2n = O(n)$
$1+n \log n + n^{1.5} = O(n^{1.5})$
$f(n) = n+f\left(\frac{n}{2}\right)= O(n)$


**Napredno urejanje**

Merge sort
quick sort
heap sort


**Urejanje brez primerjav**

s frekvenčno tabelo - v neko tabelo če se pojavi število incrememntamo na tistem indeksu za 1.

Bucket / bin sort

Radix sort