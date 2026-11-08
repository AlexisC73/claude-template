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

2. Faire remplir `AGENTS.md` par l'agent : lui donner le fichier avec la
   phrase ci-dessous (voir [Phrase à copier](#phrase-à-copier)).
3. Remplacer ce README par celui du nouveau projet.
4. Pour Claude Code, qui lit `CLAUDE.md`, créer un `CLAUDE.md` qui contient
   simplement la ligne `@AGENTS.md`.

### Phrase à copier

À envoyer à l'agent en même temps que `AGENTS.md` :

```text
Voici AGENTS.md, le brief de ce projet. Lis-le en entier et applique-le dès maintenant. Repère tout ce qui reste à compléter (les [...] et [ce que je ne veux jamais casser]). S'il y a déjà du code dans ce dossier, déduis-en ce que tu peux et montre-le-moi pour validation. Pour le reste, pose-moi tes questions une par une, en langage simple. Remplis ensuite le fichier avec mes réponses, sans toucher aux autres sections, puis montre-moi le résultat avant de commiter.
```

## Au fil du projet

- **Conventions et décisions prises** et **Où on en est** se remplissent au
  fur et à mesure, par l'agent.
- La **règle vivante** permet d'ajuster le brief : quand une habitude de
  l'agent gêne, on lui demande de modifier la ligne concernée.
- Pour un contrôle de sécurité, demander : « fais l'audit de la ligne rouge ».

## Améliorer le modèle

Une amélioration du brief qui vaut pour tous les projets se reporte ici, dans
ce dépôt, pour en profiter dès le projet suivant.
