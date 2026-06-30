# Tableau de bord Notion

Notion est le **tableau de bord** de l'organiseur (mobile, partageable). Le **classement** de chaque
mail vit dans **Gmail** (libellés ①→⑤) ; **Notion** ne reçoit que la **shortlist** : ce qui demande
une décision ou un suivi (`① À faire`, `② En attente`, `③ Délégué` à suivre). Le `④ À lire` et le
`⑤ Archive` n'y vont pas. L'appariement se fait par l'**ID** (`AAAA-MM-JJ-NNN`).
`etat/en-cours.md` (versionné par git) est le miroir court et inspectable de ce même contenu.

> L'agent peut créer cette base lui-même via le connecteur Notion, ou tu la crées et lui donnes le lien.

## Base : « Suivi Organiseur »

| Propriété | Type | Valeurs / notes |
|---|---|---|
| **Titre** | Title | Résumé court de l'élément |
| **ID** | Texte | `AAAA-MM-JJ-NNN` — clé d'appariement avec `en-cours.md`. Unique. |
| **Libellé GTD** | Select | ① À faire · ② En attente · ③ Délégué *(reflet du libellé Gmail)* |
| **Statut** | Select | À valider · En cours · En attente · Programmé · Fait |
| **Qui** | Select | Adam · Sabrina · David · Léa · Qalipse · Autre *(à qui revient l'action)* |
| **Priorité** | Select | Urgent · Haut · Normal · Bas |
| **Contact** | Texte | Interlocuteur externe concerné |
| **Compte** | Select | oph.montreuil · caphornmontreuil · caphornsante · adam · autre *(boîte du hub)* |
| **Échéance** | Date | Pour les tâches |
| **Relance le** | Date | Pour les `② En attente` |
| **Créneau proposé** | Date | Pour les tâches à programmer |
| **Brouillon prêt** | Case à cocher | Coché si un brouillon Gmail attend relecture |
| **Lien Gmail** | URL | Vers le thread |
| **Résumé** | Texte | 1–2 lignes de contexte (enjeu opérationnel, jamais de clinique brut) |
| **Dernière MAJ** | Date | Mise à jour à chaque passage |

### Vues recommandées

- **À valider** (Statut = « À valider ») — ta vue d'arrivée chaque matin.
- **Mes actions** (Qui = Adam, Libellé = ① À faire) — ce qui te revient.
- **Relances cette semaine** (Relance ≤ 7 jours).
- **Délégué** (Libellé = ③ Délégué) — ce que tu as confié et veux suivre.
- **Par compte** (regroupé par Compte).

## Règle de synchro pour l'agent

À chaque passage, pour chaque élément de la shortlist :
1. Cherche une page Notion avec le même **ID**.
2. Si elle existe → mets à jour ses propriétés. Sinon → crée-la.
3. Quand un élément passe à « Fait » (et est archivé côté fichier), passe le **Statut** à « Fait »
   (ne supprime pas la page — historique).

> Synchro **à sens unique** : le couple Gmail + fichier mène, l'agent projette vers Notion. N'édite pas
> les éléments directement dans Notion (risque d'écrasement au passage suivant). Pour agir, dis-le à
> l'agent dans Claude Code.
