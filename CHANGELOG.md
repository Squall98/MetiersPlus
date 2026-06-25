# Changelog

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
