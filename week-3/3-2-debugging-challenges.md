# 3.2: Debugging and Review Challenges

[Python Tutor](http://pythontutor.com/javascript.html#mode=edit) is an excellent resource for debugging, and better understanding the execution of your code.

**Table of Contents:**  
  - 3.2.1: [Declaring Variable](#331-declaring-variables)
  - 3.2.2: [Loops](#332-loops)
  - 3.2.3: [Arrays](#333-arrays)
  - 3.2.4: [Objects](#334-objects)
  - 3.2.5: [Glitch Challenges](#335-glitch-challenges)

<hr/>


## 3.2.1: Declaring Variables
Debug the following code challenges

*Challenge 1: output should be 5*
```
lot x = 5;
console.log(x);
```

*Challenge 2: output should be 7*
```
let x = 5;
let x = x + 2;
console.log(x);
```

*Challenge 3: output should be 'some value'*
```
let myVariableName = 'some value';
myVariobleName = 'some other value';
console.log(myVariableName);
```

*Challenge 4: output should be 5*
```
function pointlessFun() {
   var localX = 5;
   return localX;
}
console.log(localX);
```

## 3.2.2: Loops
Complete the following challenges on loops. To avoid infinite loops crashing your browser, run your code using [Python Tutor](http://pythontutor.com/javascript.html#mode=edit).

*Challenge 1: output should be 99 through 0 bottles of beer on the wall*
```
let bottlesOfBeer = 99;
while (bottlesOfBeer >= 0) {
  console.log(bottlesOfBeer + ' bottles of beer on the wall');
}
```

*Challenge 2: convert the code into a while loop*
```
let dogsWalked = 0;
if (dogsWalked < 2) {
   dogsWalked++;
   console.log("Dogs walked so far: " + dogsWalked); 
}
```

## 3.2.3: Arrays

*Challenge 1: output should be an array with the values 1 through 5*
```
let myArray = {1, 2, 3, 4, 5};
console.log(myArray);
```

*Challenge 2: output should just be 'orange'*
```
let arr = ['red', 'orange', 'yellow'];
console.log(arr);
```


*Challenge 3: output should be the length of the array*
```
let arr = [0, 1, 2, 3, 4];
console.log(length);
```

## 3.2.4: Objects

*Challenge 1: output should be an object with the key:value pairs 1:a and 2:b*
```
let myObject = [
    1: a,
    2: b
];
console.log(myObject);
```

*Challenge 2: output should be the value stored in green*
```
let myObject = {
  blue: 'ocean',
  green: 'chlorophyll'
};
console.log(green);
```

*Challenge 3: output should be the value 'Gunter is the best penguin'*
```
let myObject = {
  penguins: {
    emperor: 'pretty good penguin',
    puffin: 'heck of a penguin',
    gunter: 'Gunter is the best penguin'
  }
};
console.log(gunter);
```

*Challenge 4: output should be the value of flightAbility*
```
let myObject = {
  penguins: [
    emperor,
    puffin,
    gunter,
    {
      beaks: 'excellent',
      flightAbility: 'sub-par'
    }
  ],
};
console.log(flightAbility);
```

## 3.2.5: Glitch Challenges
*Challenge 1:*
https://glitch.com/edit/#!/ltc-wk3-challenge-1

*Challenge 2:*
https://glitch.com/edit/#!/ltc-wk3-challenge-2

*Challenge 3:*
https://glitch.com/edit/#!/ltc-wk3-challenge-3

*Challenge 4:*
https://glitch.com/edit/#!/ltc-wk3-challenge-4

*Challenge 5:*
https://glitch.com/edit/#!/ltc-wk3-challenge-5
