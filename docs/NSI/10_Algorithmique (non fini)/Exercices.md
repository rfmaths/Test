---
title: Exercices
weight: 4
---

# Exercices 

Vous trouverez ci-dessous les exercices de cette séquence.

- Les exercices marqués avec :fontawesome-solid-pencil: se réalisent **sans ordinateur**.  
  Ceux indiqués par :fontawesome-solid-laptop: nécessitent **un ordinateur**.

- Le **niveau de difficulté** est indiqué par des étoiles :  
    <ul style="list-style: none;">
        <li>:fontawesome-solid-star: :fontawesome-regular-star: :fontawesome-regular-star: → Exercices pour **s'approprier les notions**.</li>
        <li>:fontawesome-solid-star: :fontawesome-solid-star: :fontawesome-regular-star: → Exercices pour **renforcer vos compétences**.</li>
        <li>:fontawesome-solid-star: :fontawesome-solid-star: :fontawesome-solid-star: → Exercices pour vous **challenger** et tester vos acquis.</li>
    </ul>

Les corrections sont généralement disponibles, mais elles ne doivent être consultées **qu'après validation de votre production par l'enseignant**.

---

## Coût d'un algorithme 

!!! exoordi "Exercice 1 - :fontawesome-solid-star: :fontawesome-regular-star: :fontawesome-regular-star:" 
    En utilisant l'interface « Complexité », [disponible ici](https://www.cahier-nsi.fr/complexite/), classer les temps d'exécution des algorithmes suivants de 1 (rapide) à 7 (extrêmement lent).

    | Complexité | $n^2$ | $n!$ | $n \cdot \log(n)$ | $\log(n)$ | $2^n$ | $n$ | $n^{\frac{3}{2}}$ |
    |------------|-------|------|-------------------|-----------|-------|-----|-------------------|
    | Classement | ...... | ...... | ...... | ...... | ...... | ...... | ...... |

    ??? success "Correction"
        | Complexité | $n^2$ | $n!$ | $n \cdot \log(n)$ | $\log(n)$ | $2^n$ | $n$ | $n^{\frac{3}{2}}$ |
        |------------|-------|------|-------------------|-----------|-------|-----|-------------------|
        | Classement | 4 | 7 | 3 | 1 | 6 | 2 | 5 |

