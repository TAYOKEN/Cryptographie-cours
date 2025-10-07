# 🔐 Cryptographie

# 🌐 Graphes

---

## 📘 Introduction aux Graphes

Un **graphe** est un ensemble de **points** (appelés *sommets*) reliés par des **arêtes**.

* 🔵 **Sommets** : points non étiquetés et non orientés
* 🟢 **Arêtes** : relient deux sommets et peuvent être étiquetées

> 🧠 Le mot *graphe* vient de l’allemand *graphen*.
> 💻 Les **automates finis** sont des applications de la théorie des graphes, notamment en **compilation**.
> 🕰️ Les graphes apparaissent dès **1736** avec le célèbre [problème des sept ponts de Königsberg](https://fr.wikipedia.org/wiki/Probl%C3%A8me_des_sept_ponts_de_K%C3%B6nigsberg).

---

## 🧩 Définition formelle

\[
G = (S, A)
\]


* <span style="color:#4CAF50">**S**</span> : ensemble de sommets
* <span style="color:#2196F3">**A**</span> : ensemble d’arêtes ({x, y}) où (x, y \in S) et (x \neq y)

Un graphe est **fini** si le nombre de sommets est fini.

**Notations :**

| Symbole | Signification | Nom |                   |                              |
| ------- | ------------- | --- | ----------------- | ---------------------------- |
| (       | S             | )   | Nombre de sommets | **Ordre du graphe** ((n_g))  |
| (       | A             | )   | Nombre d’arêtes   | **Taille du graphe** ((m_g)) |

\[
0 \leq m \leq \frac{n(n - 1)}{2}
\]


---

## 🤝 Propriété de la poignée de mains

\[
\sum_{s \in S} d(s) = 2m
\]


> 🔹 Le **nombre de sommets de degré impair** dans un graphe est **toujours pair** ✅

---

## 📐 Propriété des tiroirs

Dans tout graphe à au moins deux sommets :
➡️ **Deux sommets au moins ont le même degré.**

\[
0 \leq d(s) \leq n - 1
\]


---

## 🪢 Chaîne et Cycle

Une **chaîne** est une suite de sommets :

\[
s_0,\, s_1,\, s_2,\, \dots,\, s_N
\]


* 📏 Longueur = nombre d’arêtes
* 🔹 Longueur 0 → un seul sommet
* 🔸 Longueur 1 → deux sommets adjacents
* 🔗 Notation : (S - T) si une chaîne relie (S) et (T)

### Types de chaînes

| Type           | Définition               |
| -------------- | ------------------------ |
| 🌱 Élémentaire | Sommets tous distincts   |
| 🌀 Simple      | Arêtes toutes distinctes |
| 🔒 Fermée      | (s_0 = s_N)              |

### Cycles

* 🔄 **Cycle** = chaîne fermée simple
* 🌳 **Graphe acyclique** = graphe sans cycle

---

## 🌲 Arbres et Forêts

| Terme        | Définition                               |
| ------------ | ---------------------------------------- |
| 🌳 **Arbre** | Graphe connexe, acyclique et non vide    |
| 🌲 **Forêt** | Graphe acyclique (pas forcément connexe) |

### Représentations possibles

* 📊 **Matrice d’adjacence**
* 📜 **Liste d’adjacence**

---

## 🎯 Exercices

### 1️⃣ Enseignants et cours

👨‍🏫 6 enseignants : \[
(E_1, \dots, E_6)
\]

📚 6 cours : \[
(C_1, \dots, C_6)
\]


| Enseignant | Cours      |
| ---------- | ---------- |
| E₁         | C₁, C₂     |
| E₂         | C₁, C₂, C₃ |
| E₃         | C₂         |
| E₄         | C₂, C₄, C₅ |
| E₅         | C₄, C₆     |
| E₆         | C₅, C₆     |

---

### 2️⃣ Jurys

⚖️ 7 jurys \[(J_1, \dots, J_7)\]

**Conditions :**

1. Chaque examinateur participe à **2 jurys**
2. Deux jurys quelconques ont **exactement 1 examinateur en commun**

**Résultats :**

* 🔢 Nombre total d’examinateurs :
 \[
  n = \frac{6 \times 7}{2} = 21
 \]
* 👩‍⚖️ Examinateurs par jury : **6**

---

### 3️⃣ Traversée Homme – Femme – Maîtresse

🚤 Un homme, sa femme et sa maîtresse veulent traverser une rivière avec un passeur.

**Contraintes :**

* 👩 La femme refuse que **mari + maîtresse** soient seuls.
* 👨 Le mari refuse que **femme + maîtresse** soient seules.

**Tâches :**

1. Modéliser le problème en **graphe biparti**
2. Trouver les **chaînes minimales** (traversées les plus courtes)

---

### 4️⃣ Théorème d’Euler (1736)

Dans un graphe sans sommet isolé :

| Cas                            | Type de parcours      |
| ------------------------------ | --------------------- |
| 0 ou 2 sommets de degré impair | **Chaîne eulérienne** |
| Tous les sommets pairs         | **Cycle eulérien**    |

---

### 5️⃣ Graphe k-régulier

Si un graphe est **k-régulier** avec (n) sommets :

\[
m = \frac{n \cdot k}{2}
\]

---

### 6️⃣ Exercices sur les degrés

| Degrés        | Possible ? | Raison                             |
| ------------- | ---------- | ---------------------------------- |
| 2, 3, 3, 3, 3 | ✅          | —                                  |
| 2, 2, 3, 3, 3 | ❌          | Nombre impair de degrés impairs    |
| 2, 2, 2, 3, 3 | ✅          | —                                  |
| 0, 1, 2, 3, 4 | ❌          | Contredit la propriété des tiroirs |
| 1, 1, 2, 3, 3 | ✅          | —                                  |
| 2, 2, 4, 4, 4 | ❌          | Impossible structurellement        |
| 1, 1, 1, 3, 4 | ❌          | Degrés impairs impairs             |

---

### 7️⃣ Tournoi de football

⚽ 5 équipes, chacune joue contre 3 autres.

🚫 Impossible : cela donnerait **5 sommets de degré 3** (nombre impair de degrés impairs).

---

### 8️⃣ Pays et frontières

5 pays, 7 frontières :

1. 🔄 Peut-on faire un **cycle eulérien** ? → **Non**
2. 🚶 Peut-on faire une **chaîne eulérienne** ? → **Oui** (2 sommets impairs)
3. ✏️ Tracer une route avec **12 segments** sans repasser ? → **Non** (4 sommets impairs)

---

## ⚙️ Algorithmes

### 🌳 Arbre couvrant

```pseudo
Fonction ArbreCouvrant(G, S₀)
    P[s_j] ← S₀  # père origine (init)
    Pour tout sommet S ∈ G
        P[s] ← ∅  # init de la liste des pères
    FinPour

    Tant que E ≠ ∅ faire
        Prendre s ∈ E
        Pour tout k ∈ S adjacent à s faire
            Si E = E ∪ {k} alors
                P[k] ← s  # ajout du père
            FinSi
        FinPour
        E ← E − {s}  # suppression du sommet traité
    FinTantQue

    Retour P
FinFonction
```

---

### 🔗 Recherche de chaîne

```pseudo
Fonction Chaîne(G, S₀, S)
    Si S₀ et S sont connectés alors
        Pour toute suite S de sommets distincts de S₀ à S faire
            Si S est une chaîne alors
                Retour S
            FinSi
        FinPour
    FinSi
FinFonction
```

---

### 🌲 Forêt couvrante

```pseudo
Fonction ForetCouvrante(G, Sommet)
    P ← ∅
    Pour tout sommet s faire
        P[s] ← 0
    FinPour

    Tant que ∃ s tel que P[s] = 0 faire
        E ← {s}
        Tant que E ≠ ∅ faire
            Prendre x ∈ E
            Pour tout t voisin de x faire
                Si P[t] = 0 alors
                    E ← E ∪ {t}
                    P[t] ← s
                FinSi
            FinPour
        FinTantQue
    FinTantQue

    Retour P
FinFonction
```

---

### 🔍 Vérification d’accessibilité

```pseudo
Fonction Acces(G, S₀)
    Pour tout sommet s ≠ S₀ faire
        Atteint[s] ← Faux
    FinPour
    Atteint[S₀] ← Vrai
    E ← {S₀}

    Tant que E ≠ ∅ faire
        Prendre s ∈ E
        Pour tout t voisin de s faire
            Si Atteint[t] = Faux alors
                E ← E ∪ {t}
                Atteint[t] ← Vrai
            FinSi
        FinPour
        E ← E − {s}
    FinTantQue

    Retour Atteint
FinFonction
```

---

# Rappel semaine dernière

Algorithme d'accessibilité 

**Entrée** : G graphe simple, S₀ sommet 

**Sortie** : arbre couvrant pour les sommets accessibles de S₀

## Algorithmes vus

1) **Algo énumératif** : minimalité : oui - Compléxité:   exponentielle a^n 💀

