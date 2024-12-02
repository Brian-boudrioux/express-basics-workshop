# Atelier : Création d'une API avec Express pour la gestion de pistes et d'albums 🎵

[⬅ English version](./README)

## Objectif
Apprendre à créer une API REST simple avec Express.js en implémentant progressivement les fonctionnalités CRUD (Create, Read, Update, Delete). Ce projet se fera dans un unique fichier (index.js) pour simplifier la prise en main. L’objectif est aussi d’encourager l’autonomie en consultant la documentation officielle.

## Prérequis
Avoir Node.js installé sur votre machine. Si ce n'est pas le cas, téléchargez-le depuis Node.js Official.
Installer Express via npm.


## Étape 1 : Initialisation du projet
Créez un dossier pour le projet et initialisez-le :

```bash
npm init -y
```

Installez Express :

```bash
npm install express
```

Definir le type module dans votre package.json :
```json
"type": "module"
```


Créez un fichier index.js qui servira à tout le développement.

## Étape 2 : Mise en place d’un serveur Express
Dans le fichier index.js, configurez un serveur Express minimal.

Consultez la documentation pour démarrer un serveur :
👉 [express hello world](https://expressjs.com/en/starter/hello-world.html)

Créez une route par défaut (GET /) qui retourne une réponse simple pour vérifier que le serveur fonctionne.
Exemple : "Bienvenue sur mon API Express".

Lancez le serveur avec la commande suivante et testez votre route dans un navigateur ou avec un outil comme Postman :

```bash
node --watch index.js
```

## Étape 3 : Ajout des routes pour les pistes (tracks)

### Objectif : Implémentez les routes suivantes :

GET /tracks : Récupère toutes les pistes.
GET /tracks/:id : Récupère une piste par son ID.
POST /tracks : Crée une nouvelle piste.
PUT /tracks/:id : Modifie une piste existante.
DELETE /tracks/:id : Supprime une piste.

### Étapes :

Ajoutez une liste statique de pistes (tableau en mémoire) dans votre fichier index.js.

Exemple :

```js
const tracks = [
  { id: 1, title: 'Track 1', albumId: 1 },
  { id: 2, title: 'Track 2', albumId: 1 }
];
```

Implémentez chaque route dans le fichier.

Consultez la documentation sur les routes :

👉 [Express Routing](https://expressjs.com/en/guide/routing.html)

### Conseils :

Pour GET /tracks : Retournez la liste complète avec res.json(tracks).
Pour GET /tracks/:id : Utilisez req.params pour récupérer l’ID et recherchez la piste correspondante dans le tableau.
Pour POST /tracks : Ajoutez une piste au tableau et gérez les données envoyées par le client via req.body.
Pour PUT /tracks/:id et DELETE /tracks/:id, mettez à jour ou supprimez une piste en fonction de l'ID.

### Points importants :

Activez le middleware express.json() pour lire les données JSON du corps des requêtes.
👉 [Express JSON Middleware](https://masteringjs.io/tutorials/express/express-json)

## Étape 4 : Ajout des routes pour les albums (albums)

### Objectif : Implémentez les fonctionnalités CRUD pour les albums :

GET /albums : Récupère tous les albums.
GET /albums/:id : Récupère un album par son ID.
POST /albums : Crée un nouvel album.
PUT /albums/:id : Modifie un album existant.
DELETE /albums/:id : Supprime un album.

### Étapes :

Créez une liste statique d’albums similaire à celle des pistes.
Ajoutez des routes pour chaque action dans index.js.
Implémentez une route spécifique pour récupérer les pistes d’un album (GET /albums/:id/tracks).

Documentation associée :

👉 [Express Params](https://dev.to/ericlecodeur/nodejs-express-partie-2-route-parameters-3n12)

## Étape 5 : Améliorations et persistance des données

### Objectif : Ajoutez des fonctionnalités avancées comme :

Une validation basique des données envoyées (par exemple, vérifier que le title d'une piste n'est pas vide avant de l’ajouter).
Gérer les erreurs si une piste ou un album n’est pas trouvé.

Documentation utile :

👉 [Error Handling](https://dev.to/srishtikprasad/error-handling-with-express-40pk)

## Étape 6 : Tests de l’API
Testez toutes les routes avec un outil comme Postman, Insomnia ou en utilisant fetch/Axios dans une application front-end simple.
Vérifiez que les données retournées sont correctes et que toutes les fonctionnalités CRUD fonctionnent.

## Étape 7 : Aller plus loin
Structuration du code : Une fois que toutes les fonctionnalités fonctionnent, réfléchissez à structurer le projet (séparation des routes, contrôleurs, modèles).
Documentation supplémentaire :
👉 [Express architecture best practice](https://blog.treblle.com/egergr/)

## Conclusion
Félicitations 🎉 ! Vous avez créé une API REST fonctionnelle en partant de zéro. Vous avez appris à configurer Express, à implémenter des routes, et à manipuler des données côté serveur. En continuant, vous pourrez approfondir en explorant des bases de données comme MongoDB ou PostgreSQL pour une persistance des données robuste.
