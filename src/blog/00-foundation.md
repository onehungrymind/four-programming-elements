---
title: The Foundation
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-01
---

# {{ title }}

---

Before we start writing code, we need to establish the foundation. 


## The Four Elements

- Nouns
- Verbs
- Conditionals
- Iterators


## Describing Things

As small children, we understand that we live in a world with objects. We understand that these objects have characteristics that make them unique. Each characteristic or attribute can store a value that describes the object.

*"The ball is red."*

*"That dog is black."*

*"That car is blue and it has two doors and four wheels."*

We can use data structures to describe these objects.

```javascript
const ball = {
  color: 'red',
}

const dog = {
  color: 'black',
}

const car = {
  color: 'blue',
  doors: 2,
  wheels: 4,
}
```

We can think of data structures as **nouns**.

We can also have more than one object which we refer to as an **array** or **collection**.

```javascript
const infinityStones = [
  redStone,
  blueStone,
  greenStone,
  yellowStone,
  purpleStone,
  orangeStone,
]
```

## Performing Actions

We also understand that objects can perform actions. 

*You can drive a car.*

*A car can stop.*

*You can throw a ball.*

*You can fold a shirt.*

We can use methods to describe these actions.

```javascript
const car = {
  color: 'blue',
  doors: 2,
  wheels: 4,
  drive() {
    console.log('Vroom vroom!')
  },
  stop() {
    console.log('Screech!')
  },
}

myCar.drive();
myCar.stop();
```

```javascript
const ball = {
  color: 'red',
}

me.throw(ball);
```

```javascript
const shirt = {
  color: 'blue',
  fold() {
    console.log('Folded!')
  },
}

me.fold(shirt);
```

We can think of methods as verbs. Like methods, we can capture very sophisticated actions as a single verb. How many things are happening when we fly a plane? 

## Making Decisions

Eventually, we have to make a decision based on some conditions. 

"If you ate your dinner, you can have dessert. Else, you need to go to finish your plate."

"If you are in your pajamas, you can watch TV. Else, you need to get ready for bed."

```javascript
if (child.ateDinner) {
  child.eatDessert();
} else {
  child.finishDinner();
}
```

```javascript
if (child.isInPajamas) {
  child.watchTV();
} else {
  child.getReadyForBed();
}
```

We choose one course of action over another based on conditions. Conditionals are the basis of decision-making in programming. 

## Repeating via Iteration

We can repeat a process several times or until a condition is met.

```javascript
const foldedItems = items.forEach(item => me.fold(item));

const washedDishes = dirtyDishes.forEach(dish => me.wash(dish));
```

We use iterators or loops to act on each item in a collection. 