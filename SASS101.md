# SASS
## Syntactically Awesome StyleSheets

---


```bash
sass --watch chemin/vers/scss:public/css
```

---

# SASS vs SCSS

---

# Pourquoi SASS, c'est génialement formidable ?

---
# Variables
```
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```
---
# Règles imbriquées (nesting)
```
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```
---
# Règles imbriquées (nesting)
## Compilé
```
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav li {
  display: inline-block;
}

nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```
---
# Import

```
// _reset.scss

html,
body {
  margin: 0;
  padding: 0;
}
```

```
// base.scss

@import 'reset';

body {
  font: 100% Helvetica, sans-serif;
  background-color: #efefef;
}
```
---
# Mixins (logicless functions)
```
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }
```
---
# Héritage
```
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}

.error {
  @extend .message;
  border-color: red;
}
```
---
# Les Maths
```
.container { width: 100%; }


article[role="main"] {
  float: left;
  width: 600px / 960px * 100%;
}

aside[role="complementary"] {
  float: right;
  width: 300px / 960px * 100%;
}
```
---
# Aller plus loin
---
## Faire référence au parent avec `&`
```
a {
	color:#fff;
    &:hover {
    	color:#000;
    }
}
```
--- 
## Modifier la teinte d'une couleur
```
$color: #ffee33;
a {
   color: lighten($color, 10%);
   text-shadow: 0 1px 0 darken($color, 20%);
}
```