2) **Algorithme Bellmann ford** : minimalité oui (parcours en largeur) - Compléxité : quadratique

3) **Algo parcours par voisinage** : Minimalité : non - Compléxité : linéaire 

## I) Parcours en Largeur

### Stratégie de parcours en largeur :

Le **parcours en largeur** sert à explorer **tous les sommets accessibles** d’un graphe à partir d’un sommet de départ, **niveau par niveau**.

1. On **met le sommet de départ dans une file (queue)**.
2. Tant que la file n’est pas vide :

   * On **retire** le premier sommet de la file.
   * On **visite tous ses voisins non encore visités** et on les **ajoute à la file**.
3. On continue jusqu’à ce que **tous les sommets atteignables soient visités**.

#### File FIFO 
(First in first out, premier entré, premier sorti)

```PYTHON
def FonctionLargeur (G: Graphe, S₀: Sommet) p : sommet -> sommet U {O} d: Sommet -> N U {∞}
d[s] = d(S₀, S) # + petite longueur des chaines de S₀ à S 

#initialistation
P[S₀] = S₀
d[S₀] = 0

for sommet s in graphe: 
    p[s] = 0 
    d[s] = ∞ 
Atteint = [S₀]
#Traitement

while Atteint is not []:
    S = "premier élement de atteint"
    for t-s and p[t] = 0:
        "Ajout de t à la fin de atteint"
    # S est traité
    p[t] = s
    d[t] = d[s] + 1
    "Enlever S en début de File"
return (p,d)
```
___
### 🧩 Graphe d’initialisation

