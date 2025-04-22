# vbg_bénin
# 📊 Analyse des Violences Basées sur le Genre au Bénin (2023–2025)

> Un projet data pour éclairer, sensibiliser et agir.

---

## 🧠 Contexte

Entre avril 2023 et avril 2025, **100 000 signalements** anonymisés de violences faites aux femmes ont été collectés via différents canaux numériques (WhatsApp, SMS, App, etc.).  
L'objectif de cette analyse est de **dégager des tendances clés** pour informer les **ONG**, les **institutions publiques** et les **acteurs du changement** au Bénin.

---

## 📂 Données

- **Source** : Données fictives mais réalistes, générées pour simuler un projet d’analyse terrain.
- **Période couverte** : Avril 2023 → Avril 2025  
- **Format** : CSV (`data/signalements_femmes_benin_clean.csv`)  
- **Colonnes principales** :
  - `type_violence` (Sexuelle, Économique, etc.)
  - `departement` (Zou, Littoral, etc.)
  - `lien_agresseur` (Conjoint, Inconnu, etc.)
  - `source_signalement`, `niveau_education`, `delai_signalement`...

---

## 📌 KPIs Clés

| Indicateur                            | Résultat        |
|--------------------------------------|-----------------|
| Nombre total de cas                  | 100 000         |
| Violence la plus fréquente           | Psychologique   |
| Département le plus touché           | Atlantique      |
| Âge moyen des victimes               | 36.5 ans        |
| Délai moyen de signalement           | 15 jours        |

---

## 📈 Aperçu Visuel

Quelques visualisations clés sont disponibles dans le notebook `notebooks/analyse_vbg_femmes_benin.ipynb`.

- Répartition des types de violence  
- Lieux d'incidents les plus fréquents  
- Profils des agresseurs  
- Évolution temporelle des signalements

*(Screenshots à venir)*

---

## 🗄️ Importer dans une base PostgreSQL

```sql
-- Créer la table
\i sql/create_table_signalements.sql;

-- Importer le fichier CSV (version PostgreSQL)
COPY signalements_vbg FROM '/chemin/vers/signalements_femmes_benin_clean.csv' 
DELIMITER ',' CSV HEADER;
