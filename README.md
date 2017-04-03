# Spread Rest Operator in ES6

We know that ECMA6/ES2015 came up with a lot of new features and syntatic sugars. In this blog, we are going to discuss about a new feature introduced in ECMA6 that is `...`.

`...` is known as **Spread**/**Rest** operator depending upon how and where it is used.

But before we move onto discussing **Spread/Rest** operator, it's important to go into the flashback and take a quick look at the following:

1. **arguments** -  **arguments** is an array like object. It corresponds to the arguments passed to a function. Here is a quick look at it:
```Javascript
(function(a, b, c){
    console.log(arguments);
})(1, 2, 3);
```

Output would be `[1,2,3]`.

2. **apply** - We use apply, when we want a function to be executed as if it is a method of a particular object(delegate this into function). Here is a simple example:
```Javascript
var user = {firstname: 'John', surname: 'Doe'};

function getUserDetails(profession, experience){
    var detail = this.firstname + ' ' + this.surname + ' is an ' + profession + ' with ' + experience + ' years of experience.'
    return detail;
}

getUserDetails.apply(user, ['engineer','20']);
```

and at many a times we have also used it as:
```Javascript
function getSum(){
    var sum = 0;
    for(var i=0; i<arguments.length; i++){
        sum = sum + arguments[i];
    }
    return sum;
}

var numbers = [10, 10, 20, 20, 30];
getSum.apply(null,numbers);
```

3. **concat**

We all have concatenated arrays using the concat functions. Here is an example:
```Javascript
var a = [1, 2];
var b = [3, 4];
a.concat(b);
```

Output would be `[1, 2, 3, 4]`.

Now, let's move onto `spread` operator introduced in **ECMA6**.
```Javacript
function getSum(x, y, z){
    console.log(x+y+z);
}
getSum(...[10,20,30]);
```

We have put `...` in front of array, so it spred the elements of array into individual values.

Now, let's concatenate two arrays:
```Javascript
var a = [1, 2];
var b = [3, 4];
var c = [...a,...b]
console.log(c);
```

Output would be `[1, 2, 3, 4]`;

Now, let's look at the **Rest** operator.

As the name suggests, **Rest** operator will take care of the rest of the parameters. Here is a snippet:
```Javascript
function numbers(x, y, ...z){
    console.log(x, y, z);
}
numbers(1, 2, 3, 4, 5, 6);
```

The output of above code would be `1 2 [3, 4, 5, 6]`.

As you can see the x and y have been assigned the values 1 and 2 respectively whereas rest of the parameters got assigned to z.

> Remmeber: It's the same three dots ..., the **how** and **where** of use make these three dots **Spread** or **Rest**.

That's all for this blog. Happy Learning folks!