**Légende** :  
🔵 = Non atteint  
🟢 = Atteint non traité  
🔴 = Traité  


       1🟢───2🔵───3🔵───4🔵
        │              │     |
        │              │     |
        │              │     |
        5🔵──────────6🔵───7🔵
                        
                        
                        8🔵───9🔵

### Étape 2 :


       1🔴───2🟢───3🔵───4🔵
        │              │     |
        │              │     |
        │              │     |
        5🔴──────────6🟢───7🔵
                        
                        
                        8🔵───9🔵

### Étape 3 :
       1🔴───2🔴───3🟢───4🔵
        │              │     |
        │              │     |
        │              │     |
        5🔴──────────6🔴───7🟢
                        
                        
                        8🔵───9🔵

### Étape 4 :
       1🔴───2🔴───3🔴─── 4🟢
        │              │     |
        │              │     |
        │              │     |
        5🔴──────────6🔴───7🔴
                        
                        
                        8🔵───9🔵

### Étape 5 :
       1🔴───2🔴───3🔴─── 4🔴
        │              │     |
        │              │     |
        │              │     |
        5🔴──────────6🔴───7🔴
                        
                        
                        8🔵───9🔵

___

Atteint [2,6]

### Tableau des pères :

| Sommet | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|:-------:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| **d**   | 0 | 1 | ∞ | ∞ | ∞ | ∞ | ∞ | ∞ | ∞ |

| Sommet | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|:-------:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| **p**   | 1 | 1 | 0 | 0 | 1 | 5 | 0 | 0 | 0 |
___
### II) Algorithme de Dijkstra :

