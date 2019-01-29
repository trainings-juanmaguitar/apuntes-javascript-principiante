#Funciones

```javascript
function sum(a, b) {
  var c = a + b;
  return c;
}
```

Las [**funciones**](https://developer.mozilla.org/en/JavaScript/Reference/Functions_and_function_scope) nos permiten agrupar varias líneas de código bajo un nombre.
De esta forma podemos reutilizar este código, invocando el nombre de la función.

Las partes de una [función](https://bonsaiden.github.io/JavaScript-Garden/#function):

- La _sentencia `function`_
- El _nombre_ de la función (_sum_)
- _Parámetros_ (argumentos) que espera la función (_a_ y _b_)
Una función puede aceptar cero o más argumentos separados por comas
- Un bloque de código, también llamado el _cuerpo de la funcion_
- La sentencia _`return`_  
Una función siempre devuelve un valor.  
Si no devuelve explícitamente un valor, implícitamente devuelve el valor
`undefined`  

Una función _solo puede devolver un valor._  
Si se necesita devolver mas de un valor, se puede devolver un array o un objeto con esos valores

Para llamar a una [función](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Objetos_globales/Function) tan solo tenemos que usar su nombre seguido de algunos parámetros (o ninguno) entre paréntesis

```javascript
>>> var result = sum(1, 2);
>>> result;
3
```

##Parametros

Una función puede no requerir parámetros, pero si los requiere y no se les pasa a la función, Javascript les asignará el valor `undefined`

Si la función recibe mas parámetros de los esperados, simplemente los ignorará

Dentro de cada función tenemos disponible el objeto (pseudo-array) [`arguments`](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Obsolete_Pages/Gu%C3%ADa_JavaScript_1.5/Usando_el_objeto_arguments) que contiene los argumentos pasados a la función

```javascript
function sumOnSteroids() {
  var i, res = 0;
  var number_of_params = arguments.length;
  for (i = 0; i < number_of_params; i++) {
    res += arguments[i];
  }
  return res;
}
```

##Funciones pre-definidas

Hay una serie de funciones que están directamente definidas dentro del motor de Javascript. 
Estas funciones pre-definidas son:

- `parseInt()`
- `parseFloat()`
- `isNaN()`
- `isFinite()`
- `encodeURI()`
- `decodeURI()`
- `encodeURIComponent()`
- `decodeURIComponent()`
- `eval()`

###[`parseInt()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/parseInt)

`parseInt()` toma un valor e intenta transformarlo en número entero.
Si falla devuelve NaN.  
`parseInt()` admite un segundo parámetro opcional que indica la base del numero que se le está pasando (decimal, hexadecimal, binario, etc…)

```javascript
>>> parseInt('123')
123
>>> parseInt('abc123')
NaN
>>> parseInt('1abc23')
1
>>> parseInt('123abc')
123
```

Se recomienda especificar siempre la base (10 normalmente) para [evitar problemas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt#Octal_interpretations_with_no_radix) de interpretaciones

```javascript
>>> parseInt(" 0xF", 16);
15
>>> parseInt(" F", 16);
15
>>> parseInt("17", 8);
15
>>> parseInt(021, 8);
15
>>> parseInt("015", 10);
15
>>> parseInt(15.99, 10);
15
>>> parseInt("FXX123", 16);
15
>>> parseInt("1111", 2);
15
>>> parseInt("15*3", 10);
15
>>> parseInt("15e2", 10);
15
>>> parseInt("15px", 10);
15
>>> parseInt("12", 13);
15
```

###[`parseFloat()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/parseFloat)

`parseFloat()` toma un valor e intenta transformarlo en número de coma flotante (con decimales).

```javascript
>>> parseFloat('123')
123
>>> parseFloat('1.23')
1.23
>>> parseFloat('1.23abc.00')
1.23
>>> parseFloat('a.bc1.23')
NaN
```

###[`isNan()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/isNaN)

`isNan()` comprueba si el valor que se le pasa es un numero válido (devuelve true en caso de que no lo sea)

```javascript
>>> isNaN(NaN)
true
>>> isNaN(123)
false
>>> isNaN(1.23)
false
>>> isNaN(parseInt('abc123'))
true
```

###[`isFinite()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/isFinite)

`isFinite()` comprueba si el valor que se le pasa no es ni Infinity ni NaN

```javascript
>>> isFinite(Infinity)
false
>>> isFinite(-Infinity)
false
>>> isFinite(12)
true
>>> isFinite(1e308)
true
>>> isFinite(1e309)
false
```

###[`encodeURI()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/encodeURI)

`encodeURI()` Nos permite ‘escapar’ (codificar) una URL reemplazando algunos caracteres por su correspondiente secuencia de escape UTF-8.
_encodeURI()_ nos devuelve una URL usable (solo codifica algunos caracteres)

```javascript
>>> var url = 'http://www.packtpub.com/scr ipt.php?q=this and that';
>>> encodeURI(url);
http://www.packtpub.com/scr%20ipt.php?q=this%20and%20that
```

###[`decodeURI()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/decodeURI)

`decodeURI()` Nos permite ‘decodificar’ un string codificado por `encodeURI()`

###[`encodeURIComponent()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/encodeURIComponent) y [`decodeURIComponent()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/decodeURIComponent)

`encodeURIComponent()` y `decodeURIComponent()` Lo mismo que
encodeURI()` pero esta función codifica (decodifica) TODOS los caracteres transformables

```javascript
>>> encodeURIComponent(url);
"http%3A%2F%2Fwww.packtpub.com%2Fscr%20ipt.php%3Fq%3Dthis%20and%20that"
```

###[`eval()`](https://developer.mozilla.org/es/Referencia_de_JavaScript_1.5/Funciones_globales/eval)

`eval()` toma una cadena de texto y la ejecuta como código Javascript

`eval()` [no debe utilizarse ](https://bonsaiden.github.io/JavaScript-Garden/#core.eval)básicamente por 2 motivos:  

- Rendimiento: Es mucho más lento evaluar código “en vivo” que tenerlo
directamente en el script  
- Seguridad: Teniendo en cuenta que ejecuta todo lo que se le pase puede ser un agujero de seguridad.  

```javascript
>>> eval('var ii = 2;')
>>> ii
2
```

###`alert()`

`alert()` Nos muestra una ventana con un string  
`alert()` no es parte del core JS pero está disponible en todos los navegadores  

¡OJO! `alert()` para el código hasta que se acepte el mensaje  