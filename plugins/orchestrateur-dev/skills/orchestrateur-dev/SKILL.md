---
name: orchestrateur-dev
description: This skill should be used when the user asks to run the full quality pipeline on an application, or says "lance l'orchestrateur", "pipeline qualite", "audit complet puis correction", "passe l'app au crible", "cycle qualite", or asks to chain audit, tests, fixes, design and UX review on a web (React/Next/Vue) or mobile (Flutter/React Native) app. It coordinates the five agents of the orchestrateur-dev plugin in the correct order with guardrails.
version: 0.1.0
---

# Orchestrateur qualite applicative

## Pre-vol

- Confirme le perimetre de l'application a traiter (dossier, module ou application complete).
- Verifie qu'un acces en lecture/ecriture au code est disponible.
- Signale si l'un des cinq agents necessaires n'est pas disponible avant de demarrer.

## Pipeline nominal

1. testeur-app etablit un etat de reference (build, tests, parcours critiques).
2. auditeur-app produit la liste des constats priorises sur les six dimensions d'audit.
3. Point de controle humain : les constats critiques et majeurs sont soumis a validation avant correction.
4. correcteur-auto corrige les constats valides, en respectant ses garde-fous.
5. testeur-app rejoue les tests et parcours critiques pour confirmer l'absence de regression.
6. design-ui puis ux-navigation interviennent en dernier pour ameliorer l'interface et la navigation sans perturber les corrections techniques.

## Regles de coordination

- Chaque agent reste dans son perimetre strict, aucun agent ne prend le role d'un autre.
- Aucune fusion, aucun push ni deploiement automatique n'est declenche par le pipeline.
- Toute correction touchant a un choix produit ou de design est remontee a l'utilisateur avant application.
- Le pipeline peut s'arreter a tout point de controle si l'utilisateur le demande.

## Rapport final

- Un tableau recapitulatif du deroule du pipeline (etape, agent, resultat).
- La liste des constats corriges, restants et ceux necessitant une decision humaine.
- Une comparaison avant/apres sur les points cles (tests, build, constats).
- Le nom de la branche utilisee et la commande de fusion suggeree (sans l'executer).
- Au maximum 3 recommandations pour la suite.
