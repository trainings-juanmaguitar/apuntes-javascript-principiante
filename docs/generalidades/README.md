# Ideas Claras de Javascript

- JavaScript es un [lenguaje de programación interpretado](http://es.wikipedia.org/wiki/Lenguaje_de_programaci%C3%B3n_interpretado) por lo que no es necesario compilar los programas para ejecutarlos  

- La interpretación (y ejecución) del código javascript que hay en cada página web se realiza en el navegador (browser) cuando se carga la página

- Según una [separacion en 3 capas de la pagina web](http://titleandsummary.com/separation-of-layers-content-presentation-and-behavior/), con el Javascript controlariamos [la capa](http://jeffcroft.com/blog/2007/sep/26/new-layers-web-development/) del comportamiento:  

  - Contenido → HTML  
  - Presentacion → CSS  
  - Comportamiento → Javascript  

- Con [la llegada de AJAX](http://www.uberbin.net/archivos/internet/ajax-un-nuevo-acercamiento-a-aplicaciones-web.php) (que no es más que el uso del objeto javascript [XMLHttpRequest](https://es.wikipedia.org/wiki/XMLHttpRequest) con el que se puede interactuar con el servidor sin tener que forzar una recarga de página) se abrió una nueva era en la historia del lenguaje

- El uso tradicional de Javascript ha sido en el browser, pero [ya](http://www.youtube.com/watch?v=F6k8lTrAE2g) [se](http://clintberry.com/2013/html5-apps-desktop-2013/) [ha](http://www.hongkiat.com/blog/mobile-frameworks/) extendido [su uso tambien en el lado del servidor](http://net.tutsplus.com/tutorials/javascript-ajax/learning-serverside-javascript-with-node-js/) ([Node.js](http://nodejs.org/)), en [aplicaciones desktop](https://nodesource.com/blog/node-desktop-applications) y en [aplicaciones mobile](http://phonegap.com/) 

- Hay diferencias entre los navegadores debido al uso de [diferentes motores de Javascript](http://www.etnassoft.com/2011/05/31/comparativa-entre-los-distintos-motores-ecmascript/). Algunos de ellos son:

  + Mozilla → Spidermonkey
  + Chrome → V8
  + Safari → JavaScriptCore
  + IE → Chakra
  + Node.js → V8

T> Aunque la diferencia grande siempre ha estado entre Internet Explorer y el resto (hasta IE9)

- Estos interpretes ([motores](http://en.wikipedia.org/wiki/JavaScript_engine#JavaScript_engines)) de JS que hay en cada navegador, realizan optimizaciones de código cada uno a su manera de ahí el diferente [rendimiento](http://jsperf.com/browse) entre navegadores

- Un [Framework](http://www.desarrolloweb.com/articulos/listado-distintos-framework-javascript.html) (o libreria) es una coleccion de utilidades comunmente utilizadas que pueden ser utilizadas para desarrollar aplicaciones ahorrando tiempo y esfuerzo. La libreria más conocida y utilizada es [jQuery](https://jquery.com/).

#ECMAScript

[Javascript](https://developer.mozilla.org/en/JavaScript_Language_Resources) está basado en [ECMAScript](http://es.wikipedia.org/wiki/ECMAScript) (o Ecma-262) que es una especificación de lenguaje de programacion (otro lenguaje "famoso" basado en este standard es _ActionScript_).  

Las [diferentes revisiones del Ecma-262](http://www.ecma-international.org/publications/standards/Ecma-262-arch.htm) y su [implementacion en los navegadores](http://kangax.github.io/compat-table/es5/) han ido marcando los desarrollos en Javascript

**ECMAScript 5** (ES5) y **ECMAScript 2015** (tambien conocido como ECMAScript 6, ES6 o ES2015) son las dos "versiones" de Javascript que se utilizan actualmente. 

##EcmaScript 5

**[ECMAScript5.1](http://www.ecma-international.org/ecma-262/5.1/)** fue lanzado en 2011 y podemos decir que [es el actual standard de Javascript](http://blog.oio.de/2013/04/16/ecmascript-5-the-current-javascript-standard/) (2014).  

Si miramos las [estadisticas de uso de navegadores](http://clicky.com/marketshare/global/web-browsers/versions/) junto con la [compatibilidad de estos con ES5](http://kangax.github.io/compat-table/es5/) podemos concluir que: _basandonos en ES5 nuestro codigo funcionará bien en la mayoria de los navegadores utilizados actualmente (2016)_. 

Si queremos, podemos dar soporte de algunas features de ES5 en navegadores antiguos que no la soporten, utilizando el correspondiente [shim](https://github.com/es-shims/es5-shim)

ES5 **amplia** los anteriores standards [con algunas mejoras](http://www.jayway.com/2011/04/05/what-is-new-in-ecmascript-5/):

## EcmaScript 2015

[ECMAScript 2015](https://people.mozilla.org/~jorendorff/es6-draft.html) es el último standard de Javascript pero [aun no está lo suficientemente implantado](http://kangax.github.io/compat-table/es6/) en los navegadores mas utilizados.

- [Learn ES6 | A detailed overview of ECMAScript 6 features](https://6to5.org/docs/tour/)    
- [ECMAScript 6 Learning! (Eric Douglas Github)](https://github.com/ericdouglas/ES6-Learning)    
- [ES6 Rocks | A collaborative website about the ECMAScript sixth edition, a.k.a. ES6.](http://es6rocks.com/)    
- [Use ECMAScript 6 Today (tutsplus.com) ](http://code.tutsplus.com/articles/use-ecmascript-6-today--net-31582)    

Aunque podemos utilizar ES2015 en nuestros proyectos desde hoy mismo si:

- damos soporte de estas features de ES2015 en navegadores que no las soporten utilizando el correspondiente [shim](https://github.com/paulmillr/es6-shim/)

- [transformamos el código a ES5](http://www.barbarianmeetscoding.com/blog/2016/02/21/start-using-es6-es2015-in-your-project-with-babel-and-gulp/) mediante un proceso de transpilacion (transformación de un tipo de código a otro tipo de código)

- _Estos libros estan centrados en ES5 que es el código que funcionará sin problemas directamente en tus páginas web._










