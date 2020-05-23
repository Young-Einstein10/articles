### Creating a Set

In Dart, a set is an unordered collection of unique items. This means that items do not have a specified position in a set, therefore, a set cannot have duplicates of the same item.

- Using Literals
``
  var setName = { elem 1, elem 2, ..., elem n}
  
  main() {
    var simpleSet = { 1, 2, 3};

    print(simpleSet); // {1,2,3}
  }

``

### Adding a Single Item to a Set

  `` setName.add(item);
  ``

```dart
 main() {
    var setOfFruit = <String>{};

    setOfFruit.add('apples');
    setOfFruit.add('bananas');
    setOfFruit.add('oranges');

    print(setOfFruit);
  }
```
### Adding Multiple Items to a Set

`` setName.addAll([item1, item2, ..., item n]);
``

## Map

A map is an unordered collection of key-value pairs. It associates keys and values. Every value has a key. This means that every key must be unique, however, the same value can be used multiple times. Two items with the same value will still be unique through their separate key.

Use a map when you need to access objects by a unique identifier.

    Maps are of the type Map.

### Creating a Map

- Using Literals
- Using Constructor
  

**Using Literals**

    var mapName = {
      key1: value1,
      key2: value2,
      key3:value3
    }

    Example
    main() {
      var capitals = {
        'United States' : 'Washington D.C.',
        'England' : 'London',
        'China' : 'Beijing',
        'Germany' : 'Berlin',
        'Nigeria' : 'Abuja',
        'Egypt' : 'Cairo',
        'New Zealand' : 'Wellington'
      };

      // Driver Code
      print(capitals); // {United States: Washington D.C., England: London, China: Beijing, Germany: Berlin, Nigeria: Abuja, Egypt: Cairo, New Zealand: Wellington}
    }

The map created above has 7 key-value pairs and when printed, it is displayed exactly as it was declared; between curly brackets ({}) with each key-value pair separated with a comma (,) and each key and value separated by a colon (:).

    Dart infers that capitals has a type Map<String,String> (a Map with both the keys and values being of type String).


**Using a Contructor**

You can also create a map using the Map constructor. Its basic syntax is similar to the List constructor. Let’s take a look. 

    var mapName = Map();
Using a constructor results in an empty map.

    main() {
      var emptyMap = Map();

      // Driver Code
      print(emptyMap); // {}
    }

**Specifying the Type**

Maps are parameterized types. This means that you can specify what types the keys and values should be.

The general syntax is as follows:

    var mapName = Map<dataType of key, datatype of value>();

**Adding Key-Value Pairs**

To add a new key-value pair to a map that has already been declared, use the following syntax:

    mapName[key] = value;

    main() {
    var numbers = Map<int, String>();

    numbers[1] = 'one';
    numbers[2] = 'two';
    numbers[3] = 'three';

    print(numbers); // {1: one, 2: two, 3: three}
  }

**Accessing a Value**

By providing a key, you can access its corresponding value using square brackets ([]).

The general syntax is as follows:

    mapName[key];

    main() {
    var capitals = {
      'United States' : 'Washington D.C.',
      'England' : 'London',
      'China' : 'Beijing',
      'Germany' : 'Berlin',
      'Nigeria' : 'Abuja',
      'Egypt' : 'Cairo',
      'New Zealand' : 'Wellington'
    };

    print(capitals['Germany']);  // Berlin

    if key doesn't exist, you get null in return.

    print(capitals['Austria']); // null
  }


**Checking a Key**
```dart
    mapName.containsKey(key);
```

**Retrieving All the Keys and Values**
```dart
    main() {
      var capitals = {
        'United States' : 'Washington D.C.',
        'England' : 'London',
        'China' : 'Beijing',
        'Germany' : 'Berlin',
        'Nigeria' : 'Abuja',
        'Egypt' : 'Cairo',
        'New Zealand' : 'Wellington'
      };

      // Retrieving all the keys 
      var allKeys = capitals.keys;    
      print("Keys: $allKeys");

      // Retrieving all the values
      var allValues = capitals.values;
      print("Values: $allValues");  
    }
```

**Removing a Key-Value Pair**

```dart
    main() {
      var capitals = {    
        'United States' : 'Washington D.C.',
        'England' : 'London',
        'China' : 'Beijing',
        'Germany' : 'Berlin',
        'Nigeria' : 'Abuja',
        'Egypt' : 'Cairo',
        'New Zealand' : 'Wellington'
      };   
      
      // Removing a key-value pair
      capitals.remove('China'); 
                  
      print(capitals);  
    }
```


** Functions **

In computer programming, a function or a method is a block of code that performs a specific task. The block of code is given a name, much like a variable. The function is called using this name whenever that specific task needs to be performed. This removes the need to type the same code over and over again; all you have to do is call the function’s name.

Functions take in inputs called **argument**

**Functions in Dart**

- Built-In Functions
- User-Defined Functions

```dart
main() {} // built-in function
```
**Example**

```dart
// Print the statement "Function Called"
// NB: `void` is useed whenever the function has no return value
void newPrint(){
  print("Function Called");
}

// Return the sum of two numbers
num sum(num x, num y){
  return x+y;
}

main() {
  // Calling newPrint
  newPrint();

  //Calling sum
  var result = sum(5,3);
  print(result);
}
```

**Another Example**
```dart
// Function to find the square of a number
num square(num x) {
  return x * x; 
}
  
// Function to find the sum of the squares of two numbers
num squareSum(num x, num y){
  return square(x) + square(y);
}

main() {
  var result = squareSum(2,5);
  print(result);
}
```

A function can have two types of parameters: **required** and **optional**. The required parameters are listed first, followed by any optional parameters. Optional parameters can be **named** or **positional**.

**Named Parameters**

In a function, named parameters are declared using curly brackets ({}).

```dart
(requiredParam, { optionalParam1, optionalParam2, ...})
```

**Example**
```dart
printer(num n,{String s1, String s2}) { 
  print(n); 
  print(s1); 
  print(s2);
}

main() {
  printer(75, s1: 'hello');
}
```

**Positional Parameters** 

Wrapping a set of function’s parameters in square brackets `([])` marks them as optional parameters.

The syntax is as follows: `(requiredParam, [optionalParam])`

**Example**

```dart
String mysteryMessage(String who, [String what, String where]){
  var message = '$who';
  if(what != null && where == null){
    message = '$message said $what';
  } else if (where != null){
    message = '$message said $what at $where';
  }
  return message;
}

main() {
  var result = mysteryMessage('Billy', 'howdy');
  print(result);
}
```

It is important to mention that one of the main differences between positional and named parameters lies in the fact that you must use positional parameters in the order they are declared. In the example above, we cannot use where without using what. However, this is not the case with named parameters.