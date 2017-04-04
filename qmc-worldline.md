---
layout: math_page
title: Quantum MC - World Line
permalink: /qmc-worldline/
menu: false
---

La funzione di partizione canonica della MQ, analogamente al caso classico, è definita come somma di pesi di Boltzmann:

$$
Z(\beta) = Tr[e^{-\beta H}]
$$

La traccia di un operatore è una quantità invariante sotto trasformazioni unitarie: non è pertanto necessario specificare una particolare base rispetto cui calcolarla.

Risulta naturale allora la forma per la matrice densità $$\rho$$ (in generale e decomposta sugli autostati dell'hamiltoniana):

$$
\rho = \dfrac{e^{-\beta H}}{Z(\beta)} = \dfrac{\sum_{n} |n\rangle\langle n|e^{-\beta E_n}}{\sum_{n} e^{-\beta E_n}} ,
$$

mentre per il valore di aspettazione di un'osservabile $$\mathcal{A}$$:

$$
\langle \mathcal{A}\rangle = Tr[\mathcal{A}\rho].
$$

Un generico problema si riduce allora al calcolo di tracce e dunque elementi di matrici su una generica base di stati. 
Supponiamo di poter scomporre l'hamiltoniana in due termini (non commutanti tra loro) $$H = H_0 + V$$. Il termine $$H_0$$ rappresenta l'evoluzione libera del sistema, mentre $$V$$ è un generico termine di interazione. 
Usiamo l'approssimazione di Suzuki-Trotter:

$$
e^{-\epsilon(H_0+V)} = e^{-\epsilon H_0}e^{-\epsilon V} + o(\epsilon^2)
$$

$$
\lim_{N\rightarrow\infty} \left(e^{-\frac{\beta}{N} H_0}e^{-\frac{\beta}{N} V}\right)^N = e^{-\beta(H_0+V)}
$$


Equivalenza propagatore std e path integral

$$
\displaystyle U(x,t;x_0) = \langle x |e^{-iHt}|x_0\rangle = \sum_{\text{all paths}} e^{iS[x(t)]}
$$

Dall'evoluzione temporale alle fluttuazioni termiche:

$$ t \rightarrow i\beta = i\tau $$

$$ U(x,\beta;x_0) = \langle x |e^{-\beta H}|x_0\rangle = \sum_{n} \langle x |n \rangle \langle n | x_0 \rangle e^{-\beta E_n} $$

da cui

$$
Z(\beta) = \int U(x,\beta;x)dx
$$

## Worldline

Fluttuazioni termiche di un insieme canonico ~ evoluzione tempo immaginario
Un problema con spazio di hilbert D-dimensionale viene rappresentato come traiettorie in spazio D+1 dimensionale. La dimensione aggiuntiva rappresenta l'evoluzione temporale, ossia la fluttuazione termica. 

### Oscillatore Armonico 1D

$$
H = \dfrac{p^2}{2m}+\dfrac{1}{2}\omega^2 x^2
$$
