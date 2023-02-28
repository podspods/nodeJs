# CheatSheet

## installation

```sh
npm init -y
npm i dotenv
npm i -D typescript @types/node  nodemon concurrenly
```

## config

### créer .gitignore
et y metre dedans les fichiers à ignorer : au moins les node_modules

```sh
echo "dist/" >> .gitignore
echo "node_modules/" >> .gitignore
echo "package-lock.json" >> .gitignore
```

### modification de la configuration dans tsconfig.json

```sh
npx tsc --init
```

puis modifer `tsconfig.json`

```json
 "rootDir": "./src",
 "outDir": "./dist",
```

### modification de la configuration dans package.json

```json
 "watch:typescript": "npx tsc --watch",
 "watch:app": "npx nodemon dist/index.js",
  "start": "npx concurrently npm:watch:typescript npm:watch:app"
```

démarrage de l'application

```sh
npm run start

```

## autre commande pour information

lancement de l'application
initialise le fichier `tsconfig.json`

```sh
npx tsc --init
```

lancer l'application index.js

```sh
node dist/index.js
```

rootDir = répertoire des fichier source (_.ts)
outDir = répertoire des fichier cible (_.js)

compiler tous les fichiers du répertoire source et les mettre dans le répertoire cible

```sh
npx tsc
```

Option précompilation à chaque modification (enregistrement).

```sh
npx tsc --watch
```

npm permet de creer des commandes (script)

nodemon : surveille le fichier et s'il change alors l'excuter

```sh
nmp i nodemon
```

exécution

```sh
node  dist/index.js
```

attention : penser à lancer la compilation `npx tsc --watch`
pour le rafraichissement Live

lancer les commandes en parallèle
package `concurrently`

```sh
npm i concurrently
```
