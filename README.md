# 🔐 Cryptographie

# 🌐 Graphes

---

## 📌 Introduction des Graphes

- 🔵 Ensemble de points **non étiquetés, non orientés**
- 🟢 Reliés par des arêtes pouvant être étiquetées  
- 📦 Un graphe = **paquet de sommets** + **paquet d’arêtes**  

> 📖 *Le terme* **graphe** *vient de l’allemand* **graphen**  
> 💻 Les automates finis en informatique servent à la compilation des données.  
> 🕰️ Apparition en **1736** avec le [problème des sept ponts de Königsberg](https://fr.wikipedia.org/wiki/Probl%C3%A8me_des_sept_ponts_de_K%C3%B6nigsberg).

---

### 📘 Définition d’un graphe

\[
G = (S, A)
\]

- <span style="color:#4CAF50">**S**</span> : ensemble quelconque de sommets  
- <span style="color:#2196F3">**A**</span> : ensemble des arêtes \(\{x,y\}\) tel que \(x,y \in S\) et \(x \neq y\)  

⚠️ Un graphe est **fini** si le nombre de sommets est fini.  

**Notations :**
- 🧮 \(|S|\) → **ordre du graphe** (noté \(n_g\))  
- 📏 \(|A|\) → **taille du graphe** (noté \(m_g\))  
- 🔢 Nombre max d’arêtes :  
  \[
  0 \leq m \leq \frac{n(n-1)}{2}
  \]  

---

### 🤝 Propriété de la poignée de mains

\[
\sum_{s \in S} d(s) = 2m
\]

➡️ Le nombre de sommets de degré **impair** est toujours **pair**. ✅

---

### 📐 Propriété des tiroirs

- Pour tout graphe ayant ≥ 2 sommets, **au moins deux sommets ont le même degré**.  
- Bornes :  
  \[
  0 \leq d(s) \leq n-1
  \]  

---

### 🪢 Chaîne

Une chaîne est une suite :  

\[
s_0, s_1, s_2, \dots, s_N
\]

- 📏 Longueur = nombre d’arêtes  
- 🔹 Longueur 0 : un sommet  
- 🔸 Longueur 1 : deux sommets adjacents  
- 🔗 Notation : \(S-T\) si une chaîne relie \(S\) et \(T\)  

**Types de chaînes :**  
- 🌱 Élémentaire : sommets distincts  
- 🌀 Simple : arêtes distinctes  
- 🔒 Fermée : \(s_0 = s_N\)  

**Cycles :**
- 🔄 Cycle = chaîne fermée simple  
- 🌳 Graphe acyclique = graphe sans cycle  

---

### 🌳 Arbre et forêt

- 🌳 **Arbre** = graphe connexe, acyclique, non vide  
- 🌲 **Forêt** = graphe acyclique (pas forcément connexe)  

**Implémentations :**
- 📊 Matrice d’adjacence  
- 📜 Liste d’adjacence  

---

## 🎯 Exercices

---

### 1️⃣ Enseignants et cours

👨‍🏫 6 enseignants : \(E_1, \dots, E_6\)  
📚 6 cours : \(C_1, \dots, C_6\)  

- \(E_1 \to C_1,C_2\)  
- \(E_2 \to C_1,C_2,C_3\)  
- \(E_3 \to C_2\)  
- \(E_4 \to C_2,C_4,C_5\)  
- \(E_5 \to C_4,C_6\)  
- \(E_6 \to C_5,C_6\)  

---

### 2️⃣ Jurys

⚖️ 7 jurys \(J_1, \dots, J_7\).  

- 📝 C1 : chaque examinateur appartient à **2 jurys**  
- 📝 C2 : deux jurys quelconques ont **exactement 1 examinateur en commun**  

**Questions :**  
- ❓ Q1 : Nombre total d’examinateurs ?  
  \[
  n = \frac{6 \times 7}{2} = 21
  \]  
- ❓ Q2 : Combien d’examinateurs par jury ? **6**  

---

### 3️⃣ Traversée Homme-Femme-Maîtresse

🚤 Un homme, sa femme et sa maîtresse veulent traverser une rivière avec un passeur.  

⚠️ Contraintes :  
- 👩 La femme refuse que mari + maîtresse soient seuls ensemble.  
- 👨 Le mari refuse que femme + maîtresse soient seules ensemble.  

➡️ Tâche :  
1. Modéliser en **graphe biparti**  
2. Trouver les solutions minimales (chaînes les plus courtes).  

---

### 4️⃣ Théorème d’Euler (1736)

- 📏 Graphe sans sommet isolé :  
  - ✔️ 0 ou 2 sommets de degré impair ⟹ chaîne eulérienne  
  - ✔️ Tous sommets de degré pair ⟹ cycle eulérien  

---

### 5️⃣ Graphe K-régulier

Si graphe **k-régulier** avec \(n\) sommets :  

\[
m = \frac{n \cdot k}{2}
\]

---

### 6️⃣ Exercices sur les degrés

Donner un graphe avec 5 sommets et degrés :  

- ✅ \(2,3,3,3,3\)  
- ❌ \(2,2,3,3,3\) (*degrés impairs non pairs*)  
- ✅ \(2,2,2,3,3\)  
- ❌ \(0,1,2,3,4\) (*propriété des tiroirs*)  
- ✅ \(1,1,2,3,3\)  
- ❌ \(2,2,4,4,4\)  
- ❌ \(1,1,1,3,4\)  

---

### 7️⃣ Tournoi de football

⚽ 5 équipes, chaque équipe joue contre 3 autres.  

🚫 Impossible : cela impose **5 sommets de degré 3** (degrés impairs impairs).  

---

### 8️⃣ Pays et frontières

5 pays, 7 frontières :  

1. 🔄 Peut-on partir d’un pays et y revenir en franchissant chaque frontière une fois ? **Non**  
2. ⬅️➡️ Peut-on aller d’un pays à un autre en franchissant chaque frontière une fois ? **Oui** (2 sommets impairs)  
3. ✏️ Peut-on tracer une route en traversant 12 segments une seule fois ? **Non** (4 sommets impairs)  
