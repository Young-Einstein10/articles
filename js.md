# Objects in Javascript

Objects are one of the most popular and most used data type in Javascript. Everything in JavaScript is either one of the six primitive data types (strings, numbers, booleans, symbols, undefined, and null) or an object. We’ve actually come across objects already, arrays and functions are both objects, although these are built-in objects that are part of the language. In this article, we'll be looking at how objects can be created, how values are stored within them and how to access those values.


#### How are objects created in Javascript

In JavaScript, an object can be created in two ways:

    1. Object literal
    2. Object constructor
**Object Literal**
An object literal is an object that is created directly in the language by wrapping all its properties and methods in curly braces { }. It allows for the creation of objects in no time compared to the constructor method which we will talk about in a bit. Properties are stored in objects as key value pairs where the key is a **string** and the **value** is any any of the data type (be it functions, arrays, string e.t.c). If a property’s value is a
function, it is known as a **method**.

    Syntax:
      var <objectName> = { key1: value1, key2: value2, ...}


The following example creates an hotel object using object literal syntax. 

    var hotel = { 
      name: 'Sheraton',
      location: 'Lagos, Nigeria',
      numberOfRooms: 400,
      open: true
    }

**Object Contructor**

The second way to create an object is with Object Constructor using new keyword. You can attach properties and methods using **dot notation**. Optionally, you can also create properties using square brackets [ ] and specifying property name as string. 

    var hotel = new Object()

    hotel.name = 'Sheraton';
    hotel.location = 'Lagos, Nigeria',
    hotel.numberOfRooms = 400;
    hotel['open'] = true;

#### Accessing Values Within Objects

Property Values within objects are accessed using the Dot Notation or using Square Brackets. Open your browser console and type in the following:

    hotel.name;  // returns Sheraton
    
    hotel['location'];  // returns Lagos, Nigeria