[CHANGELOG.md](https://github.com/user-attachments/files/32064262/CHANGELOG.md)
# Changelog — du brief PPTX au prompt système livré

Ce document liste les écarts entre le brief d'origine (`Instruction Prompt TFR Cursus PRO.pptx`) et les fichiers livrés, pour que vous puissiez valider rapidement chaque choix.

## Réorganisation (pas de changement de contenu)# Changelog — du brief PPTX au prompt système livré

Ce document liste les écarts entre le brief d'origine (`Instruction Prompt TFR Cursus PRO.pptx`) et les fichiers livrés, pour que vous puissiez valider rapidement chaque choix.

## Réorganisation (pas de changement de contenu)

- Le texte, initialement réparti sur des diapositives PowerPoint avec des séparateurs `===`, a été réorganisé en Markdown structuré (titres, tableaux) pour être directement exploitable comme prompt système et fichiers de base de connaissances, sur le modèle utilisé pour Nissan AI Sales Coach.
- Les grilles de scoring et la liste des 37 questions BEV PRO ont été sorties du corps du prompt système vers des fichiers dédiés (base de connaissances), conformément à la consigne du brief lui-même ("les documents joints ... sont des fiches d'information passives").
- Les 3 modules ont été renommés de façon homogène : **Module 1 — Écosystème BEV PRO**, **Module 2 — Offre Grand Volume**, **Module 3 — Confrontation au réel : Offre Benne**.

## Corrections de forme (typos du brief d'origine)

- « écosytème » → « écosystème »
- « remoque » → « remorque »
- « réhaussés » → « rehaussés »
- « Tole HLE » → « Tôle HLE »
- Les deux messages d'accueil (identification + consigne RGPD/choix du module) ont été conservés **strictement à l'identique** sur le fond, seule la coquille « écosytème » a été corrigée.

## Compléments apportés (zones incomplètes du brief) — à valider

| Sujet | Ce que disait le brief | Complément apporté | Statut |
|---|---|---|---|
| Module BEV PRO | Score annoncé "X sur 37 bonnes questions", mais 38 formulations listées | Fusion des deux dernières questions ("Quand envisage-t-il de prendre une décision" + "Quelle périodicité de contact") en un seul item n°37 | À valider |
| Module Grand Volume | Barème par compétence donné, mais pas de total de référence pour un pourcentage (contrairement aux 2 autres modules) | Score affiché en points cumulés, max théorique 29 (+ bonus), plutôt qu'en pourcentage | À valider |
| Module Benne | Score annoncé "X sur 10 bonnes questions", mais seule une liste de 10 caractéristiques techniques de la benne KEROCK était fournie | Réinterprété comme "10 bons arguments techniques apportés" plutôt que "10 questions posées" | ✅ Validé le 10/09/2026 — voir ci-dessous |
| Personas | Le brief évoque des documents "PERSONAS..." déjà existants (par analogie avec Nissan), non fournis avec ce fichier | Fiches personas reconstituées à partir des seuls éléments présents dans le brief (`PERSONAS.md`) | ✅ Confirmé suffisant en l'état par Régis le 10/09/2026 |
| Rapport intermédiaire / final | Le contenu attendu était listé (identité, module, score, compétences validées/à renforcer, recommandations ; puis synthèse 3 modules + tableau + 3 axes) sans gabarit de présentation | Gabarits texte structurés proposés dans `SYSTEM_PROMPT.md` §6, réutilisant exactement les champs listés dans le brief | Libre à ajuster à la charte du builder utilisé |

## Ajout — section technique nouvelle

- Ajout d'une section « Comment l'intégrer » dans `README.md` couvrant : où coller le prompt système, comment joindre la base de connaissances, comment gérer la persistance du score/module/persona selon que l'API cible garde ou non l'état de la conversation, et la liste des commandes de contrôle à exposer côté interface.

## Mise à jour du 10/09/2026 — validation du module Benne

- Vous avez fourni la fiche technique officielle Gruau *Benne arrière KEROCK, TOYOTA PROACE MAX* (BTP Environnement, juin 2026).
- Les 10 arguments techniques de `SCORING_BENNE.md` correspondent mot pour mot à ce document : la note « à valider côté métier » est levée.
- `SCORING_BENNE.md` a été enrichi avec :
  - les précisions techniques exactes (tôle Z140, épaisseurs de peinture époxy/polyuréthane, référence d'ouverture H350, référence d'option SE16) ;
  - une section « Argumentaire complémentaire » (structure 4T, porte-échelle, poteaux type pied de rancher, personnalisation RAL 9003, options courantes) — non comptabilisée dans le score /10, pour rester fidèle à la règle de scoring déjà validée, mais utile pour enrichir le réalisme des échanges ;
  - un tableau des données véhicule (empattement, longueur utile, masse de transformation par version L2/L3) pour que le persona René Toullan reste cohérent si le conseiller pose des questions précises de gabarit.

## Mise à jour du 10/09/2026 — organisation à plat sur GitHub

- Lors de l'upload web sur GitHub, les 4 fichiers de base de connaissances (`SCORING_BEV_PRO.md`, `SCORING_GRAND_VOLUME.md`, `SCORING_BENNE.md`, `PERSONAS.md`) se sont retrouvés à la racine du dépôt plutôt que dans un sous-dossier `knowledge-base/`.
- Décision : garder cette organisation à plat plutôt que de la corriger sur GitHub — cela ne change rien au fonctionnement (le prompt système référence chaque fichier par son nom, pas par un chemin de dossier). `README.md` et `SYSTEM_PROMPT.md` ont été mis à jour pour refléter cette structure réelle.


- Le texte, initialement réparti sur des diapositives PowerPoint avec des séparateurs `===`, a été réorganisé en Markdown structuré (titres, tableaux) pour être directement exploitable comme prompt système et fichiers de base de connaissances, sur le modèle utilisé pour Nissan AI Sales Coach.
- Les grilles de scoring et la liste des 37 questions BEV PRO ont été sorties du corps du prompt système vers des fichiers `knowledge-base/` dédiés, conformément à la consigne du brief lui-même ("les documents joints ... sont des fiches d'information passives").
- Les 3 modules ont été renommés de façon homogène : **Module 1 — Écosystème BEV PRO**, **Module 2 — Offre Grand Volume**, **Module 3 — Confrontation au réel : Offre Benne**.

## Corrections de forme (typos du brief d'origine)

- « écosytème » → « écosystème »
- « remoque » → « remorque »
- « réhaussés » → « rehaussés »
- « Tole HLE » → « Tôle HLE »
- Les deux messages d'accueil (identification + consigne RGPD/choix du module) ont été conservés **strictement à l'identique** sur le fond, seule la coquille « écosytème » a été corrigée.

## Compléments apportés (zones incomplètes du brief) — à valider

| Sujet | Ce que disait le brief | Complément apporté | Statut |
|---|---|---|---|
| Module BEV PRO | Score annoncé "X sur 37 bonnes questions", mais 38 formulations listées | Fusion des deux dernières questions ("Quand envisage-t-il de prendre une décision" + "Quelle périodicité de contact") en un seul item n°37 | À valider |
| Module Grand Volume | Barème par compétence donné, mais pas de total de référence pour un pourcentage (contrairement aux 2 autres modules) | Score affiché en points cumulés, max théorique 29 (+ bonus), plutôt qu'en pourcentage | À valider |
| Module Benne | Score annoncé "X sur 10 bonnes questions", mais seule une liste de 10 caractéristiques techniques de la benne KEROCK était fournie | Réinterprété comme "10 bons arguments techniques apportés" plutôt que "10 questions posées" | À valider — remplacer si une vraie liste de 10 questions de découverte existe déjà |
| Personas | Le brief évoque des documents "PERSONAS..." déjà existants (par analogie avec Nissan), non fournis avec ce fichier | Fiches personas reconstituées à partir des seuls éléments présents dans le brief (`knowledge-base/PERSONAS.md`) | À valider — remplacer si les fiches d'origine existent |
| Rapport intermédiaire / final | Le contenu attendu était listé (identité, module, score, compétences validées/à renforcer, recommandations ; puis synthèse 3 modules + tableau + 3 axes) sans gabarit de présentation | Gabarits texte structurés proposés dans `SYSTEM_PROMPT.md` §6, réutilisant exactement les champs listés dans le brief | Libre à ajuster à la charte du builder utilisé |

## Ajout — section technique nouvelle

- Ajout d'une section « Comment l'intégrer » dans `README.md` couvrant : où coller le prompt système, comment joindre la base de connaissances, comment gérer la persistance du score/module/persona selon que l'API cible garde ou non l'état de la conversation, et la liste des commandes de contrôle à exposer côté interface.
