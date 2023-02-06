---
title: Conditionals
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-04
---

# {{ title }}

---

```javascript
true === true
batman.secretIdentity === ‘Bruce Wayne’
client.id !== payload.id
```

```javascript
saveClient(client) {
  if (!client.id) {
    this.createClient(client);
  } else {
    this.updateClient(client);
  }
}
```

```javascript
state.clients.map((client) => {
  // SOME_CONDITION ? TRUE_VALUE : FALSE_VALUE
  return client.id === payload.id ? Object.assign({}, client, payload) : client;
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
      return loadClients(state, action.payload);
    case 'select':
      return selectClient(state, action.payload);
    case 'create':
      return createClient(state, action.payload);
    case 'update':
      return updateClient(state, action.payload);
    case 'delete':
      return deleteClient(state, action.payload);
    case 'clear':
      return clearClient(state, action.payload);
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
const CLIENT_LOAD = '[Client] Load';
const CLIENT_CREATE = '[Client] Create';
const CLIENT_UPDATE = '[Client] Update';
const CLIENT_DELETE = '[Client] Delete';
const CLIENT_SELECT = '[Client] Select';
const CLIENT_CLEAR = '[Client] Clear';
```

```javascript
const reducer = (state = initialState, action: Action) => {
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
    case CLIENT_CLEAR:
      return clearClient(state, action.payload);
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
  ```javascript
  // HINT: The method should just return state for now 
  loadClients(state, action.payload) => state;
  ```
5. **BONUS!** Create an **Action** interface and **action.type constants**


## Solutions

```javascript
interface Action {
  type: string;
  payload?: any;
}

const PROJECT_LOAD    = '[Project] Load';
const PROJECT_CREATE  = '[Project] Create';
const PROJECT_UPDATE  = '[Project] Update';
const PROJECT_DELETE  = '[Project] Delete';
const PROJECT_SELECT  = '[Project] Select';

const loadProjects = (state, payload): ProjectsState => state;

const selectProject = (state, payload): ProjectsState  => state;

const createProject = (state, payload): ProjectsState  => state;

const updateProject = (state, payload): ProjectsState  => state;

const deleteProject = (state, payload): ProjectsState  => state;

const reducer = (state = initialProjectsState, action: Action): ProjectsState => {
  switch (action.type) {
    case PROJECT_LOAD:
      return loadProjects(state, action.payload);
    case PROJECT_SELECT:
      return selectProject(state, action.payload);
    case PROJECT_CREATE:
      return createProject(state, action.payload);
    case PROJECT_UPDATE:
      return updateProject(state, action.payload);
    case PROJECT_DELETE:
      return deleteProject(state, action.payload);
    default:
      return state;
  }
}
```