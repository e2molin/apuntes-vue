# Vue

## Instalación con CDN

<script src="https://unpkg.com/vue@next"></script>

https://www.youtube.com/watch?v=5jjMnb9qcVg&list=PLYAyQauAPx8l7G8lTbSv23UTAwbVORY1r&index=6


## Notas

### Visibilidad de elementos

La visibilidad de un elemento puede controlarse con **v-if** o con **v-show**. La cláusula **v-show** es mucho más efectiva a nivel de rendimiento porque no elimina del DOM el elemento sino que lo oculta con un *display:none*, a diferencia de **v-if** que lo elimina y lo crea en cada renderizado.

```javascript
    // Definida en data() una variable mostrarImagen = true/false
    <img src="imagen1" height="200" v-if="mostrarImagen">
    <img src="imagen2" height="200" v-show="mostrarImagen">
```

Así que para elementos que se muestran/ocultan de manera constante, es mejor utilizar **v-show**. Sin embargo para elementos que no tienen tanta fugacidad, como por ejemplo a la hora de configurar un interfaz, el botón que muestra el acceso a los menus de un administrador. Este menú, se mostraría/ocultaría mejor con un **v-if**, ya que también por temas de seguridad es mejor que permanezca oculto del DOM si no se va a usar.

### Atributos booleanos

Los atributos booleanos de las etiquetas HTML cono required, checked o disabled, pueden controlarse fácilmente desde **VUE**.

```html
<!-- Definida en data() una variable txtDisabled = true/false -->
<input type="text" v-bind:disabled="txtDisabled">
<input type="text" :disabled="txtDisabled"> <!-- Ambas son válidas -->
```

### Enlace a clases CSS

Podemos condicionar el aspecto de un elemento HTML asociandole o no determinadas clases a través de VUE

```html
<style>
        .redondo {
            border-radius: 20px;
            padding: 10px;
        } 
        .cuadrado {
            padding: 10px;
        } 
</style> 

<!-- Definimos en data() una variable redondo boolean. Según sea true/false se enlazrá o no la clase redondo-->
<div class="cuadrado has-background-primary" v-bind:class="{redondo}">
    Contenedor
</div>
<button @click="(redondo = !redondo)">Cambiar</button>
```



## Referencias

https://github.com/ricardovasconcelos/Vueflix
https://medium.com/@ivansotelo/internacionalizaci%C3%B3n-con-vue-i18n-403303872167


## APIs de desarrollo

Repositorio de API´s públicas https://github.com/public-apis/public-apis
Ejemplo de cómo programar una API con NodeJS https://github.com/bethfraser/hp-api

### MARVEL

🔗 https://developer.marvel.com/docs
🔐 Necesita API Key
🆓 1K llamadas/día
©️ Necesita atribución

### POKEMON

🔗 https://pokeapi.co
⭐ Sin límite ni API Key ni atribución
⚛️ GraphQL en Beta

### HARRY POTTER

🔗 https://hp-api.herokuapp.com
🔑 NO es necesaria API KEY

### Dragon Ball

🔗 https://dragon-ball-api.herokuapp.com/documentation
🔐 Necesita API Key
🆓 100 cada 15 minutos

### Videojuegos

🔗 https://api-docs.igdb.com
🆓 Para proyectos NO comerciales
🔑 Token de Twitch
🛑 4 peticiones por segundo

### Star Wars

🔗 https://swapi.dev
🆓 10K peticiones al día
🔑 NO necesita API KEY
