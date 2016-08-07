#ES 2015

### Getters & Setters

Getter and setters are pseudo properties that return or set a dynamically computed value

```javascript
var obj = {
  a: 1,
  get b() {
    return this.a + 1;
  },
  set b(x) {
    this.a = b / 2;
  }
};
```
### Object.keys

Converts the keys of an object in an array

```javascript
var keys = Object.keys(dictionary);
```

### Var, Let and Const

Var is not blocked scope, hence there is some unexpected behavior.  

```javascript
var day = "today"
if (true) {
  var day = "tomorrow"
}

console.log(day)  // this turns out to be "tomorrow" which is not the usual expected behavior.
```

Let is blocked scope, while const is read-only (like final)


### Arrow Functions

Syntax for maintaining the parent object scope in callback functions

```javascript
var obj = {
  collection: ["bart", "rick", "tom"],
  domain: "names.com",
  cb: function () {
    return this.collection.map(item => {
      return `${ item }@${ this.domain }`
    })
  }
}
```

### Template Strings

- multiline support
- string interpolation
- useful for creating html templates

```javascript
var name = "Bahul Jain"

var template = `
  <div>
    ${ name }
  </div>
`
```

### Destructuring

A way to pluck properties from a data structure and assign them to variables

```javascript
var object = {
  a: 1,
  b: 2
}

var {a, b} = object;
```

```javascript
var prism = {
  l: 10,
  w: 30
}

function volume({l, w, h = 10}) {
  return l * w * h;
}
```

### Rest Parameters

A way to collect multiple parameters into a single one by using `...` before the argument name
 
```javascript
printArgs(1, 2, 3)
 
function printArgs(...args) {
  args.forEach(function (arg) {
    console.log(arg);
  }
}
```
 
### Spread Operator
 
conceptually opposite of the rest parameters. Enables dynamic expansion of expressions
 
```javascript
let nums = [1, 2, 3];
 
function add(x, y , z) {
  return x + y + z;
}

add(...nums)
```
