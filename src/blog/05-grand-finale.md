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

const CLIENT_LOAD = '[Client] Load';
const CLIENT_CREATE = '[Client] Create';
const CLIENT_UPDATE = '[Client] Update';
const CLIENT_DELETE = '[Client] Delete';
const CLIENT_SELECT = '[Client] Select';
const CLIENT_CLEAR = '[Client] Clear';

const loadClients = (state, payload): ClientsState => {
  return {
    clients: payload,
    currentClient: null,
  };
};

const selectClient = (state, payload): ClientsState => {
  return {
    clients: state.clients,
    currentClient: payload,
  };
};

const createClient = (state, payload): ClientsState => {
  return {
    clients: [...state.clients, payload],
    currentClient: state.currentClient,
  };
};

const updateClient = (state, payload): ClientsState => {
  return {
    clients: state.clients.map((client) => {
      return client.id === payload.id
        ? Object.assign({}, client, payload)
        : client;
    }),
    currentClient: state.currentClient,
  };
};

const deleteClient = (state, payload): ClientsState => {
  return {
    clients: state.clients.filter((client) => client.id !== payload.id),
    currentClient: state.currentClient,
  };
};

const reducer = (state = initialClientsState, action: Action): ClientsState => {
  switch (action.type) {
    case CLIENT_LOAD:
      return loadClients(state, action.payload);
    case CLIENT_SELECT:
      return selectClient(state, action.payload);
    case CLIENT_CREATE:
      return createClient(state, action.payload);
    case CLIENT_UPDATE:
      return updateClient(state, action.payload);
    case CLIENT_DELETE:
      return deleteClient(state, action.payload);
    default:
      return state;
  }
};
```

```javascript
class Store {
  reducer;
  state: ClientsState;

  constructor(state: ClientsState, reducer) {
    this.reducer = reducer;
    this.state = state;
  }

  getState(): ClientsState {
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
const spiderMan: Client = {
  id: '1111111',
  firstName: 'Miles',
  lastName: 'Morales',
  company: 'High School',
};

const store = new Store(initialClientsState, reducer);
const aClient = store.select('currentClient');
store.dispatch({ type: CLIENT_SELECT, payload: spiderMan });
const bClient = store.select('currentClient');
```
