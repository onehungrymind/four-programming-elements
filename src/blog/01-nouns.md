---
title: Nouns
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-02
---

# {{ title }}

---

## Values

We are defining a new variable that creates a space in computer memory. The space is defined but it has not been initialized with a value.

```javascript
const user;
```

We are now defining the variable and assigning a value to it.

```javascript
const user = 'John Doe';
```

When we log the **user** variable to the console, we are telling the JavaScript runtime to print whatever value is stored at the memory pointer occupied by the **user** variable.

```javascript
console.log(user); // output: John Doe
```

We can even update the value stored in the **user** memory space.

```javascript
let user = 'John Doe';
console.log(user); // output: John Doe
user = 'Mark James';
console.log(user); // output: Mark James
```

Notice that we used **let** instead of **const** in this case. This is not the right place to get into the underpinnings of how JavaScript works but I recommend that you take a few minutes to read the [const documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) on the [Mozilla Developer Network](https://developer.mozilla.org/en-US/) (MDN). For the record, I use the MDN constantly and it is one of my favorite reference resources.

It is important to know how to set a single variable but just like in the real world, most things are not simple values.

```javascript
const user = {
  firstName: 'John'
  lastName: 'Doe'
}
```

This is where objects come in.

## Objects

```javascript
const qb = {
  id: '123',
  firstName: 'Patrick',
  lastName: 'Mahomes',
  position: 'Quarterback',
};
```

```javascript
const emptyPlayerSlot = {
  id: null,
  firstName: '',
  lastName: '',
  position: '',
};
```

## A Collection of Objects

```javascript
const quarterBack = {
  id: '1',
  firstName: 'Patrick',
  lastName: 'Mahomes',
  position: 'Quarterback',
};

const tightEnd = {
  id: '2',
  firstName: 'Travis',
  lastName: 'Kelce',
  position: 'Tight End',
};

const players = [
  quarterBack,
  tightEnd,
];
```

## Interfaces

```javascript
interface Player {
  id: string;
  firstName: string;
  lastName: string;
  position: string;
}
```

```javascript
const quarterBack: Player = {
  id: '1',
  firstName: 'Patrick',
  lastName: 'Mahomes',
  position: 'Quarterback',
};

const tightEnd: Player = {
  id: '2',
  firstName: 'Travis',
  lastName: 'Kelce',
  position: 'Tight End',
};

const players: Player[] = [
  quarterBack,
  tightEnd,
];
```

## Classes

```javascript
class Rookie implements Player {
  firstName;
  lastName;
  position;
  constructor(firstName, lastName, position) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.position = position;
  }
}
```

```javascript
const draftPick = new Rookie('Isaac', 'Pacheco', 'Running Back');
console.log(draftPick.firstName); // Isaac
console.log(draftPick.lastName); // Pacheco
console.log(draftPick.company); // Running Back
```

## In Practice

```javascript
interface TeamState {
  players: Player[];
  currentPlayer: Player;
}
```

```javascript
const unknown: Player = {
  id: null,
  firstName: '',
  lastName: '',
  position: '',
};

const initialState: TeamState = {
  players,
  currentPlayer: unknown,
};
```

## Challenges
1. Pick something interesting to you such as a player, recipe, album, instrument, etc. 
2. Create an **object** to represent the object of your choice. 
3. Add three or four **properties** that are relevant to your **object** and assign them **values**.
4. Create an interface to represent your **object**.
5. Create an **array** with a few instances of your objects.
6. Create an **interface** to represent the application state of your object i.e. **AlbumsState** or **RecipesState**
7. Create an **initialState** object that implements your state interface
