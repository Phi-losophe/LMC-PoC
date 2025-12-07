# LMC-PoC
Proof of Concept et tests pour la Loi de Minimisation de l'Entropie Cognitive

# LMC-Law: Cognitive Entropy Minimization

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)
![Status](https://img.shields.io/badge/status-research_prototype-orange)
![License](https://img.shields.io/badge/license-MIT-green)

## 🧠 Introduction

Ce dépôt contient l'implémentation de référence (Proof of Concept) de la **Loi de Minimisation de l’Entropie Cognitive (LMC)**.

La **LMC** est une proposition théorique modélisant la prise de décision cognitive comme un problème d'optimisation thermodynamique. Elle postule que tout système intelligent (biologique ou artificiel) sélectionne les structures d'information qui maximisent la cohérence contextuelle tout en minimisant leur entropie interne (coût énergétique de traitement).

## 📐 Le Modèle Mathématique

Le système évalue des structures candidates $s$ dans un contexte $\Omega$ selon la fonction de coût suivante :

$$Score(s) = \frac{\mathcal{C}(s | \Omega)}{H(s) + \epsilon}$$

Où :
* **$\mathcal{C}$ (Cohérence)** : Calculée via la **Similarité Cosinus** entre les vecteurs d'embeddings du contexte et du candidat.
* **$H$ (Entropie)** : Approximée via le taux de compression (Zlib/Deflate) ou l'Entropie de Shannon, représentant la complexité descriptive (MDL).
* **$\epsilon$** : Constante de régularisation ($1e^{-6}$).



[Image of vector space model NLP]

*Visualisation conceptuelle de l'espace vectoriel utilisé pour calculer C (la cohérence).*

## 🚀 Installation

1. Clonez ce dépôt :
```bash
git clone [https://github.com/votre-user/lmc-law.git](https://github.com/votre-user/lmc-law.git)
cd lmc-law
```

## 📚 Références

- Friston, K. (2010). *The free-energy principle: a unified brain theory?* Nature Reviews Neuroscience, 11, 127–138.
- Rissanen, J. (1978). *Modeling by shortest data description.* Automatica, 14(5), 465–471.
- Shannon, C. E. (1948). *A Mathematical Theory of Communication.* Bell System Technical Journal, 27, 379–423, 623–656.

## ⚠️ Limitations et Approximations

- **Approximation de l’entropie :** l’usage de la compression zlib/DEFLATE est un proxy pour la complexité de Kolmogorov ; reflète les tendances globales mais n’est pas exact.  
- **Constante ε :** empêche la division par zéro si H = 0. Valeur par défaut = 1e-6.  
- **Mesure de cohérence :** basée sur la similarité cosinus des embeddings vectoriels ; précision dépend de la qualité des embeddings et du prétraitement du texte.  
- **Validité générale :** PoC pour démontrer le principe LMC ; ne modélise pas parfaitement le cerveau humain ni tous les LLM existants.

## 🛠️ Exemple d'utilisation rapide

```python
from lmc_model import calculateScore

context = "Le ciel est bleu"
candidate = "Le ciel est clair"
score = calculateScore(context, candidate)
print(f"Score LMC : {score}")

