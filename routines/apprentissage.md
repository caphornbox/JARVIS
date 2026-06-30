# Routine — Apprentissage (relecture des envoyés)

But : faire converger les brouillons vers la façon d'écrire d'Adam, en écrivant des règles explicites.
Fréquence conseillée : 1×/semaine (ex. dimanche soir), ou à la demande. Phase 2.

## Étapes

1. **Récupérer les mails envoyés** depuis le dernier passage d'apprentissage (connecteur Gmail :
   `in:sent newer_than:7d`, à ajuster).

2. **Apparier brouillon ↔ envoi** :
   - Lis le log des brouillons dans `cerveau/journal/decisions.md`.
   - Pour chaque envoi, retrouve le brouillon correspondant **par thread** (même conversation) et
     destinataire. Si aucun brouillon ne correspond (Adam a écrit de zéro), c'est une donnée tout aussi
     utile : analyse quand même son style sur ce message.

3. **Extraire les écarts** entre ton brouillon et ce qu'Adam a réellement envoyé :
   - Formule d'ouverture / clôture modifiée ? Tutoiement/vouvoiement changé ? Signature différente ?
   - Longueur (a-t-il coupé ? développé ?) Ton (plus direct ? plus chaleureux ?)
   - Formules supprimées / ajoutées ? Tournures récurrentes ?

4. **Écrire les règles** :
   - Règle spécifique à une personne → dans sa fiche `cerveau/contacts/`.
   - Règle générale → dans `cerveau/style.md`.
   - Marque chaque règle inférée `(auto, à confirmer)`.
   - Consigne chaque ajout dans `cerveau/apprentissage.md` (format du fichier) avec statut `proposée (auto)`.

5. **Ne jamais** sur-généraliser à partir d'un seul exemple ambigu. Si un écart peut être ponctuel,
   note-le comme hypothèse plutôt que comme règle ferme.

6. **Commit git** : ex. `apprentissage: semaine du 28/06 — 4 règles proposées`.

## Garde-fou

Tu **proposes** des règles, tu ne réécris pas le style d'Adam autoritairement. Adam relit
`cerveau/apprentissage.md`, valide (`validée`) ou corrige (`corrigée`) directement dans les fichiers.
Tu respectes ensuite la version d'Adam.
