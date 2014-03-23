!SLIDE
# Plusieurs cibles

Votre archi va évoluer : les services vont être répartis différement, des noeuds vont être ajoutés.

Vous avez déja plusieurs cibles, au minimum le poste de dev et la prod.

!SLIDE
## La tactique

Une des tactiques est de n'avoir aucunes références à un host dans Les playbooks,
et autant d'inventaires que de cibles.

Les inventaires contiennent les variables.

Attention à maintenir la cohérence des variables entre les différents inventaires.

!SLIDE
# Size does matter

Ansible n'est pas super véloce.

Il faut pouvoir simplifier le scénario :

 * En découpant le playbook, un sommaire "include" les autres.
 * Les tags permettent de cibler précisément.

Les rôles doivent être autonomes.

!SLIDE
# Idempotances

Un playbook peut être joué et rejoué sans risque.

En confiant à Ansible la charge de ne toucher que ce qu'il y a à mofier, on gagne en confiance et en stress.

!SLIDE
## Actions dangereuses

Ajouter un esclave a une base de donnée est il idempotant?

Oui.

Doit on le faire à chaque fois?

Non.

Il faut un playbook par action longue et/ou dangereuse.

!SLIDE
# Agnostique

Ansible se fiche bien de votre distribution.

Conçu sur RedHat, je l'utilise sans soucis sous Debian.

Les systèmes les plus exotiques ont leur module, et les BSD ne sont pas oubliés.

!SLIDE
## Packages

Les modules utilisent avec *parcimonie* des paquets systèmes.

Il faut les installer explicitement avant d'utiliser le module.

Certains modules sont trop vieux dans les distributions conservatrices. Pymongo dans Debian.

!SLIDE
## Recettes agnostiques

Il est utopique de penser trouver des roles tout pret, fonctionnant sur toutes les plateformes.

Il est crédible d'écrire ses recettes pour gérer quelques OS sans heurts.

!SLIDE
#Actions en ping-pong

Certaines actions nécessitent des allers-retours, mise en place d'un maître, puis connexion de son esclave.

Ansible propose la notion de *délégation* pour ça.

Il est sage d'utiliser des assertions, avec *wait_for*, par exemple, ou les attributs *until* et *retries*.
