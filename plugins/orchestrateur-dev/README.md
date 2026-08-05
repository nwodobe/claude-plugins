# orchestrateur-dev

Plugin Claude qui coordonne cinq agents specialises pour ameliorer la qualite d'une application web (React/Next/Vue) ou mobile (Flutter/React Native) : tests, audit technique, correction encadree, design d'interface et navigation.

## Composants

### Agents

| Agent | Role | Frontiere |
| --- | --- | --- |
| testeur-app | Evalue l'etat de sante technique (build, tests, parcours critiques) | Ne corrige rien lui-meme |
| auditeur-app | Produit des constats priorises sur 6 dimensions de qualite | N'applique pas de correctif |
| correcteur-auto | Corrige les constats valides avec des garde-fous stricts | Ne fusionne ni ne deploie jamais |
| design-ui | Harmonise l'interface visuelle | Ne touche pas a la logique metier |
| ux-navigation | Ameliore la structure de navigation | Ne touche pas au visuel ni a la logique metier |

### Skill

Le skill orchestrateur-dev coordonne les cinq agents dans un pipeline ordonne, avec un point de controle humain avant toute correction.

## Usage

Declenche le pipeline en demandant par exemple :

- "lance l'orchestrateur"
- "pipeline qualite"
- "audit complet puis correction"
- "passe l'app au crible"
- "cycle qualite"

## Garde-fous

- Aucune fusion, push ou deploiement automatique.
- Les corrections sont realisees sur une branche dediee, par exemple fix/audit-2026-08-05.
- Toute decision impactant le produit ou le design est soumise a validation humaine.

## Personnalisation

Chaque agent est un fichier .md dans agents/. Le pipeline de coordination est defini dans skills/orchestrateur-dev/SKILL.md. Modifie ces fichiers pour ajuster le comportement a ton contexte.
