# Paramétrage du plugin

Cette étape est la deuxième du processus d'installation du plugin ZiGate.

Vous devez donc avoir suivi et terminé l'[étape 1 Installation du plugin](Plugin_Installation.md)



## Le paramétrage

* Ouvrir __DomoticZ__ dans votre navigateur

* Aller dans le menu __Configuration__ puis __Matériel__
* Pour ajouter le plugin ZiGate, renseigner les informations suivantes :

| Paramètre    | Description | Information |
| ------------ | ------------------ | ----------- |
| __Nom__                  | Renseigner un Nom à la ZiGate  | Si vous utiliser plusieurs ZiGate, vous aurez besoin de plusieurs instances du matériel ZiGate et le nom permettra de les identifier.<br/><br/>Il est conseillé de ne pas mettre d'espace ou de caractère spécial dans le nom du plugin. Ce nom peut être utiliser dans une URL et un espace ou des caractères spéciaux peuvent générer des problèmes. |
| __Type__                 | Sélectionner `ZiGate plugin` | Si ZiGate plugin n'apparait pas en bas de la liste, c'est que le plugin n'est pas correctement installé.
| ZiGate Model         | Sélectionner le modèle de ZiGate | - ZiGate (modèle V1)<br/> - ZiGate+ (modèle V2)|
| ZiGate Communication         | Sélectionner mode de communication | -  USB<br/>-  DIN<br/>- PI<br/>- TCPIP (wifi ou ethernet)<br/>- Aucun|
| __IP__                   | Renseigner l'IP de la ZiGate | Pour le mode TCPIP uniquement<br/>Laisser 0.0.0.0 pour les autres modes |
| __Port__                 | Renseigner le Port de la ZiGate (9999 par défaut)| Pour le mode TCPIP uniquement<br/>Laisser 9999 pour les autres modes |
| __Port série__           | Sélectionner le port USB sur lequel est branché la ZiGate | Penser à fixer le port de vos équipements usb [Méthode persistent USB](https://easydomoticz.com/mon-premier-peripherique-z-wave-2)|
| __Initialize ZiGate (Erase Memory)__ `Erase PDM` | Sélectionner True pour initialiser la ZiGate avec les paramètres du plugin (False par défaut). <br/>A __activer obligatoirement__ lors de la configuration initiale (ou après un Erase EEPROM). | __ATTENTION :__ L'activation va effacer toutes des informations d'appairage de la ZiGate.<br/> Redémarrer le plugin pour lancer l'initialisation. Vérifier que le paramètre est à l'état False après le redémarrage. |
| __Port for Web Admin GUI__| Renseigner le port pour accéder à l'administration web du plugin (9440 par défaut). | A modifier en cas d'utilisation de plusieurs instances du plugin. |
| __Verbors and Debuging__ | Sélectionner le niveau du log du plugin (Aucun par défaut) |

* Si c'est pour la création du plugin, mettre Initialize ZiGate à __True__, sinon toujours laisser à __False__ (ce paramètre efface les informations de la ZiGate).

* Cliquer sur __Ajouter__.

La ligne correspondante à votre plugin ZiGate (avec le nom défini) est normalement apparue dans la liste des matériels.

* Cliquer sur la ligne de votre plugin ZiGate.

__ATTENTION :__ à partir de maintenant, il ne faut surtout plus cliquer sur le bouton __Ajouter__ en bas : cela aurait pour effet de dupliquer le plugin. Remontez toujours en haut des paramètres pour utiliser le bouton __Modifier__.

* Mettre __Initialize ZiGate (Erase Memory)__ à __False__.
* Décoché __Activé__ pour désactiver le plugin.
* Cliquer sur __Modifier__ (ne pas cliquer sur Ajouter car cela dupliquera le plugin).

* Recliquer sur la ligne du plugin ZiGate.
* Recocher __Activé__ pour réactiver le plugin.
* Cliquer sur __Modifier__ pour relancer le plugin.

Vérifier les logs que le plugin ZiGate s'initialise correctement.

![Domoticz Hardware Menu for Plugin](Images/FR_Plugin-Parametrage.png)

*Cette image est susceptible d'avoir évolué depuis l'écriture de cette documentation.*

## Les widgets du plugin

A l'installation, le plugin créé 2 widgets dans l'onglet __Mesures__ de DomoticZ.

![Administration Widgets](../Images/Widgets_Admin.png)

### Widget Statut

Le widget s'appelle 'Zigate Status XX' avec XX correspondant au numéro de matériel du plugin ZiGate. Il indiquera l'état du plugin. Le Log du widget permettra d'avoir l'historique des états du plugins.

Les différents états possibles sont :

| État | Couleur | Description |
| ---- | ------- | ----------- |
| Off | Rouge | Le plugin s'éteint ou il y a un problème de communication |
| Démarrage | Gris | Le plugin démarre |
| Prêt | Vert | Le plugin est en fonctionnement normal |
| Appairage | Ambre | Le plugin est en mode appairage |
| Saturation | Ambre | Le plugin sature : il peut y avoir des délais de transmissions rallongés |


### Widget Texte

Liste non-exhaustive des notifications :

* Succès d'appairage
* Échec d'appairage
* Exclusion d'un objet
* Rapport de topologie réseau disponible
* Rapport d'interférences réseau disponible
* Problème réseau
* Canal ZigBee

Un exemple de l'historique des notifications (en anglais)

![Notification Widgets](../Images/Widget_Notifications.png)


Si tout semble fonctionner normalement, passer à l'[étape 3 Configuration du plugin](Plugin_Configuration.md)
