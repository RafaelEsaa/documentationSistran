---
title: "Guía para la escritura de Markdown"
---
En este artículo, vamos a describir brevemente la sintaxis de Markdown.

## Capítulos, apartados, subapartados

    # Header 1
    ## Header 2
    ### Header 3
    #### Header 4
    ##### Header 5

    Header 1
    ========
    
    Header 2
    --------

### Resultado

# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5

Header 1
========

Header 2
--------

## Tipografía

    _italicas_ y __negritas__
    *italicas* y **negritas**
    **_negrita e itálica_** o __*negrita e itálica tambien*__
    `tipo terminal: código sin colores según lenguaje`
    ~~tachado~~

### Resultado

_italicas_ y __negritas__

*italicas* y **negritas**

**_negrita e itálica_** o __*negrita e itálica tambien*__

`tipo terminal: código sin colores según lenguaje`

~~tachado~~

# Caracteres y símbolos

## Comillas

    ''texto''
    "double quotes"
    'single quotes'

### Resultado

''texto''

"double quotes"

'single quotes'

## Listas

    * Es fácil hacer una lista de itmes
    - añadiendo otro
    + y otro mas

### Resultado

* Es fácil hacer una lista de itmes
- añadiendo otro
+ y otro mas

## Enumeradores

    1. Una lista numerada
    2. también es fácil;
    3. un número, un punto y un espacio
    4. No importa el valor

### Resultado

1. Una lista numerada
2. también es fácil;
3. un número, un punto y un espacio
4. No importa el valor

## Anidación de listas

    1. Lista numerada con sub´ıtem
        * No olvidar la regla
        1. de los 4 espacios
        2. pero seamos sistem´aticos
    2. Para terminar

### Resultado

1. Lista numerada con sub´ıtem
    * No olvidar la regla
    1. de los 4 espacios
    2. pero seamos sistem´aticos
2. Para terminar

## Citas

    > Pueden utilizarse tal como se hace en los mensajes de correo electrónico (para indicar el momento en que se remite el texto)
    >> Y claro, puede anidarse sin problemas
    >>> Con varios niveles

### Resultado

> Pueden utilizarse tal como se hace en los mensajes de correo electrónico (para indicar el momento en que se remite el texto)
>> Y claro, puede anidarse sin problemas
>>> Con varios niveles

## Tablas

    | Header | Left | Right |
    | ------ | :----- | -----: |
    | Cell | $10 | $10 |
    | Cell | $200 | $200 |

### Resultado

| Header | Left | Right |
| ------ | :----- | -----: |
| Cell | $10 | $10 |
| Cell | $200 | $200 |

* Los dos puntos se utilizan para determinar la alineación.

## Enlace y definiciones

    [Página principal docs de Microsoft](https://docs.microsoft.com/en-us/ "Comentario sobre el enlace")

    <https://docs.microsoft.com/en-us/>
    Es posible definir el [enlace] visible para hacer más legible el texto, o tener dos versiones de un mismo texto cambiando sólo los enlaces, hablamos obviamente de un hiper[enlace]. No hay sensibilidad a mayúsculas. Puede haber mas de una palabra.

    [Enlace]: http://es.wikipedia.org/wiki/Hiperenlace "Hiperenlace"

### Resultado

[Página principal docs de Microsoft](https://docs.microsoft.com/en-us/ "Comentario sobre el enlace")

<https://docs.microsoft.com/en-us/>
Es posible definir el [enlace] visible para hacer más legible el texto, o tener dos versiones de un mismo texto cambiando sólo los enlaces, hablamos obviamente de un hiper[enlace]. No hay sensibilidad a mayúsculas. Puede haber mas de una palabra.

[Enlace]: http://es.wikipedia.org/wiki/Hiperenlace "Hiperenlace"

## Figuras

    [Ocarina](images/photo.jpg "Título optional")

### Resultado

[Ocarina](images/photo.jpg "Título optional")

## Caracteres especiales

    * Contra barra y espacio: \\
    * Tilde gráve: \'
    * Asterisco y barra baja: \* \_
    * Paréntesis: \{\} \[\] \(\)
    * Sostenido: \#
    * Otros: \+ \- \. \! \: \|

### Resultado

* Contra barra y espacio: \\
* Tilde gráve: \'
* Asterisco y barra baja: \* \_
* Paréntesis: \{\} \[\] \(\)
* Sostenido: \#
* Otros: \+ \- \. \! \: \|

## Líneas horizontales

    Al menos:
    ___: tres subrrados consecutivos
    ---: tres guiones consecutivos
    ***: tres asteriscos consecutivos

### Resultado

Tres subrrados

___


tres guiones

---

tres asteriscos

***

* Se utilizan para separar

## Comentarios

    <!-- Esto es un comentario -->

### Resultado

Aquí hay un comentario
<!-- Esto es un comentario -->
;-)

* El comentario no se ve, es interno al documento
* Se utilizan en su caso para separar listas reiniciando la numeración

## Código

    En la línea: `esto es código`.

    En bloque:
        ```
        Código
        aquí con opción 1
        ```

        ~~~
        Código
        aquí con opción 2
        ~~~

### Resultado

En la línea: `esto es código`.

En bloque:

```
Código
aquí con opción 1
```

~~~
Código
aquí con opción 2
~~~

## Resaltando la sintáxis

Se debe indicar el lenguaje luego de las comillas. Ejemplo para C#:

    ```CSharp
        ...
    ```

Los siguientes son algunos ejemplos de los lenguajes mas utilizados.

### CSharp

```CSharp
static void Main()
{
    Console.WriteLine("Hello World!");
    // Keep the console window open in debug mode.
    Console.WriteLine("Press any key to exit.");
    Console.ReadKey();
}
```

### HTML

```HTML
<!DOCTYPE HTML>
<html>
<body>
  <p>Before the script...</p>
  <script>
    alert( 'Hello, world!' );
  </script>
  <p>...After the script.</p>
</body>
</html>
```

### javascript

```javascript
var express = require('express');
var app = express();

app.get('/', function (req, res) {
  res.send('Hello World!');
});

app.listen(3000, function () {
  console.log('Example app listening on port 3000!');
});
```

### SQL

```SQL
CREATE PROCEDURE HelloWorld AS
PRINT 'Hello, world!'
RETURN (0)
```

## Referencias cruzadas

### Apartado con enlace

    #### Apartado con enlace {#idApartado}

    Aquí escribimos un apartado para poder [volver al enlace](#idApartado).

### Resultado 

#### Apartado con enlace {#idApartado}

Aquí escribimos un apartado para poder [volver al enlace](#idApartado)

## Referencia

[Introducción a Markdown](/docs/introMarkdown/)

[Rules of Markdown](https://github.com/DavidAnson/markdownlint/blob/v0.10.0/doc/Rules.md#md007)

[Guía breve y detallada](http://fobos.inf.um.es/R/taller5j/30-markdown/guiabreve.pdf)

[Markdown en español](https://github.com/ricval/Documentacion/tree/master/Markdown)