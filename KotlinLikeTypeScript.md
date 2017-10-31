Hello World
------------
+ Kotlin
```Kotlin
println("Hello, world!")
```
+ TypeScript
```TypeScript
console.log("Hello, world!");
```

Variables And Constants
------------
+ Kotlin
```Kotlin
var myVariable = 42
myVariable = 50
val myConstant = 42
```
+ TypeScript
```TypeScript
let myVariable = 42;
myVariable = 50;
const myConstant = 42;
```

Explicit Types
------------
+ Kotlin
```Kotlin
val explicitDouble: Double = 70.0
```
+ TypeScript
```TypeScript
const explicitDouble: number = 70;
```

Type Coercion
------------
+ Kotlin
```Kotlin
val label = "The width is "
val width = 94
val widthLabel = label + width
```
+ TypeScript
```TypeScript
const label = "The width is ";
const width = 94;
const widthLabel = label + width;
```

String Interpolation
------------
+ Kotlin
```Kotlin
val apples = 3
val oranges = 5
val fruitSummary = "I have ${apples + oranges} " +
                   "pieces of fruit."
```
+ TypeScript
```TypeScript
const apples = 3;
const oranges = 5;
const fruitSummary = `I have ${apples + oranges} ` +
                   "pieces of fruit.";
```


Range Operator
------------
+ Kotlin
```Kotlin
val names = arrayOf("Anna", "Alex", "Brian", "Jack")
val count = names.count()
for (i in 0..count - 1) {
    println("Person ${i + 1} is called ${names[i]}")
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack
```
+ TypeScript
```TypeScript
import * as _ from 'lodash';
const names = ["Anna", "Alex", "Brian", "Jack"];
const count = names.length;
for (let i of _.range(0, count)) {
    console.log(`Person ${i + 1} is called ${names[i]}`)
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack
```

Inclusive Range Operator
------------
+ Kotlin
```Kotlin
for (index in 1..5) {
    println("$index times 5 is ${index * 5}")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```
+ TypeScript
```TypeScript
import * as _ from 'lodash';

for(let index of _.range(1, 6)) {
    console.log(`${index} times 5 is ${index * 5}`)
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```


Arrays
------------
+ Kotlin
```Kotlin
val shoppingList = arrayOf("catfish", "water",
    "tulips", "blue paint")
shoppingList[1] = "bottle of water"
```
+ TypeScript
```TypeScript
let shoppingList = ["catfish", "water",
    "tulips", "blue paint"];
shoppingList[1] = "bottle of water";
```


Maps
------------
+ Kotlin
```Kotlin
val occupations = mutableMapOf(
    "Malcolm" to "Captain",
    "Kaylee" to "Mechanic"
)
occupations["Jayne"] = "Public Relations"
```
+ TypeScript
```TypeScript
let occupations = {
    "Malcolm": "Captain",
    "Kaylee": "Mechanic",
};
occupations["Jayne"] = "Public Relations";
```

Empty Collections
------------
+ Kotlin
```Kotlin
val emptyArray = arrayOf<String>()
val emptyMap = mapOf<String, Float>()
```
+ TypeScript
```TypeScript
const emptyArray: string[];
const emptyDictionary: {[key: string]: number};
```

Functions
------------
+ Kotlin
```Kotlin
fun greet(name: String, day: String): String {
    return "Hello $name, today is $day."
}
greet("Bob", "Tuesday")
```
+ TypeScript
```TypeScript
function greet(name: string, day: string): string {
    return `Hello ${name}, today is ${day}.`
}
greet("Bob", "Tuesday");
```

Tuple Return
------------
+ Kotlin
```Kotlin
data class GasPrices(val a: Double, val b: Double,
     val c: Double)
fun getGasPrices() = GasPrices(3.59, 3.69, 3.79)
```
+ TypeScript
```TypeScript
function getGasPrices(): [number, number, number] {
    return [3.59, 3.69, 3.79];
}
```

Variable Number Of Arguments
------------
+ Kotlin
```Kotlin
fun sumOf(vararg numbers: Int): Int {
    var sum = 0
    for (number in numbers) {
        sum += number
    }
    return sum
}
sumOf(42, 597, 12)

// sumOf() can also be written in a shorter way:
fun sumOf(vararg numbers: Int) = numbers.sum()
```
+ TypeScript
```TypeScript
function sumOf(...numbers: number[]): number{
    let sum = 0;
    for (let number of numbers) {
        sum += number;
    }
    return sum;
}
sumOf(42, 597, 12);
```

