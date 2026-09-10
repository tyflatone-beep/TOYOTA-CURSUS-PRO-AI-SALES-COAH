# Changelog — du brief PPTX au prompt système livré

Ce document liste les écarts entre le brief d'origine (`Instruction Prompt TFR Cursus PRO.pptx`) et les fichiers livrés, pour que vous puissiez valider rapidement chaque choix.

## Réorganisation (pas de changement de contenu)

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
