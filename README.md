# weighted-random

## Install

You know the drill:

```
npm install @ldegen/weighed-random
```

## Usage

It works like this: You have a (finite) distribution, i.e. an array
containing 'weights'. Use this to create a `WeigtedRandom` function
that will return indices into this array.

``` javascript
var WeightedRandom = require('@ldegen/weighted-random');

// don't worry, weights will be normalized so that the sum up to 1.0
var wr = WeightedRandom([0 ,12, 6, 3]);

// choice will be 
// 0  never, 
// 1  with probability 4/7, 
// 2  with probability 2/7 or 
// 3  with probability 1/7 

var choice = wr(); 
```

By default, `WeightedRandom` uses `Math.random()`, but you can use any
parameter-less function that returns float between 0.0 (inclusive) and 1.0
(exclusive). Just pass it as second argument like this:

```
var wr = WeightedRandom([0 ,12, 6, Math.PI/2], myCustomMathRandomReplacement);
```



