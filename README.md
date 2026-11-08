# claude-template

Modèle de départ pour mes nouveaux projets pilotés avec un agent de code IA
(Claude Code, Codex, Cursor…).

Le cœur du modèle est [`AGENTS.md`](AGENTS.md) : le brief que l'agent lit au
début de chaque session. Il fixe la façon de travailler ensemble, les
garde-fous et les règles de sécurité non négociables du produit.

## Contenu

| Fichier | Rôle |
| --- | --- |
| `AGENTS.md` | Brief de l'agent : projet, langue, façon de travailler, garde-fous, ligne rouge sécurité, audit, décisions, avancement. |
| `README.md` | Ce fichier. |

## Démarrer un nouveau projet

1. Copier ce modèle : bouton **Use this template** sur GitHub, ou :

   ```bash
   git clone https://github.com/AlexisC73/claude-template.git mon-projet
   cd mon-projet
   rm -rf .git && git init
   ```

2. Remplir la section **Le projet** de `AGENTS.md` : ce que fait le produit,
   pour qui, et ce qu'il ne faut jamais casser.
3. Remplacer `[ce que je ne veux jamais casser]` dans **Comment je veux qu'on
   travaille** par la même chose.
4. Remplacer ce README par celui du nouveau projet.
5. Pour Claude Code, qui lit `CLAUDE.md`, créer un `CLAUDE.md` qui contient
   simplement la ligne `@AGENTS.md`.

## Au fil du projet

- **Conventions et décisions prises** et **Où on en est** se remplissent au
  fur et à mesure, par l'agent.
- La **règle vivante** permet d'ajuster le brief : quand une habitude de
  l'agent gêne, on lui demande de modifier la ligne concernée.
- Pour un contrôle de sécurité, demander : « fais l'audit de la ligne rouge ».

## Améliorer le modèle

Une amélioration du brief qui vaut pour tous les projets se reporte ici, dans
ce dépôt, pour en profiter dès le projet suivant.
