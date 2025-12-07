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
