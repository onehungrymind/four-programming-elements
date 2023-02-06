---
title: Iterators
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-05
---

# {{ title }}

---

```javascript
for (let i = 0, len = clients.length; i < len; ++i) {
  console.log(clients[i]);
}
```

```javascript
clients.forEach((client) => console.log(client));
```

```javascript
// Filter
const inactiveClientId = '1';
const filteredClients = clients.filter(
  (client) => client.id !== inactiveClientId
);
// Map
const poachClients = clients.map(
  (client) => (client.company = 'MINE! MWAHAHAHAH!')
);
// Reduce
const totalLTV = clients.reduce((acc, curr) => acc + curr.spend, 0);
```

## In Practice

```javascript
const createClient = (state, payload) => {
  const newClient = Object.assign({}, payload, { id: uuidv4() });
  return {
    clients: [...state.clients, newClient],
    currentClient: state.currentClient,
  };
};
```

```javascript
const updateClient = (state, payload) => {
  return {
    clients: state.clients.map((client) => {
      return client.id === payload.id
        ? Object.assign({}, client, payload)
        : client;
    }),
    currentClient: state.currentClient,
  };
};
```

```javascript
const deleteClient = (state, payload) => {
  return {
    clients: state.clients.filter((client) => client.id !== payload.id),
    currentClient: state.currentClient,
  };
};
```

## Challenges

1. Update your reducer methods to properly modify state using immutable operations
2. Use **array.concat** or **[... ]** for creating a project
3. Use **array.map** and **Object.assign** to update an existing project
4. Use **array.filter** to delete an existing project

## Solutions

```javascript
const loadProjects = (state, payload): ProjectsState => {
  return {
    projects: payload,
    currentProject: null,
  };
};

const selectProject = (state, payload): ProjectsState => {
  return {
    projects: state.projects,
    currentProject: payload,
  };
};

const createProject = (state, payload): ProjectsState => {
  return {
    projects: [...state.projects, payload],
    currentProject: state.currentProject,
  };
};

const updateProject = (state, payload): ProjectsState => {
  return {
    projects: state.projects.map((project) => {
      return project.id === payload.id
        ? Object.assign({}, project, payload)
        : project;
    }),
    currentProject: state.currentProject,
  };
};

const deleteProject = (state, payload): ProjectsState => {
  return {
    projects: state.projects.filter((project) => project.id !== payload.id),
    currentProject: state.currentProject,
  };
};
```
