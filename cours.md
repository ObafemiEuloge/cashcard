## Base de donées intégrée

Une BDD intégrée est base de données qui est intégrée directement dans une application logicielle et fonctionne en mode embarqué. Cela signifie qu'elle est gérée et utilisée par l'application elle-même, sans nécessiter de serveur de base de données externe. Ces BDD sont stockées localement sur le système de l'utilisateur ou dans le répertoire de l'application, et elles sont généralement légères et optimisées pour être rapides et efficaces.

## H2

H2 est l'un des exemples les plus couramment utilisés de BDD intégrées. H2 es tune BDD relationelle écrite en Java qui peut être embarquée dans une application Spring. Elle prend en charge le mode mémoire (les données sont stockées en mémoire et sont perdues lorsque l'application est arrêtée) ainsi que le mode fichier (les données sont stockées dans un fichier sur le sytème de fichiers de l'ordinateur)

## Optional

`Optional` est une classe générique qui peut contenir soit une valeur non nulle, soit aucune valeur (c'est-à-dire vide). L'utilisation plus explicite en indiquant clairement qu'une valeur peut être absente et en forçant les développeurs à traiter ce cas

## Utilisations courantes de Optionzl

1. Eviter les `NullPointerException`: 
    En utilisant "Optional" noud pouvons éviter les erreurs de pointer nul en vérifiant d'abord si une valeur est preésente avant d'essayer d'y accéder . Par exemeple : 


    ```java 

        Optional<String> valeurOptional = //... obtenir une valeur, peut-être sous
    
        if(valeurOptional.isPresent()) {
            String valeur = valeurOptional.get(); // récupère la valeur présente 
            
            // On fait quelque chose en cas d'absence de valeur.
        } else {
            // On fait quelque chose en cas d'absence.
        }

    ```

2. Chaînage de méthodes
    Nous pouvons chaîner des méthodes pour effectuer des opérations sur la valeur si elle présente, ou simplement ignorer l'opération si la valeur est absente

    ```java
        Optional<String> valeur = // ... obtenir une valeur peut-être nulle

        valeur.isPresent(v -> System.out.println("Valeur présnte : " + v))
    ```

3. Traitement des valeurs par défaut
   Nous pouvons spécifier une valeur par défaut à utiliser si la valeur `Optional` est absente, en utilisant la méthode `orElse`

   ```java
        Optional<String> valeur = // ... obtenir une valeur nulle

        valeur.orElse("Valeur par défaut")
   ```