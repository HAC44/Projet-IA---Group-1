# Data Engineer - Instructions

Instructions 1 : 30/09/2024

En tant que Data Engineer, vous devez soumettre un premier livrable, faisant office de premier draft pour une description détaillée du jeu de données du projet (lien de la base de données uniquement accessible avec une adresse eigsica) [https://drive.google.com/drive/folders/12JSV8jCCBftZ5bF6Ci2Lk65XtKiDcolv?usp=sharing] . Ce rapport doit contenir les éléments suivants :

## Informations clés

La region couverte.
Le nombre d'images disponibles.
La taille de chaque image.
Le poids des images en mégaoctets (Mo).
La résolution spatiale, temporelle et spectrale des images.
Le satellite d'origine des images. (Ici Landsat 4 et 8)
La signification des noms de fichiers.
Le format des fichiers ...

## Critique de la Base de Données :
Évaluez les limitations de la base de données. Réfléchissez aux points suivants :

Quelles sont les lacunes potentielles dans les données ?
Y a-t-il des problèmes de qualité ou de couverture ?
Comment ces limitations pourraient-elles affecter le projet ?

## Affichage de la Base de Données 
Écrivez un code pour afficher les images du jeu de données. Par exemple, vous pouvez utiliser le framework Rasterio de Python. 

Date Limite : 07 octobre 2024



----------------------------------------------------------------------------------------------------------------------------------

Instruction 2 : 12/10/2024

Les data engineers doivent en urgence préparer le dataset d'ici ce lundi afin de pouvoir démarrer la phase de labélisation. Vous devez découper, à l’aide de QGIS, une partie du dataset correspondant à environ 10 années d'images. Les coordonnées à utiliser pour le découpage sont les suivantes :

301545.0000, 403215.0000, 3445395.0000, 3547065.0000 [EPSG:32630].

Pour effectuer le découpage de plusieurs fichiers en même temps selon le même cadre, vous pouvez vous inspirer de ce tutoriel :
https://www.youtube.com/watch?v=ffdgVGA_mk4.

Veuillez vous assurer que ce découpage est correctement réalisé avant de transmettre le dataset à l'équipe de labélisation.

Date Limite : 14 octobre 2024

---------------------------------------------------------------------------------------------------------------------------------------------

Instruction 3 : 16/10/2024

Vous êtes invité(e) à finaliser la partie labellisation du nouveau dataset Croper en suivant la méthodologie décrite ci-dessous.

1. **Installation de l'extension SCP** : Veuillez d'abord installer l'extension SCP (Semi-Automatic Classification Plugin) en suivant le tutoriel disponible à cette adresse : [Tuto SCP](https://www.youtube.com/watch?v=uq5ZmX5RXNs). 

2. **Problèmes d'installation** : Si vous rencontrez des problèmes lors de l'installation, vous pouvez mettre à jour la bibliothèque `remotior-sensus` à la dernière version. Pour ce faire, ouvrez l'interface de commande de QGIS :

   - Allez dans le menu `Plugins` > `Python Console`.
   - Dans la console qui s'ouvre, cliquez sur l'icône de la boîte de dialogue (ou utilisez le raccourci Ctrl+Shift+P) pour accéder à l'interface de commande.
   - Tapez la commande suivante et appuyez sur Entrée :

   ```bash
   pip install remotior-sensus --upgrade
   ```

3. **Labellisation des images** : Une fois l'extension installée, suivez les tutoriels pour labelliser vos images :
   - [Tuto pour labelliser les images](https://www.youtube.com/watch?v=7SZDCFXjIbA).
   - Les classes à définir sont : 
     - Oasis (végétation)
     - Eau
     - Erg (Sahara sableux)
     - Reg (Sahara rocheux)
     - Terrain artificiel (panneaux solaires, routes, bâtiments, etc.)
   - Assurez-vous d'exporter les fichiers labellisés au format GeoJSON et que le système de référence de coordonnées (CRS) soit le même que celui utilisé dans votre projet.

Date limite : 21/10/2024


