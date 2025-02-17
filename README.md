# Quête les logs

1. **Installation du Serveur Web sur une VM Linux**

- Choix de la distribution :
  - Utiliser une distribution courante comme **Ubuntu** ou **Debian** pour bénéficier d'une large documentation et d'une communauté active.

**Installation d'Apache :**
 Installer l'un des serveurs web via le gestionnaire de paquets (apt-get pour Ubuntu/Debian) et vérifier son fonctionnement.

**2. Configuration du Logging**
- Logs d'accès et d'erreurs :
    Apache : Les logs sont généralement situés dans /var/log/apache2/ avec access.log pour les accès et error.log pour les erreurs.

    Personnalisation :
- Modifier la configuration pour adapter le format des logs à vos besoins, par exemple en ajoutant des informations supplémentaires comme l'agent utilisateur ou le référent.

**3. Génération de Trafic**
    Utilisation de curl ou d'un navigateur :
    Envoyer des requêtes au serveur pour générer des entrées dans les logs.
    Scénarios à tester :
        Requête réussie (200) : Accéder à la page d'accueil.
        Erreur 404 : Tenter d'accéder à une page inexistante.

**4. Analyse de Logs**

**Extraction des requêtes réussies :**
Utiliser des commandes comme `grep` pour filtrer les lignes contenant le code `200`.
![erreur 200](https://github.com/ff1337p/leslogs/blob/main/imglg/erreur200.png)
    
**Identification des erreurs `404` :**
De même, filtrer les lignes comportant le code 404 pour identifier les pages non trouvées.
![erreur 404](https://github.com/ff1337p/leslogs/blob/main/imglg/erreur404.png)
   
**Détection des adresses IP les plus fréquentes :**
Combiner **awk** sort et **uniq** pour compter le nombre d'accès par IP et identifier celles les plus actives.

![awk](https://github.com/ff1337p/leslogs/blob/main/imglg/awk.png)

