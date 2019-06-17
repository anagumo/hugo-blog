---
title: "100 Days of Swift: Day 1"
date: 2019-03-08T10:40:40-06:00
draft: true
---

* Scope:  Variables, Simple Data Types & String Interpolation

Este es el gran inicio del maratón [100 Days of Swift](https://hackingwithswift.com/100), nunca antes intenté hacer un reto
similar pero la idea de Paul Hudson es simplemente maravillosa, usualmente uno ve a personas haciendo 100 días de algo 
pero no a nivel de comunidad, así que mi compromiso social incluye un post diario en este blog y una breve cápsula semanal en Youtube;
si te has involucrado y quieres compartir tu experiencia escríbeme un [tweet](https://twitter.com/gowtski).

### Variables
Podemos crear variables usando la palabra clave `var`, una variable guarda valores que pueden cambiar en cualquier momento:
```
var greeting = "Hello, world!"
greeting = "Goodbye, cruel world!"
```

Swift es un lenguage Type-Safe, por lo cual se asegura de que uses tus variables de forma apropiada de acuerdo a los valores que haz
guardado en ellas, en el caso de la variable `greeting` no puedes cambiar su valor a un número literal pues previamente haz guardado 
una serie de caracteres.
```
greeting = 13 // Cannot assign value of type 'Int' to type 'String'
```

Pero qué es eso de `Int` y `String`

### Strings e Integers
Por default si asignamos un valor inicial a una nueva variable, sin especificar su tipo, Swift inferirá que es de tipo `Int`
si hemos guardado literalmente un número entero; o un `String`, si es que hemos guardado una cadena de texto en nuestra variable.
Es por eso que no podemos mezclar tipos de datos.
```
var age = 29 // Int
var bookPrice = 1_900 // Int 
var myName = "Ariana" // String
```
El underscore, que es opcional, nos permite leer de forma clara cantidades grandes, el valor será el mismo.

### Strings Multilinea
Esto es simple, nuestros Strings también pueden expandirse en varias líneas si usamos triple comilla doble:
```
var haiku = """
Mil pequeños peces blancos
Como si hirviera
El color del agua
"""
```

Incluye `\` al final de cada línea si no deseas que el salto de línea sea parte del valor de tu multi-string.

### Doubles y Booleans
Los tipos de dato `Int` y `String` son muy comunes en Swift, pero también existen otros aún más interesantes. Si deseamos guardar
números decimales en nuestras variables, por default serán de tipo `Double`. Un `Double` nos da una precisión más exacta en comparación 
con los flotantes:
```
var area = 3.5 // Double
```

Los Booleans son más simples en el valor que guardan, pueden ser sólo `true` o `false`:
``` 
var isFebruary = true
```

### String Interpolation
Hasta entonces hemos creado variables independientes, que no pueden ser mezcladas entre si debido a su tipo, pero existe una forma
de darle útlidad a sus valores creando un nuevo `String`. Esta técnica se llama `String Interpolation` y sólo hace falta encerrar cada variable entre
paréntesis incluyendo `\` al inicio para incluir su valor:
```
var numberOfDays = 100
var marathon = "Este maratón de Swift dura \(numberOfDays) días"

Imprime: Este maraton de Swift dura 100 días
```

### Constants
Así como tenemos variables que pueden cambiar de valor, también existen las constantes donde una vez asignado un valor inicial no puede volver cambiar;
para crear una constante usamos la palabra clave `let` en lugar de `var`:
```
let pi = 3.14159
```
Hay que definir constantes en nuestro código lo más que podamos \o/

### Type Annotations
Finalmente, si queremos ser explícitos acerca del tipo de dato que queremos guardar en nuestras variables y constantes, sin dejarle a Swift la chamba 
de inferirlo, podemos agregar una anotación de tipo de la siguiente forma:
```
let year: Int = 1989
let lastName: String = "Nagumo"
```

#### Resources:

* [Playground for Xcode: Day 1](https://github.com/shhnagumo/swift-playground/blob/master/0-100-days-of-swift/1-day.swift)
* [Hacking With Swift: Day 1](https://www.hackingwithswift.com/100/1)
* [Type Safe & Type Inference](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID322)
* [Type Annotations](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID310)
* [Types & Operations](https://www.raywenderlich.com/6364-swift-tutorial-part-2-types-and-operations)
