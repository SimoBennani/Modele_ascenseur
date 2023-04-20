# Modele_ascenseur

Ce banc de TP est constitué, comme tout automatisme, d'une partie commande et d'une
partie opérative. La partie commande est assurée par un automate M340 de chez SCHNEIDER.
Cet automate est muni d'une interface permettant de le programmer par l'intermédiaire d'un PC
à l’aide du logiciel Unity Pro. La partie opérative est constituée d'une maquette miniaturisée
simulant un ascenseur 5 étages, et permettant différents modes de gestion des montées et
descentes.

#La partie Commande : L'automate shneider M340

La configuration de l'automate M340 dont nous disposons est la suivante :
- 1 CPS 2000 : bloc d’alimentation 24V CC
- Rack 0 : 1 UC BMX P34 1000 V 2.50 : unité centrale avec prise terminal permettant la
liaison avec le PC comprenant une zone mémoire de 64 KO
- Rack 2 et 3 : 2 modules DRA1605 de 16 sorties relais tout ou rien
- Rack 1 et 4 : 2 modules DDI 1602 de 16 entrées tout ou rien

Les utilisateurs disposent :

- d’une commande cabine : un bouton poussoir par étage
- des appels paliers : un bouton poussoir par étage

Il n’y a aucune priorité entre les appels étages. Lorsqu’un ordre est enregistré (suite à
un appel palier ou à une commande depuis la cabine), il est exécuté quelles que soient
les autres demandes effectuées par les utilisateurs.
La cabine est prioritaire 4 secondes sur les appels paliers. Durant ces 4 secondes, les
appels paliers ne sont pas pris en compte. La cabine doit s’arrêter au moins trois
secondes à l’arrivée à l’étage demandé pour permettre la circulation des usagers.
