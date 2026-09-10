# TOYOTA AI Sales Coach — TFR Cursus PRO

Instructions prêtes à intégrer dans une nouvelle API, sur le même principe que ce qui a été fait pour **Nissan AI Sales Coach** : un prompt système central + une base de connaissances séparée en fichiers dédiés, à pousser sur GitHub puis à référencer depuis l'API/le builder.

## Structure du dépôt

```
TFR_Cursus_PRO_AI_Sales_Coach/
├── README.md                          → ce fichier
├── SYSTEM_PROMPT.md                   → prompt système à coller tel quel dans le champ "instructions"/"system" de l'API
├── CHANGELOG.md                       → ce qui a été corrigé/complété par rapport au brief d'origine (PPTX)
└── knowledge-base/
    ├── SCORING_BEV_PRO.md             → grille des 37 questions de référence (Module 1)
    ├── SCORING_GRAND_VOLUME.md        → barème de points + gestion des objections (Module 2)
    ├── SCORING_BENNE.md               → 10 arguments techniques de référence (Module 3)
    └── PERSONAS.md                    → fiches personas des 3 modules
```

## Comment l'intégrer

1. **Prompt système :** copier l'intégralité de `SYSTEM_PROMPT.md` dans le champ d'instructions système de l'API/du builder utilisé (GPT personnalisé, Assistants API, Voiceflow, Dust, agent maison, etc.).
2. **Base de connaissances :** joindre les 4 fichiers du dossier `knowledge-base/` en pièces jointes / fichiers de contexte, exactement comme les fichiers `SCORING...` et `PERSONAS...` mentionnés dans le brief d'origine.
3. **Gestion d'état (`état ÉVALUATION`) :** le prompt suppose que l'assistant garde en mémoire, sur toute la session, l'identité du conseiller, le module en cours, le persona actif et le score courant. Deux options selon la plateforme cible :
   - Si l'API/le builder gère nativement une conversation longue avec mémoire de session (cas général des Assistants/GPT personnalisés), aucun développement supplémentaire n'est nécessaire : l'assistant tient le score "en interne" au fil de la conversation.
   - Si l'intégration est faite via un appel API sans état (ex. appel Chat Completions à chaque tour sans persistance), il faut faire porter l'état par le backend : renvoyer à chaque appel un résumé structuré (JSON) du score courant, du module et du persona dans le contexte, pour que l'assistant reste cohérent d'un tour à l'autre.
4. **Commandes de contrôle** à faire remonter telles quelles côté interface (bouton ou saisie libre) : `Démarrer la formation`, `terminer`, `TERMINER MISSION`, `Mon bilan de journée`.

## Points à valider côté métier avant mise en production

Le brief d'origine (PPTX) contenait quelques zones à compléter pour rester cohérent d'un module à l'autre. Les choix retenus sont documentés en détail dans chaque fichier concerné et résumés dans `CHANGELOG.md` :

- **Module BEV PRO :** la liste comptait 38 formulations de questions pour un score annoncé sur 37 — deux ont été fusionnées en une seule question double.
- **Module Grand Volume :** aucun total de référence n'était donné pour exprimer un pourcentage (contrairement aux 2 autres modules) → score affiché en points cumulés (max théorique 29 + bonus).
- **Module Benne :** le score annoncé ("X sur 10 bonnes questions") ne correspondait à aucune liste de 10 questions fournie, mais correspondait exactement aux 10 caractéristiques techniques attendues de la benne KEROCK → réinterprété comme "10 bons arguments techniques apportés".
- **Personas :** les documents "PERSONAS..." évoqués dans le brief (par analogie avec Nissan) n'ont pas été fournis avec le fichier TFR Cursus PRO — les fiches de `PERSONAS.md` ont été reconstituées à partir des seuls éléments du brief et doivent être remplacées si des fiches plus complètes existent déjà.

Merci de confirmer ces points (ou de fournir les documents manquants) avant intégration finale et mise en ligne.
