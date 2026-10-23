🥊 FightFlow Suite
Laboratoire d'entraînement de mémoire musculaire, timing et télémétrie pour jeux de combat (FGC) — accessible directement dans le navigateur, sans avoir à lancer le jeu.

________________________________________
🎯 Pourquoi FightFlow ?
S'entraîner aux jeux de combat demande de la répétition pure : calibrer un just-frame, nettoyer un quart de cercle sans diagonales parasites ou travailler un réflexe de hit-confirm. Lancer un jeu lourd (30 à 80 Go) n'est pas toujours possible ou optimal pour une session rapide de 15 minutes.

FightFlow est une suite d'outils web légers et autonomes conçue pour :

1.	Entraîner la mémoire musculaire sur vos périphériques réels (Stick arcade, Hitbox / Leverless, manette, clavier).
2.	Diagnostiquer vos erreurs : détection des inputs parasites (dirty inputs), calcul du jitter en frames (60 FPS) et vérification du nettoyage SOCD.
3.	Conditionner vos réflexes : modes cognitifs intégrés (Hit-Confirm aléatoire, mode Blind, défi Streak).

________________________________________
📦 Les Composants de la Suite
1. /lab — FightFlow Lab
Le banc d'essai d'exécution temps réel :

-	Visualiseur multi-contrôleurs : Stick Sanwa orientable, Leverless (Hitbox), Gamepad standard et Pad 6 boutons style Hori Fighting Commander.
-	Support matériel : Gamepad API (sticks USB/Bluetooth) et Clavier hybride (e.code + e.key sans conflit AZERTY / QWERTY).
-	Moteur SOCD configurable : Neutre CPT, Priorité Haut, Last-Input et Brut.
-	Audio synthétisé Web Audio : Clics de boutons arcade et bips métronome synchronisables de 60 à 180 BPM.
-	Télémétrie d'exécution : Ratio de complétion, historique de frames et analyseur d'écarts de timing.
2. /studio — FightFlow Data Studio
Le pipeline d'ingestion et de formatage :

-	Moteur Regex FGC : Traduction automatique de la notation Tekken (f, n, d, df+2) et 2D universelle (236P > 623HP) vers le format d'inputs atomiques.
-	Connecteur API & Tables : Intégration de structures type TekkenDocs et support de copier-coller CSV / Google Sheets.
-	Pipeline d'exportation : Fichiers .json prêts à l'emploi et liens partageables avec combo encodé dans l'URL.

________________________________________
🎮 Configuration des Touches (Layout Clavier par Défaut)
Action	Clavier (AZERTY / QWERTY)	Périphérique Dédié
Gauche	Q ou A / Flèche Gauche	D-Pad Gauche / Stick 4
Bas	S / Flèche Bas	D-Pad Bas / Stick 2
Droite	D / Flèche Droite	D-Pad Droite / Stick 6
Saut (Haut)	Espace / Z / W / Flèche Haut	Hitbox Thumb / Stick 8
Bouton 1 / LP	U ou NumPad 4	Carré / X / Bouton 1
Bouton 2 / RP	I ou NumPad 5	Triangle / Y / Bouton 2
Bouton 3 / LK	J ou NumPad 1	Croix / A / Bouton 3
Bouton 4 / RK	K ou NumPad 2	Rond / B / Bouton 4
Inversion P1 ⇄ P2	Tab	Toggle Miroir

________________________________________
📄 Format de Données JSON (Schéma Spécification)
[

  {

    "id": "tekken_ewgf",

    "title": "Kazuya - Electric Wind God Fist",

    "char": "Kazuya Mishima",

    "diff": "justframe",

    "timingMs": 140,

    "inputs": [

      { "dir": "6", "btn": "", "label": "f" },

      { "dir": "5", "btn": "", "label": "n" },

      { "dir": "2", "btn": "", "label": "d" },

      { "dir": "3", "btn": "RP", "label": "df+2" }

    ]

  }

]
