# Analyse marketing : comprendre les clients et la performance des campagnes

Analyse statistique de **1 200 clients** d'une entreprise marocaine (18 variables) pour comprendre leurs dépenses, leurs canaux d'acquisition et ce qui les fait répondre à une campagne marketing.

![Aperçu](images/apercu.png)

## Les questions
- Combien dépensent les clients, et quels profils dépensent le plus ?
- Quels canaux d'acquisition et quelles actions font le plus répondre aux campagnes ?
- Quels leviers l'équipe marketing doit-elle prioriser ?

## Les données
- `clients_marketing.csv` : 1 200 clients, inscrits entre janvier 2022 et décembre 2025
- Variables : profil (âge, sexe, région, niveau d'étude, revenu), comportement (visites, durée de session, achats, panier moyen, dépense annuelle), marketing (canal d'acquisition, segment, newsletter, ouverture des emails, satisfaction, réponse à la campagne)
- Qualité : 36 revenus manquants (3 %), aucun doublon

## Démarche
1. **Prise en main et qualité des données :** types, valeurs manquantes, doublons, conversion des dates.
2. **Analyse univariée :** tendance centrale, dispersion, asymétrie, valeurs atypiques (règle de Tukey), fréquences.
3. **Analyse bivariée :** corrélations (Pearson, Spearman), ANOVA et η², tests de comparaison, tableaux croisés et khi-deux (V de Cramér).
4. **Analyse trivariée :** effet combiné segment × achats, canal × newsletter, niveau d'étude × sexe.
5. **Analyse multivariée :** matrice de corrélation, pairplot, ACP, segmentation K-means et régression logistique.

## Résultats clés
| Constat | Chiffre |
| --- | --- |
| Dépense annuelle médiane | **3 035 MAD** (moyenne 3 369 MAD, 38 gros clients atypiques) |
| Taux de réponse global à la campagne | **21,3 %** |
| Meilleur canal / plus faible | **Email 29,6 %** / Publicité TV 8,6 % |
| Abonnés newsletter vs non-abonnés | **29,2 %** de réponse vs 14,0 % |
| VIP vs Standard | **5 156 MAD** vs 2 667 MAD par an (près de 2 fois plus) |
| Revenu × panier moyen | r = 0,91 : +1 000 MAD de revenu ≈ +35 MAD de panier |

- Les **VIP** n'achètent pas plus souvent que les clients Standard : ils dépensent plus parce que leur **panier moyen** est plus élevé.
- La **newsletter** augmente la réponse dans **tous les canaux**, surtout pour les clients venus des moteurs de recherche (+20 points).
- Les **18–29 ans** arrivent surtout par les **réseaux sociaux** (46 %), les **45–70 ans** par l'**email** (35 %).
- Le **temps passé sur le site** n'a pas de lien significatif avec la dépense, et le **sexe** n'influence pas la réponse aux campagnes.
- L'ACP retient **3 axes** (règle de Kaiser) ; le plan F1–F2 porte 48 % de l'information. Le K-means distingue **3 groupes** de clients.

## Recommandations
1. **Développer les inscriptions à la newsletter** : c'est le levier le plus net sur le taux de réponse.
2. **Adapter le canal à l'âge** : réseaux sociaux pour les 18–29 ans, email pour les 45 ans et plus.
3. **Revoir le budget de la publicité TV**, qui recrute le moins de clients et répond le moins.
4. **Augmenter le panier moyen** (offres groupées, montée en gamme) plutôt que le temps passé sur le site.

## Outils
Python · Pandas · NumPy · Matplotlib · Seaborn · Plotly · SciPy (tests statistiques) · Scikit-learn (ACP, K-means, régression logistique)

## Structure
```
├── analyse_marketing.ipynb   # analyse complète
├── clients_marketing.csv     # données
├── images/                   # graphiques clés
└── README.md
```

## Lancer le projet
```bash
pip install pandas numpy matplotlib seaborn plotly scipy scikit-learn
jupyter notebook analyse_marketing.ipynb
```
