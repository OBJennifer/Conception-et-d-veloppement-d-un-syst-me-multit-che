# Conception-et-d-veloppement-d-un-syst-me-multit-che
Gestion automatisé des télévisions dans une maison intelligente 

Résumé du projet ( Abstract) : Noys nous proposons de gérer automatique les télévisions dans une maison intelligente. Uniquement allumées en journée avec un cycle de 2 heures, seules 2 télévisions peuvent s'allumer en même temps. Et pour prévenir d'une éventuelle infraction, un message d'urgence est programmé pour s'afficher sur la télévision principale.

Code et Simulation du projet (Lien Wokwi) : https://wokwi.com/projects/398558043039519745


Membre du Groupe : ....


----------------------------------------- Rappel des consignes ------------------------------------------------

Le but de ce projet est de concevoir et développer un système temps réel et multitâche utilisant une carte ESP32 avec le système d'exploitation FreeRTOS. L'objectif du système est de contrôler automatiquement les écrans d'une maison intelligente en fonction de certaines contraintes temporelles et logiques spécifiques qui sont définies ainsi :

1. Pendant la journée, seulement deux télévisions parmi trois peuvent être allumées simultanément. Une même télévision peut être allumée plusieurs fois pendant la journée.
2. Si une télévision est allumée, elle doit s'éteindre automatiquement après un délai maximum de deux heures pour économiser de l'énergie.
3. En cas de détection d'intrusion à la maison, un message d'alerte doit être affiché en urgence sur l'écran principal numéro 1 de la maison.
4. Si une télévision est allumée et qu'un message d'urgence doit être affiché, il faut d'abord éteindre la télévision, puis la rallumer avant d'afficher le message.
5. Pendant la nuit, toutes les télévisions doivent s'éteindre automatiquement, sauf en cas d'affichage d'un message d'urgence.

Pour la simulation et l'outil de développement, nous utiliserons le simulateur en ligne WOKWI avec la carte de traitement ESP32. Pour détecter la luminosité ambiante, nous utiliserons un capteur de luminosité LDR (photoresistor). Pour simuler les écrans de télévision, nous utiliserons des écrans LCD avec le module I2C. Enfin, pour simuler l'entrée de l'intrus, nous utiliserons un capteur de mouvement.


Question 1 : Est-ce que ce système est un système temps réel et multi-tâche ? Justifiez. (Cette question est similaire à celle que je vous ai posée lors du TP 2)

Question 2 : Réalisez la modélisation par Réseau de Petri de ce système.

Question 3 : Grâce au Réseau de Petri, énumérez vos tâches ainsi que leurs propriétés.

Par défaut, FreeRTOS utilise l'ordonnanceur ROUND ROBIN en mode préemptif. Il faudra donc programmer manuellement les priorités des tâches. Contrairement aux autres algorithmes comme EDF, RMA ou DMA qui assignent automatiquement les priorités.

Question 4 : Programmez de manière concurrentielle (en utilisant que l'un des deux coeurs de ESP) et effectuez la simulation de ce système via WOKWI.

Question 5 : Vérifiez votre système (y a-t-il des bugs ? ) et corrigez ces derniers.
