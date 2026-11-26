# EcoBots – Protection d'une réserve naturelle

Projet Informatique 1 – ECE ING1 – Semestre 1, 2026-2027

Simulation en C (mode console) d'un **drone** qui détecte les déchets dans une réserve naturelle et d'un **robot** qui les ramasse puis les rapporte à un centre de collecte. Les deux engins sont pilotés au clavier.

## Équipe et répartition des tâches

| Membre | Rôle | Fichiers |
|---|---|---|
| Matteo Speranza | Coordination, programme principal, intégration, dépôt GitHub | `main.c` |
| *[Nom 2]* | Module affichage (IHM) : grille, couleurs, infos, lecture du clavier | `affichage.c`, `affichage.h` |
| *[Nom 3]* | Module simulation, partie 1 : réserve, déplacements, détection. Extension 1 : réserve aléatoire | `simulation.c`, `simulation.h` |
| *[Nom 4]* | Module simulation, partie 2 : déchets, collecte, dépôt, compteurs. Extension 2 : types de déchets et statistiques | `simulation.c`, `simulation.h` |

## Planning

| Période | Travail |
|---|---|
| Semaine du 23/11 | Conception : règles, données, logigrammes, prototypes. **Rendu mi-parcours le 29/11 à 20 h 30** |
| Semaine du 30/11 | Codage de la version de base, chacun son module, tests unitaires |
| Semaine du 07/12 | Intégration, tests d'ensemble, puis extensions |
| Jusqu'au 14/12 | Tests finaux, captures d'écran, compte rendu. **Rendu final le 14/12** |
| Janvier | Soutenances (semaines du 04/01 et du 11/01) |

## Contenu du dépôt

```
conception/
  EcoBots_rendu_mi-parcours.pdf   dossier de conception complet (rendu du 29/11)
  logigrammes.md                  tous les logigrammes, avec explications
  donnees.md                      tableaux des données et leurs types
  images/                         logigrammes et graphe d'appels en PNG
src/                              code source (à partir de la semaine du 30/11)
```

## Règles de travail avec Git

1. **Avant de commencer** : `git pull` pour récupérer le travail des autres.
2. **Après une tâche qui compile** :
   ```
   git add .
   git commit -m "ce que j'ai fait"
   git push
   ```
3. Chacun travaille surtout dans **ses propres fichiers**, pour éviter les conflits.
4. Les **prototypes** du dossier de conception sont un contrat entre nous : on ne les change qu'après en avoir parlé au groupe.
5. On ne pousse **jamais** de fichiers compilés (`.exe`, `.o`) : le `.gitignore` s'en charge.
