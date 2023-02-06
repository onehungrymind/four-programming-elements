---
title: Immutable Operations
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-02
---

# {{ title }}

---

## Mutable Operations

### Create

```javascript
case CREATE_WIDGET:
  state.push(action.payload);
  return state;
```

### Update

```javascript
case UPDATE_WIDGET:
  state.forEach((widget, index) => {
    if (widget[comparator] === action.payload[comparator]) {
      state.splice(index, 1, action.payload);
    }
  });
  return state;
```

### Delete

```javascript
case DELETE_WIDGET:
  state.forEach((widget, index) => {
    if (widget[comparator] === action.payload[comparator]) {
      state.splice(index, 1);
    }
  });
  return state;
```

## Immutable Counterparts

### Create

```javascript
case CREATE_ITEM:
  return [...state, action.payload];
case CREATE_ITEM:
  return state.concat(action.payload);
```

> The concat() method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

### Update

```javascript
case UPDATE_ITEM:
  return state.map(item => {
    return item[comparator] === action.payload[comparator]
      ? Object.assign({}, item, action.payload) : item;
  });
```

> The map() method creates a new array with the results of calling a provided function on every element in this array.

> The Object.assign() method is used to copy the values of all enumerable own properties from one or more source objects to a target object. It will return the target object.

### Delete

```javascript
case DELETE_ITEM:
  return state.filter(item => {
    return item[comparator] !== action.payload[comparator];
  });
```

> The filter() method creates a new array with all elements that pass the test implemented by the provided function.
