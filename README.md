# Métiers+ — port WotLK 3.3.5a

Une fenêtre de métiers améliorée pour **World of Warcraft 3.3.5a** (Wrath of the Lich King),
portée pour le serveur **Ebonhold**. Elle remplace la fenêtre de métiers par défaut par une
version bien plus complète : file d'attente de fabrication, liste de courses, recherche
avancée, catégories de recettes personnalisées, et suivi des réactifs dans les sacs, la
banque et les autres persos.

> *Métiers+* est le nom donné au portage pour Ebonhold. L'addon d'origine est
> **Advanced Trade Skill Window 2** — tout le mérite revient à ses auteurs (voir Crédits).
> Ce dépôt ne fait qu'adapter leur addon Vanilla (1.12) au client 3.3.5a.

---

## Français

### Fonctionnalités
- Remplace automatiquement la fenêtre de métiers Blizzard.
- File d'attente de fabrication + bouton « tout créer ».
- Recherche avancée (par réactif, niveau, qualité, faisabilité).
- Tri personnalisé avec éditeur de catégories.
- Suivi des réactifs : sacs, banque, autres personnages, marchands.
- L'enchantement passe par la fenêtre de métiers normale.

### Installation
- **Via le launcher Ebonhold** (recommandé) : Catalogue → installer « Métiers+ ».
- **Manuel** : télécharge le `.zip` de la dernière release, extrais le dossier
  `MetiersPlus` dans `World of Warcraft\Interface\AddOns`, puis `/reload` en jeu.

### Utilisation
Ouvre n'importe quel métier — la fenêtre remplace celle de Blizzard automatiquement.
Options en jeu : `/atsw config`.

### Compatibilité avec les autres addons
- Les SavedVariables gardent leurs noms d'origine (`ATSW_*`) et la fenêtre s'appelle toujours
  `ATSWFrame`, ce qui permet à AckisRecipeList de s'y accrocher.
- Depuis la v1.2, les fonctions de secours de l'ancienne API Craft (absente en 3.3.5a) sont
  locales à l'addon : Métiers+ ne déclare plus de fausses fonctions Blizzard globales qui
  pourraient tromper d'autres addons.

### Crédits
Addon d'origine **Advanced Trade Skill Window 2**, par :
- **Alexander Shelokhnev** (*Dreamios* / *Shellyoung*) — auteur de la réécriture ATSW2 (2022).
  Dépôt d'origine : <https://github.com/Shellyoung/AdvancedTradeSkillWindow2>
- **Rene Schneider** (*Slarti*) — auteur de l'Advanced Trade Skill Window original (2006).
- **laytya** — contributeur (2017).

Le projet d'origine vise WoW **Vanilla 1.12** et n'a **aucune licence** (tous droits réservés
à ses auteurs). Ce portage 3.3.5a est partagé pour la communauté Ebonhold par reconnaissance
de leur travail. Si un auteur d'origine préfère qu'il ne soit pas hébergé ici, qu'il ouvre une
issue et il sera retiré.

---

## English

A WotLK **3.3.5a** port of **Advanced Trade Skill Window 2** for the Ebonhold server, here
named *Métiers+*. It replaces the default tradeskill window with a much better one: recipe
queue, shopping list, advanced search, custom recipe categories, and reagent tracking across
bags / bank / alts.

### Install
- **Ebonhold launcher** (recommended): Catalogue → install "Métiers+".
- **Manual**: download the latest release `.zip`, extract the `MetiersPlus`
  folder into `World of Warcraft\Interface\AddOns`, then `/reload` in game.

Open any profession — the window replaces the Blizzard one automatically. Options: `/atsw config`.

### Credits
All credit for the addon itself goes to the original authors — **Shellyoung** (ATSW2 rewrite),
**Rene Schneider** (original ATSW), **laytya**. Original repository:
<https://github.com/Shellyoung/AdvancedTradeSkillWindow2>. The upstream project targets Vanilla
1.12 and carries no license (all rights reserved). This 3.3.5a port is shared for the Ebonhold
community; if an original author objects, open an issue and it will be removed.

### What the port changes
Compatibility fixes only — no feature changes (events, Craft API, Lua 5.0 `arg`, Button
font/colour methods, `UIDropDownMenu` / `FauxScrollFrame` signatures, renamed globals,
protected-function tainting, etc.). The SavedVariables keep their original `ATSW_*` names and
the window is still `ATSWFrame` (AckisRecipeList hooks into it). Since v1.2 the fallback stubs
for the missing Craft API are local to the addon, so no fake Blizzard globals are declared.
