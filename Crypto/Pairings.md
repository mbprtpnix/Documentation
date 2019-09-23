vim: ft=markdownlight fdm=expr

Préliminaires
=============

Embedding degree
----------------

* Valuation of q^d-1

q^d-1=(q-1)(1+q+...+q^{d-1}). So
1) v_l(q^d-1)>=v_l(q-1)

Now 1+q+...+q^{d-1}=q-1+q^2-1+...+q^{d-1}-1+d
so an easy induction shows that if v_l(q-1)>0, then
2) v_l(q^d-1)=v_l(q-1) if l does not divides d.

If d=l and v_l(q-1)>1, by the nonarchimedean property, we have
3) v_l(q^l-1)=v_l(q-1)+1
By reasoning modulo l^2, we have that this is also true if v_l(q-1)=1 and l>2
(or also if v_l(q-1)=1 and l=2 with q=1 mod 4, since v_2(q^2-1)=v_2(q-1)+v_2(q+1))

Résumé: si e=v_l(q-1)>0, alors
-v_l(q^d-1)=e si d n'est pas divisible par l
-v_l(q^l-1)>=e+1
 il y a égalité si e>=2 ou si l>=3 ou si q=1 mod 4

Suite de Kummer
---------------
(k=Fq)

Rappel: #\mu_l(k)=#k*/k*^l
De plus k*/k*^l = H^1(G,\mu_l)=\mu_l(kbar)/(\pi-1)
via l'identification x -> \sigma y/y (où y^l=x) -> \pi y/y=y^{q-1}=x^{(q-1)/l}

On en déduit que \mu_{d_1d_2}/(\pi-1) ->> \mu_{d_1}/(\pi-1)
                                    x -> x^{d_2}
correspond au morphisme naturel k*/k*^{d_1d_2} ->> k*/k*^{d_1}
et l'injection naturelle \mu_{d_1}/(\pi-1) --> \mu{d_1d_2}/(\pi-1)
correspond à k*/k*^{d_1} ->> k*/k*^{d_1d_2}
                      x  ->  x^{d_2}

Annulation de certains groupes d'homologie
------------------------------------------

H^n(G,k)=0
H^1(G,k*)=0 (Hilbert 90)
H^3(G,k*)=0 quand k est p-adique (Tate)
  (cf Milne, J.S.: Arithmetic Duality Theorems. Perspectives in Mathematics)

Hom(A,Gm)=0
H^1(G,A)=0 pour A va sur un corps fini (Lang, Abelian varieties over finite fields.)

Corollaire (cf plus bas), si k corps fini: 
si 0->K->A->B->0, on a H^1(k,K)=B(k)/f(A(k))
or H^1(k,K)=K/(\pi-1) et est de cardinal égal à K(k).

Tate Pairing
============

Frey-Ruck version of the Tate pairing
-------------------------------------
(n does not divides the characteristic)

1)
The Kummer exact sequence 1->\mu_n-> \kbar^* -[n]> \kbar^* -> 1 give the
sequence of G=Gal(\kbar/k) modules cohomology:
H^0(G,\mu_n)-> k^* -> k^* -> H^1(G,\mu_n) -> H^1(G,\kbar^*)

But H^1(G,\kbar^*)=0 (Hilbert 90), so we get the exact sequence
k^* -[n]> k^* -> H^1(G,\mu_n) -> 0
The isomorphism H^1(G,\mu_n) = k^*/k^{*,n} is given by
y -> (\sigma -> \sigma(x)/x) where x \in \kbar^* is such that y=x^n

Remark: if \mu_n \subset k^*, then H^0(G,\mu_n) = \mu_n,
H^1(G,\mu_n)=Hom(G,\mu_n), so if the n-part quotient of G is cyclic (think
k=finite field), we have H^1(G,\mu_n) = \mu_n
Over k=F_q, unraveling the isomorphism $k^*/k^{*,n}=\mu_n$ is simply $x ->
x^{(q-1)/n}$

Continuing the exact sequence we have
0=H^1(G,k*) -> H^2(G,\mu_n) -> H^2(G,\kbar*) -[n]> H^2(G,\kbar*) -> ...
so H^2(G,\mu_n)=H^2(G,\kbar*)[n]=Br(k)[n]