!!! exoordi "Exercice 2 - :fontawesome-solid-star: :fontawesome-solid-star: :fontawesome-regular-star:" 
    On considère ici un problème de taille $n = 10^6$ (par exemple, un tableau avec un million de données), traité avec un ordinateur capable d'effectuer $10^9$ opérations élémentaires par seconde. Le tableau ci-dessous propose de calculer la durée d'exécution de cet algorithme, en fonction de sa complexité.

    On indique que $\log_2(n) = \dfrac{\log(n)}{\log(2)}$.

    | Nom de la complexité | Notation $O$ | Durée de l'exécution de l'algorithme | Commentaire |
    |----------------------|--------------|---------------------------------------|-------------|
    | Temps constant | $O(1)$ | 1 ns | Le temps d'exécution ne dépend pas de la taille $n$ du problème |
    | ...... | $O(\log_2(n))$ | $\dfrac{\log_2(10^6)}{10^9} \approx 20 \text{ ns}$ | Quasi instantané |
    | ...... | $O(n)$ | ...... | ...... |
    | Quasi linéaire | $O(n \cdot \log_2(n))$ | ...... | ...... |
    | ...... | $O(n^2)$ | ...... | ...... |
    | ...... | $O(n^3)$ | ...... | ...... |
    | Polynomiale | $O(n^k)$ avec $k > 3$ | Pour $k = 4$ : ...... | ...... |
    | ...... | $O(2^n)$ | ...... | ...... |
    | ...... | $O(n!)$ | ...... | ...... |

    1. Compléter la première colonne en recherchant sur le Web le nom de chaque complexité.

    2. Compléter enfin les deux dernières colonnes en calculant le temps d'exécution des différents algorithmes, avec chaque modèle de complexité.

    3. Un GPS muni d'un processeur capable d'effectuer 800 000 calculs élémentaires par seconde doit traiter une carte routière composée de 100 000 entrées. Quelles sont les complexités envisageables pour l'algorithme afin que les calculs de route puissent être menés en temps réel pendant le déplacement du véhicule ?

    ??? success "Correction"
        **2. Noms et durées d'exécution pour $n = 10^6$ et $10^9$ op/s :**

        | Nom de la complexité | Notation $O$ | Durée | Commentaire |
        |----------------------|--------------|-------|-------------|
        | Temps constant | $O(1)$ | 1 ns | Indépendant de $n$ |
        | Logarithmique | $O(\log_2(n))$ | $\approx 20$ ns | Quasi instantané |
        | Linéaire | $O(n)$ | $\dfrac{10^6}{10^9} = 1$ ms | Très rapide |
        | Quasi linéaire | $O(n \cdot \log_2(n))$ | $\approx 20$ ms | Rapide |
        | Quadratique | $O(n^2)$ | $\dfrac{10^{12}}{10^9} \approx 16$ min | Lent |
        | Cubique | $O(n^3)$ | $\dfrac{10^{18}}{10^9} \approx 31$ ans | Très lent |
        | Polynomiale ($k=4$) | $O(n^4)$ | $\dfrac{10^{24}}{10^9} \approx 3 \times 10^7$ ans | Inutilisable |
        | Exponentielle | $O(2^n)$ | Astronomique | Totalement inutilisable |
        | Factorielle | $O(n!)$ | Astronomique | Totalement inutilisable |

        **3.** Pour un GPS avec 800 000 op/s et $n = 100\,000$ entrées, le calcul doit s'effectuer en temps réel (moins d'une seconde). Les complexités envisageables sont :

        - $O(1)$, $O(\log_2(n))$, $O(n)$ et $O(n \cdot \log_2(n))$ sont acceptables.
        - $O(n^2)$ donne $\dfrac{(10^5)^2}{8 \times 10^5} \approx 12\,500$ s → trop lent.
        
        Seules les complexités **constante, logarithmique, linéaire et quasi-linéaire** sont envisageables.

!!! exoordi "Exercice 3 - :fontawesome-solid-star: :fontawesome-solid-star: :fontawesome-regular-star:" 
    Reprenons les algorithmes 1 et 2 de calcul de $x^n$ : 

    ```title="Algorithme 1"
    Algorithme : puissance1(x, n)
    p ← 1
    pour i allant de 1 à n
    p ← p * x
    renvoyer p
    ```

    ```title="Algorithme 2"
    Algorithme : puissance2(x, n)
    p ← 1
    tant que n > 0
    si n est impair alors
        p ← p * x
    x ← x * x
    n ← n // 2
    renvoyer p
    ```

    1. Écrire une fonction Python `puissance1(x, n)` qui implémente l'algorithme 1 et qui renvoie la valeur de $x^n$.
    2. Écrire une fonction Python `puissance2(x, n)` qui implémente l'algorithme 2.
    3. En utilisant le module Python `time`, effectuer des mesures comparatives de durées d'exécution en calculant le nombre $2^{500\,000}$.
    4. Ces résultats sont-ils en accord avec la complexité attendue ?

    ??? success "Correction"
        **1.** `puissance1` suit l'algorithme 1 : une boucle de $n$ tours, chacun effectuant une multiplication → complexité $O(n)$ :

        ```python
        def puissance1(x, n):
            p = 1
            for i in range(1, n + 1):
                p = p * x
            return p
        ```

        **2.** `puissance2` suit l'algorithme 2 : à chaque tour on divise $n$ par 2 → le nombre de tours est $\log_2(n)$ → complexité $O(\log_2(n))$ :

        ```python
        def puissance2(x, n):
            p = 1
            while n > 0:
                if n % 2 != 0:  # si n est impair
                    p = p * x
                x = x * x
                n = n // 2
            return p
        ```

        **3.** Mesure comparative avec le module `time` :

        ```python
        import time

        t1 = time.time()
        puissance1(2, 500000)
        t2 = time.time()
        print("puissance1 :", t2 - t1, "s")

        t1 = time.time()
        puissance2(2, 500000)
        t2 = time.time()
        print("puissance2 :", t2 - t1, "s")
        ```

        `puissance2` est nettement plus rapide que `puissance1`.

        **4.** Oui, les résultats sont en accord avec la complexité attendue :

        - `puissance1` est en $O(n)$ : le nombre de multiplications est exactement $n$.
        - `puissance2` est en $O(\log_2(n))$ : le nombre de tours de boucle est $\lfloor \log_2(n) \rfloor$.

        Pour $n = 500\,000$, `puissance2` effectue seulement $\approx 19$ tours contre $500\,000$ pour `puissance1`, ce qui explique la très grande différence de durée observée.

