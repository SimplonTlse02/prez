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
</style>

ES6 101
---
---

## ES6 aka ES2015 aka ES next

Nouvelle version de javascript !== nouveau language

---
ES : Ecma Script
---
Version supportée dans les navigateurs : ES 5.1

---

Support partiel dans Chrome & Firefox
(ne sera jamais supporté apar les anciens navigateurs)

---

# Pas grave !
car on peut **transpiler**

---

## **transpiler** 
\tʁɑ̃s.paj.lœʁ\ *nom commun masculin*

(Anglicisme informatique) Logiciel traduisant du code d’un langage à un autre.

#### Synonymes
- compilateur source à source

---

## **transpiler** 
\tʁɑ̃s.pi.le\ verbe du 1er groupe (conjugaison) transitif

Convertir du code d’un langage à un autre.

source : [Wikitionary](https://fr.wiktionary.org/wiki/transpiler)

---

# Les nouveautés 

---

## Les fonctions fléchées
*arrow functions*

---
```
$('button').on('click', (event)=>{
	console.log(this)
});

```
---
Equivalent à
```
$('button').on('click', function(event){
	console.log(this)
}.bind(this));

```

---

## Objets simplifiés
*Objects literals*

---

```
var me = {
    hobby: 'raspberry',
    say(){
    	console.log('I like '+this.hobby)
    }
}
```

---

## Templates

---

```
var foo = "variables";

var template = `Je suis un template, avec un backtick
et non pas une apostrophe, je peux tenir sur plusieurs
lignes et aussicontenir des ${foo} !`;
```
---

## Destructuration
*destructuring*

---
```
var [a, b] = [1, 2];

a === 1

b === 2
```

---
```
var {foo, bar} = {foo : 'stuff', bar: 'things' };

foo === 'stuff'

bar === 'things'
```


---
```
var {foo, bar} = { bar: 'things' };

foo === undefined

bar === 'things'
```

---

## Arguments par défaut

---
```
function hello(person: 'you'){
	console.log('hello '+person);
}

hello('Tom'); //hello Tom

hello(): // hello you
```
---

## Déclaration de portée locale
*local scope*

---

`let` is the new `var`

```
if(something === true) {
	let a = 2;
}

console.log(a); //undefined
```

---

et pleins d'autres choses ! Cette prez n'est pas exhaustive !
 
Pour en savoir plus : [ES6 CheatShet](https://es6cheatsheet.com/)
Pour tester facilement : [Babel - try it out](http://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=latest%2Creact%2Cstage-2&experimental=false&loose=false&spec=false&code=%5B1%2C2%2C3%5D.map(n%20%3D%3E%20n%20%2B%201)%3B&playground=true)