2)
The Kummer exact sequence 0 -> A[n]-> A(\kbar) -[n]> A(\kbar) -> 0 give
H^0(G,A[n])-> A(k) -> A(k) -> H^1(G,A[n])) -> H^1(G,A(\kbar)) -[n]> H^1(G,A(\kbar))
In other words
0 -> A(k)/nA(k) -\delta> H^1(G,A[n]) -\alpha> H^1(G,A(\kbar))[n] -> 0
The connection morphims $\delta$ is such that
$\delta(P)=(\sigma -> \sigma(Q)-Q$ where $Q \in A(\kbar), nQ=P$
(\alpha comes from the inclusion A[n] -> A(\kbar))

The Weil pairing gives a cup product
H^1(G,A[n])xH^1(G,A[n])->H^2(G,\mu_n)=H^2(G,\kbar^*)[n]
c_1, c_2 -> (\sigma_1,\sigma_2) -> e_{W,n}(c_1(\sigma_1), c_2(\sigma_2))

Composing this cup product with alpha and delta, we have the Tate pairing
A(k)/nA(k) x H^1(G,A(\kbar))[n] -> H^2(G,\kbar^*)[n]
e_T(P,Q) = cup product(\delta(P),\alpha^-1(Q))

Th: If K is a local field, the Tate pairing is non degenerate.

We have H^1(G,A(\kbar))[n] = Hom(G(K_tame/K_unramified),A[n])^G
where K_tame/K_unramified is the unique tame extension of degree n, the
Galois group G is generated by a lift of the Frobenius.
Summing up, H^1(G,A(\kbar))[n]  = A[n]_0 = {P \in A[n], \pi_q(P)=[q]P}

Now if A/\Fq is an abelian variety, we can descend the results from a lift
of A/\Qq, by Hensel A(k)/nA(k) = A(\Fq)/nA(\Fq), ...

Over \Fq, we get that the Tate pairing is non degenerate
A(\Fq)/nA(\Fq)xA[n]_0 -> Br(K)[n] (K=Q_q)
The Brauer group Br(K)=\Q/\Z, and Br(K)[n]=\Z/n\Z

Explicitely, if \Fqd=\F_{q^d}=\F_q(\mu_n) ie n \mid (q^d-1),
K_n is the cyclic ramified extension of degree n of K(\mu_n), then
Br(K)[n]=H^2(G(K_n/K),K_n^*)[n] = \Fqd^*/\Fqd^{*,n} (up to a choice of a generator of G(K_n/K))

We then get the non degenerate (on the left) pairing
A(\Fq)/nA(\Fq) x A[n]_0 -> \Fqd^*/\Fqd^{*,n} = \mu_n (via the isomorphism from 1)
(It is easy to see that A[n]_0 live in \Fqd).

In particular
A(\Fqd)/nA(\Fqd) x A[n](\Fqd) -> \Fqd^*/\Fqd^{*,n} = \mu_n is non degenerate.

Remark: since the isomorphism from Br(k)[n] and \mu_n, H^1(G,A(\kbar)) and
A[n]_0 comes from a choice of a generator of the cyclic Galois tame
extension, we can describe the Tate pairing as
A(k)/nA(k) x A[n]_0 -> H_1(G',\mu_n)
   P, Q -> (\sigma -> e_W,n(\sigma(P')-P',Q) where P=nP'
the pairing is in value H_1(G',\mu_n) where G' is the galois group of \Fqd
because Q lives in \Fqd, so we get a cocycle only in G'.
Now since H_1(G',\mu_n)=\Fqd^*/\Fqd^{*,n} by the Kummer sequence, and
A[n]_0 \subset A[n](\Fqd), we get that the Tate pairing is a non degenerate
pairing on the left:
A(\Fq)/nA(\Fq) x A[n](\Fqd) -> \mu_n = \Fqd^*/\Fqd^{*,n}
      P, Q -> e_W,n(\pi(P')-P',Q) where P=nP' and \pi is the Frobenius of \Fqd

3) The Lichtenbaum pairing

We have the sequence of G-module
1->Princ_Cbar -> Div^0_Cbar -> Pic^0_Cbar -> 0
hence the connection \delta: H^1(G, Pic^0_Cbar) -> H^2(G, Princ_Cbar)

Lichtenbaum pairing:
Pic^0_C x H^1(G, Pic^0_Cbar)-> H^2(G,\kbar*)
     E, \gamma ->  (\sigma_i -> (\delta(\gamma)(\sigma_i)(E)))
The pairing induces another pairing:
Pic^0_C/n Pic^0_C x H^1(G, Pic^0_Cbar)[n] which is \pm 1 the Tate pairing

Explicit computation: if c \in Jac(C)[n]_0, c corresponds to the cocycle
H^1(G, \Pic^0_Cbar) via \sigma(\tau^i)=[i] c, where \tau is the generator of the cyclic extension of degree n K_tame/K_unramified.

The image by \delta is then
\tau^i, \tau^j -> \tau^i j D - (i+j mod n) D + j D
(where D corresponds to c, is chosen rational over K_unramified)
In particular, nD corresponds to a function f_D since c is of order n.

If c_1 \in Pic^0_C, the Lichtenbaum pairing give
(c_1+n \Pic^0_C, c)(\tau^i, \tau^j) = 1 (i+j <n)
                                    = f_D(E) (i+j>=n)
      (where E is the divisor prime to D corresponding to c_1)
So the corresponding element of the Brauer group is the cyclic algebra splits by K_tame corresponding to the class <\tau, f_D(E)>, it is uniquely determined by the norm class f_D(E) N_Ktame/Kunramified(K_tame*)
But this norm class is isomorphic to \Fqd^*/\Fqd^{*,n}

Thus the Lichtenbaum pairing is the class of f_D(E) \Fqd^{*,n}

### Summary

* Original version of the Tate pairing

- k p-adic field, A ppav/k, G Galois group, \mu=\union \mu_n
- H^1(G,A):=H^1(G,A(kbar))=lim_{K/k Galois} H^1(\Gal(K/k),A(K))
- Br(k)=H^2(G,\kbar*)=_{inv} Q/Z =_{t \to e^{2\pi i t} \mu
e: H^1(G,A) x A(k) -> \mu
Non degen: H^1(G,A) -> Hom(A(k),\mu) is bij.

* Frey-Ruck version
(reduction mod p)

-k=\Fq, n \mid q-1
e: H^1(G,A)xA(k) -> \mu
e_T:A(k)/nA(k) x A[n](k) -> \mu_n

Ate pairing
===========
(cf hyperelliptic ate pairing)

Couplage de Tate:
  A[r]xA/rA -> \mu_r
Ou encore (dans les cas A(k) n'a pas de points de r^2-torsion)
  G_1xG_2 -> \mu_r
e_T,r(D_1,D_2)=f_{r,D_1}(D_2)^{(q^d-1)/r}

Si k contient aussi \mu_N, avec r | N
e_T,N(D_1,D_2)=f_{N,D_1}(D_2)^{(q^d-1)/N}
car f_{N,D_1}=f_r{D_1}^{N/r} (en fait ça marche pour des isogénies plus générales, cf PairingsIsogenies)

[Plus généralement on a le lemme (en regardant le diviseur)
f_{ab,D_1}=f_{a,D_1}^b f_{b, aD_1}
et on applique avec N=ab, a=r]

Th (Ate: #E(k)=q+1-t, T=t-1 (=q mod r))
a: G_2xG_1 -> \mu_r
a(Q,P)=f_{T,Q}(P) (non réduit)
Si N=gcd(T^d-1,q^d-1), T^d-1=LN, alors
e_T(Q,P)^L=a(Q,P)^{c(q^d-1)/N}
où c = \sum_{i=0}^{d-1} T^{d−1−i} q^i ≡ dq^{d−1} mod r
et donc le couplage est non dégénéré si r \not\mid L.

Note: dans le cas d'une courbe hyperelliptique, on a r ~ q^g, donc on prend T=q, et on a
e_T(Q,P)=a(Q,P)^{dq^{d-1}}
De plus f_{T,Q}(P) est déjà réduit (ie dans \mu_r)
Pr: hyperelliptic_ate, Lemma 2.

(D_1, et D_2 dans A[r] pour l'instant, diviseurs réduits)
Lemme: e_T(D_2,D_1)=f_{q^d,D_2}(D_1)
Pr: e_T(D_2,D_1)=f_{r,D_2}(D_1)^{(q^d-1)/r}
                =f_{q^d-1,D_2}(D_1)
                =f_{q^d,D_2}(D_1)
car div(f_{q^k-1,D_2})=(q^k-1)D_2-[q^k-1](D_2)=(q^k-1)D_2
et div(f_{q^k,D_2})=(q^k)D_2-[q^k](D_2)=(q^k-1)D_2
(et plus généralement si r|N, f_{N,D_2}=f_{N+1,D_2})

Lemme: f_{q^d,D_2}=\prod_{i=0}^{k-1} f_{q,q^i D_2)^{q^{k-i-1}}

Lemme: si \psi est purement inséparable sur la courbe C (qui fixe le point à l'infini), alors
f_{n,\psi(D_2)} o \psi=f_{n,D_2}^{\deg \psi}

Pr du Th:
si D_2 \in G_2 et D_1 \in G_1, on prend \psi=\pi et on a
f_{q,q^i D_2)(D_1)=f_{q,\psi^i D_2)(\psi D_1)=f_{q,D_2}(D_1)^{q^i}

Si on déroule tout:
e_T(Q,P)=f_q^d,Q(P)=f_q,Q(P)^{dq^(d-1)}
Plus généralement, si on pose T=q mod r, m=(T^d-1)/r, on a
e_T(Q,P)^m=f_(T^d-1),Q(P)^((q^k-1)/r)=f_T^d,Q(P)^((q^k-1)/r)
          =f_T,Q(P)^(c (q^k-1)/r) où c=\sum \lambda^(k-1-i)q^i
  car f_T^d,Q=f_T,Q^{T^{d-1}} f_T,qQ^{T^{d-1}} ... f_T,q^{d-1}Q
On obtient l'égalité plus haut avec lambda=q.
On peut remplacer r par N (dans le théorème) pour obtenir le théorème
(qui montre que le couplage est non dégénéré dans un cas plus général).

Résumé: on remplace la multiplication P->rP par P->crP avec
cr=q^k-1 (donc on a un multiple du couplage), on remarque que comme P est d'ordre r calculer (cr+1)P nous donne la même fonction de Miller,
or (cr+1)P=q^dP et comme P est dans G_2 et Q dans G_1 il suffit essentielement de
calculer f_q(P) puis d'utiliser le Frobenius. Pour une courbe elliptique
avec les courbes pairing friendly on a 1-t+q=0 mod r, donc q=t-1:=T.

Optimal Ate: même idée, on remplace rP par un multiple crP avec
cr=\sum c_i q^i (c_i petit). Une puissance du couplage de Tate vient de la
fonction de Miller f_{cr,P} que l'on peut calculer via les f_{c_i q^i,P} et
les fonctions de Miller fbis_{\sum c_j q^j, c_i q^i, P}. Comme P est dans
G_2 et Q dans G_1, pour calculer f_{c_i q^i,P}(Q) il suffit de calculer
f_{c_i}(Q).

Ate sur courbe superspéciale
----------------------------
Le verschiebung V est alors aussi inséparable (on a besoin d'une Jacobienne
superspéciale plutôt que supersingulière pour que le Verschiebung soit
définir sur la courbe).
On obtient a': G_1xG_2 -> \mu_r
a(P,Q)=f_{P,Q}(P)^e (e=gcd(d,q^d-1))
e_T(Q,P)^L=a(Q,P)^{dq^{d-1}/e}

Twisted Ate
-----------
(cf eta pairing revisited)

E_1, E_2 twists de degrés d, isomorphes à E sur \Fq^d
Si \phi_d: E_1->E_2 iso sur \Fq^d
alors \phi_d^\sigma \phi_d^{-1} est un automorphisme \gamma d'ordre d (où
\sigma est le Frobenius)
le Frobenius sur E_1 est twisté par \gamma par rapport à celui sur E_2
On a E(\Fq^d)=\somme_{i=0}^{d-1} E_i(\Fq) où E_i parcourt les twists de E
lorsque E(Fq) != 0 mod p_i pour tout diviseur premier p_i de d

Pr: \pi^d-1= \pm \prod \gamma^i \pi -1, et avec la condition les noyaux sont deux à deux d'intersections disjointes.

Application: soit m=pgcd(k,d) (k embedding degree), e=k/m, alors il existe
un twist E' de degré m tel que G_2 soit isomorphe à E'(Fq)
De plus on en déduit que \gamma agit par q^e sur G_1 et q^{-e} sur G_2 (car \gamma \pi^e est rationel sur G_2, et \gamma est d'ordre 1)
On obtient le twisted ate pairing en raisonnant avec \gamma \pi^e comme
pour ate (ici \gamma \pi^e agit comme q^e sur G_1 et comme 1 sur G_2):
G_1 x G_2 -> \mu
a'(P,Q)=f_{T^e,P}(Q)

Si on a un twist, on peut réduire les calculs de plusieurs manière:
- faire du Tate ou du Ate, mais quand on doit calculer sur G_2, le faire sur la twist (donc sur une extension plus petite) avant de revenir sur la courbe
- faire du twisted ate pour avoir du G_1xG_2 mais avec une boucle plus petite (mais pas autant que ate)
- faire du ate/tate sur la twist (cf le papier de DJB, Tanja, Costello quand la twist est en Edwards)

Pairings and Isogenies: Couplage de Weil-Cartier
================================================

(Silverman)

La variété abélienne duale peut être vue comme Ext^1(A,G_m).
Si f:A->B est une isogénie, de la suite exacte
0->K->A->B->0 on en déduit la suite de Cohomologie
0 -> Khat -> Bhat -> Ahat -> 0
où Khat=Hom(K,Gm) est le dual de Cartier de K.
(on utilise le fait que Hom(A,Gm)=0 et Ext^1(K,Gm)=0)
ie on voit directement le noyau de l'isogénie duale comme le dual de K.
On en déduit le couplage de Weil-Cartier:
e_W: K x Khat -> \mu_l

L'iso Ahat -> Ext^1(A,G_m) est donné par
[D] -> ( (P,Q)->f_{D,P}(Q)/f_{D,P}(0) ) où div f_{D,P}=t_P*D - D;
ce qui redonne la formule pour le calcul de Weil (la version g).

De plus Ext^1(A, G_m) =~ {extensions centrales de A par G_m}; via cet
isomorphisme, on retrouve l'iso avec Ahat via L \in Pic^0(A) -> G(L) le
groupe thêta.

Plus concrètement, si f: A-> B est une isogénie, Q \in Khat, alors f^* Q
est un diviseur D_Q sur A, linéairement équivalent à 0 (car Q in Khat).
On note g une fonction représentant D_Q, alors g(x+P) est une autre
section, et comme D_Q est dans Pic^0 il a une seule section (à une
constante près), donc e_f(P,Q)=g(x+P)/g(x).

Si on applique ça à une polarisation \Phi_L: A->A^, alors \Phi_L est
autoduale, et si D_Q est le diviseur t_Q* \Theta - \Theta.

Avec la réciprocité de Weil/Lang, on a la formule alternative:
- si Z_P est un cycle équivalent à (P)-(0)
- si Z_Q est un cycle équivalent à (Q)-(0)
- si Z=\sum P_i est un cycle, on note f_Z une section du diviseur \sum
  t_P_i* \Theta; ce diviseur est principal quand deg Z=0 et \sum P_i \in K(L)
Alors e_L(P,Q)= f_{l Z_P}(Z_Q)/f_{l Z_Q)(Z_P).

Tate-Cartier
============

On a la flêche \delta: B(k)/f(A(k)) -> H^1(G, K)
qui composé avec le couplage de Weil-Cartier donne une application
e_T: B(k)/f(A(k)) x K(k) -> H^1(G,\mu_l) \iso k*/k*^l
Si k contient les racines l-ièmes de l'unité, cette
application est non dégénérée (autrement k*/k*^l est trivial si l est premier.)

Si l est quelconque, dans le cas d'un corps fini on peut supposer G
cyclique (cf TateCohomology), et H^1(G,\mu_l)=\mu_l/(Fr-Id) où
l'application k*/k*^l -> H^1(G,\mu_l) = \mu_l/(Fr-Id) est donnée par x/
y^l=x -> (\sigma -> \sigma(y)/y) -> \pi(y)/y=x^{(p-1)/l} (si k contient les
racines de l'unité alors l divise p-1 et Fr-Id=0, on retombe dans la
situation classique).

Via cette identification, on peut dérouler:
H^1(G,K)=K/(\pi -1),
si P \in B / f(P0)=P, \delta(P)=\pi P0 - P0 \in K/(\pi-1)
et e_T(P,Q)=e_W(\pi P0 - P0,Q) \in \mu_l/(Fr-Id)=H^1(G,\mu_l)=F_q*/F_q*^l.

(on retrouve la formule de Tate en partant de g pour Weil [cf le book
pairing], on peut aussi partir de f_P/f_Q pour Weil, mais bizarrement c'est
un tout petit plus dur à retrouver la formule f_P pour Tate comme ça [cf Bruin Tate Pairing])

Lien entre Tate et Weil
-----------------------

Si on prend Weil-Cartier pour \pi-1 (d l'embedding degree), on tombe pour
Weil-Cartier sur le couplage
A(k)xA_0 -> \mu
où A_0=Ker \pidual-1, or (\pi-1)(\pidual-1)=1-\pi-\pidual + [q]
donc si x \in A_0, (\pidual-1)(x)=0, donc \pi(x)=[q]x, ie A_0=G_2

Si on regarde Tate-Cartier, on a
A(k)xA_0 -> \mu
e_T(P,Q)=e_W(P, \pi Q_0-Q_0) où (\pi-1)Q_0=Q, donc e_T(P,Q)=e_W(P,Q)

Structure dans le cas d'une courbe elliptique
---------------------------------------------

E(k)=<P1,P2>, P1 d'ordre n_1 et P2 d'ordre n_2 (avec n_1 | n_2, n_1|q-1)
on suppose n_2=r^k l avec n_1 |l, ie r ne divise pas n_1
(E de trace 2)
- \exist P,Q / e(P,Q) est une racine primitive n_2-ième
- l'ordre de e(P_2,P_2) divise r^k
- Soit P d'ordre r et Q d'ordre r^a, alors
  e(P,Q) est primitif d'ordre r ssi a=k
Pr: The Generalized Weil Pairing, Section 4.1

Non dégénérescence de Tate-Cartier
----------------------------------
k corps fini

Si on a un couplage AxB -> C, être non dégénéré signifie que
A --> Hom(B,C) et B --> Hom(A,C)
dans ce cas #A<=#Hom(B,C)<=#B et donc #A=#B=#Hom(A,C)=#Hom(B,C),
les injections sont des bijections et lcm(#A)|#C
(réciproquement si lcm(#A) et lcm(#B) | #C, et qu'on a des surjections
A ->> Hom(B,C) et B ->> Hom(A,C), alors on a des bijections et le couplage
est non dégénéré)

On ne suppose pas que k contienne \mu_l, où l est le degré de l'isogénie
(pas forcément entier).
Le même raisonnement que dans Schaefer montre que dans H^1(G,K) on peut se
ramener au groupe de Galois d'une extension cyclique (l'extension cyclique
de degré l au-dessus du corps de définition des points de K). De plus cette
extension est telle que \hat{H}^0(M)=Invariants sur invariants évidents =
Invariants car dans la trace on va avoir la multiplication par l.

### Version de Schaefer

0->K(k)->A(k)->B(k)->B(k)/A(k)->0 d'où
1) On a #K(k) = #B(k)/A(k)
2) B(k)/A(k) s'envoit dans H^1(G,K)=K(kbar)/Fr-Id
(Rem: H^1(G,A)=0 donc on a même une bijection B(k)/A(k) = H^1(G,K))
3) Via Weil, on a un morphisme K(k) -> \mu_l^(rank K) dont l'image est
   isomorphe au dual T de K(k), donc de même cardinal (sur une extension).
   Concrêtement si K(k) est de type d_1,...d_r, on a T=\somme \mu_{d_i}
   Autrement dit on considère l'iso:
   0-> W -> K -> T -> 0 (où la flêche K->T est l'évaluation d'un point de K
   en le couplage de Weil avec la base duale de K(kbar)).
   On en déduit la suite:
   0->W(k)->K(k)->T(k)->H^1(k,W)->H^1(k,K)->H^1(k,T)
   qui sont de cardinaux respectivement 0,a,b,c,a,b,c
   (parce que #Hhat^1=#Hhat^0).
   On en déduit que H^1(k,K)->H^1(k,T) est surjectif.
   Or H^1(k,T)=\somme k*/k*^d_i (chacun étant de cardinal \mu_{d_i}(k))
On en déduit qu'on a bien une surjection de B(k)/A(k) -> Hom(K(k),\mu_l)

### Version de Bruin

(Tate pairing for abelian varieties over finite fields); k=F_q
G agit continument sur M, muni de la topologie discrète
H^1(G,M)=M/(\pi-1)M (via l'image du Frobenius qui correspond à l'élément 1
\in G=\hat{Z})
 #H^1=#Hhat^0=M(k)

Lemme: Si F est annihilé par q-1 alors
Fdual(k) x H^1(G,F) -> G_m(k) est un couplage parfait
(a, c) -> a(c(\pi))

Pr: Fdual(k) = Hom(F,kbar*)^G
             = Hom(F, k*)^G
             = Hom(F/(\pi − 1)F, k*).
Donc Fdual(k)=Hom(H^1(G,F), k*)

Cas général: si F annihilé par l, on a
Fdual(k) x H^1(G,F) -> H^1(G, \mu_l)
via l'identification
Hom(F,Gm)^G x F/(\pi-1)F -> \mu_l/(\pi-1): (f,[x]) -> [f(x)]
qui est bien défini car si f est rationnelle, f(\pi m-m)=\pi f(m) -f(m)
On retrouve si l=\pi-1: \mu_l/(\pi-1)=\mu_{q-1}=k*

En particulier, si f: A->B, \coker f(k) =~ H^1(k, \Ker f)
Donc si ker f est annihilé par q-1, on a un couplage
coker f(k)=B(k)/f(A(k)) x (ker f^)(k) -> k*

### Version de Lenstra

(cf l'article de Bruin, Remark p. 2) 
Weil induit un couplage parfait Ker f x Ker f^ -> G_m
d'où, comme q-1 annule Ker f et Ker f^ et que Gal(kbar/k) agit trivialement
sur k*, un couplage parfait Ker f[\pi -1] x ker f^/(\pi-1) -> G_m.
Or par Tate, ker f^/(\pi-1)=H^1(k, \ker f^)=coker f^(k) [*], donc on a un
couplage: (Ker f)(k) x (coker f^)(k)->k*

On peut retrouver [*] directement (on note σ=π et φ=f):
σ−1: Bˆ[φˆ◦(σ−1)]/(Bˆ[φˆ]+Bˆ[σ−1]) −∼→ Bˆ[φˆ]/(σ−1)Bˆ[φˆ]=(ker φˆ)/(σ−1) ker φˆ
and φˆ: Bˆ[φˆ◦(σ − 1)]/(Bˆ[φˆ]+ Bˆ[σ−1]) −∼→
Aˆ[σ−1]/φˆ(Bˆ[σ−1])=Aˆ(k)/φˆ(Bˆ(k)).

Si Ker f n'est pas annulé par q-1, on retrouve comme plus haut le couplage
(Ker f)(k) x (coker f^)(k)=ker f^/(p-1) ->\mu/(\pi-1)

Réduction de Tate à G_1 x G_2
-----------------------------

soit d / F_q^d contient les racines l-ièmes de l'unité
soit A[l]_0=A[l](F_q)
alors A[l]_0 est de type (Z/lZ)^r, comme \pi est un nombre de Weil, A[l]
contient A[l]_q=\mu_l^r, où A[l]_q={P \in A[l] / \pi P=[q] P}
soit Bhat = A/A[l]_q, et \phi: B -> Ahat =~ A l'isogénie duale.
Ker \phibar=A[l]_q, donc K=Ker \phi = \hat{\mu_l^r}=(Z/lZ)^r
et donc A(F_q)/\phi B(F_q)=A(F_q)/l A(F_q) est rang r.

On a l'application A(F_q)/\phi B(F_q) -> H^1(F_q,K),
mais comme K est de type (Z/lZ)^r, H^1(F_q,K)=H^1(F_q^m,K)
d'où en déroulant tout le couplage de Tate:
A(F_q)/lA(F_q) x A[l]_q -> F_q^m/(F_q^m)^l = \mu_l
(qui est non dégénéré et toujours donné par f_P à cause de toutes les
identifications, cf Schaefer)
et bien sûr si A(F_q) n'a pas de points de l^2-torsion,
A(F_q)/lA(F_q)=A[l]_0

Dans le cas particulier où K=F_q contient \mu_l, on retombe sur
A(K)/lA(K) x G_2(K)=A[l](K) -> K(\mu_l)*/K(\mu_l)*^l.
Si de plus B[l](K) est cyclique et B[l](K) \iso
B(K)/lB(K), alors le couplage de Tate est non dégénéré et symmétrique. Donc
si P est d'ordre l, e_T(P,P) est une racine primitive l-ième.
Par contre si F_q ne contient pas \mu_l, e_T(P,P) n'est pas défini
et si on prend une extension pour qu'il le soit il est alors nul
(cf Handbook, Example 6.9)

Résumé:
------
- Réduire le couplage de Tate à la Frey-Ruck donne un couplage (k=Fq,
  k'=k(\mu_l))
A(k)/lA(k)xG_2 -> k'*/k'*^l
et #A(k)/lA(k)=#G_1(k) (et est même isomorphe à G_1(k) s'il n'y a pas de
points de l^2-torsion).
- Avec Tate-Cartier, on obtient la même situation en prenant l'isogénie
  duale de A->B=A/G_2:
  A/\phi(B)(k') x G_2 -> k'*/k'*^l
  Mais comme G_2 est de type \mu_l, \Ker \phi est de type Z/lZ et est
  isomorphe à G_1. Donc H^1(G_k',Ker \phi)=H^1(G_k, \Ker \phi), ou
  autrement dit
  A/\phi(B)(k')=A/\phi(B)(k)=A(k)/lA(k) (car les groupes sont tous de card
  #G_1(k))
  Donc on a
  A(k)/lA(k) x G_2 -> \mu_l; et si A(k) ne contient pas de points de l^2
  torsions, A(k)/lA(k)=G_1
- On pourrait aussi considérer l'isogénie duale de A->B=A/G_1 pour obtenir
  A/\phi(B)(k') x G_1 -> k'*/k'*^l
  mais cette fois A/\phi(B)(k') est un sous-groupe de A(k')/lA(k') qu'on ne
  peut pas exprimer avec seulement k.
  Par contre, si A(k') ne contient pas de points de l^2-torsion, on a
  A/\phi(B)(k') correspond à G_2(k') \subset A(k')/lA(k') (parce qu'on a le
  bon cardinal et que G_1 est dans \phi(B)(k') car il donne l'isogénie
  duale de \phi). D'où
  G_2 x G_1 -> \mu_l
  (qui a l'intéret que le calcul f_P(Q) du couplage se fait avec P \in G_1
  et Q \in G_2)

Compatibilité entre couplage et isogénie
========================================

f: A-> B, g: B -> C; alors l'application
Ker \hat{g} \subset Ker \hat{g o f}
vient de l'application naturelle:
Ker gof ->_{f} Ker g
       \        |
        \       v
         \-->  G_m

Idée générale: Weil est invariant par extension de corps mais pas par
changement de l'isogénie du couplage; alors que pour Tate c'est l'inverse.
Par contre dans les deux cas, e(fP,Q)=e(P, f^Q) donc e(fP, fQ)=e(P,Q)^deg f
quand c'est bien défini.

Weil
----

Pour se simplifier la vie, on identifier Khat à Ktilde, ie l'iso duale à
l'iso contragrédiente, en supposant qu'on a des polarisations principales
partout.

On déduit que (P \in Ker gof, Q \in Ker \hat{gof}
- e_{g o f}(P,Q)=e_g(f(P),Q) si Q \in Ker \hat{g}
- e_{g o f}(P,Q)=e_{f}(P,\hat{g} Q) si P in Ker f

On en déduit: f: A->B, g:B->C, h:C->D, P \in A, Q \in D
- e_{h o g}(f(P),Q)=e_{gof}(P,\htilde Q)=e_{hogof}(P,Q)
D'où avec g=ftilde, h=f que (P \in A, Q \in B, f:A->B)
- e_l(f(P),Q)=e_l(P,ftilde(Q))
d'où si A=B
- e_l(f(P),f(Q))=e_l(P,Q)^{deg f}
Et aussi e_l^2(P,Q)=e_l(lP,Q) si P \in A[l^2] et Q \in A[l], et donc si P \in A[l], e_l^2(P,Q)=1.

[Question: le dual de G_1=\Z/l\Z est G_2=\mu_l
Est-ce que le couplage de Weil restreint à G_1xG_2 \subset A[l]*A[l]
reste non dégénéré? (On sait qu'un énoncé similaire est bien vrai pour Tate).
La réponse est oui si on considère les espaces caractéristiques, cf [SymplecticGroup]:
> Si M est une matrice symplectique, il est facile de voir que son polynôme
> caractéristique P est un polynôme égal à son polynôme réciproque.
> Si Q_1 est un polynôme irréductible divisant P, je note Q_2 son polynôme
> réciproque, qui divise donc aussi P.
> 
> Est-ce que la forme symplectique, restreinte à la somme des espaces
> caractéristiques de Q_1 et Q_2 reste non dégénérée?]

Tate
----

- e_{T,g o f}(P,Q)=e_{T,g}(P,Q) si Q \in Ker \hat{g}, P \in C(k)

Si on compare on a Ker \hat{g} \subset \ker \hat{g o f}, mais par contre
C/gof(A(k)) ->> C/g(B(k)), et on fait cette identification implicitement à
droite, ce qui veut dire qu'à gauche il faut bien voir que e_T doit être vu
dans k*/k*^{deg g} <<- k*/k*^{deg g deg f}
(ou autrement dit il y a égalité une fois que l'on prend les couplages
réduits)

- Extension de corps: e^{F_q^d}_f(P,Q)=e_f(P,Q)^{1+q+...+q^{d-1}=e_f(P,Q)^d

Pr: avec f_Q(P)^{(q-1)/l} c'est immédiat, q^d-1=(q-1)(1+q+...+q^{d-1}),
avec le passage par Weil: e_W(P,\pi^d Q_0-Q_0)=e_W(P,\pi^d Q_0-\pi^{d-1}
Q_0+\pi^{d-1}Q_0 ... -Q_0)=e_W(P,\pi Q_0-Q_0)^{q^{d-1}+...+1}
Or 1+q+...+q^{d-1}=q-1+q^2-1+...+d=d mod l^n

Corollaire: si P, Q \in A[l], e_{Fq,l^2}(P,Q)=e_{T,l}(P,Q)
            si P \in A[l^2], e_{Fq^\ell, l^2}(P,Q)=e_{T,l}(lP,Q)


Sorina:
si P \in A(k), d=deg f on a
T_l(f(P),f(Q))     =  T_l(P,Q)^d (Q \in A[l])
    || (f(Q) in B[l]         || (Q \in A[l])
T_ld(f(P),f(Q))    =  T_ld(P,Q)^d (Q \in A[ld])

Preuve: le morphisme de connexion commute avec l'isogénie f, on est ramené
au cas de Weil e_l(f(P),f(Q)) prouvé plus haut.

En fait plus généralement: si
f:A->B, g:C->D et alpha_1:A->C et alpha_2:B->D qui rend le carré
A -> C commutatif, on a pour P \in B(k), Q \in Ker g^ / \alpha_2(Q) \in Ker f^:
|    |
v    v
B -> D

e_{T,g}(\alpha_2 P, Q)=e_{T, f}(P, \alpha_2^ Q).

Preuve: si P_0 est tel que f(P_0)=P, alors g(\alpha_1(P_0))=alpha_2(P).
Le membre de gauche est donc donné par e_{W,g}(\pi alpha_1(P_0)-\alpha_1(P_0),Q)
alors que le membre de droite par e_W,f(\pi P_0 - P_0, \alpha_2^ Q)
donc dans les deux cas on tombe sur e_{W, g o \alpha_1 = \alpha_2 o f}(\pi P_0-P_0,Q).