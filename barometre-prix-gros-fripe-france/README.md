---
license: cc-by-4.0
language:
- fr
pretty_name: "Baromètre des prix de gros de la fripe en France"
size_categories:
- n<1K
tags:
- fripe
- seconde-main
- prix
- france
- open-data
configs:
- config_name: offres
  data_files: barometre-prix-gros-fripe-france-offres.csv
  default: true
- config_name: synthese
  data_files: barometre-prix-gros-fripe-france-synthese.csv
- config_name: sources
  data_files: barometre-prix-gros-fripe-france-sources.csv
---

# Baromètre des prix de gros de la fripe en France

Producteur : **Bee Wholesale** (bee-wholesale.com), grossiste français de vêtements de marque seconde main.
Version 2026.11, publiée le 17 novembre 2026. Licence : [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.fr).

## Description

Prix publics de 16 grossistes de vêtements de seconde main établis en France ou dans l'Union européenne et livrant la France, relevés le 16 octobre 2026 : 54 prix ramenés au kilo ou à la pièce, médianes et fourchettes par format (lots triés au kilo, ballots de 25 à 50 kg, box et lots de marque, lots à la pièce, déstockage, vintage et premium). Données reprises du baromètre publié sur bee-wholesale.com.

Les chiffres sont ceux de la page [Baromètre des prix de la fripe en gros](https://bee-wholesale.com/pages/barometre-prix-fripe-en-gros), relevé du 16 octobre 2026. Chaque ligne indique sa date de relevé et sa source.

## Fichiers

| Fichier | Contenu | Lignes |
|---|---|---|
| `barometre-prix-gros-fripe-france-offres.csv` / `.json` | Une ligne par prix retenu | 54 |
| `barometre-prix-gros-fripe-france-synthese.csv` / `.json` | Médiane, fourchette et nombre d'offres par catégorie | 8 |
| `barometre-prix-gros-fripe-france-sources.csv` / `.json` | Vendeurs retenus, pays, nombre de prix | 16 |
| `datapackage.json` | Description Frictionless (schéma de chaque table) | |
| `CITATION.cff` | Référence à citer | |

CSV en UTF-8, séparateur virgule, point décimal, dates au format AAAA-MM-JJ, booléens `true`/`false`, valeur absente = cellule vide.

## Méthode

- **Date du relevé :** 16 octobre 2026. Prix publics affichés, promotions comprises, frais de port exclus.
- **Périmètre :** 99 sites visibles sur 21 requêtes Google France liées à l'achat de vêtements en gros (données Semrush, base France), dont 38 grossistes de seconde main ou de vintage.
- **Inclusion :** vendeur de seconde main établi en France ou dans l'UE, livrant la France, affichant au moins un prix associé à un poids ou à un nombre de pièces : 16 vendeurs, 54 prix.
- **Exclusions :** 19 vendeurs de seconde main écartés (7 hors UE, 3 sans livraison France confirmée, 8 sans prix publics, 1 dépôt-vente), ainsi que les sites de neuf, plateformes et outils. 35 mentions de prix ambiguës écartées, dont 26 sans poids ou nombre de pièces explicite. 3 remises et 3 paliers du même produit ne sont pas comptés.
- **Calcul :** prix affiché divisé par le poids ou le nombre de pièces affichés, sans conversion ni estimation. Pour une fourchette sur un format identifié, les deux bornes sont retenues. Médiane calculée à partir de 3 offres.
- Le vendeur de chaque offre n'est pas publié ; la table `sources` liste les 16 vendeurs retenus. Les prix de Bee Wholesale ne font pas partie du relevé.
- Grade : « n.c. » = non communiqué par le vendeur. Un seul prix est explicitement affiché hors taxes (`prix_affiche_ht = true`).

## Champs

### offres
| Champ | Type | Description |
|---|---|---|
| `id` | string | Identifiant stable de la ligne |
| `date_releve` | date | Date du relevé des prix publics (AAAA-MM-JJ) |
| `categorie` | string | Catégorie de format (lots triés au kilo, ballots de 25 à 50 kg, box de marque, lots à la pièce, déstockage, vintage et premium) |
| `offre` | string | Libellé de l'offre relevée, tel que publié dans le baromètre (vendeur non publié) |
| `grade_annonce` | string | Grade annoncé par le vendeur, tel que publié (n.c. = non communiqué ; vide = non indiqué dans le baromètre) |
| `prix_ramene` | number | Prix affiché divisé par le poids ou le nombre de pièces affichés, en euros |
| `unite` | string | EUR/kg ou EUR/piece |
| `valeur_approchee` | boolean | true si la valeur est publiée comme approchée (≈) |
| `prix_affiche_ht` | boolean | true si le vendeur affiche explicitement un prix hors taxes |
| `source` | string | Publication d'origine de la valeur (titre et date du relevé) |
| `source_url` | string | Page de bee-wholesale.com où la valeur est publiée |

### synthese
| Champ | Type | Description |
|---|---|---|
| `id` | string |  |
| `date_releve` | date |  |
| `categorie` | string | Catégorie ou sous-ensemble de catégorie |
| `perimetre` | string |  |
| `n_offres` | integer | Nombre de prix retenus |
| `n_vendeurs` | integer | Nombre de vendeurs (vide si non publié) |
| `mediane` | number | Médiane publiée, calculée à partir de 3 offres (vide si n < 3) |
| `minimum` | number |  |
| `maximum` | number |  |
| `unite` | string |  |
| `valeur_approchee` | boolean |  |
| `source` | string | Publication d'origine de la valeur (titre et date du relevé) |
| `source_url` | string | Page de bee-wholesale.com où la valeur est publiée |

### sources
| Champ | Type | Description |
|---|---|---|
| `site` | string | Domaine du vendeur retenu |
| `pays` | string | Pays d'établissement du vendeur |
| `prix_retenus` | integer | Nombre de prix retenus chez ce vendeur |
| `date_releve` | date |  |
| `source` | string | Publication d'origine de la valeur (titre et date du relevé) |
| `source_url` | string | Page de bee-wholesale.com où la valeur est publiée |

## Mise à jour

Fréquence prévue : **mensuelle**. Chaque nouveau relevé publié sur bee-wholesale.com est ajouté avec sa propre date (`date_releve`) ; les lignes existantes ne sont pas modifiées.

## Licence

[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.fr). Vous pouvez copier, redistribuer, modifier et utiliser ces données, y compris à des fins commerciales, à condition de créditer : **Bee Wholesale (bee-wholesale.com)**, avec un lien vers la source.

## Comment citer

> Bee Wholesale (bee-wholesale.com), « Baromètre des prix de gros de la fripe en France », version 2026.11, relevé du 16 octobre 2026, licence CC BY 4.0, https://bee-wholesale.com/pages/barometre-prix-fripe-en-gros

Le fichier `CITATION.cff` donne la même référence dans un format lisible par GitHub, Zenodo et les gestionnaires de références.

DOI (Zenodo) : [10.5281/zenodo.24310054](https://doi.org/10.5281/zenodo.24310054). Dépôt GitHub : [Bee-Wholesale/donnees-ouvertes](https://github.com/Bee-Wholesale/donnees-ouvertes).

Contact : bonjour@bee-wholesale.com

---

## Summary (English)

**Wholesale second-hand clothing price barometer, France.** Public prices of 16 second-hand clothing wholesalers based in France or the EU and shipping to France, collected on 16 October 2026: 54 prices normalised per kilogram or per piece, with medians and ranges by format (sorted lots by the kilo, 25 to 50 kg bales, branded boxes and lots, lots by the piece, clearance, vintage and premium). Source: the barometer page published on bee-wholesale.com. Planned update frequency: monthly. Licence: CC BY 4.0; please credit "Bee Wholesale (bee-wholesale.com)". Column names and labels are in French.
