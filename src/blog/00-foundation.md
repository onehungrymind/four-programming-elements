---
title: The Foundation
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-01
---

# {{ title }}

---

Before we start writing code, we need to establish a solid foundation. As impressive as modern computers are, they are still just a bunch of *really* tiny switches turning on and off. Even the most advanced programs are *just* a bunch of ones and zeroes working together to produce a meaningful outcome. When we understand the first principles that control how a system operates, we can start to deconstruct the system and put it back together in new and novel ways. 

## The Big Reveal

The four things that I realized that I was doing over and over when I programmed are as follows:

- Describing things
- Performing actions
- Making decisions
- Repeating via iteration

Here is a slightly modified and more programming-specific variation:

- Data structures or Nouns
- Functions or Verbs
- Conditionals
- Iterators or Loops

And this is it! It took me 20 years to realize that I was just doing the things that I had *"learned"* within the first couple of weeks of programming.  
## Nouns as Data Structures

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

## Functions as Verbs

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

## Conditional Decision Making

Eventually, we have to make a decision based on a condition or conditions. 

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

## Repeating via Iterators

We can repeat a process several times or until a condition is met.

```javascript
const foldedItems = items.forEach(item => me.fold(item));

const washedDishes = dirtyDishes.forEach(dish => me.wash(dish));
```

We use iterators or loops to act on each item in a collection. 