!!! exoordi "Exercice 4 - :fontawesome-solid-star: :fontawesome-solid-star: :fontawesome-solid-star:" 
    Pour résoudre un problème algorithmique, qui traite un tableau de taille $n$, Arthur et Maxime ont implémenté un algorithme dans leur langage préféré.

    - Le programme de **Maxime** fait exactement $2n^2$ opérations élémentaires. Il le fait tourner sur sa super machine, capable d'effectuer **20 milliards** d'opérations élémentaires par seconde.
    - **Arthur**, quant à lui, propose un programme qui ne fait pas plus de $50 \cdot n \cdot \log_2(n)$ opérations élémentaires. Il le fait tourner en salle de TP tout en regardant YouTube, sa machine étant alors **20 fois plus lente** que celle de Maxime.

    Répondre aux questions suivantes : 

    1. En tenant compte de la complexité (ou coût) de chaque programme et de la performance des machines, émettre une conjecture sur la durée d'exécution la plus courte.
    2.  Exprimer la durée d'exécution d'un programme en fonction du nombre d'opérations $m$ et du nombre $N$ d'opérations par seconde.
    3. Aller à l'adresse [lycee.editions-bordas.fr/cahier-NSI1re](http://lycee.editions-bordas.fr/cahier-NSI1re), puis cliquer sur « Éditeur Python ».
    Vérifier la conjecture faite à la question 2 en proposant un programme en Python qui renvoie le rang $n$ à partir duquel une solution l'emporte sur l'autre, en termes de temps de calcul.

        > **Aide** : On peut utiliser la fonction `math.log2(x)` du module `math`, pour calculer $50 \cdot n \cdot \log_2(n)$.
    4. Il est possible d'illustrer ce résultat par les graphiques ci-dessous, représentant la durée d'exécution en fonction de $n$ et obtenus à la calculatrice. Redonner chaque courbe à son propriétaire et conclure.

    ??? success "Correction"
        **1.** Pour les petites valeurs de $n$, Maxime (complexité $O(n^2)$) peut être plus rapide grâce à sa machine plus puissante. Mais pour les grandes valeurs de $n$, Arthur (complexité $O(n \cdot \log_2(n))$) devrait l'emporter malgré une machine 20 fois plus lente.

        **2.** La durée d'exécution est :

        $$t = \frac{m}{N}$$

        - Durée pour Maxime : $t_M = \dfrac{2n^2}{20 \times 10^9}$
        - Durée pour Arthur : $t_A = \dfrac{50 \cdot n \cdot \log_2(n)}{10^9}$

        **3.** Programme Python pour trouver le rang $n$ à partir duquel Arthur l'emporte :

        ```python
        import math

        n = 1
        while (2 * n**2) / (20e9) <= (50 * n * math.log2(n)) / (1e9):
            n += 1
        print("Arthur l'emporte à partir de n =", n)
        ```

        Arthur l'emporte à partir d'un certain rang $n$ (aux alentours de $n \approx 1000$).

        **4.** Sur le graphique :
        - La courbe **noire** (croissance plus lente) correspond à **Arthur** ($O(n \cdot \log_2(n))$).
        - La courbe **rouge** (croissance plus rapide) correspond à **Maxime** ($O(n^2)$).

        **Conclusion** : Même avec une machine plus lente, l'algorithme quasi-linéaire d'Arthur finit par surpasser l'algorithme quadratique de Maxime dès que $n$ devient suffisamment grand.