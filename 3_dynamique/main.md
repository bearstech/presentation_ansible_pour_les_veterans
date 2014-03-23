!SLIDE
# Facts

Ansible commence une lecture par la collecte des faits :
il récupère un longue liste d'informations sur chacune des machines concernées.

Ces valeurs, comme les adresses IP des différentes interfaces, le nombre de coeurs,
ou la quantité de RAM, permettent d'utilisé des valeurs en dur, mais de manière dynamique.

Il est possible d'utiliser les attributs de la machine concerné par la lecture,
mais aussi les autres faisant partis du groupe.

!SLIDE
# Sans états

Ansible ne conserve pas d'états, ce qui permet d'intervenir à la main sur les machines sans trop de risques.

Une lecture commence par la collecte des faits, et les taches font de même.

Un bon playbook ne doit pas avoir de prérequis, il construit en état, sans a priori sur son état actuel.

!SLIDE
# Agir par le non-agir

Ansible essaye de ne pas agir, il dépense beaucoup d'énergie à simuler une action pour savoir si ça changerait quelques chose de l'appliquer.

Le système de notification participe à cette approche.

Certaines scripts initd et certaines applications s'avère être bugués et pourrisse le coté sans surprise d'Ansible.
