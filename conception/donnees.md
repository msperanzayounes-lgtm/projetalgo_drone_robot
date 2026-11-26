# Données de la simulation

Toutes les données sont regroupées dans une variable `sim` de type `Simulation`, déclarée dans le `main` (pas de variable globale) et transmise **par adresse** aux sous-programmes qui la modifient.

## Constantes symboliques

| Constante | Valeur | Rôle |
|---|---|---|
| `LIGNES`, `COLONNES` | 15, 30 | dimensions de la grille |
| `LIBRE`, `OBSTACLE`, `CENTRE` | 0, 1, 2 | types de case |
| `CAPACITE_ROBOT` | 3 | nombre maximal de déchets transportés par le robot |
| `DELAI_APPARITION` | 20 | un déchet apparaît tous les 20 tours de boucle |
| `DUREE_TOUR` | 100 | pause entre deux tours (ms) |
| `CMD_AUCUNE` … `CMD_QUITTER` | 0 … 9 | codes des commandes clavier |

## Principales données

| Donnée | Type | Rôle |
|---|---|---|
| **Une case (`Case`)** | | |
| `type` | `int` | `LIBRE`, `OBSTACLE` ou `CENTRE` |
| `dechet` | `int` | 1 si un déchet est présent, 0 sinon (extension 2 : 0 aucun, 1 plastique, 2 verre, 3 métal) |
| `detecte` | `int` (booléen) | 1 si le déchet a été détecté par le drone |
| **Une position (`Position`)** | | |
| `lig`, `col` | `int` | ligne et colonne dans la grille |
| **La simulation (`Simulation`)** | | |
| `grille` | `Case[LIGNES][COLONNES]` | la réserve |
| `drone` | `Position` | position du drone |
| `robot.pos` | `Position` | position du robot |
| `robot.charge` | `int` | nombre de déchets transportés (0 à `CAPACITE_ROBOT`) |
| `tour` | `int` | compteur de tours de boucle |
| `nbApparus`, `nbDetectes`, `nbCollectes`, `nbDeposes` | `int` | statistiques |
| `enCours` | `int` (booléen) | 1 tant que l'utilisateur n'a pas quitté |
| **Variables du `main`** | | |
| `sim` | `Simulation` | toutes les données |
| `commande` | `int` | commande issue de la touche appuyée |

## Traduction en C

```c
typedef struct {
    int type;          /* LIBRE, OBSTACLE ou CENTRE */
    int dechet;        /* 1 si un dechet est present, 0 sinon */
    int detecte;       /* 1 si le dechet a ete detecte par le drone */
} Case;

typedef struct {
    int lig;
    int col;
} Position;

typedef struct {
    Position pos;
    int charge;        /* nombre de dechets transportes */
} Robot;

typedef struct {
    Case grille[LIGNES][COLONNES];
    Position drone;
    Robot robot;
    int tour, nbApparus, nbDetectes, nbCollectes, nbDeposes;
    int enCours;       /* 1 tant que la simulation continue */
} Simulation;
```
