INSTALLATION
------------

D�zarchiver le fichier stm32-update-package.zip dans votre dossier personnel sous mac ou Linux,
ou sur votre Bureau sous windows

Le programme pour flasher le microcontroleur est en fait un script python, il faut donc
dans un 1er temps installer l'interpreteur python.

Installation de Python pour Windows :
-------------------------------------

- Dans le dossier stm32-update-package/install/windows, executer python-2.7.2.msi et proc�der
  � l'installation

Installation de Python pour Linux ou Mac :
------------------------------------------

- Python est d�j� probablement install�, si ce n'est pas le cas, l'installer avec le gestionnaire de logiciel integr�
  � votre distribution



Ensuite il faut installer l'extension python "pySerial" permettant de communiquer sur un port s�rie.


Installation de l'extension pySerial pour Windows :
---------------------------------------------------

- Aller dans le dossier stm32-update-package/install/pyserial-2.5
- Executer le script install.bat



Installation de l'extension pySerial pour Linux ou mac :
--------------------------------------------------------

- Ouvrir une ligne de commande (Application/Utilitaires/Terminal sous Mac)
- Aller dans le dossier stm32-update-package, puis dans le sous dossier install/pyserial-2.5 :
  - cd stm32-update-package
  - cd install
  - cd pyserial-2.5
- Puis installer l'extension en executant la commande suivante : python setup.py install
- Fermer l'invite de commande


Ensuite il faut configurer le n� du port s�rie qui va �tre utilis� pour communiquer avec la carte



Configuration du port s�rie sous Windows :
------------------------------------------

- Editer le fichier stm32-update-package/load_windows.bat (clic droit / modifier) et sur la
  1�re ligne remplacer COM1 par le bon COM si c'est n�cessaire
- Si une interface USB/RS232 est utilis�e, aller dans le gestionnaire de p�riph�rique
  windows pour d�terminer le bon N� de COM. 
- Enregistrer le fichier une fois la configuration effectu�e.

Configuration du port s�rie sous Linux ou Mac :
-----------------------------------------------

- Editer le fichier stm32-update-package/load_linux_mac.bash et sur la 3�me ligne indiquer
  le chemin du port s�rie � utiliser
- Sous linux �a va ressembler � port=/dev/ttyS0 ou port=/dev/ttyUSB0 par exemple
- Sous Mac �a va ressembler � ?????



PROCEDURE DE REFLASH
--------------------

- Placer le fichier firmware.bin � flasher dans le dossier stm32-update-package
- Couper l'alimentation du syst�me
- Connecter le syst�me au PC avec le port s�rie
- Sur la carte m�re positionner le jumper de mise en mode boot
- Remettre l'alimentation du syst�me
- Lancer la mise � jour en double cliquant sur le fichier load_windows.bat ou load_linux_mac.bash
- Lorsque la mise � jour fonctionne, une s�rie de ligne de programmation d�file dans la console
- Une fois la mise � jour effectu�e, couper l'alimentation du syst�me
- Retirer le jumper de mise en mode boot
- Remettre l'alimentation


