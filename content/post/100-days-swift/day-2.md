---
title: "100 Days of Swift: Day 2"
date: 2019-03-09T12:36:25-06:00
draft: true
---

* Scope: Arrays, dictionaries, sets and enums.

El día dos de este maratón inicia con una frase mágica a la que Paul hizo alusión: Cuando las cosas se ponen difíciles, todos se van, ¡bom!

### Arrays
Swift provee tres tipos de colecciones primarias para guardar colecciones de valores, una de ellas son los arreglos.
Un arreglo guarda una colección de valores del mismo tipo en una lista ordenada. Hasta entonces hemos creado variables y constantes
independientes que no sólo podemos utilizar en un nuevo `String` sino también agruparlas en un sólo tipo:
```
let song1 = "Nobody Else Will Be There"
let song2 = "Day I Die"
let song3 = "Walk It Black"

let album = [song1, song2, song3]
```

Si usamos Type Annotations creamos nuestro arreglo de la siguiente manera:
```
let scores: [Int] = [10, 25, 99]
```

Podemos acceder a un valor de un arreglo usando Subscript Syntax, es decir, pasando el `index` del valor que quieres obtener dentro de corchetes:
```
album[2] // Imprime Walk It Black, ya que toda lista comienza en la posición 0
```

### Sets
Al igual que los `Arrays`, los `Sets` son colecciones de valores, excepto porque son listas donde el orden de los elementos no importa
pero sus valores tienen que ser únicos:
```
let primeNumbers = Set([2, 3, 5, 7])
let colors: Set<String> = ["Purple", "Red", "Purpule"] // Esto sólo creará un Set con dos elementos
```

### Dictionaries
Finalmente tenemos a los diccionarios que guardan asociaciones entre llaves y valores en una colección donde tampoco importa tanto el orden:
```
var credits: [String: String] = ["Main Actor": "Yalitza Aparicio", "Director": "Alfonso Cuarón", "Soundtrack": "Leo Dan"]
```

La forma de acceder a los valores de un diccionario es mediante las llaves que los identifican, si ésta no existe podemos asignar una por default:
```
credits["Main Actor", default: "Unknown"] // => Yalitza Aparicio
```

### Tuples
Existe otro tipo de colección en el mundo de Swift llamada Tupla, éstas agrupan múltiples valores que pueden ser de cualquier tipo y 
no tienen que ser del mismo tipo entre ellas \o/
```
let date = (year: 1990, month: 10, day: 13)
let person = (name: "Mateo", age: 3)
```

Para acceder al valor de una tupla podemos hacerlo mediante su posición o por el nombre que le hemos dado a su valor:
```
person.1 // => 3
person.name // => Mateo
```

### Enumerations
Qué pasa cuando lo único que queremos es tener un lista de valores que se relacionan entre sí, usamos Enums:
```
enum Weekend {
    case saturday
    case sunday
}

let day = Weekend.sunday // => sunday
```

Si queremos proveer información adicional a un `enum` usamos valores asociados:
```
enum Weekdays {
    case monday(activity: String)
    case friday(activity: String)
}

let monday = Weekdays.monday(activity: "Work starts")
let friday = Weekdays.friday(activity: "Work ends")
```

Finalmente, podemos asignar valores a los `enums`, dado que todo elemento de una lista comienza en la posición 0, un ejemplo muy práctico
para que los casos de un enum coincidan con una serie númerica que comienza en 1, sería el siguiente:
```
enum Numbers: Int {
    case one = 1
    case two
    case three
    case four
}

let first = Numbers(rawValue: 4) // => four
```

Sólo hace falta asignar el primer valor y Swift hará el resto.

#### Resources
* [Playground for Xcode: Day 2](https://github.com/shhnagumo/swift-playground/blob/master/0-100-days-of-swift/2-day.swift)
* [Hacking With Swift, Day 2: Arrays, Dictionaries, Sets and Enums](https://www.hackingwithswift.com/100/2)
* [Collection Types](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html)
* [Enumerations](https://docs.swift.org/swift-book/LanguageGuide/Enumerations.html)
