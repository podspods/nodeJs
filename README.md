# nodeJs

lun. 27 févr. 2023 08:54:14 CET

[CheatSheet](./cheatSheet.md)
[support de cours Djef](https://slides.com/davidjegat-1/nodejs-mongodb/fullscreen#/2)

## Back end

1. serveur
2. infrastructure
3. Bdd
4. sécurite

## Serveur Physique

hardward, connecté 24/24

## Serveur logique

serveur de base de donnée
mysql, postgres, mongodb etc.

ping pour récupere l'adresse ip et en suite
geolocalisation.com

[repository de david](https://github.com/Djeg/formation-nodejs-mongo/tree/session/27-02-23/03-03-23)

Installation :

```sh
    node --version
    npm --version

```

## Projet javascrip

contient le fichier `package.json` pour configurer le projet

tracert l'hôte pour récupérer l'adresse Ip

    tracert www.google.com

ensuite utiliser geolocatisation.com pour connaitre l'emplacement physique

![List des ports](./cours/image/tableau-ports-connexion.webp)

[info ici](https://www.malekal.com/liste-des-ports-ports-reseaux-de-connexion-et-ce-que-cest/)

installation de la structure du projet de base

```sh
npm init -y

```

installation de typescript

```sh
npm i -D typescript @types/node
```

lancement de l'application

```sh
node index.js
```

créer .gitignore
et y metre dedans les fichiers à ignorer : au moins les node_modules

```sh
touch .gitignore
```

initialiser typescript (creation de trsconfig.json)

```sh
npx tsc --init
```

option type script
rootDir en général src
outDir en général dist (pour distribué) qui sera mis dans .gitignore

compiler l'ensemble des fichiers (dans le répertoire `src`) vers le répertoire `dist`

```sh
npx tsc
```

Option précompilation à chaque modification (enregistrement).

```sh
npx tsc --watch
```

npm permet de creer des commandes (script)

a mettre dans package.json

nodemon : surveille le fichier et s'il change alors l'excuter
installation

```sh
npm i -D nodemon
```

exécution

```sh
node  dist/index.js
```

attention : penser à lancer la compilation `npx tsc --watch`
pour le rafraichissement Live

lancer les commandes en parallèle

```sh
npm i -D concurrenly
```

installation de la configuration

```sh
npm i dotenv
```

utilisation
dans le package.json

```json
"start" : npx nodemon -r dotenv/config dist/index.js

```

va parser le fichier .env pour trouver les variables d'environnement

```js
process.env.<NOM_VAR_ENV>
```

```sh
npm i dotenv
```

attention : fichier .env à mettre dans `.gitignore`

à la place créer un fichier .env.dist et à l place mettre les valeurs d'exemple

# théorie du backend

serveur http
`express` : bibliothèque de server logique n'est plus maintenu et remplacé par `fastify` :

ou alors utiliser un framework

voir schéma .

comment ca marche ?

1. fichier texte pour une request GET
2. fichier texte pour une response POST

5 methode
GET : obtenir
POST : créer
DELETE : suppriner
PATCH : modification partiel
PUT : modification global

découpe d'une requette

1. méthode
2. url
3. métadonnée header coockie
4. body (html, json,png pdf, doc etc.)

découpe d'une réponse

1. version de http utilisé
2. code status http
3. métadonnée
4. Body

pour creer un serveur http avec nodejs

utilisation de fastify

installation

```sh
npm i fastify
```

```js
import fastify from "fastify";
const app = fastify();
```

```js
app.listen({port:5353,host: '127.0.0.1'}), () => {
console.Log ("le serveur a démarré sur l'adresse hoste et le port)
}
```

déclarer les routes (ressource)
exemple

app.get (<RESSOURCE>), FONCTION_A_EXECUTER)

```js
app.get("/"), ()=> code_a_executer)

```
