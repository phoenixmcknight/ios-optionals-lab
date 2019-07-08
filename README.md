# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap

var userName: String? 
if userName == nil {
print("No name")

} else {
print("\(userName!)")
}

- Method two: Optional binding

var userName: String?
if let userName1 = userName {
print("\(userName1)")
} else {
print("No name")
}

- Method three: Nil coalescing

var userName: String? 
var username1 = userName ?? "No name"
print(username1)


## Question 2

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`

var backgroundColor: String? 
var backgroundColor2 = backgroundColor ?? "White"
print(backgroundColor2)



## Question 3

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double?
var height: Double?
```
var length: Double? = 5.0
var height: Double? = 4.0

if let length2 = length, let height2 = height {
print(length2 * height2)
} else {
print("No value")
}

## Question 4

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?
```
var name: String? = "chris"
var age: Int? = 3
var height: Double? = 4.5

if let name2 = name, let age2 = age, let height2 = height {
print("My name is \(name2), my age is \(age2) and my height is \(height2) feet")
} else {
print("No value")
}

## Question 5

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"
```
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"
var fullName = ""

if middleName == nil {
print("\(firstName) \(lastName)")
} else {
fullName = ("\(firstName) \(middleName!) \(lastName)")
}
print(fullName)


## Question 6

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

let myIntString = "35"
print(Int(myIntString)! + 15)


`let myIntString = "35"`


## Question 7

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne = (4, nil, 7)
var testCaseTwo = (nil, nil, 9)
var testCaseThree = (5, 10, 24)
```


## Question 8

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}
```
var tuple: (Int, Int)?
if Bool.random() {
tuple = (5, 3)
}
if tuple == nil {
print("nil")
} else {
print(tuple!)
}



## Question 9

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
let myInt: Int?
if Bool.random() {
 myInt = 5
}
```
var myInt: Int?
if Bool.random() {
myInt = 5
}

if myInt == nil {
print("nil")
} else {
print(myInt!*2)
}



## Question 10

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}
```
var myDouble: Double?
let doubleTwo: Double = 5
if myDouble == nil {
print("nil")
} else {
print(myDouble!*doubleTwo)
}


## Question 11

Determine if the variable contains a Boolean or nil value. If nil, set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}
```
var isTheGreatest: Bool? 
if Bool.random() {
isTheGreatest = true
}
if isTheGreatest == nil {
print(false)
} else {
print(true)
}


## Question 12

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}
```
var myTuple: (Int?, Int?, Int?, Int?)
var sum = 0
if Bool.random() {
myTuple.0 = 5
myTuple.2 = 14
} else {
myTuple.1 = 9
myTuple.3 = 10
}
if myTuple.0 != nil {
sum += myTuple.0!
if myTuple.1 != nil {
sum += myTuple.1!
}else {
if myTuple.2 != nil {
sum += myTuple.2!

if myTuple.3 != nil {
sum += myTuple.3!
}
}
}
}
print(sum)

## Question 13

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()
```
let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()
if let check = pokemon {
if let check2 = evolutionaryStone {
if check == "Pikachu" && check2 == "Electric" {
print("Use \(check2) stone to evolve \(check)")
} else if check == "Pikachu" && check2 != "Electric"{
print("You can NOT use \(check2) stone to evolve \(check)")
}
if check == "Bulbasaur" && check2 == "Grass" {
print("Use \(check2) stone to evolve \(check)")
} else if check == "Bulbasaur" && check2 != "Grass"{
print("You can NOT use \(check2) stone to evolve \(check)")
}
if check == "Charmander" && check2 == "Fire" {
print("Use \(check2) stone to evolve \(check)")
}else if check == "Charmander" && check2 != "Fire"{
print("You can NOT use \(check2) stone to evolve \(check)")
}
if check == "Squirtle" && check2 == "Water" {
print("Use \(check2) stone to evolve \(check)")
}else if check == "Squirtle" && check2 != "Water"{
print("You can NOT use \(check2) stone to evolve \(check)")
}
if check == "Not a Pokemon" && check2 == "No Stone" {
print("You cant use \(check2) stone to evolve \(check)")
}
}
}


## Question 14

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}
```
var numberOfPeople: Int?

if Bool.random() {
numberOfPeople = 108
}
if let numberOfPeople2 = numberOfPeople  {
if numberOfPeople2 % 2 == 0 {
print("\(numberOfPeople2) is even")
} else {
print("\(numberOfPeople2) is odd")
}
}

## Question 15

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}
```

var someNumbers: [Int?] = []

for i in 0..<20 {
someNumbers.append(Bool.random() ? i : nil)
}
var multiply = 1
for num in someNumbers {
if let num = num {
multiply = multiply * num

}
}
print(multiply)



## Question 16

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
```
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]
var city2 = [String]()
for city in poorlyFormattedCityNames where city != nil {

city2.append(city!.capitalized)



}
print(city2)


## Question 17

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
```
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
var aBunchofNumbers2 = [0]
for num in aBunchOfNumbers {
if let num = num {
if num % 2 == 0 {
aBunchofNumbers2 += [num]
}


}
}
print(aBunchofNumbers2)


## Question 18

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`

let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]
var empty = [Int]()
for zipcode in zipCodeStrings {
empty.append((Int(zipcode)!))
}
print(empty)


## Question 19

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

- Print the names of the students that do not have a favorite color.

- Print the names of the students that don't have a favorite color or a favorite food.

- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`

let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]

var FavoriteFoodAndColor = [String]()
for info in studentInfo {
if info.2 == nil {
print("\(info.0) does not have a favorite color")
}
if info.1 == nil  {
print("\(info.0) does not have a favorite food")
}
if info.2 != nil && info.1 != nil {
FavoriteFoodAndColor.append("\(info.0) does have a favorite food and color")
}
}
print(FavoriteFoodAndColor)


## Question 20

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`


## Question 21

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`


## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`
