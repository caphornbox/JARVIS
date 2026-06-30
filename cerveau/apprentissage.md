# Apprentissage — journal de ce que l'agent a appris

Ce système s'améliore en **écrivant des règles explicites**. Ce fichier est le changelog : il trace
chaque règle ajoutée/modifiée au cerveau, sa source, et son statut.

La routine d'apprentissage (`routines/apprentissage.md`) tourne périodiquement : elle relit les mails
**envoyés** par Adam, les compare aux brouillons préparés (journalisés dans `cerveau/journal/decisions.md`),
en déduit les écarts, et inscrit les règles ici + dans `cerveau/style.md` / la fiche contact concernée.

> Statuts : `proposée (auto)` = inférée, en attente de validation d'Adam · `validée` = confirmée par Adam ·
> `corrigée` = Adam a modifié la règle.

## Format d'une entrée

```
### AAAA-MM-JJ — <Contact ou Global>
- Observation : <ce qu'Adam a changé entre le brouillon et l'envoi>
- Règle déduite : <règle écrite>
- Écrite dans : <style.md / fiche contact X>
- Statut : proposée (auto)
```

## Journal

<!-- Les entrées s'ajoutent ici, plus récentes en bas -->

### 2026-06-30 — Global (corrections d'Adam après le 1er passage réel)
- Observation : Adam corrige le classement de notifications et de partages.
- Règle déduite 1 : **prélèvement automatique → `⑤ Archive`** (rien à faire), pas `③ Délégué` ni `④ À lire`.
- Règle déduite 2 : **si les personnes qui doivent agir sont déjà en copie → `④ À lire`** (Adam n'a rien à faire), ne pas créer de `③ Délégué`.
- Écrites dans : `CLAUDE.md` §4 (arbre de décision, Q1 et Q2).
- Statut : validée (corrections explicites d'Adam).

### 2026-06-30 — Global (clarification du fonctionnement)
- Observation : la taxonomie écrite comme une liste de questions parallèles prêtait à confusion.
- Règle déduite : formaliser la décision en **arbre ordonné** (action ? → à qui ? → quoi ? → Notion ne fait qu'afficher).
- Écrite dans : `CLAUDE.md` §4.
- Statut : validée.
