---
title: Iterators
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-05
---

# {{ title }}

---

```javascript
for (let i = 0, len = players.length; i < len; ++i) {
  console.log(players[i]);
}
```

```javascript
players.forEach((player) => console.log(player));
```

```javascript
// Filter
const releasedPlayerID = '1';
const activePlayers = players.filter(
  (player) => player.id !== releasedPlayerID
);
// Map
const administerSupplements = players.map(
  (player) => (player.administer(player.supplements);)
);
// Reduce
const totalPoints = players.reduce((acc, curr) => acc + curr.points, 0);
```

## In Practice

```javascript
const createPlayer = (state, payload) => {
  const newPlayer = Object.assign({}, payload, { id: uuidv4() });
  return {
    players: [...state.players, newPlayer],
    currentPlayer: state.currentPlayer,
  };
};
```

```javascript
const updatePlayer = (state, payload) => {
  return {
    players: state.players.map((player) => {
      return player.id === payload.id
        ? Object.assign({}, player, payload)
        : player;
    }),
    currentPlayer: state.currentPlayer,
  };
};
```

```javascript
const deletePlayer = (state, payload) => {
  return {
    players: state.players.filter((player) => player.id !== payload.id),
    currentPlayer: state.currentPlayer,
  };
};
```

## Challenges

1. Update your reducer methods to properly modify the state using immutable operations.
2. Use **array.concat** or **[... ]** for creating a project. Important! Read the hint for how to handle UUIDs.
3. Use **array.map** and **Object.assign** to update an existing project.
4. Use **array.filter** to delete an existing project.

## Hint!

When you create a new object, a universally unique identifier (UUID) is generally created by the database for it. Since we are not working with a database, we need to simulate that functionality. I have enclosed a sample function you can use to create the UUID for a new object for you to use in your creation method.

```javascript
// THIS IS FOR DEMONSTRATION PURPOSES ONLY!
// YOU DO NOT NEED TO UNDERSTAND HOW IT WORKS
const generateUUID = () => {
    let dt = new Date().getTime();
    return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, (c) => {
        let r = (dt + Math.random()*16)%16 | 0;
        dt = Math.floor(dt/16);
        return (c=='x' ? r :(r&0x3|0x8)).toString(16);
    });
}

const createRecipe = (state, payload): RecipesState => {
  return {
    payload.id = generateUUID();
    // THE REST OF THE FUNCTION
  };
};
```
