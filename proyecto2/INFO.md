# Curso de Desarrollo Web

## Proyecto 2 - Tienda Virtual

Para este proyecto realizaremos una Tienda Virtual con CSS Grid

## Commit Nro 1 - v0.1

### Tabla de Cambios

| **Archivos Nuevos**                                          | Archivos Editados                                         |
| ------------------------------------------------------------ | --------------------------------------------------------- |
| index.html<br />index.css<br />normalize.css<br />INFO.md<br />../img | index.html<br />index.css<br />normalize.css<br />INFO.md |

### Cambios

Inicializacion del proyecto. Añadimos normalize y creamos algunas variables globales en CSS:

```css
/* Globales del root*/
:root {
	--primary: #FACC28;
	--darkPrimary: #D9AE15;
	--lightPrimary: #FDE488;
	--secondary: #49456D;
	--darkSecondary: #28263D;
	--black: #14131E;
	--white: #FEF8E3;
	--principalFont: 'Lato', sans-serif;
}

html {
	box-sizing: border-box;
	font-size: 100%; /* 16px = 1rem */
}

*, *:before, *:after {
  -webkit-box-sizing: border-box; 
  -moz-box-sizing: border-box; 
  box-sizing: border-box;
}

/* Globales del CSS */

body {
	background-color: var(--darkSecondary);
	font-family: var(principalFont);
	font-weight: 400;
	line-height: 1.75;
	color: #FEF8E3;
}

p {
	margin-bottom: 1rem;
}

a {
	text-decoration: none;
}

img {
	width: 100%;
}

.container {
	max-width: 120rem;
	margin: 0 auto;
}

h1, h2, h3, h4, h5 {
  margin: 3rem 0 1.38rem;
  font-family: var(principalFont);
  font-weight: 900;
  line-height: 1.3;
}

h1 {
  margin-top: 0;
  font-size: 3.052rem;
}

h2 {
	font-size: 2.441rem;
}

h3 {
	font-size: 1.953rem;
}

h4 {
	font-size: 1.563rem;
}

h5 {
	font-size: 1.25rem;
}
```

------

