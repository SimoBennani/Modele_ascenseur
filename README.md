# Modele_ascenseur

Ce banc de TP est constitué, comme tout automatisme, d'une partie commande et d'une
partie opérative. La partie commande est assurée par un automate M340 de chez SCHNEIDER.
Cet automate est muni d'une interface permettant de le programmer par l'intermédiaire d'un PC
à l’aide du logiciel Unity Pro. La partie opérative est constituée d'une maquette miniaturisée
simulant un ascenseur 5 étages, et permettant différents modes de gestion des montées et
descentes.

# La partie Commande : L'automate shneider M340

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

# Gestion de l’ascenseur

Un ascenseur peut fonctionner suivant différents types de manœuvres qui peuvent être
plus ou moins sophistiquées. Les manœuvres les plus usuelles sont : la manœuvre à blocage, la
manœuvre collective descente ou collective montée, et la manœuvre collective montée -
descente.

La manœuvre à blocage :
Les utilisateurs disposent :

- d’une commande cabine : un bouton poussoir par étage
- des appels paliers : un bouton poussoir par étage

Il n’y a aucune priorité entre les appels étages. Lorsqu’un ordre est enregistré (suite à
un appel palier ou à une commande depuis la cabine), il est exécuté quelles que soient
les autres demandes effectuées par les utilisateurs.
La cabine est prioritaire 4 secondes sur les appels paliers. Durant ces 4 secondes, les
appels paliers ne sont pas pris en compte. La cabine doit s’arrêter au moins trois
secondes à l’arrivée à l’étage demandé pour permettre la circulation des usagers.
La manœuvre collective descente :
Les utilisateurs disposent :
- d’une commande cabine : un bouton poussoir par étage
- des appels paliers : un bouton poussoir par étage
Dans ce type de manœuvre on considère que, dans la majorité des cas, les personnes
quittent la rue pour se rendre à un étage, ou inversement quittent un étage pour se rendre
dans la rue. C’est le cas des immeubles d’habitation où le trafic entre les étages est peu
important. L’ascenseur ne s’arrête aux étages intermédiaires que pour prendre un
passager supplémentaire qui descend.
La cabine est prioritaire 4 secondes sur les appels paliers. Durant ces 4 secondes, les
appels paliers ne sont pas pris en compte.
Pour cette manœuvre, tous les appels sont enregistrés et mémorisés quel que soit le
contexte dans lequel se trouve l’ascenseur.
D’autre part, dans le cas où plusieurs appels paliers sont enregistrés, la cabine doit se
rendre à l’étage le plus haut parmi ceux demandés, ceci afin de prendre ensuite les
personnes qui descendent (et afin que les étages supérieurs n’attendent pas éternellement
l’ascenseur).

La manœuvre collective montée – descente :

Cette manœuvre correspond au fonctionnement de l’ascenseur d’un immeuble de
bureaux. Le trafic entre les étages est important. Tous les boutons poussoirs de palier
sont utilisés (1 pour la demande de montée, 1 pour la demande de descente).
L’ascenseur s’arrête pour répondre à un appel en cas de correspondance entre le type
d’appel (montée ou descente) et le mouvement en cours. Dans le cas de plusieurs appels
paliers montée, la cabine doit se rendre à l’étage le plus bas parmi ceux demandés. Les
autres appels sont traités pendant la montée (de la même façon que pour les appels
descente de la manœuvre précédente).
