---
title: Conditionals
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-04
---

# {{ title }}

---

```javascript
true === true;
true === false;
player.id !== payload.id;
player.salary < AVAILABLE_CAP_SPACE;
```

```javascript
savePlayer(player) {
  if (!player.id) {
    this.createPlayer(player);
  } else {
    this.updatePlayer(player);
  }
}
```

```javascript
state.players.map((player) => {
  // SOME_CONDITION ? TRUE_VALUE : FALSE_VALUE
  return player.id === payload.id ? updatePlayer(player) : player;
});
```

```javascript
const calculate = (a, b, operation) => {
  switch (operation) {
    case 'add':
      return a + b;
    case 'subtract':
      return a - b;
    case 'multiply':
      return a * b;
    case 'divide':
      return a / b;
    default:
      return 42; // DUH!
  }
};
```

## In Practice

```javascript
const reducer = (state = initialState, action) => {
  switch (action.type) {
    case 'load':
      return loadPlayers(state, action.payload);
    case 'select':
      return selectPlayer(state, action.payload);
    case 'create':
      return createPlayer(state, action.payload);
    case 'update':
      return updatePlayer(state, action.payload);
    case 'delete':
      return deletePlayer(state, action.payload);
    case 'clear':
      return clearPlayer(state, action.payload);
    default:
      return state;
  }
};
```

```javascript
interface Action {
  type: string;
  payload?: any;
}
```

```javascript
const PLAYER_LOAD = '[Players] Load';
const PLAYER_CREATE = '[Players] Create';
const PLAYER_UPDATE = '[Players] Update';
const PLAYER_DELETE = '[Players] Delete';
const PLAYER_SELECT = '[Players] Select';
```

```javascript
const reducer = (state = initialState, action: Action) => {
  switch (action.type) {
    case PLAYER_LOAD:
      return loadPlayers(state, action.payload);
    case PLAYER_SELECT:
      return selectPlayer(state, action.payload);
    case PLAYER_CREATE:
      return createPlayer(state, action.payload);
    case PLAYER_UPDATE:
      return updatePlayer(state, action.payload);
    case PLAYER_DELETE:
      return deletePlayer(state, action.payload);
    case PLAYER_CLEAR:
      return clearPlayer(state, action.payload);
    default:
      return state;
  }
};
```

## Challenges

1. Create a **reducer** function that accepts **state** and an **action** parameter
2. Add a **switch** statement that evaluates the **action.type**
3. Add a condition for **load**, **read**, **create**, **update**, and **delete**
4. Create an appropriate method for each condition that accepts **state** an **action.payload** parameter
5. **BONUS!** Create an **Action** interface and **action.type constants**

## Hint!

Your methods should just return **state** for now.

```javascript
// HINT: The method should just return state for now
loadPlayers(state, action.payload) => state;
```

