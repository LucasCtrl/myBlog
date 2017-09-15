---
title: Hello World
categories:
- La vie du blog
tags:
- hexo
- La vie du blog
photos: https://blog.lucasalt.fr/img/hexo-logo.png
---

Aujourd'hui, j'ouvre mon blog. Il est propulsé par Hexo, un petit générateur de site web statique. C'est un peu déstabilisant au début, mais on s'y fait rapidement. C'est un peu comme Jekyll sauf que celui-ci fonctionne avec Node à contratio de Jekyll qui lui fonctionne avec Ruby. C'est un gain de temps au niveau de l'installation, car node est pratiquement sur toutes les machines Linux, donc il suffit juste de mettre à jour node ainsi que npm.

Au niveau de l'installation, rien de plus simple. Il y a une [documentation](https://hexo.io/docs/) relativement claire et précise et une mise à jour presque constante du framework, qui lui est en open source sur [GitHub](https://github.com/hexojs/hexo/).


Pour installer Hexo, rien de plus simple !


#### On installe Hexo globalement sur la machine
```
npm install hexo-cli -g
```

#### Puis on commence à créer le blog
```bash
$ hexo init NOMDUBLOG # on crée le blog
$ cd NOMDUBLOG # on va dans le dossier de celui-ci
$ npm install # on installe toutes le dépenses du blog pour qu'il puisse tourner normalement
$ hexo serve # et on lance une petite preview du site
```

#### Pour finir on peut rajouter des articles
```bash
$ hexo new 'post|draft|page' "Titre du post"
# On demande à ce qu'Hexo nous crée un nouveau billet|brouillon|page
```

Ensuite, on peut s'amuser à modifier le template de base ou alors télécharger un nouveau template dans la rubrique dédiée à cela. Personnellement, j'ai gardé le theme de base qui est le _landscape_ et je l'ai légèrement modifié à ma sauce.