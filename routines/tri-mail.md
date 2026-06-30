# Routine — Tri du mail (passage principal)

Consigne exécutée à chaque passage planifié. Le « comment penser » est dans `CLAUDE.md` (§3–§7) ;
ici, le « quoi faire, dans l'ordre ». Respecte toujours les Règles d'or et les Niveaux d'autonomie.

## Pré-requis du passage

- Lis `CLAUDE.md`, `cerveau/style.md`, `etat/en-cours.md`.
- Garde à l'esprit `mode_agenda = proposer` (voir CLAUDE.md §6).

## Étapes

1. **Récupérer les mails non traités** (connecteur Gmail) :
   recherche les messages de la **boîte de réception** sans le libellé `Organiseur/Traité`.
   Recommandé : `in:inbox -label:Organiseur/Traité newer_than:7d` (ajuste la fenêtre au besoin).
   Limite ce passage à ~20 messages max ; s'il y en a plus, traite les plus récents et signale le reste.

2. **Pour chaque mail**, dans l'ordre :
   a. Identifie l'expéditeur. S'il a une fiche `cerveau/contacts/`, lis-la. Sinon → étape 6.
   b. Si la situation est récurrente, lis le playbook correspondant.
   c. Analyse selon la **taxonomie** (CLAUDE.md §4) : répondre ? tâche ? créneau ? suivi ? lié à un
      élément existant ? info ? urgent ?
   d. **RGPD** : si c'est un courrier patient/clinique → libelle `Organiseur/Patient — manuel`,
      n'extrais aucun détail, crée seulement la mention « courrier patient — à traiter manuellement ».
      Passe au suivant.
   e. Si une réponse est attendue → **prépare un brouillon Gmail** (style + fiche + playbook).
      Marque `[À ARBITRER]` si une décision de fond manque, avec la question précise.
   f. **Journalise** le brouillon dans `cerveau/journal/decisions.md` (thread, dest, objet, résumé).

3. **Mettre à jour l'état** `etat/en-cours.md` :
   - Crée / modifie les éléments (ID `AAAA-MM-JJ-NNN`). Rattache aux éléments existants au lieu de dupliquer.
   - Range chaque élément dans la bonne section (À valider / Brouillons / À programmer / À faire / À suivre).
   - Pour un « à suivre » avec échéance → note la/les date(s) de relance.

4. **Appliquer les libellés Gmail** correspondants à chaque message, puis `Organiseur/Traité`.
   (Aucun envoi, aucun archivage, aucune suppression.)

5. **Créneaux** : pour chaque tâche nécessitant du temps, inscris une proposition dans « À programmer »
   (durée estimée + fenêtre suggérée). N'écris **rien** dans l'agenda tant que `mode_agenda = proposer`.

6. **Nouveaux contacts** : pour un expéditeur sans fiche, crée un squelette à partir de
   `cerveau/contacts/_modele.md` (remplis ce que le mail révèle, laisse le reste à compléter), et
   ajoute-le aux « Nouveaux contacts repérés » du rapport.

7. **Rapport de passage** : écris le bloc du format CLAUDE.md §7 en tête de `etat/en-cours.md`
   (section « À valider » mise à jour) **et** dans `etat/rapports/AAAA-MM-JJ.md` (un fichier par jour ;
   ajoute le passage à la suite s'il existe déjà).

8. **Commit git** : message clair, ex. `run: tri 30/06 14h — 7 mails, 3 brouillons, 2 à valider`.

## Mode « à blanc » (Phase 0)

Si la consigne dit « à blanc » / « dry-run » : exécute l'**analyse** des étapes 2a–2c et montre, pour
chaque mail, classement + ce que tu rédigerais — mais **n'effectue aucune action réelle** (pas de
brouillon, pas de libellé, pas d'écriture d'état, pas de commit). C'est uniquement pour juger la qualité.
