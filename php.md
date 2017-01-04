<style>
	.slide {
    background-color:#000;
    color:#fff;
    }
    h1, h2, h3, h4, h5 {
   	color: #fff !important;
    }
    .slide pre {
    color:#000;
    }
</style>
<!-- $size: 16:9 -->
# PHP 101

---
<!-- footer: PHP 101 -->
## Génèse

--- 

PHP, Rasmus Ledorf, 1995
Python, Guido Von Rossum, 1991
Ruby, Yukihiro Matsumoto "Matz", 1995

---

## PDM

2010 |	75 %
2013 |	75 %
2016 |	82 %

---

Conçu pour le développement web, peut être aussi utilisé pour des applications en CLI

---

<center>Comme Node, ne vis que dans le contexte du serveur</center>

![center](term-frontendvsbackend.jpeg)

---

## Avantages

---

## Inconvénients

---

# Les Bases

---

Pas de typage

---

- Les variables s'écrivent avec un $ au début
- Les instructions se terminent avec un `;`
- Les fichiers portent l'extension `.php` et le code s'exécute entre les balises `<?php` ET `?>`
- la concaténation se fait avec un point
```
<?php
$foo = "bar";
$fruit = 'pomme';
$pomme = $fruit . ' granny';
$total = 8;
echo "J'ai mangé $foo $pomme"

// va afficher : J'ai mangé 8 pommes granny

/* Ceci est un commentaire
multi-ligne
*/
```

---

On peut insérer du php dans un fichier html (à condition qu'il porte l'extension `.php`)

```html
<div>
	<h1><?php echo myfunc("PHP is awesome") ?></h1>
</div>	

```

---

Si un fichier ne contient que des instructions PHP (donc pas de HTML), il vaut mieux ne pas le fermer avec `?>`

---

Pour débugger le contenu d'une variable, on utilise la fonction `var_dump` (`echo` ne marche pas avec un  tableau)
```php
<?php
$fruits = array('orange', 'pomme', 'poire');
var_dump($fruits);

/*affichera
array(3) { 
    [0]=> string(6) "orange" 
    [1]=> string(5) "pomme" 
    [2]=> string(5) "poire" 
}
*/
```

---

Intégrer un autre fichier est facile !

`header.php`
```
<html>
<head>
	<title><?php echo $pageTitle; ?></title>
    <link src="style.css" />
</head>
<body>
```

`home.php`
```
<?php
$pageTitle = "Welcome home !"
include "header.php";
?>
<h1>Welcome to my awesome Site</h1>
<p>Bla bla bla</p>
<?php
include "footer.php";
```
---
Ce n'est pas la façon optimale de faire, mais en attendant de savoir ce qu'est un moteur de template, on s'en contentera !

---

# Variables superglobales

---

Si on accède à l'url `http://localhost:8000/index.php?page=home&foo=bar`, un tableau géré automatiquement par le moteur de PHP créera le tableau `$_GET`
```
echo $_GET['page']; // affichera home
```
---

Pour un formulaire `<form action="/save.php" method="post">`, on utilisera la superglobale `$_POST` où l'indice du tableau est la valeur de l'attribut `name`

`formulaire.html`
```
<form action="/save.php" method="post">
  <input name="username" />
</form>
```

`save.php`
```
echo $_POST['username'];
```
---

Vérifier l'existence d'une variable ou d'un élément de tableau : `isset`

```
if(isset($pomme)) {
  echo 'la variable $pomme existe et vaut : ' . $pomme;
}

if(!isset($_GET['foo'])) {
  echo 'le querystring ne contient pas foo';
}
```
---

## Au prochain épisode : 
- # manipulation de tableaux et chaîne de caractères
- # gestion des dépendances avec Composer
- # initiation à la POO

---

# Pratique

---

Installer PHP sous ubuntu 16.06/16.10

```bash
sudo apt update
sudo apt install php-fpm php-cli php-json php-mcrypt php-mysql
```

---

Utiliser le serveur interne du moteur PHP (dev only!)
```
php -S 0.0.0.0:8000 -t public
```

---

Practice Time !
