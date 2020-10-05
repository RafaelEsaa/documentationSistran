---
title: "Introducción a Markdown"
---

## Introducción

Markdown es un lenguaje de formateo ligero, con una sintaxis fácil de usar para dar formato a todos los documentos.

## ¿Qué es Markdown?

Markdown es la forma de dar estilo al texto en la web. Controlas la forma en como se ve un documento; dando formato a las palabras como hacerlas negritas o itálicas, agregar imágenes, y creando listas, estás son solo algunas de las cosas que puedes hacer con Markdown. En general, Markdown es sólo un texto normal con un poco de caracteres no-alfabeticos en él, como `#` o `*`.

Este artículo está escrito en Markdown y puedes ver que se encuentra perfectamnte formateado en los diferentes dispositivos.

## ¿Por qué usar Markdown?

Markdown será perfecto para ti sobre todo si publicas de manera constante en Internet, donde el lenguaje HTML está más que presente.

Pero no estoy hablando solo de blogs o páginas web. Servicios como TFS o foros como Stackoverflow también soportan este lenguaje, y con el paso del tiempo encontrarás aún más lugares que lo utilicen.

Además, Markdown está cada vez más extendido en el mundo “offline”. Nada te impedirá utilizar este lenguaje para tomar notas y apuntes de tusreuniones en una determinada aplicación.

Incluso podrías escribir un libro con él, ya que puedes exportar fácilmente el resultado final a un formato ePub y otros (pdf, word, txt, etc.)

Muchas la publicaciones de Amazon, Google Play o incluso iBooks, han sido escritas con Markdown. Puedes ver el nuevo portal de documentos de microsfot escrito completamente en markdown <http://docs.microsoft.com>, o moodle en <https://docs.moodle.org>, o boostrap <https://getbootstrap.com/docs/4.1/getting-started/introduction/> y así.

Este tipo de formato siempre será compatible con todas las plataformas que utilices, así que utilizar Markdown es una manera de mantener todo tu contenido siempre accesible desde cualquier dispositivo (smartphones, ordenadores de escritorio, tablets…), ya que en cualquiera de ellas siempre encontrarás las aplicaciones adecuadas para leer y editar este tipo de contenido.

Observa la diferencia entre un archivo creado por un procesador de textos (Pages, aunque podría ser Word), y el mismo archivo abierto con un editor de texto plano.

Si en el futuro Microsoft Word desapareciese perderías acceso a todo el contenido que has creado durante años utilizando dicho procesador. Así que lo más inteligente para evitar eso es generar tu contenido de la manera más sencilla posible: utilizando texto plano.

## Ejemplos

### Texto

Es bastante sencillo convertir algunas palabras en
\*\*negritas\*\* y otras en \*italicas\* con Markdown.

Proporciona

Es bastante sencillo convertir algunas palabras en **negritas** y otras en *italicas* con Markdown. Incluso puedes hacer un [link a Google](http://google.com).

## Sintaxis básica

Aquí un resumen de la sintaxis de Markdown que puedes utilizar en tus archivos de texto.

### Encabezados

    # Este es una etiqueta <h1>
    ## Este es una etiqueta <h2>
    ###### Este es una etiqueta <h6>

### Énfasis

    *Este texto estará en itálica*
    _Este texto también estará en itálica_

    **Este texto estará en negritas**
    __Este texto también estará en negritas__

    *Incluso **puedes** combinarlos*

### Listas

#### Desordenadas

    * Item 1
    * Item 2
        * Item 2a
        * Item 2b

#### Ordenadas

    1. Item 1
    2. Item 2
    3. Item 3
        * Item 3a
        * Item 3b

#### Imágenes

    ![GitHub Logo](/images/logo.png)

Formato:

    ![Atributo Alt](url "Atributo title Opcional")

#### Links

    1. http://github.com - ¡link automático!

    2. [GitHub](http://github.com)

    3. [GitHub][id]

    4. [GitHub][]

  1. **Link automático -** Cualquier dirección explicita será convertida en un link.
  2. **Link _en-línea_ -** `[Texto del Link](url)`.
  3. **Link _por-referencia_ -** `[Texto del Link][id]`. el id necesitará ser declarado en otra parte del documento así: `[id]: url`.
  4. **Link _por-referencia_ automática -** El id es el "Texto del Link", y también necesita ser declarado en otra parte del documento de igual manera que el "link por-referencia".

#### Citas

    Esto es un párrafo normal:

    > Y aquí está la cita que puede
    > seguir en varios renglones, y tener anidado más
    > > citas así, con un doble signo mayor-que.

#### Código en-línea

    Creo que debería utilizar una etiqueta `<addr>` aquí.

## Referencias

[Guia Markdown](/docs/guia_markdown/)