L’**algorithme de Dijkstra** sert à trouver le **plus court chemin** depuis un **sommet de départ** vers **tous les autres sommets** d’un graphe pondéré (sans arêtes négatives).

1. On **initialise** les distances : 0 pour le sommet de départ, ∞ pour les autres.
2. On **choisit le sommet non traité** avec la plus petite distance actuelle.
3. On **met à jour les distances** de ses voisins si un chemin plus court est trouvé.
4. On **marque le sommet comme traité** et on recommence jusqu’à ce que tous soient traités (ou que les distances minimales soient connues).
___
### 🧩 Graphe d’initialisation

**Légende** :  
🔵 = Non atteint  
🟢 = Atteint non traité  
🔴 = Traité  

### Début :
       0🟢───∞🔵───∞🔵───∞🔵
        │              │     |
        │              │     |
        │              │     |
        ∞🔵──────────∞🔵───∞🔵
                        
                        
                        ∞🔵───∞🔵

### Étape 2 :
       0🔴───1🔴───∞🔵───∞🔵
        │              │     |
        │              │     |
        │              │     |
        1🔴──────────∞🔵───∞🔵
                        
                        
                        ∞🔵───∞🔵

### Étape 3 :
       0🔴───1🔴───2🔴───∞🔵
        │              │     |
        │              │     |
        │              │     |
        1🔴──────────2🔴───∞🔵
                        
                        
                        ∞🔵───∞🔵

### Étape 4 :
       0🔴───1🔴───2🔴───3🔴
        │              │     |
        │              │     |
        │              │     |
        1🔴──────────2🔴───∞🔵
                        
                        
                        ∞🔵───∞🔵
___
## Longueur minimale

> Si l’on cherche le chemin le plus court de **Paris à Marseille**, alors au moment où l’algorithme de Dijkstra détermine la **distance minimale de Paris à Lyon**, cette distance est déjà **optimale et définitive**.

Autrement dit, même si l’algorithme continue ensuite à calculer la distance jusqu’à Marseille ou d’autres villes,
le **chemin Paris → Lyon** ne changera plus, car il représente déjà la **plus courte distance possible** entre ces deux points.

Pas de file mais juste une table dépendant de P.
Distance partiel de S₀ à S selon P.

$P \subseteq S$ sommets -> distance partielles de S₀ à S selon P.
___

### Exemples : 
$$
dp(s)= min [d(S₀,r)| r - s, et, r \in P ]
$$

$$
\min(\varnothing) = \infty
$$

$$
   min[1,3,5](7) = ∞
    $$
$$
   min[1,4](7) = 4
    $$
$$
d[S₀](S₀) = 0
$$

### Propriété :

$S₀ \in $P  et $P \subset $S

Soit $s \in $S-P tel que dp(s) <= dp (t) pour tout $t \in $S-P 
Alors dp(s) = d(S₀, s)

__Premier cas__ : S non connecté à S₀ : d(S₀,s) <= dp(s) => dp(s) = ∞

__Cas contraire__ : S connecté à S₀

### Exemple : 
P -> P U {s}

Si t est voisin de s

#### si t-s :
$$ dp U [s] (t)= \min [dp(t), d(S₀, S)+1] 
$$
#### si t=s : 
$$ dp U [s] (t)=d(S₀, S)
$$
#### Sinon :
$$
dp U [s] (t)=dp(t)
$$

___

## Algorithme écrit en pseudo :
```PYTHON
def FonctionDijstra(G: Graphe, S₀: Sommet):
     """P:sommet -> sommet U {O}
        d:Sommet -> N U {∞}"""

        #initialisation
        d[s] = 0
        p[S₀] = S₀
        E = {S₀}

        for sommet s and s is not S₀ in Graphe:
            d[s] = ∞
            p[s] = 0
            E = E U {s}
        # E = S : tous les sommets doivent être traités
        # Traitement
        while E is not ∅:
            'prendre s dans E tel que d[s] minimal'
            # alors d[s] = d(S₀, S)
            for t-s and t in E:
                if d[s] +1 < d[t]:
                    d[t] = d[s]+1
                    p[t] = S
            E = E - {s}
        return (p,d)            
```

**Compléxité** : $$O(m+n)$$   