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

## Commit 2 - v0.2

### Tabla de Cambios

| Archivos Nuevos | Archivos Editados         |
| --------------- | ------------------------- |
| None            | index.html<br />index.css |

### Cambios 

Se añadió la estructura en HTML del header y el nav, asi como sus estilos CSS

* HTML:

```html
<header class="header">
		<a href="index.html">
			<img class="header__logo" src="img/logo.png" alt="Logotipo">
		</a>
	</header>

	<nav class="nav">
		<a class="nav__link nav__link--active" href="#">Inicio</a>
		<a class="nav__link nav__link--active" href="#">Nosotros</a>
	</nav>
```

* CSS:

```css
/* Header */

.header {
	display: flex;
	justify-content: center;
}

.header__logo {
	margin: 2rem 0; 
}

/* Nav */

/* Clase de Bloque */
.nav {
	background-color: var(--secondary);
	padding: 0.5rem 0;
	display: flex;
	justify-content: center;
	gap: 2rem;
}

/* Clase de Elemento */
.nav__link {
	color: var(--white);
	font-size: 1.563rem;
	font-weight: 900;
}

/* Clase de Modificador */
.nav__link:hover,
.nav__link--active {
	color: var(--primary);
}
```

Cómo se puede apreciar hemos usado la metodología BEM (Block, Element, Modifier) al proyecto.

* Para los bloques, las clases deben ser nombres cortos de 1 ó 2 palabras.
* Para los elementos, las clases deben tener el nombre del bloque padre que contiene al elemento, seguido de 2 guiones bajos (__) y el nombre del elemento.
* Para los modificadores, las clases deben tener el nombre del elemento, seguido de 2 guiones (--) y el nombre del modificador.

------

## Commit 3 - v0.3

### Tabla de Cambios

| Archivos Nuevos              | Archivos Editados                                            |
| ---------------------------- | ------------------------------------------------------------ |
| about.html<br />product.html | index.html<br />about.html<br />product.html<br />index.css<br /> |

### Cambios

Se crearon 2 .html nuevos para las páginas del about y los productos.

También añadimos estilos al Footer

------

## Commit 4 - v0.4

### Tabla de Cambios

| Archivos Nuevos | Archivos Editados         |
| --------------- | ------------------------- |
| None            | index.html<br />index.css |

### Cambios

Se añadió el Grid para los productos y unas imagenes en index.html

* Estructura de cada producto en HTML:

```html
<main class="container">
	<h1>Nuestras Camisas</h1>

	<div class="grid">
		<div class="product">
			<a href="product.html">
				<img class="product__img" src="img/1.jpg" alt="Imagen Camisa">
				<div class="product__info">
					<p class="product__name">VueJs</p>
					<p class="product__prize">$10</p>
				</div>
			</a>
		</div> <!-- Fin de la Clase product -->
        
        <div class="grafico grafico--camisas">
        </div>
    </div>
</main>
```

* Estilos del grid en CSS:

```css
/* Grid */

.grid {
	display: grid;
	grid-template-columns: repeat(2, 1fr);
	gap: 1.5rem;
}

@media (min-width: 768px){
	.grid {
		grid-template-columns: repeat(3, 1fr);
	}
}

```

* Estilos del producto en CSS:

```css
/* Productos */

.product {
	background-color: var(--secondary);
	padding: 0.5rem;
}

.product__img {
	width: 100%;
}

.product__info {

}

.product__name {
	font-size: 1.953rem;
	color: var(--white);
}

.product__prize {
	font-size: 1.25rem;
	color: var(--primary);
}

.product__name, .product__prize {
	margin: 0;
	text-align: center;
}
```

* Estilos del Grafico en CSS:

```css
/* Graficos */

.grafico {
	min-height: 30rem;
	background-repeat: no-repeat;
	background-size: cover;  
	grid-column: 1 / 3;
}

.grafico--camisas {
	grid-row: 2 / 3;
	background-image: url("../img/grafico1.jpg");
}

.grafico--node {
	background-image: url("../img/grafico2.jpg");
	grid-row: 8 / 9;
}

@media (min-width: 768px){
	.grafico--node {
		grid-row: 5 / 6;
		grid-column: 2 / 4;
	}
}
```

------

## Commit 5 - v0.5

### Tabla de Cambios 

| Archivos Nuevos | Archivos Editados         |
| --------------- | ------------------------- |
| None            | about.html<br />index.css |

### Cambios

Creado el contenido de la página de About

* Estructura HTML para la info principal:

```html
<main class="container">
	<h1>Nosotros</h1>

	<div class="about">
		<div class="about__text">
			<p>	Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime iure modi nihil laborum perferendis? Officia doloribus veritatis, voluptas ducimus quas consequatur libero dolorem accusantium velit molestias unde maxime nihil tempore quos dignissimos harum, quaerat laudantium. Molestiae tempore, dolor amet ab?
			Lorem ipsum dolor sit amet.
			</p>
		</div>
		<img class="about__img" src="img/nosotros.jpg" alt="">			
	</div>	
</main>
```

* Estilos CSS para la info principal:

```css
/* About Us Page */

.about {
	display: grid;
	grid-gap: 1rem;
}

@media (min-width: 768px){
	.about {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
	}

	.about__img {
		grid-column: 2 / 3;
	}
}

.about__img {
	grid-row: 1 / 2;
}

.about__text {
	text-align: left;
}
```

Creada tambien la lista de los beneficios de comprar con nosotros

* Estructura de los bloques y del bloque individual en HTML:

```html
<section class="container get">
	<h2 class="get__title"> ¿Por qué preferirnos?</h2>
		
	<div class="blocks">
		<div class="block">
			<img class="block__img" src="img/icono_1.png" alt=" Porque comprar">
			<h3 class="block__title">Precio</h3>
			<p>Lorem, ipsum dolor sit amet consectetur, adipisicing elit. Fugit, reprehenderit.</p>
		</div> <!-- Bloque -->	
    </div> <!-- Bloques -->
</section>
```

* Estilos de los bloques y del bloque individual en CSS:

```css
/* Bloques */

.blocks {
	display: grid;
	gap: 1rem;
}

@media (min-width: 768px){
	.blocks {
		grid-template-columns: repeat(4, 1fr);
	}
}

.block {
	text-align: center;
}


.block__title {
	margin: 0;
}
```

------

## Commit 6 - v0.6

### Tabla de Cambios

| Archivos Nuevos | Archivos Editados                           |
| --------------- | ------------------------------------------- |
| None            | index.html<br />product.html<br />index.css |

### Cambios

Se terminó de agregar el estilo CSS a la página de productos

```css
/* Pagina del Producto */

@media (min-width: 768px){
	.shirt {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		column-gap: 1rem;
	}
}

.form {
	display: grid;
	grid-template-columns: repeat(2, 1fr);
	gap: 1rem;

}

.form__camp {
	border: 0.125rem solid var(--darkPrimary);
	background-color: transparent;
	padding: 0.5rem;
	color: var(--white);
	appearance: none;
}

.form__submit {
	background-color: var(--primary);
	border: none;
	font-size: 1rem;
	padding: 1rem;
	transition: background-color 0.2s ease;
	grid-column: 1 / 3; 
}

.form__submit:hover {
	cursor: pointer;
	background-color: var(--darkPrimary);
}
```

Con esto hemos terminado el proyecto 2.

------

