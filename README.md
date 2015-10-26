# xml-1a

Cours d'initiation à XML

# Dépendances logiciels #

Plate-forme de test : Ubuntu 14.04.2

* `node.js`
* `npm`
* `reveal.js` (Cf. ci-dessous)
* `pandoc` (Cf. ci-dessous)

## Installation de reveal.js ##

### Préalable ###

* Installation de Grunt :

```bash
$ sudo http_proxy=host:port https_proxy=host:port npm install -g grunt-cli
```

### Installation de reveal.js ###

Dans le répertoire du projet :

```bash
$ http_proxy=host:port https_proxy=host:port wget https://github.com/hakimel/reveal.js/archive/3.1.0.zip
$ unzip reveal.js-3.1.0.zip
$ ln -s reveal.js-3.1.0 reveal.js
$ cd reveal.js
# certains répertoires de $HOME/.npm appartiennent à root avec l'installation
# de grunt-cli en global, les re-donner à $USER :
$ sudo chown -R $USER:$(groups $USER | sed -e 's/^.* : //' | cut -d\  -f1) $HOME/.npm/{nopt,minimatch,glob,lodash,inherits}
$ http_proxy=host:port https_proxy=host:port npm install
$ $ grunt cssmin uglify
```

## Dépendance pandoc ##

Il faut installer le paquet `libghc-highlighting-kate-dev`.

Il est possible de tester la génération d'un diaporama avec :

```bash
$ pandoc -s -t revealjs -i --slide-level=1 --self-contained -o README.html README.md
```

Puis d'ouvrir le fichier `README.html` dans un navigateur.

