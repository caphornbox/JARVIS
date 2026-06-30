# Routine — Tri du mail (passage principal)

Consigne exécutée à chaque passage planifié. Le « comment penser » est dans `CLAUDE.md` (§3–§9) ;
ici, le « quoi faire, dans l'ordre ». Respecte toujours les Règles d'or et les Niveaux d'autonomie.
Rappel : **hub partagé** (plusieurs comptes, plusieurs personnes) — demande-toi « à qui revient l'action ».

## Pré-requis du passage

- Lis `CLAUDE.md`, `cerveau/style.md`, `etat/en-cours.md`.
- Réglages : `mode_agenda = proposer`, `mode_archivage = manuel` (voir CLAUDE.md §6).
- Libellés utilisés : `① À faire`, `② En attente`, `③ Délégué`, `④ À lire`, `⑤ Archive`, et le
  marqueur agent `🤖 Trié`. (Si `🤖 Trié` n'existe pas encore, crée-le une fois.)

## Étapes

1. **Récupérer les mails à trier** (connecteur Gmail) :
   messages de la **boîte de réception** sans le marqueur `🤖 Trié` :
   `in:inbox -label:🤖-Trié newer_than:7d` (ajuste la fenêtre au besoin).
   Limite à ~20 messages/passage ; s'il y en a plus, traite les plus récents et signale le reste.

2. **Pour chaque mail**, dans l'ordre :
   a. Identifie l'expéditeur **et le compte du hub** concerné. S'il a une fiche `cerveau/contacts/`, lis-la.
      Sinon → étape 6 si c'est un interlocuteur qui compte.
   b. Si la situation est récurrente, lis le playbook correspondant.
   c. **À qui revient l'action ?** (CLAUDE.md §8). Si ce n'est pas Adam → `③ Délégué` (+ brouillon de
      transfert si utile).
   d. Choisis **UN** libellé GTD selon la taxonomie (CLAUDE.md §4) : `① À faire` / `② En attente` /
      `③ Délégué` / `④ À lire` / `⑤ Archive`. Un seul.
   e. **Données de santé** : traite normalement (pragmatique, non bloquant). Ne recopie pas de contenu
      clinique brut dans le dépôt/Notion — résume l'enjeu opérationnel. Un mail de pur soin → classe et
      délègue à l'équipe médicale sans en reproduire le contenu.
   f. Si une **réponse d'Adam** est attendue → libellé `① À faire` **et** prépare un **brouillon Gmail**
      (style + fiche + playbook). Marque `[À ARBITRER]` si une décision de fond manque, avec la question.
   g. **Journalise** le brouillon dans `cerveau/journal/decisions.md` (thread, dest, objet, résumé).

3. **Faire remonter ce qui compte** (état + Notion) — *pas* chaque mail :
   - Crée / modifie un élément (ID `AAAA-MM-JJ-NNN`) **seulement** pour : `① À faire`, `② En attente`,
     et les `③ Délégué` qu'Adam doit suivre. Rattache aux éléments existants au lieu de dupliquer.
   - `④ À lire` et `⑤ Archive` : pas d'entrée d'état (juste comptés dans le rapport/digest).
   - Pour un `② En attente` → note la/les date(s) de relance.

4. **Appliquer les libellés** : le bon libellé GTD (un seul), puis `🤖 Trié`.
   (Aucun envoi, aucune suppression ; pas de retrait de l'inbox tant que `mode_archivage = manuel`.)

5. **Créneaux** : pour chaque tâche nécessitant du temps, inscris une proposition dans « À programmer »
   (durée estimée + fenêtre suggérée). N'écris **rien** dans l'agenda tant que `mode_agenda = proposer`.

6. **Nouveaux contacts** : pour un interlocuteur important sans fiche, crée un squelette à partir de
   `cerveau/contacts/_modele.md` (remplis ce que le mail révèle) et ajoute-le au rapport.
   (Inutile de créer une fiche pour un no-reply / expéditeur automatique.)

7. **Rapport de passage** : écris le bloc du format CLAUDE.md §7 en tête de `etat/en-cours.md`
   **et** dans `etat/rapports/AAAA-MM-JJ.md` (un fichier/jour ; ajoute à la suite s'il existe).
   Puis **synchronise Notion** (voir `docs/notion-schema.md`).

8. **Commit git** : message clair, ex. `run: tri 30/06 14h — 18 mails, 2 brouillons, 3 à valider`.

## Mode « à blanc » (Phase 0)

Si la consigne dit « à blanc » / « dry-run » : exécute l'**analyse** des étapes 2a–2d et montre, pour
chaque mail, le libellé GTD choisi + ce que tu rédigerais — mais **n'effectue aucune action réelle**
(pas de brouillon, pas de libellé, pas d'écriture d'état/Notion, pas de commit). Uniquement pour juger.
