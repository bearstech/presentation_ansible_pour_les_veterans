!SLIDE

![Hockeyeur gardien](vet.jpg)

!SLIDE
# Approche Déscriptitive

Ansible a une approche déscriptive, orthogonale à la notion de script.
Les boucles et les condtions sont possibles, mais restent rare.
Les playbooks sont volontairement linéaires et verbeux.

!SLIDE
# Souplesse et rigueur

Ansible à une approche implicite, déscriptive et séquentielle.

!SLIDE
## Les modules

La plupart des modules sont paraphrasables par une "command".

On commence souvent par une version simple, un peu crado, puis dans une seconde passe, on affine en utilisant la commande adéquate.

Un gros effort est fait pour que les commandes de bases soient cohérentes et homogènes.

!SLIDE
### Shell vs command

*shell* et *raw* sont là pour décoincer la situation, mais elles sont mauvaises pour le karma.

*command* est lui tout à fait légitime, par contre.

Attention à bien préciser le *creates* pour limiter le nombre d'actions.

!SLIDE
## Les playbooks

Ansible est trés libéral sur l'organisation du playbook.
La chronologie traditionnelle est :

 * Un playbook kilométrique
 * Redistribution vers de multiples rôles
 * Découpage en plusieurs playbook et un sommaire
 * Utilisation avancé, les includes conditionnels, les tags

!SLIDE
## Les inventaires

Même souplesse au niveau des inventaires.

Les groupes permettent d'anonymiser un playbook.

Les groupes acceptent les opérations booléennes.
