# Introduction à la physique des matériaux

## Chapitre 1 : Introduction


### 1.1 Problématique générale
Faire le lien entre micro et macro. Depuis environ 20 ans, les ordis nous permettent de prédire les propriétés des matériaux à partir de calculs.
### 1.2 Réduction de l'Hamiltonien

<!--TODO-->
L'état fondamental d'un matériau composé de $N_i$ noyaux et $N_e$ électrons est donné par l'équation de Schrödinger indépendante du temps, à savoir:

\begin{equation}
    H(\vec{r},\vec{R})\phi(\vec{r},\vec{R}) = E \phi(\vec{r},\vec{R})
\end{equation}


Présentation de l'[approximation de Born-Oppenheimer](https://en.wikipedia.org/wiki/Born%E2%80%93Oppenheimer_approximation).


### 1.3 Plan du cours

- Partie I
    - Hypothèse de travail : $E_{el}(\vec{R})$ et donc  $E_{e+i}(\vec{R})$ sont connues.
    - Étude de la dynamique des noyaux
    - Explication du concept de <i>phonons</i>
    - Comment les noyaux contribuent à différentes propriétés
- Partie II
    - Comment déterminer $E_{el}(\vec{R})$ en pratique (ici, avec l'hypothèse des électrons indépendants). 
    - Éléments de [DFT](https://en.wikipedia.org/wiki/Density_functional_theory)
- Partie III
    - Application des concepts vus précédemment à l'étude de différentes classes de matériaux


## Chapitre 2 : Modes normaux de vibration et phonons

### 2.1 Introduction

Dans l'approximation de B-O, le mouvement des noyaux est découplé de celui des électrons. Ainsi, les propriétés du matériau peuvent elles aussi être catégorisées comme étant dues au mouvement des noyaux, ou à celui des électrons. Dans ce chapitre, nous nous intéresserons à la dynamique des noyaux <i>dans les solides cristallins</i>.


### 2.2 Cadre général

#### 2.2.1 Positions atomiques

Un solide cristallin est caractérisé par une répétition périodique de sa maille élémentaire. Nous pouvons donc utiliser cette propriété pour désigner la position d'un atome $\kappa$ présent dans une maille $a$ par : 

\begin{equation}
    \vec{R_{\kappa}^a} = \vec{R^a} + \tau_{\kappa}
\end{equation}

avec $\vec{R^a}$ le vecteur spécifiant la position de la maille et $\tau_{\kappa}$ donnant la position de $\kappa$ au sein de la maille $a$.

Plus précisément, le noyau oscille autour de sa position d'équilibre $\vec{R_{\kappa}^a}$, mais avec une amplitude faible. Notons que, dans la suite, nous allons dénoter la <i>position instantanée de l'atome $\kappa$ dans la maille $a$</i> par 

\begin{equation}
    \vec{r_{\kappa}^a} = \vec{R_{\kappa}^a} + \vec{u_{\kappa}^a}
\end{equation}

avec $\vec{u_{\kappa}^a}$ le déplacement instantané, qui peut varier d'une cellule à l'autre.

#### 2.2.2 Approximation harmonique 
L'approximation que nous allons faire repose plutôt sur une simplification de théorie que sur un argument fondamental. En ayant déjà fait l'approximation de B-O, on a vu que les positions d'équilibre des noyaux ($\vec{R_{\kappa}^a}$) sont celles qui minimisent $E_{e+i}$. On peut regarder l'évolution de cette énergie en effectuant son développement en série. Nous obtenons: 

\begin{equation}
    E_{e+i}[\vec{r_{\kappa}^a}] = E_{e+i}[\vec{R_{\kappa}^a}] + \sum_{\kappa \alpha a}\frac{\partial E_{e+i}}{\partial r_{\kappa \alpha}^a} u_{\kappa \alpha}^a + \frac{1}{2} \sum_{\kappa \alpha a\\ \kappa ' \beta b}\frac{\partial^2 E_{e+i}}{\partial r^a_{\kappa \alpha}\partial r^b_{\kappa '\beta}} u^a_{\kappa \alpha} u^b_{\kappa ' \beta} + \dots
\end{equation}

Ressource utile pour comprendre l'approximation harmonique : https://youtu.be/LGK2IZ77hZc

<!--TODO-->

#### 2.2.3 Signifiation des constantes de forces interatomiques

Un modèle utile pour interpréter les forces interatomiques est celui des ressorts. On peut en effet considérer le solide comme un ensemble d'atomes liés entre eux, deux à deux, par des ressorts de constante de raideur $K_ij$. 
