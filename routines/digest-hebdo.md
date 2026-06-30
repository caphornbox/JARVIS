# Routine — Digest hebdomadaire

But : produire un récapitulatif prêt pour la réunion hebdo et pour qu'Adam demande facilement « où en
est-on ». Fréquence conseillée : lundi matin (ou la veille au soir). Phase 2.

## Étapes

1. Lis `etat/en-cours.md` et les `etat/rapports/` de la semaine écoulée.

2. Produis un **digest** structuré (à écrire dans `etat/rapports/DIGEST-AAAA-Www.md` et à afficher) :

```
# Digest — semaine du JJ/MM au JJ/MM

## En attente de ta décision
- <éléments « À valider » encore ouverts>

## Échéances à venir (14 jours)
- <date> — <quoi> — <contact>

## En cours par dossier
- <dossier / contact> : <état en une ligne>

## À suivre / relances dues cette semaine
- <contact> — <quoi> — relance prévue le <date>

## Réglé cette semaine
- <liste courte>

## Chiffres
- Mails traités : <n> · Brouillons préparés : <n> · Éléments clôturés : <n>
```

3. **Nettoyage** : déplace les éléments `[x]` terminés depuis `etat/en-cours.md` vers
   `etat/archive/AAAA-Www.md`.

4. **Commit git** : ex. `digest: semaine 27 + archivage`.

## Usage à la demande

Adam peut aussi demander à tout moment, dans Claude Code : « fais-moi le point sur le dossier <X> »
ou « qu'est-ce qui n'est pas traité là ? » → tu réponds à partir de `etat/en-cours.md` et du cerveau,
sans attendre le digest hebdo.
