# 🧭 Roadmap de formation — Construire ta librairie de finance quantitative

**Objectif général :**  
Apprendre à coder toi-même une vraie librairie modulaire de finance quantitative (type mini-QuantLib), sans code IA, avec un module fonctionnel, un notebook de validation et une documentation chaque semaine.

**Période :** du **12 novembre 2025** au **26 janvier 2026** (≈ 10 semaines)

---

## 📂 Structure du dépôt

```
quant-finance-lab/
│
├── quantlib/
│   ├── data/
│   ├── models/
│   ├── risk/
│   ├── strategies/
│   ├── utils/
│   └── tests/
│
├── notebooks/
│   ├── 01_stylized_facts.ipynb
│   ├── ...
│   └── 09_final_project.ipynb
│
├── research/
│   ├── papers/
│   └── Research_Roadmap.md
│
├── data/
├── README.md
├── Roadmap.md
├── setup.py
├── requirements.txt
└── LICENSE
```

---

## 📅 Semaine 1 — Mise en place & stylized facts  
**Dates : 12 → 17 novembre 2025**

🎯 *Poser les fondations techniques et explorer les propriétés empiriques des rendements.*

**À faire :**
- [ ] Créer le dépôt GitHub `quant-finance-lab/`
- [ ] Configurer ton environnement Python (venv ou conda)
- [ ] Créer le module `quantlib/data/data_loader.py` :
  - [ ] Téléchargement de données (Yahoo Finance, FRED)
  - [ ] Calcul des rendements simples et logarithmiques
  - [ ] Conversion de fréquences et nettoyage de NA
- [ ] Analyser les *stylized facts* sur un indice (S&P500, Eurostoxx…)

**Livrables :**
- [ ] `notebooks/01_stylized_facts.ipynb`
- [ ] Graphiques : histogrammes, autocorrélation, volatilité en grappes

📘 *Réf : Cont (2001), “Empirical properties of asset returns”*

---

## 📅 Semaine 2 — Simulation & pricing Monte Carlo  
**Dates : 18 → 24 novembre 2025**

🎯 *Maîtriser les processus stochastiques et le pricing par simulation.*

**À faire :**
- [ ] Module `quantlib/models/stochastic.py`
  - [ ] Simulation GBM, OU process, Jump Diffusion
  - [ ] Pricing Monte Carlo d’options (européenne, asiatique)
  - [ ] Implémenter variance reduction (antithetic, control variate)
- [ ] Comparer avec la formule fermée de Black-Scholes

**Livrables :**
- [ ] `notebooks/02_montecarlo_pricing.ipynb`
- [ ] Graphes : convergence du prix, histogramme du payoff

📘 *Réf : Glasserman (2003), Broadie & Glasserman (1997)*

---

## 📅 Semaine 3 — Courbes de taux & modèles de rendement  
**Dates : 25 novembre → 1 décembre 2025**

🎯 *Construire une courbe zéro-coupon et pricer des obligations.*

**À faire :**
- [ ] Module `quantlib/models/yield_curve.py`
  - [ ] Bootstrap zéro-coupon à partir d’obligations
  - [ ] Estimation Nelson–Siegel et Svensson
  - [ ] Calculs de duration, convexité, taux instantané
  - [ ] Visualisation des courbes à plusieurs dates

**Livrables :**
- [ ] `notebooks/03_yield_curve_bootstrap.ipynb`
- [ ] Graphiques : courbe zéro, taux instantané

📘 *Réf : Nelson & Siegel (1987), Svensson (1994)*

---

## 📅 Semaine 4 — Risque de marché : VaR & Expected Shortfall  
**Dates : 2 → 8 décembre 2025**

🎯 *Évaluer et backtester les mesures de risque.*

**À faire :**
- [ ] Module `quantlib/risk/var_es.py`
  - [ ] VaR historique, paramétrique, Monte Carlo
  - [ ] Expected Shortfall (ES)
  - [ ] Backtesting VaR (Kupiec & Christoffersen)
  - [ ] Application à un portefeuille de 10 actifs

