---
title: Nouns
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-02
---

# {{ title }}

---

## Objects

```javascript
const client = {
  id: '123',
  firstName: 'John',
  lastName: 'Doe',
  company: 'Acme Inc.',
};
```

```javascript
const newClient = {
  id: null,
  firstName: '',
  lastName: '',
  company: '',
};
```

## A Collection of Objects

```javascript
const clients = [
  {
    id: '1',
    firstName: 'John',
    lastName: 'Doe',
    company: 'Acme, Inc',
  },
  {
    id: '2',
    firstName: 'Jane',
    lastName: 'Smith',
    company: 'Super, Inc',
  },
];
```

## Interfaces

```javascript
interface Client {
  id?: string;
  firstName: string;
  lastName: string;
  company: string;
}
```

```javascript
const clients: Client[] = [
  {
    id: '1',
    firstName: 'John',
    lastName: 'Doe',
    company: 'Acme, Inc',
  },
  {
    id: '2',
    firstName: 'Jane',
    lastName: 'Smith',
    company: 'Super, Inc',
  },
];
```

## Classes

```javascript
class VipClient implements Client {
  firstName;
  lastName;
  company;
  constructor(firstName, lastName, company) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.company = company;
  }
}
```

```javascript
const ironMan = new VipClient('Tony', 'Stark', 'Stark Industries');
console.log(ironMan.firstName); // Tony
console.log(ironMan.lastName); // Stark
console.log(ironMan.company); // Stark Industries
```

## In Practice

```javascript
interface ClientState {
  clients: Client[];
  currentClient: Client;
}
```

```javascript
const newClient: Client = {
  id: null,
  firstName: '',
  lastName: '',
  company: '',
};
const initialState: ClientState = {
  clients,
  currentClient: newClient,
};
```

## Challenges

1. Create an **object** that represents a client **project**
2. Add some approproate **properties** to the **project** object
3. Create an **interface** that represents your **project** model
4. Create an **array** of **project** objects
5. Create an **interface** to represent **project state**
6. Create an **initialState** object that implements a **ProjectsState** interface

## Solutions

```javascript
interface Project {
  id: string;
  title: string;
  description: string;
}

interface ProjectsState {
  projects: Project[];
  currentProject: Project;
}

const firstProject: Project = {
  id: '1',
  title: 'Project 1',
  description: 'This is project 1',
};

const secondProject: Project = {
  id: '2',
  title: 'Project 2',
  description: 'This is project 2',
};

const emptyProject = {
    id: null,
    title: '',
    description: '',
  },

const projects: Project[] = [
  firstProject,
  secondProject,
];

const initialState: ProjectsState = {
  projects,
  currentProject: emptyProject,
}
```