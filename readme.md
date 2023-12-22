Definicion o concepto y ejemplo de todo lo mencionado posteriormenteSass(que es sass, ventajas de sass ,  desventajas de css plano, variables sass, anidamiento , nesting y finalmente modularizacion)


Arquitectura CSS (nomenclatura css con BEM) (Arquitectura con SMACSS)Resumen en el archivo readme.mdSubir todo a git hub pages y pasarme enlace por interno


# SASS


Un preprocesador es un lenguaje que parte de CSS (stylus, SASS), al compilarse se vuelve CSS, SASS no reconoce el navegador (solo reconoce HTML, CSS y JAVASCRIPT).

Desventajas de CSS Plano:
1. Escalabilidad: puede generar problemas de lectura

Ventajas de SASS:
1. Nos permite la modularisación
2. Tiene gran posibilidad de soporte por su comunidad.

## Uso de SASS

#### 1. Uso de variables

El nombrar las variables se hace con el $, se nombra al inicio, antes de todos los codigos.


$first-color:red;

$widthBox:300px;

$heightBox:300px;


#### 2. ANIDAMIENTO

El SASS permite el uso de anidamiento dentro uno de otro, de esta forma se puede trabajar de esta manera en vez de separarlo


#### 3. NESTING o MODULARIZACIÓN

Va junto con la nomenclatura de las clases

Sirve para trabajar de manera más atómica, esto sirve para no crear multiples archivos css por pagina que creamos, aun pudiendo añadir cierta independencia entre los archivos.

Como funciona
1. Se crear un archivo nuevo con el nombre de la parte que queremos separar: _menu.scss, siempre se tiene que agregar el "_" __

2. Se importa la pagina nueva creada al archivo principal que si compila

3. Esto va a compilar en el archivo styles.css


## NOMENCLATURA Y ARQUITECTURA CSS



### Nomenclarura: nombrado de clases

Universalisar el codigo

1. BEM (Block, Element, Modifier)  

B - Bloque

E - Elemento

M - Modifier

menu es bloque
item, link, son elementos
--active: seria un modifier, porque se activa con la variación de un estado, esto se utiliza con JAVASCRIPT en ese momento lo veremos a detalle
  

    <nav class="menu"

        <u class="menu_list">

            <li class="menu_item"><a class="menu_link" href="#">Inicio</a></li>

            <li class="menu_item"><a class="menu_link" href="#">Nosotros</a></li>

            <li class="menu_item"><a class="menu_link" href="#">Contacto</a></li>

        </ul>

    </nav
### ARQUITECTURA: ordenamiento de carpetas adicionales


La arquitectura en CSS sigue usualmente la forma SMACSS

[Categorizing CSS Rules - Scalable and Modular Architecture for CSS (smacss.com)](https://smacss.com/book/categorizing/)

En este link hay un libro que se puede leer.

Se crean 5 carpetas iniciales:

1. base: esta carpeta contiene lo que son valores de reseteo para los distintos elementos, de esta forma de no tienen valor por defecto, reemplaza lo que es el *, *::after *::before{
   box-sizing:box-border;
   padding:0;
   margin:0;}


Codigo copiado en _base.scss_

[necolas.github.io/normalize.css/8.0.1/normalize.css](https://necolas.github.io/normalize.css/8.0.1/normalize.css)


2.  layout: en esta sección va todo lo que son contenedores. Iria especificaciones de estos no relacionados a font, sino a width o heigh, padding, margin. Para colocar grid a un componente.

.container{

    max-width: 200px;

}

3. module: en este apartado va todo los componentes de una pagina, las secciónes: header, footer, menu de navegación, cada una en una pagina scss

4. state: en esta carpeta va todo los elementos que varian de estado con JAVASCRIPT a partir de alguna interacción. En el ejemplo colocamos lo que era un color diferente en el menu de navegación para la sección en la que estabamos.


5. theme: va todo lo que sont font y colores
