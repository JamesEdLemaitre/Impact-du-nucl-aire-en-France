
# ⚛️ Le nucléaire a-t-il un impact positif sur le bilan carbone de la France ?

Analyse des données de production électrique française (2012–2025) pour évaluer la contribution du nucléaire aux émissions de CO₂ du mix électrique, en analyse de cycle de vie (ACV).

## ❓ Question de recherche

> **Est-ce que le nucléaire a un impact positif, en termes d'impact carbone, en France ?**

Sous-questions :
1. Quelle part de la production électrique française vient du nucléaire ?
2. Quelle part des émissions de CO₂e du mix lui est attribuable ?
3. Quelles émissions supplémentaires si le nucléaire était remplacé par une autre filière (ici le solaire) ?

## 📊 Résultats

### 1. Émissions de CO₂e du mix par filière
![Émissions par filière](figures/co2_par_filiere.jpg)

Les émissions du mix passent de **35,7 MtCO₂e en 2012 à 13,6 MtCO₂e en 2025**. Le gaz et le charbon dominent chaque année. En 2017, ils représentent environ 9 % de la production mais **81 %** des émissions (gaz 49,9 %, charbon 31,1 %).

### 2. Part du nucléaire : production vs émissions
![Nucléaire : production vs émissions](figures/nucleaire_production_vs_co2.jpg)

Le nucléaire fournit **63 % à 77 %** de l'électricité selon l'année, pour une part d'émissions bien plus faible (environ 6 % à 16 %). Cette part augmente sur la période parce que les émissions des autres filières baissent, pas parce que celles du nucléaire augmentent.

### 3. Émissions supplémentaires si le nucléaire était remplacé
![Émissions évitées](figures/emissions_evitees.jpg)

À production égale, remplacer le nucléaire (6 g/kWh) par du solaire (55 g/kWh) ajouterait **14 à 20 MtCO₂e par an**. Ce scénario est volontairement simple : il ne tient compte ni de l'intermittence ni du stockage.

## 🧪 Méthode

1. Données éCO2mix consolidées (RTE), 2012–2025. L'année 2026 est exclue car incomplète.
2. Suppression des lignes de 15 minutes vides, puis puissance moyenne annuelle par filière (MW).
3. Énergie annuelle : `kWh = MW × 1000 × heures` (8760 h, ou 8784 h en année bissextile).
4. Émissions : `énergie (kWh) × facteur ACV (g/kWh) / 10⁶ = tCO₂e`.
5. Intensité du mix (g/kWh) comparée au taux de CO₂ publié par RTE.

Facteurs ACV utilisés (g CO₂e/kWh) : fioul 730, charbon 1058, gaz 418, nucléaire 6, éolien 13, solaire 55, hydraulique 6, bioénergies 36.

## ⚠️ Limites

- Les échanges commerciaux et le pompage ne sont pas pris en compte (production uniquement).
- Les facteurs ACV sont uniques par filière (le gaz et les bioénergies regroupent plusieurs technologies).
- L'ACV du nucléaire varie de 4 à 6 g/kWh selon les sources. On retient 6.
- Le scénario de remplacement est théorique.
- Les aspects hors carbone (déchets, coût, sûreté, ressources) ne sont pas traités.

## 🏁 Conclusion

Sur le seul critère du carbone, **le nucléaire a un impact positif** : il produit environ 70 % de l'électricité pour une part d'émissions bien inférieure. Il explique en grande partie le faible niveau du mix français. Cela ne dit rien de ses autres enjeux, non étudiés ici.

## 📚 Sources

- RTE, jeu de données **éCO2mix national (données consolidées)**, production d'énergie par filière en France.
- EDF, [Plaquette ACV du nucléaire (2022)](https://www.edf.fr/sites/groupe/files/2022-06/edfgroup_acv-4_plaquette_20220616.pdf) : ACV du nucléaire de 4 à 6 g/kWh.
- Ministère de la Transition écologique, [Données et calcul pour l'actualisation du facteur d'émission de l'électricité (RE2020)](https://rt-re-batiment.developpement-durable.gouv.fr/IMG/pdf/donnees_et_calcul_pour_l_actualisation_du_fe_de_l_electricite.pdf) : facteurs ACV par filière.