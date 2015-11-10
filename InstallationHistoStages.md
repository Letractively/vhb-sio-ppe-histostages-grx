L'application web de consultation de l'historique des stages sera opérationnelle après avoir suivi les deux étapes suivantes. On suppose ici que le serveur web hébergeant les scripts PHP et le serveur de base de données tournent sur la même machine.

# Installation des scripts PHP #

  * Téléchargez l'archive !Appli-HistoStages-Vx.y.zip sous l'onglet Downloads.
  * Dézippez ce fichier sous le répertoire racine du serveur web utilisé, par exemple c:\xampp\htdocs dans le cas du serveur web Apache inclus dans le package xampp.

# Installation de la base de données #
  * Assurez-vous d'avoir démarré votre serveur de données MySql local
  * Lancez l'outil client de votre choix pour administrer votre serveur MySql, soit MySql WorkBench ou l'application web PhpMyAdmin.
  * Se connecter sous le compte root du serveur MySql ou tout autre compte ayant le droit de créer une base de données, un compte utilisateur et lui attribuer des droits.
  * Importez le fichier createSchemaBDStages.sql qui va créer la base de données de nom HistoStages, le compte utilisateur stssio et affecter à ce dernier tous les droits sur la base HistoStages.
  * Importez le fichier insertDonneesBDStages\_Tests.sql qui va alimenter les lignes des tables de la base de données HistoStages.

# Vérification du bon fonctionnement de l'application web #
  * Lancez un navigateur sur un poste distant ou non de celui qui héberge l'application web et la base de données
  * Saisir l'url http://monServeur/Intranet/Accueil.php et vérifier que la page qui s'affiche soit la page d'accueil de l'application sans message d'erreur

# Messages d'erreur sur la page d'accueil #
  * Echec de la connexion au serveur MySql : vérifiez que votre serveur MySql est bien démarré, que le nom d'hôte qui l'héberge est bien celui  indiqué dans la fonction connect du fichier gestionBase.inc.php, idem pour le nom de compte MySql et son mot de passe.
  * La base de données stsig est inexistante ou non accessible : vérifiez l'orthographe et la casse du nom de la base de données indiqué dans la fonction selectBase du fichier 