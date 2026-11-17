---
license: cc-by-4.0
language:
- fr
pretty_name: "Friperies et boutiques solidaires vérifiées"
size_categories:
- n<1K
tags:
- friperie
- seconde-main
- economie-sociale-et-solidaire
- france
- open-data
configs:
- config_name: adresses
  data_files: friperies-boutiques-solidaires-verifiees.csv
  default: true
---

# Friperies et boutiques solidaires vérifiées

Producteur : **Bee Wholesale** (bee-wholesale.com), grossiste français de vêtements de marque seconde main établi à Nantes.
Version 2026.11, publiée le 17 novembre 2026. Licence : [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.fr).

## Description

Adresses de friperies, boutiques solidaires, Emmaüs, dépôts-ventes et friperies au kilo citées dans les guides de lieux publiés par Bee Wholesale, une ligne par adresse : nom, type, adresse, code postal, ville, date de vérification et lien vers le guide. Ni avis, ni note, ni donnée personnelle. Le jeu s'enrichit à chaque guide publié.

Version 2026.11 : 53 adresses de 32 enseignes, tirées des 3 guides publiés au 17 novembre 2026 (Nantes, Lyon, Paris). Les guides programmés ou en brouillon ne sont jamais repris.

## Fichiers

| Fichier | Contenu | Lignes |
|---|---|---|
| `friperies-boutiques-solidaires-verifiees.csv` / `.json` | Une ligne par adresse | 53 |
| `datapackage.json` | Description Frictionless (schéma) | |
| `CITATION.cff` | Référence à citer | |

CSV en UTF-8, séparateur virgule, dates au format AAAA-MM-JJ, valeur absente = cellule vide.

## Méthode

- Une adresse n'entre dans un guide que si elle est confirmée par une source récente : collectivité (Nantes Métropole, Ville de Paris), office de tourisme, site de la boutique, presse locale ou plusieurs annuaires à jour. Les sources sont citées en bas de chaque guide.
- `date_verification` reprend la mention « Dernière vérification des adresses » du guide.
- Une enseigne à plusieurs boutiques donne une ligne par adresse écrite dans le guide. Les boutiques citées sans numéro de voie ne sont pas reprises.
- `type` suit le guide : Emmaüs (enseigne Emmaüs), dépôt-vente, boutique solidaire (association, insertion, réseau solidaire), au kilo (prix au poids), friperie (autres boutiques de seconde main, y compris une recyclerie spécialisée). `type_secondaire` est rempli quand le guide indique deux formats.
- `code_postal` : repris du balisage schema.org (PostalAddress) du guide, ou de l'arrondissement écrit dans le guide (Paris, Lyon). Laissé vide quand le guide ne le donne pas (6 adresses dans cette version).
- Ni horaires, ni prix, ni avis, ni note, ni donnée personnelle. Les horaires changent souvent : vérifiez-les auprès de la boutique.

## Champs

| Champ | Type | Description |
|---|---|---|
| `id` | string | Identifiant stable de l'adresse |
| `nom` | string | Nom de l'enseigne tel qu'écrit dans le guide |
| `type` | string | Type principal |
| `type_secondaire` | string | Second type quand le guide en indique deux (ex. boutique solidaire qui vend au kilo) |
| `adresse` | string | Numéro et voie |
| `complement_adresse` | string | Repère ou complément écrit dans le guide |
| `code_postal` | string | Code postal du balisage schema.org du guide ou de l'arrondissement écrit dans le guide ; vide sinon |
| `ville` | string |  |
| `pays` | string | Code pays ISO 3166-1 alpha-2 |
| `date_verification` | date | Dernière vérification de l'adresse indiquée dans le guide |
| `url_guide` | string | Guide publié qui cite l'adresse |
| `guide_publie_le` | date | Date de publication du guide |

## Mise à jour

Fréquence prévue : **mensuelle**. Chaque guide de lieux publié depuis la version précédente ajoute ses adresses ; une adresse retirée d'un guide est retirée du jeu.

## Licence

[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.fr). Vous pouvez copier, redistribuer, modifier et utiliser ces données, y compris à des fins commerciales, à condition de créditer : **Bee Wholesale (bee-wholesale.com)**, avec un lien vers la source.

## Comment citer

> Bee Wholesale (bee-wholesale.com), « Friperies et boutiques solidaires vérifiées », version 2026.11, adresses vérifiées le 15 novembre 2026, licence CC BY 4.0, https://bee-wholesale.com/blogs/guides/friperies-france

Contact : bonjour@bee-wholesale.com

---

## Summary (English)

**Verified thrift shops and charity shops in France.** Addresses of thrift shops, charity and social-economy shops, Emmaüs stores, consignment stores and pay-by-weight thrift shops listed in the place guides published by Bee Wholesale, one row per address: name, type, street address, postcode, city, verification date and link to the guide. No reviews, no ratings, no personal data. Version 2026.11: 53 addresses in Nantes, Lyon and Paris; the dataset grows with each published guide. Planned update frequency: monthly. Licence: CC BY 4.0; please credit "Bee Wholesale (bee-wholesale.com)". Column names and labels are in French.
