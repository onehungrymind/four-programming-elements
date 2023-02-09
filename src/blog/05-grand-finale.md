---
title: The Grand Finale
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-06
---

# {{ title }}

---

```javascript
interface Action {
  type: string;
  payload?: any;
}

interface TeamState {
  players: Player[];
  currentPlayer: Player;
}

const PLAYERS_LOAD  = '[Players] Load Players';
const PLAYER_CREATE = '[Players] Create Player';
const PLAYER_UPDATE = '[Players] Update Player';
const PLAYER_DELETE = '[Players] Delete Player';
const PLAYER_SELECT = '[Players] Select Player';

const loadPlayers = (state, payload): PlayersState => {
  return {
    players: payload,
    currentPlayer: null,
  };
};

const selectPlayer = (state, payload): PlayersState => {
  return {
    players: state.players,
    currentPlayer: payload,
  };
};

const createPlayer = (state, payload): PlayersState => {
  return {
    players: [...state.players, payload],
    currentPlayer: state.currentPlayer,
  };
};

const updatePlayer = (state, payload): PlayersState => {
  return {
    players: state.players.map((player) => {
      return player.id === payload.id
        ? Object.assign({}, player, payload)
        : player;
    }),
    currentPlayer: state.currentPlayer,
  };
};

const deletePlayer = (state, payload): PlayersState => {
  return {
    players: state.players.filter((player) => player.id !== payload.id),
    currentPlayer: state.currentPlayer,
  };
};

const reducer = (state = initialPlayersState, action: Action): PlayersState => {
  switch (action.type) {
    case PLAYERS_LOAD:
      return loadPlayers(state, action.payload);
    case PLAYER_SELECT:
      return selectPlayer(state, action.payload);
    case PLAYER_CREATE:
      return createPlayer(state, action.payload);
    case PLAYER_UPDATE:
      return updatePlayer(state, action.payload);
    case PLAYER_DELETE:
      return deletePlayer(state, action.payload);
    default:
      return state;
  }
};
```

```javascript
class Store {
  reducer;
  state: PlayersState;

  constructor(state: PlayersState, reducer) {
    this.reducer = reducer;
    this.state = state;
  }

  getState(): PlayersState {
    return this.state;
  }

  select(key: string) {
    return this.state[key];
  }

  dispatch(action) {
    this.state = this.reducer(this.state, action);
  }
}
```

```javascript
const unknown: Player = {
  id: null,
  firstName: '',
  lastName: '',
  position: '',
};

const initialPlayersState: TeamState = {
  players,
  currentPlayer: unknown,
};

const mecole: Player = {
  id: '12345',
  firstName: 'Mecole',
  lastName: 'Hardman',
  position: 'Wide Receiver',
};

const store = new Store(initialPlayersState, reducer);
let ballCarrier  = store.select('currentPlayer');
store.dispatch({ type: PLAYER_SELECT, payload: mecole });
ballCarrier = store.select('currentPlayer');
```
