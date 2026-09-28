# 🐧 Penguins Dashboard — Quarto + Shiny

Tableau de bord interactif en **R** pour explorer le jeu de données **Palmer Penguins**, construit avec le format **Quarto Dashboard** et un serveur **Shiny**. Le dépôt contient aussi un rapport d'analyse exploratoire au format HTML.

> Projet réalisé dans le cadre du module **R Approfondi**.

---

## Le tableau de bord

`Dashboard_Penguins.qmd` est organisé en trois onglets.

### 1. Statistiques descriptives et distribution des espèces par île

- Aperçu des données
- **Statistiques par espèce** (min, max, moyenne, variance, écart-type, médiane) pour la variable choisie dans la barre latérale
- Effectifs par **espèce et par île** (tableau + graphique en barres)

### 2. Analyse morphologique

- **Nuage de points** : variables X et Y au choix, colorées par espèce
- **Boîte à moustaches** de la longueur du bec par espèce
- **Densité** de la variable choisie
- Répartition des **sexes** par espèce

### 3. Régression

- Relation **longueur de la nageoire → masse corporelle** avec droite de régression linéaire

Tous les graphiques sont construits avec ggplot2 et rendus interactifs avec **plotly**.

---

## Le rapport d'analyse

`Projet2 R Approfondi.qmd` produit un rapport HTML qui répond aux questions du projet :

1. Nombre de valeurs manquantes par variable
2. Nombre de lignes contenant au moins une valeur manquante
3. Suppression des lignes incomplètes
4. Statistiques univariées commentées
5. Graphiques : longueur vs profondeur du bec, bec vs nageoire, longueur du bec par espèce

---

## Données

`penguins.csv` — **344 manchots** observés sur trois îles de l'archipel Palmer (Antarctique) entre 2007 et 2009. Il en reste **333** après suppression des lignes incomplètes.

| Variable | Description |
|---|---|
| `species` | Espèce : Adelie, Chinstrap, Gentoo |
| `island` | Île : Biscoe, Dream, Torgersen |
| `bill_length_mm` | Longueur du bec (mm) |
| `bill_depth_mm` | Profondeur du bec (mm) |
| `flipper_length_mm` | Longueur de la nageoire (mm) |
| `body_mass_g` | Masse corporelle (g) |
| `sex` | Sexe |
| `year` | Année d'observation |

*Source : Horst, Hill & Gorman (2020), package R [`palmerpenguins`](https://allisonhorst.github.io/palmerpenguins/).*

---

## Installation

### Prérequis

- R ≥ 4.1
- [Quarto](https://quarto.org/docs/get-started/) ≥ 1.4 (nécessaire pour le format `dashboard`)
- RStudio (recommandé)

### Packages

```r
install.packages(c("tidyverse", "plotly", "shiny", "knitr", "rmarkdown"))
```

---

## Lancement

### Tableau de bord interactif

Le dashboard utilise `server: shiny` : il doit être **exécuté**, pas seulement rendu en HTML statique.

```bash
cd "Kounga_ryan_yvan _R_Approfondi"
quarto serve Dashboard_Penguins.qmd
```

Ou dans RStudio : ouvrir `Dashboard_Penguins.qmd` et cliquer sur **Run Document**.

### Rapport d'analyse

```bash
quarto render "Projet2 R Approfondi.qmd"
```

---

## Structure

```
Dashbord_penguins_R-main/
└── Kounga_ryan_yvan _R_Approfondi/
    ├── Dashboard_Penguins.qmd        # Tableau de bord Quarto + Shiny
    ├── Projet2 R Approfondi.qmd      # Rapport d'analyse exploratoire
    ├── penguins.csv                  # Données
    ├── _quarto.yml                   # Configuration du projet Quarto
    ├── Projet2 R Approfondi.Rproj    # Projet RStudio
    ├── Dashboard_Penguins.html       # Rendu du dashboard
    └── Dashboard_Penguins_files/     # Dépendances du rendu HTML
```

> 💡 Les dossiers `.Rproj.user/` et `.quarto/` sont des fichiers de travail générés automatiquement par RStudio et Quarto. Ils peuvent être retirés du dépôt et ajoutés au `.gitignore`.

---

## Technologies

R · Quarto Dashboard · Shiny · ggplot2 · plotly · dplyr · tidyverse

## Auteur

**Ryan Kounga** — [@KoungaRyan](https://github.com/KoungaRyan)
