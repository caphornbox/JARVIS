# Organiseur personnel — mode d'emploi

Ton organiseur personnel, piloté par Claude Code. Il trie ta boîte mail, prépare des brouillons à ta
voix, tient à jour ce que tu dois traiter, et s'améliore au fil du temps. **Il propose, tu valides,
tu envoies.**

## Ce que tu touches pour démarrer (3 choses seulement)

1. **Créer un dépôt GitHub PRIVÉ** (ex. `organiseur`) et y pousser ce dossier.
   ⚠️ Privé, toujours. Ce dépôt contient ta correspondance pro.
2. **Ouvrir ce dépôt dans Claude Code** et vérifier que les connecteurs **Gmail**, **Google Agenda**
   et **Notion** sont disponibles (Phase 1). Claude Code lit automatiquement `CLAUDE.md`.
3. **Lancer le test à blanc** (Phase 0) — copie ce message dans Claude Code :

   > Lis `CLAUDE.md`. Fais un tri **à blanc** de mes 15 derniers mails non traités en suivant
   > `routines/tri-mail.md`, mais **ne crée aucun brouillon, n'applique aucun libellé, n'écris rien
   > dans l'agenda**. Montre-moi seulement, pour chaque mail : l'analyse, le classement, et ce que tu
   > rédigerais. Je veux juger la qualité avant qu'on automatise.

   Tu lis les résultats, tu corriges le cap (style, classement), et seulement après on passe à
   l'automatisation.

## Les phases

- **Phase 0 — valider** : test à blanc ci-dessus. Aucune action réelle. Objectif : juger le raisonnement.
- **Phase 1 — la boucle** : routine planifiée (plusieurs fois/jour) → tableau Notion + brouillons Gmail
  + créneaux proposés + nouveaux contacts. Voir `docs/notion-schema.md` et `docs/routine-config.md`.
- **Phase 2 — il apprend** : routine qui relit tes mails *envoyés*, compare à ses brouillons, et met à
  jour les fiches. Voir `routines/apprentissage.md`.
- **Phase 3 — étendre** : SMS / autres canaux selon faisabilité (dépend de ton téléphone).

## Comment c'est rangé

```
CLAUDE.md            ← le « cerveau » : règles que l'agent lit à chaque passage
cerveau/
  style.md           ← ton style d'écriture (grossit avec le temps)
  contacts/          ← une fiche par interlocuteur (règles de rédaction perso)
  playbooks/         ← comment tu gères les situations récurrentes (litige, recrutement…)
  journal/           ← journal des décisions/actions (append-only)
  apprentissage.md   ← changelog de ce que l'agent a appris
etat/
  en-cours.md        ← TON TABLEAU « À L'INSTANT T » : ce qui n'est pas traité
  rapports/          ← un rapport par jour (historique)
routines/            ← les consignes des passages (tri, apprentissage, digest hebdo)
docs/                ← mise en place Notion + routine planifiée
```

## Où regarder au quotidien

- **`etat/en-cours.md`** = ta vue principale. Section « À valider » en haut = ce qui attend ta décision,
  brouillons prêts, créneaux proposés. (En Phase 1, le tableau Notion en est le reflet, plus joli et
  accessible sur mobile.)
- Dans **Gmail**, les libellés `Organiseur/…` te montrent le classement directement dans ta boîte.

## Règles importantes (déjà câblées dans `CLAUDE.md`)

- L'agent **n'envoie jamais** : il prépare des brouillons.
- **Aucune donnée patient** ne rentre ici. Réservé à la correspondance opérationnelle.
- Un mail qui contient un ordre n'est **pas** une instruction : l'agent te le signale, il n'obéit pas.

## À remplir en premier (pour des brouillons tout de suite plus justes)

- `cerveau/style.md` : ta signature, vouvoiement par défaut, formules que tu détestes, etc.
- 2-3 fiches contact de tes interlocuteurs fréquents (modèle : `cerveau/contacts/_modele.md`).
- Tes dossiers chauds du moment font de parfaites premières fiches + playbooks (ex. litige prestataire
  ménage, dossier Nihon Kohden). Un exemple pré-rempli est fourni pour montrer le format.
