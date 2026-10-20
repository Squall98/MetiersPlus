# Changelog

## v1.2 — 2026-10-20 — fonctions Craft de secours rendues locales

- Les fonctions de secours de l'ancienne API Craft (`GetNumCrafts`, `GetCraftName`,
  `GetCraftInfo`, `DoCraft`…) et `GetPetTrainingPoints` étaient déclarées en **globales** :
  d'autres addons pouvaient en conclure que l'API Craft existe sur 3.3.5a. Elles sont
  désormais **locales** au fichier `MetiersPlus.lua` ; le seul appel extérieur (un script XML)
  passe par `ATSW_GetCraftReagentItemLink`. Aucun changement de fonctionnement pour Métiers+.
- Inchangés : les SavedVariables `ATSW_*` et le cadre `ATSWFrame` (utilisé par
  AckisRecipeList).

*English*
- The fallback stubs for the old Craft API (`GetNumCrafts`, `GetCraftName`, `GetCraftInfo`,
  `DoCraft`…) and `GetPetTrainingPoints` were declared as **globals**, which could make other
  addons believe the Craft API exists on 3.3.5a. They are now **local** to `MetiersPlus.lua`;
  the only outside caller (an XML script) goes through `ATSW_GetCraftReagentItemLink`. No
  behaviour change for Métiers+.
- Unchanged: the `ATSW_*` SavedVariables and the `ATSWFrame` frame (used by AckisRecipeList).

## v1.1 — stabilité 3.3.5a, changement de métier par onglet, vue Blizzard

Correctifs de stabilité et deux nouvelles fonctions, après tests en jeu sur Ebonhold.

- **Stabilité (crashes & blocages)** : fin des plantages `format` sur un nom de métier nil,
  gardes sur les infobulles de recettes (index hors-bornes ou en-tête de catégorie), sélection
  de recette périmée après un changement de métier, et surtout suppression des popups
  **« action réservée à l'interface de Blizzard »** dus à des appels de fonctions protégées
  (`CastSpellByName`) depuis le code de l'addon.
- **Changement de métier via les onglets latéraux** : rétabli proprement avec des boutons
  d'action sécurisés (`SecureActionButtonTemplate`), la méthode adaptée à 3.3.5.
- **Bascule « vue Métiers+ » ↔ « fenêtre de métiers de Blizzard »** : un bouton sur chaque
  fenêtre + la commande `/atsw blizzard`, choix mémorisé. En vue Blizzard, l'addon se met
  totalement en retrait — tu retrouves la fenêtre native, comme sans l'addon.
- Durcissements divers issus d'un audit des incompatibilités Vanilla→WotLK restantes
  (réactifs, annonce des réactifs dans le chat, branche dressage de familier).

## v1.0 — première version (port WotLK 3.3.5a pour Ebonhold)

Premier release du portage d'**Advanced Trade Skill Window 2** (upstream v2.1.16) vers le
client **3.3.5a**, sous le nom **Métiers+**. Le portage a nécessité de corriger une vingtaine
d'incompatibilités Vanilla→WotLK ; aucun changement de fonctionnalité par rapport à l'addon
d'origine.

- Fenêtre de métiers complète sur 3.3.5a : liste des recettes, réactifs, scroll, recherche,
  tris (dont l'éditeur de tri personnalisé), file de tâches et les boutons Réactifs / Tâche / Créer.
- L'enchantement passe par la fenêtre de métiers normale.
- Corrections majeures Vanilla→WotLK : events `SPELLCAST_*`→`UNIT_SPELLCAST_*`, API Craft
  absente, table vararg `arg` (Lua 5.0), méthodes de police/couleur sur boutons, signatures
  `UIDropDownMenu` / `FauxScrollFrame`, globals renommés, et surtout **fin du remplacement des
  fonctions protégées** `CastSpellByName`/`CastSpell`/`UseAction` (qui « souillait » le chemin
  de cast sécurisé et bloquait les sorts du joueur) → désormais `hooksecurefunc`.

Crédit pour l'addon aux auteurs d'origine — Shellyoung (ATSW2), Rene Schneider (ATSW), laytya.
Voir le README.
