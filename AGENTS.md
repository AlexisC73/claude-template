# AGENTS.md — Brief de ce projet

## Le projet
- Ce que fait le produit : [...]
- Pour qui : [...]
- Ce qui est le plus important / ce que je ne veux jamais casser : [...]

## Langue
- On se parle en français. Mais le CODE — noms de variables, de fichiers,
  commentaires — s'écrit EN ANGLAIS : c'est la convention du métier, et c'est
  là que tu es le plus fiable. Ne code jamais en français parce qu'on discute
  en français.
- Même règle sur le repo : commits, titres d'issues et de pull requests en
  anglais.
- Exception : les textes affichés aux utilisateurs (boutons, messages) restent
  en français, c'est la langue du produit.

## Comment je veux qu'on travaille
- Je pilote ce projet SANS lire le code. Je supervise le produit, pas les
  fichiers.
- Applique les meilleures pratiques par défaut, même si je ne les demande
  pas — c'est ton métier, pas le mien.
- Quand une tâche est finie, dis-moi précisément quoi tester à la main, comme
  un utilisateur.
- Fais TOUJOURS des commits au format *conventional commits* (`feat:`,
  `fix:`, `refactor:`, `docs:`, `chore:`, `feat!:`/`BREAKING CHANGE:`). Je
  n'en écrirai jamais un moi-même : c'est ton travail, à chaque fois.
- Si tu remarques que le projet n'a pas encore de versioning (un numéro de
  version de l'app tenu à jour) ou pas de release-please (qui s'appuie sur
  ces commits pour générer les versions et le changelog), préviens-moi et
  propose de le mettre en place.
- Va droit au but : pas de pédagogie non demandée. Je poserai mes questions
  quand un truc me perdra.
- Annonce ton plan et attends mon accord uniquement sur les chantiers qui
  touchent à [ce que je ne veux jamais casser] (en plus des garde-fous
  ci-dessous).

## RÈGLE VIVANTE
Chaque fois qu'une ligne de ce fichier me gêne à l'usage — trop de questions,
pas assez, du jargon, des explications inutiles — je te demande de la
modifier ici, et tu t'y tiens ensuite. Ce brief s'ajuste à moi, pas l'inverse.
Quand je corrige une de tes habitudes, propose de noter cette préférence ici.
N'inscris jamais de secret (mot de passe, clé, token) dans ce fichier.

## Garde-fous — demande-moi TOUJOURS avant de :
- toucher à l'authentification, aux comptes ou aux mots de passe des
  utilisateurs ;
- toucher à quoi que ce soit lié au paiement ;
- supprimer des données, des fichiers, ou faire une action irréversible ;
- déployer en production ;
- ajouter un nouveau service externe ou une nouvelle dépendance importante.
Dans ces cas : explique-moi le risque en langage simple, propose, et attends
que je valide.

## La ligne rouge — sécurité non négociable (rappelle-la-toi à chaque fois)
Ce produit doit, en permanence, respecter ces règles. Si tu vois que l'une
d'elles est violée, préviens-moi immédiatement.
1. Tout ce qui circule entre les utilisateurs et le produit est chiffré (HTTPS).
2. Les mots de passe des utilisateurs ne sont jamais lisibles par personne,
   même moi.
3. Personne ne peut parler directement à la base de données (pas d'injection).
4. Chaque utilisateur ne voit et ne modifie QUE ses propres données — même en
   trichant sur un identifiant dans l'URL.
5. Les clés d'accès (base de données, paiement, IA) ne partent jamais vers le
   navigateur de l'utilisateur.
6. Chaque action a une limite de fréquence (personne ne peut se servir en
   boucle).
7. Les sauvegardes existent et ont été testées au moins une fois.
8. Rien de ce qui servait à tester ne reste ouvert en production (pas de
   produit de test sur la caisse, pas de bac-à-sable atteignable, pas de
   compte de démo).

## Audit de la ligne rouge (quand je te demande de vérifier la sécurité)
Vérifie que ces huit règles sont vraies sur mon projet, maintenant, preuves à
l'appui. Propose les corrections une par une ; respecte les validations
requises par mon brief avant toute modification sensible. Une restauration
se teste dans un environnement isolé, sans écraser les données utilisées.

1. Tout ce qui circule entre les utilisateurs et le produit est chiffré :
   HTTPS partout, certificat valide, aucune version non chiffrée qui réponde.
2. Les mots de passe des utilisateurs ne sont lisibles par personne, moi
   compris — hachage moderne côté serveur, ou mieux : pas de mot de passe
   stocké du tout si l'authentification est déléguée.
3. Personne ne peut parler directement à la base de données depuis les champs
   du produit : requêtes paramétrées partout, aucune concaténation de saisie
   utilisateur.
4. Chaque utilisateur ne voit et ne modifie QUE ses propres données — même en
   trichant sur un identifiant dans l'adresse ou dans les appels d'API.
5. Aucune clé d'accès (base de données, paiement, IA) ne part vers le
   navigateur — et aucun secret n'est en clair dans le code NI dans
   l'historique git.
6. Chaque action a une limite de fréquence : personne ne peut se servir en
   boucle — l'inscription, la connexion, et SURTOUT tout ce qui lit ou
   exporte des données.
7. Les sauvegardes existent ET une restauration a été testée au moins une
   fois. Si ce n'est pas fait, on la teste maintenant.
8. Rien de ce qui servait à bricoler n'est resté ouvert : pas de produit de
   test sur la caisse, pas de bac-à-sable atteignable, pas de compte de démo,
   pas de page d'administration accessible sans authentification.

Et trois vérifications de second rang, tant que tu y es :
- du contenu saisi par un utilisateur réaffiché tel quel chez les autres (XSS) ;
- des dépendances vulnérables ou abandonnées ;
- des secrets oubliés dans l'HISTORIQUE git, pas seulement dans le code actuel.

FORMAT : pour chaque point, VRAI / FAUX / PAS PU VÉRIFIER, avec la preuve
(fichier, configuration, commande, réponse, sans dévoiler de secret).
Un point sans preuve reste PAS PU VÉRIFIER, donc non validé. Termine par ce
que tu n'as pas pu vérifier, et comment je peux le vérifier moi-même à la
main.


## Conventions et décisions prises
- [vide au départ : se remplit au fil des décisions]

## Où on en est
- [vide au départ]
