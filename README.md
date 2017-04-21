# docker-silex
Projet Docker avec Silex

## Modification
Modifier le chemin

    database:
        image: "mysql:latest"
        volumes:
            - "chemin/a/changer/data:/var/lib/mysql"
## Accès aux services
### PhpmyAdmin
    http://localhost:8080

## Mise en place des sources
 ### Création du réperoire src
     # mkdir src
 ### Installer depuis composer le paquet silex
     # composer create-project silex/silex src
    
