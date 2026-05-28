# Grafana CSV KPI Dashboard

Tableau de bord de disponibilité dynamique généré depuis un export CSV Grafana (format **Join by field**).

## Fonctionnalités

- **Chargement de fichier CSV** via une interface graphique (drag & drop ou sélecteur)
- **Détection automatique des colonnes** : toujours `Time` en première colonne, le reste est détecté automatiquement
- **Valeurs vides** et `No data` traitées comme cellules vides
- **Filtrage temporel dynamique** : boutons rapides (1h, 6h, 12h, 24h, 7j, 30j) + plage personnalisée
- **Tri des colonnes** dans le tableau de détail
- **Code couleur** : vert ≥ 99.5%, orange 95–99.5%, rouge < 95%
- **Mode clair / sombre** avec bascule
- Fonctionne **100% en local**, aucun serveur requis

## Utilisation

1. Ouvrir `index.html` dans un navigateur
2. Charger un fichier CSV exporté depuis Grafana (bouton ou glisser-déposer)
3. Utiliser les filtres de période en haut pour explorer les données

## Format CSV attendu

```
Time,Service status of ApiCAF,Service status of BAN,...
2026-05-27 19:28:39,UP,,
2026-05-27 19:28:42,,UP,
...
```

- Première colonne : `Time` (obligatoire)
- Valeurs possibles par cellule : `UP`, `DOWN`, vide ou `No data`
- Nombre de colonnes illimité

## Structure du projet

```
.
├── index.html       # Application complète (auto-suffisante)
└── README.md
```
