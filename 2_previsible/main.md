!SLIDE
# Prévisible

!SLIDE
## Variables

Les variables amènent la souplesse dans les playbooks, mais aussi des surprises.

!SLIDE
### Défaut

Les variables peuvent être complexe, mais attention, lors d'un merge de source, les clefs n'ont qu'un seul niveau.

```
toto:
  version: 1.2.3
  name: bob
```
plus

```
toto:
  name: casimir
```
donne
```
toto.version == None
```

!SLIDE
### Assertions

La rigueur des modules permettent d'avoir confiance dans leurs actions.

Rien ne garanti la cohérence des variables, surtout si il y a plusieurs cibles avec chacune leur jeu de variables.

Il est sage d'avoir queqlues assertions, comme la possibilité à un client de se connecter à son serveur depuis chacun des noeuds possibles.

!SLIDE
### Lookup

La fonctionnalité de *lookup* permet de récupérer des variables.

Les usages sont divers :

 * Contenu d'un fichier
 * Résultat d'une commande
 * Interrogation d'un DNS
 * Utilisation de Redis, comme base clef/valeur
 * …

!SLIDE
### Vault

Il est possible de ranger les variables sensibles (comme les mots de passe) dans un troussau.

Fortement recommandé pour les playbooks open source.

!SLIDE
## Séquentiel

Le traitement des actions se fait de manière séquentiel.

Le résultat est prévisible, mais mou.

Pour les bases de données, il est plus simple de générer une liste de commandes avec un *template*, puis de demander son éxécution.

Les actions asynchrone, qui rendent la main avant d'avoir agis sont une malédiction.

!SLIDE
# Gabarits

Jinja2 couvre beaucoup de besoins, mais il peut y avoir quelques surprises.

 * Collision de syntaxe avec un fichier que l'on vient de voler
 * Debug un peu laborieux quand on découvre une nouvelle fonctionnalité de Jinja2
 * Python hait le monkey patching, les actions sur les variables seront des filtres, et Ansible en propose quelques un.
 * Il est possible d'ajouter des extensions, comme le très pratique *do*


