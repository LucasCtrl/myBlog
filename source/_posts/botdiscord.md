---
title: Un bot discord
date: 2017-09-15 15:42:23
categories:
- Développement
tags:
- js
- discord
- bot
photos: https://blog.lucasalt.fr/img/banner/discord-banner.jpg
---

Bon, on change un peu du développement web.<br>
Aujourd'hui je vais vous montrer comment créer votre propre bot discord. C'est un truc relativement simple à faire, mais il faut quand même avoir certaines notions. Dans le cas présent, nous allons en créer un simple à l'aide de _discord.js_. Le bot sera donc codé en javascript.

### Les pré-requis

Il faut avoir quelques petites choses avant de commencer:
* Quelques notions en javascript
* Un IDE ou éditeur type Visual Studio Code ou Atom

### 1) L'installation de tout ce qu'il nous faut

Dans un premier temps, nous allons installer NodeJS (de préférence, la version avec l'annotation _Lastest Features_). Le lien de téléchagement est disponible [ici](https://nodejs.org). Au moment où j'écris l'article, la version de node est la v8.4.0 mais je vous conseille chaudement de prendre la plus récente. Avec l'installation de node, npm (pour _node package manager_) sera installé. Cela servira à gérer les paquets plus tard. Pour être sûr que tout est bien installé, nous allons ouvrir l'invite de commande ou un terminal et y écrire les lignes suivantes :

```bash
node -v
#vous aurez la version de node installé qui apparaitra ici
#exemple: v8.4.0

npm -v
#vous aurez la version de npm installé qui apparaitra ici
#exemple: v5.3.0
```
Si rien n'apparaît, redémarrer votre PC et refaite un essai. Si cela ne fonctionne toujours pas essayé de tout réinstaller.

Dans un second temps, nous allons installer les paquets qui nous servirons à faire fonctionner notre bot. Il nous faudra essentiellement _discord.js_. Pour cela, nous allons créer un dossier sur notre ordinateur (ou l'on veut) et ouvrir l'invite de commande dans ce dossier (clique droit -> ouvrir cmd ici). Sinon pour ceux qui le souhaiteraient, on peut y allé en mode un peu plus hardcore.

```bash
#Changer de disque
#nom du disque suivi d'un double point
D:

#aller dans un dossier
cd nomdudossier
#exemple:
cd Lab/botdiscord
```

Une fois dans le dossier souhaité avec l'invite de commande, il ne nous reste plus qu'à installer le(s) paquet(s) pour créer le bot. Et ensuite on passe au code. Promis !

```bash
#on va juste créer un petit fichier avant de commencer pour ne pas être embêté par la suite
npm init
#cela aura pour but de facilité le travail lors du partage du projet
#mais ça ce n'est pas trop important alors on appuie juste entré à chaque ligne jusqu'au bout

#pour finir, on installe enfin discord.js
#le --save aura pour but de rajouté une ligne dans le fichier
#créé précédement, mais je ne rentrerai pas dans les details maintenant
npm install discord.js --save
```

### 2) Le début du code

Maintenant, on rentre dans le vif du sujet !

Nous allons commencé par créer le token du bot. Il va nous permettre de le faire rejoindre le serveur en tant "qu'utilisateur". Pour cela, nous allons nous rendre sur l'onglet développeur du [site de discord](https://discordapp.com/developers/applications/me). Ensuite, il va falloir créer une nouvelle application avec un nom (celui de votre choix ^^'). Une fois cliquée sur `Create App`, nous allons cliquer sur le bouton bleu `Create a Bot User`. Il faudra ensuite récupérer le token du bot en cliquant sur l'encadré rouge :

![Reveal Token](https://blog.lucasalt.fr/img/articles/createToken.png)

Attention, il est vivement conseillé de ne pas donner votre token. N'importe qui pourrait l'utilisé.

Pour le bot on va faire simple. Pas de commande a rallonge ou des créations de bot du style Mee6. Je vais vous donner le code d'un bloc et vous l'expliquer en parallèle. Pour cela il va falloir créer un fichier dans le dossier dans lequel on a créé le fichier `package.json` et où il y a le dossier `node_modules` que l'on va appeler `app.js`. On va ensuite ouvrir le fichier créé avec son éditeur de texte favori.

```js
// Appel le paquet discord.js
const Discord = require("discord.js");
// Permet de créer un client/utilisateur
const client = new Discord.Client();

// Ce bloc exécute le code au lancement du bot
client.on('ready', () => {
  // Va afficher dans la console le message suivant
  console.log('Je suis bien connecté');
});

// Ce bloc exécute le code lors qu'un message est envoyé
// sur un serveur sur lequel est connecté le bot
client.on('message', msg => {
  // Ici on va détecter si un message contient le mot 'ping'
  if (msg.content === 'ping') {
    // si oui on répond à l'utilisateur en le mentionnant 'pong'
    msg.reply('Pong!');
  }
});

// Ici on rajoute le magnifique token que l'on a récupéré plus haut dans l'article
client.login('token');
```

La base du bot est maintenant réalisé il ne reste plus qu'à rajouter des commandes ainsi que de l'ajouter sur votre propre serveur.

### 3) Houston ! I'm here

Maintenant on va rajouter votre bot sur votre serveur ou sur le serveur d'un de vos amis. C'est la dernière chose à faire avant de le lancer pour pouvoir le tester.

* Dans un premier temps, nous allons ajouter le bot sur notre serveur. Pour cela, il nous faut juste l'ID du bot (id client) qui lui se trouve sur la même page que le token du bot. Dans mon cas je mets la permission d'administrateur à mon bot pour ne pas être dérangé, mais vous pouvez très bien en faire des customs à l'aide du [calculateur de permission](https://discordapi.com/permissions.html). Le site vous génèrera automatiquement un lien d'invitation pour le bot si vous y ajoutez son id client.
* Maintenant que le bot est sur votre serveur, il suffit juste d'exécuter le code. Pour cela, suffit d'ouvrir votre invite de commandes et d'aller dans le dossier du bot (voir plus haut). Une fois dans ce dossier, il suffira d'entrer la ligne suivante :

```bash
node app.js
# Normalement vous devriez voir le message edité plus haut dans le code
```

#### Et voilà votre bot est maintenant opérationnel !! Cela aura pris un peu de temps, mais cela en valait le coup.

### Sources :
Image de une par [Discord](https://discordapp.com/)
Documentation officielle : [https://discord.js.org/#/](https://discord.js.org/#/)
Livre de _AnIdiotsGuide_ : [https://www.gitbook.com/book/anidiotsguide/discord-js-bot-guide/details](https://www.gitbook.com/book/anidiotsguide/discord-js-bot-guide/details)