Function Type
------------
+ Kotlin
```Kotlin
fun makeIncrementer(): (Int) -> Int {
    val addOne = fun(number: Int): Int {
        return 1 + number
    }
    return addOne
}
val increment = makeIncrementer()
increment(7)

// makeIncrementer can also be written in a shorter way:
fun makeIncrementer() = fun(number: Int) = 1 + number
```
+ TypeScript
```TypeScript
function makeIncrementer():(number) => number{
    function addOne(number: number): number {
        return 1 + number;
    }
    return addOne
}
let increment = makeIncrementer();
increment(7);

// makeIncrementer can also be written in a shorter way:
let makeIncrementer = () => (number: number) => 1 + number;
```


Map
------------
+ Kotlin
```Kotlin
val numbers = listOf(20, 19, 7, 12)
numbers.map { 3 * it }
```
+ TypeScript
```TypeScript
let numbers = [20, 19, 7, 12];
numbers.map((it) => 3 * it);
```

Sort
------------
+ Kotlin
```Kotlin
listOf(1, 5, 3, 12, 2).sorted()
```
+ TypeScript
```TypeScript
[1, 5, 3, 12, 2].sort();
```

Named Arguments
------------
+ Kotlin
```Kotlin
fun area(width: Int, height: Int) = width * height
area(width = 2, height = 3)

// This is also possible with named arguments
area(2, height = 2)
area(height = 3, width = 2)
```
+ TypeScript
```TypeScript
function area({width, height}:{width:number, height:number}):number {
    return width * height;
}
area({width: 2, height: 3});
```

Declaration
------------
+ Kotlin
```Kotlin
class Shape {
    var numberOfSides = 0
    fun simpleDescription() =
        "A shape with $numberOfSides sides."
}
```
+ TypeScript
```TypeScript
class Shape {
    numberOfSides = 0;
    simpleDescription(){
        return `A shape with ${this.numberOfSides} sides.`;
    }
}
```


Usage
------------
+ Kotlin
```Kotlin
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```
+ TypeScript
```TypeScript
let shape = new Shape();
shape.numberOfSides = 7;
let shapeDescription = shape.simpleDescription();
```

Subclass
------------
+ Kotlin
```Kotlin
open class NamedShape(val name: String) {
    var numberOfSides = 0

    open fun simpleDescription() =
        "A shape with $numberOfSides sides."
}

class Square(var sideLength: BigDecimal, name: String) :
        NamedShape(name) {
    init {
        numberOfSides = 4
    }

    fun area() = sideLength.pow(2)

    override fun simpleDescription() =
        "A square with sides of length $sideLength."
}

val test = Square(BigDecimal("5.2"), "square")
test.area()
test.simpleDescription()
```
+ TypeScript
```TypeScript
class NamedShape {
    numberOfSides: number = 0;
    name: string;

    constructor(name: string) {
        this.name = name
    }

    simpleDescription():string {
        return `A shape with ${this.numberOfSides} sides.`;
    }
}

class Square extends NamedShape {
    sideLength: number;

    constructor(sideLength: number, name: string) {
        super(name);
        this.sideLength = sideLength;
        this.numberOfSides = 4;
    }

    area(): number {
        return this.sideLength * this.sideLength;
    }

    simpleDescription(): string {
        return "A square with sides of length " +
	       this.sideLength + ".";
    }
}

let test = new Square(5.2, "square");
test.area();
test.simpleDescription();
```

Checking Type
------------
+ Kotlin
```Kotlin
var movieCount = 0
var songCount = 0

for (item in library) {
    if (item is Movie) {
        ++movieCount
    } else if (item is Song) {
        ++songCount
    }
}
```
+ TypeScript
```TypeScript
let movieCount = 0;
let songCount = 0;

for (let item in library) {
    if (item instanceof Movie) {
        ++movieCount;
    } else if (item instanceof Song) {
        ++songCount;
    }
}
```

Downcasting
------------
+ Kotlin
```Kotlin
for (current in someObjects) {
    if (current is Movie) {
        println("Movie: '${current.name}', " +
	    "dir. ${current.director}")
    }
}
```
+ TypeScript
```TypeScript
for (let current in someObjects) {
    if (current instanceof Movie) {
        console.log(`Movie: '${movie.name}', ` +
            `dir. ${movie.director}`);
    }
}
```

Protocol
------------
+ Kotlin
```Kotlin
interface Nameable {
    fun name(): String
}

fun f<T: Nameable>(x: T) {
    println("Name is " + x.name())
}
```
+ TypeScript
```TypeScript
interface Nameable {
    name():string;
};

function f(x: Nameable) {
    console.log("Name is " + x.name());
}
```


