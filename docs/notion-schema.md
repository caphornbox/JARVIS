# Mise en place Notion (Phase 1)

En Phase 1, le tableau Notion est le **reflet** de `etat/en-cours.md`, en plus joli et accessible sur
mobile. La source de vérité reste le fichier `etat/en-cours.md` (versionné par git) ; l'agent y projette
chaque élément. L'appariement se fait par l'**ID** de l'élément (`AAAA-MM-JJ-NNN`).

> Tu peux soit créer la base toi-même avec le schéma ci-dessous, soit me demander de la créer pour toi
> via le connecteur Notion une fois que tu valides ce schéma.

## Base : « Suivi Organiseur »

| Propriété | Type | Valeurs / notes |
|---|---|---|
| **Titre** | Title | Résumé court de l'élément |
| **ID** | Texte | `AAAA-MM-JJ-NNN` — clé d'appariement avec `en-cours.md`. Unique. |
| **Type** | Select | À répondre · À faire · À suivre · À programmer · Info |
| **Statut** | Select | À valider · En cours · En attente · Programmé · Fait |
| **Priorité** | Select | Urgent · Haut · Normal · Bas |
| **Contact** | Texte | Nom de l'interlocuteur (ou relation vers une base Contacts plus tard) |
| **Échéance** | Date | Pour les tâches / suivis |
| **Relance le** | Date | Pour les « à suivre » |
| **Créneau proposé** | Date | Pour les « à programmer » |
| **Brouillon prêt** | Case à cocher | Coché si un brouillon Gmail attend relecture |
| **Lien Gmail** | URL | Vers le thread |
| **Résumé** | Texte | 1–2 lignes de contexte |
| **Dernière MAJ** | Date | Mise à jour à chaque passage |

### Vues recommandées

- **À valider** (filtre Statut = « À valider ») — ta vue d'arrivée chaque matin.
- **Cette semaine** (filtre Échéance ≤ 7 jours OU Relance ≤ 7 jours).
- **Par type** (regroupé par Type).
- **Calendrier** (sur Créneau proposé / Échéance).

## Règle de synchro pour l'agent

À chaque passage, pour chaque élément de `en-cours.md` :
1. Cherche une page Notion avec le même **ID**.
2. Si elle existe → mets à jour ses propriétés. Sinon → crée-la.
3. Quand un élément passe à « Fait » et est archivé côté fichier, passe le **Statut** de la page à « Fait »
   (ne supprime pas la page — historique).

> Note : la synchro fichier→Notion est volontairement à sens unique (le fichier mène). Évite de modifier
> les éléments directement dans Notion, sinon risque d'écrasement au passage suivant. Pour agir, dis-le
> à l'agent dans Claude Code.