**Livrables :**
- [ ] `notebooks/04_risk_measurement.ipynb`
- [ ] Graphiques : VaR vs pertes réelles, histogramme des dépassements

📘 *Réf : Acerbi & Tasche (2002), Christoffersen (1998)*

---

## 📅 Semaine 5 — Volatilité conditionnelle : modèles GARCH  
**Dates : 9 → 15 décembre 2025**

🎯 *Estimer et prévoir la volatilité.*

**À faire :**
- [ ] Module `quantlib/models/volatility.py`
  - [ ] GARCH(1,1), EWMA
  - [ ] Estimation par MLE
  - [ ] Simulation de volatilité future
  - [ ] Comparaison à la volatilité réalisée

**Livrables :**
- [ ] `notebooks/05_volatility_models.ipynb`
- [ ] Graphiques : volatilité conditionnelle vs réalisée

📘 *Réf : Bollerslev (1986), Engle (2002)*

---

## 📅 Semaine 6 — Optimisation de portefeuille  
**Dates : 16 → 22 décembre 2025**

🎯 *Appliquer la théorie de Markowitz et ses extensions modernes.*

**À faire :**
- [ ] Module `quantlib/risk/portfolio.py`
  - [ ] Frontière efficiente
  - [ ] Contraintes de poids (≥0, somme=1)
  - [ ] Régularisation (ridge, L1)
  - [ ] Comparaison avec un portefeuille 1/N

**Livrables :**
- [ ] `notebooks/06_portfolio_optimization.ipynb`
- [ ] Graphiques : frontière efficiente, composition du portefeuille

📘 *Réf : Markowitz (1952), DeMiguel et al. (2009)*

---

## 📅 Semaine 7 — Stratégies de trading & backtesting  
**Dates : 23 → 29 décembre 2025**

🎯 *Créer ton moteur de backtest et implémenter une stratégie simple.*

**À faire :**
- [ ] Module `quantlib/strategies/backtest.py`
  - [ ] Gestion du capital, frais, positions
  - [ ] Mesures de performance : Sharpe, Sortino, drawdown
  - [ ] Implémenter `momentum.py` ou `mean_reversion.py`
  - [ ] Backtest sur 20 ans de données (Yahoo Finance)

**Livrables :**
- [ ] `notebooks/07_backtesting.ipynb`
- [ ] Graphiques : equity curve, drawdown, ratios

📘 *Réf : Jegadeesh & Titman (1993), Lopez de Prado (2018)*

---

## 📅 Semaine 8 — Visualisation, reporting & documentation  
**Dates : 30 décembre 2025 → 5 janvier 2026**

🎯 *Rendre tes résultats lisibles, documentés et réutilisables.*

**À faire :**
- [ ] Module `quantlib/utils/plotting.py`
  - [ ] Visualisations standardisées
  - [ ] Dashboard Streamlit ou documentation MkDocs
- [ ] Finaliser le `README.md` et le `Roadmap.md`

**Livrables :**
- [ ] `notebooks/08_visualization_and_summary.ipynb`
- [ ] `README.md` complet et clair

---

## 📅 Semaines 9–10 — Projet final (optionnel / signature)  
**Dates : 6 → 26 janvier 2026**

🎯 *Intégrer les modules dans un projet complet.*

**Exemples de projets :**
- Calibration du modèle de Heston (pricing / volatilité implicite)
- Modèle multi-facteur (ACP + Markowitz)
- Prédiction de volatilité via XGBoost ou LSTM
- Market making simulé (Avellaneda–Stoikov)

**Livrables :**
- [ ] `notebooks/09_final_project.ipynb`
- [ ] Rapport PDF (3–5 pages : théorie, méthode, résultats, limites)

---

## 🔮 Après le plan

Une fois cette base construite :
- [ ] Étendre la librairie : Heston, SABR, multi-factor, ML
- [ ] Optimiser les performances : numba, jax, torch
- [ ] Publier la doc : MkDocs, GitHub Pages
- [ ] Ouvrir le projet à d’autres étudiants quants (collaboratif)

---

📌 *Dernière mise à jour : 11 novembre 2025*
