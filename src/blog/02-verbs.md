---
title: Verbs
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-03
---

# {{ title }}

---

```javascript
const selectClient = function (clientState, client) {
  return {
    clients: clientState.clients,
    currentClient: client,
  };
};
```

```javascript
const selectClient = (clientState, client) => {
  return {
    clients: clientState.clients,
    currentClient: client,
  };
};
```

```javascript
const selectClient = (clientState, client) => ({
  clients: clientState.clients,
  currentClient: client,
});
```

```javascript
const selectClient = (clientState, client) => {
  return {
    clients: clientState.clients,
    currentClient: client,
  };
};

const spiderMan = {
  id: '1000',
  firstName: 'Peter',
  lastName: 'Parker',
  company: 'Student',
};

// Call the method
selectClient(initialState, spiderMan);

// Store the results
const clientsState = selectClient(initialState, spiderMan);
```

```javascript
class ClientStore {
  clients: Client[];
  currentClient: Client;

  load(clients) {
    this.clients = clients;
  }

  read() {
    return this.clients;
  }

  select(client) {
    this.currentClient = client;
  }

  create(client) {
    this.clients.push(client); // this is bad but hang on
  }
}
```

```javascript
const clientStore = new ClientStore();

clientStore.load(clients);
clientStore.select(clients[0]);

const spiderMan = {
  id: '1000',
  firstName: 'Peter',
  lastName: 'Parker',
  company: 'Student',
};

clientStore.create(spiderMan);
```

## In Practice

```javascript
class Store {
  state;
  constructor(state) {
    //...
  }
  getState() {
    //...
  }
  select(key) {
    //...
  }
}
```

```javascript
class Store {
  state;
  constructor(state) {
    this.state = state;
  }
  getState() {
    return this.state;
  }
  select(key) {
    return this.state[key];
  }
}
```

## Challenges

1. Create a **ProjectStore** class
2. Add a **state** property to the class
3. Add a **constructor** to the class that accepts a **state** parameter
4. Add a **getState** method
5. Add a **select** method
6. Instantiate the **ProjectStore** class with the **initialState** object
7. Call **select** on the class to get the **projects** collection

