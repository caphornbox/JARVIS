# Mise en place de la routine planifiée (Phase 1)

Une « routine » = un **déclencheur planifié** (façon cron) qui réveille l'agent et lui fait exécuter une
consigne. Dans Claude Code, ça se fait via les **triggers** (Claude Code Remote). Au lieu d'un script
figé, ça lance un agent qui raisonne avec accès à tes outils (Gmail, Agenda, Notion).

> ⚠️ Honnêteté technique : ce n'est **pas** événementiel. « À chaque mail reçu » au sens strict n'existe
> pas ici — c'est planifié. Un passage par heure en journée suffit largement pour un organiseur. Le vrai
> temps réel (déclencher dès l'arrivée d'un mail) se fait avec une couche **n8n** qui surveille Gmail en
> push et appelle le passage — à mettre en Phase 2 si tu y tiens.

## Triggers à créer (quand tu auras validé la Phase 0)

### 1. Tri du mail — toutes les heures en journée, en semaine
- **Cron** : `0 8-19 * * 1-5`  *(à 8h, 9h, …, 19h, du lundi au vendredi)*
- **Message du trigger** :
  > Exécute la routine `routines/tri-mail.md`. Respecte `CLAUDE.md`. À la fin, mets à jour
  > `etat/en-cours.md`, applique les libellés, et commit.

### 2. Digest hebdomadaire — lundi matin
- **Cron** : `0 7 * * 1`  *(lundi 7h)*
- **Message du trigger** :
  > Exécute la routine `routines/digest-hebdo.md`.

### 3. Apprentissage — dimanche soir
- **Cron** : `0 20 * * 0`  *(dimanche 20h)*
- **Message du trigger** :
  > Exécute la routine `routines/apprentissage.md`.

> **Fuseau horaire** : vérifie si tes triggers sont en UTC ou en heure de Paris. Paris = UTC+1 (hiver) /
> UTC+2 (été). Si les triggers sont en UTC, décale les heures (ex. pour un passage à 8h Paris l'été,
> mets `6` dans le cron). Confirme le comportement avec un premier trigger de test.

## Démarrage prudent recommandé

1. Commence par **1 seul passage/jour** (ex. `0 8 * * 1-5`) pendant quelques jours, le temps de juger.
2. Garde `mode_agenda = proposer` (rien écrit dans l'agenda) tant que tu n'as pas confiance.
3. Quand les brouillons et le classement te conviennent, monte à la fréquence horaire.
4. Plus tard seulement : passe `mode_agenda = auto_focus` (l'agent pose tes blocs focus perso, préfixés
   `[auto]`), et/ou ajoute la couche n8n temps réel.

## Triggers en place (créés le 30/06/2026)

> ⚠️ **Fuseau confirmé : le cron est en UTC.** Heures Paris = UTC + 2 (été) / + 1 (hiver).
> Sessions fraîches à chaque déclenchement (l'agent relit `CLAUDE.md` et agit), push sur `claude/new-session-uir3ui`.

| Routine | ID trigger | Cron (UTC) | Heure Paris (été) | Notif |
|---|---|---|---|---|
| Tri du mail (prudent 1×/j, lun–ven) | `trig_01PZBNS1c4N9FerPup6NMm2d` | `0 8 * * 1-5` | 10h00 | push |
| Digest hebdo (lundi) | `trig_015scZCbNTvS1GV552uDNnXK` | `0 7 * * 1` | 9h00 | push |
| Apprentissage (dimanche) | `trig_01Mgog87Ek5WWrscXRuVyx7D` | `0 20 * * 0` | 22h00 | — |

### Étapes suivantes
1. **Démarrage prudent** : le tri tourne 1×/jour. Juger la qualité quelques jours.
2. **Montée en cadence** : passer le tri à l'horaire 8h–19h Paris → cron `0 6-17 * * 1-5` (UTC).
3. Plus tard : `mode_agenda = auto_focus`, `mode_archivage = auto`, couche n8n temps réel.

> Caveat technique à surveiller au 1er déclenchement : vérifier que les connecteurs (Gmail, Notion)
> sont bien disponibles dans la session planifiée. Si un run échoue faute de connecteur, me le signaler.
