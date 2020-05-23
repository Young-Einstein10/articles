**Object Literals**

```javascript
const obj = {
  name: 'John',
  age: 18
}
```

**Object Constructor**

```javascript
function Person() {
  this.name = 'John';

  this.printName = function() {
    console.log(this.name)
  }
}
```

With the `constructor` method, we can create as many instance of the `Person` object as possible. 

