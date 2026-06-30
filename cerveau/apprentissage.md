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
