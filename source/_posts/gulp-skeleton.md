---
title: Gulp, un outil fantastique
date:
categories:
- Développement
tags:
- gulp
- js
- tutoriel
photos:
---

Aujourd'hui , nous allons parler de développement front-end, ou plutôt d'un outil pour le développement. J'appel ... Gulp !  Un outil d'automatisation qui éxecute les taches que nous lui donnont. Personnellement, je l'utilise pour la majorité des sites que je développe car il me permet de créer un petit serveur web avec BrowserSync, d'utiliser SASS, Pug et bien d'autres choses. Je présenterai mon environnement de travaille plus en profondeur à la fin de l'article.

<strong>Mais c'est quoi Gulp ?</strong>
Gulp est un task runner qui permet d'optimiser le temps de travail. Il ne va pas coder à votre place mais va plutôt vous faire gagner du temps lors de la compilation de vos fichiers. Par exemple, il vous permet de minifier automatiquement votre CSS lorsque vous sauvegardé votre fichier.

<strong>Et ça fonctionne comment ?</strong>
Gulp fonctionne avec NodeJS (pour voir comment installer Node, vous pouvez lire [cet article](https://blog.lucasalt.fr/botdiscord/)). Pour ajouter des taches et optimiser votre temps de travail, vous avez plein de package disponible sur [github](https://github.com/) ou directement sur le site de [Gulp](https://gulpjs.org). Dans la majorité des cas, les packages fonctionnant avec Gulp commences par `gulp-nomdupackage`

