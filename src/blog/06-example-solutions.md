---
title: Example Solutions
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-07
---

# {{ title }}

---

## Nouns Example Solution

```javascript
interface Recipe {
  id: string;
  title: string;
  description: string;
  serves: string;
}

interface RecipesState {
  recipes: Recipe[];
  currentRecipe: Recipe;
}

const lasagna: Recipe = {
  id: '1',
  title: 'Lasagna',
  description: 'This is a delicious family recipe.',c
  serves: '4 - 6'
};

const enchiladas: Recipe = {
  id: '2',
  title: 'Enchiladas',
  description: 'Welcome to Arizona!',c
  serves: '4 - 6'
}

const emptyRecipe = {
    id: null,
    title: '',
    description: '',
    serves: '',
  },

const recipes: Recipe[] = [
  lasagna,
  enchilada,
];

const initialState: RecipesState = {
  recipes,
  currentRecipe: emptyRecipe,
}
```

## Verbs Example Solution

```javascript
class RecipesStore {
  state: RecipesState;

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

const store = new RecipesStore(initialState);
const recipes = store.select('recipes');
```

## Conditionals Example Solution

```javascript
interface Action {
  type: string;
  payload?: any;
}

const RECIPES_LOAD = '[Recipes] Load';
const RECIPE_CREATE = '[Recipes] Create';
const RECIPE_UPDATE = '[Recipes] Update';
const RECIPE_DELETE = '[Recipes] Delete';
const RECIPE_SELECT = '[Recipes] Select';

const loadRecipes = (state, payload): RecipesState => state;
const selectRecipe = (state, payload): RecipesState => state;
const createRecipe = (state, payload): RecipesState => state;
const updateRecipe = (state, payload): RecipesState => state;
const deleteRecipe = (state, payload): RecipesState => state;

const reducer = (state = initialRecipesState, action: Action): RecipesState => {
  switch (action.type) {
    case RECIPE_LOAD:
      return loadRecipes(state, action.payload);
    case RECIPE_SELECT:
      return selectRecipe(state, action.payload);
    case RECIPE_CREATE:
      return createRecipe(state, action.payload);
    case RECIPE_UPDATE:
      return updateRecipe(state, action.payload);
    case RECIPE_DELETE:
      return deleteRecipe(state, action.payload);
    default:
      return state;
  }
};
```

## Iterators Example Solution

```javascript
const loadRecipes = (state, payload): RecipesState => {
  return {
    recipes: payload,
    currentRecipe: null,
  };
};

const selectRecipe = (state, payload): RecipesState => {
  return {
    recipes: state.recipes,
    currentRecipe: payload,
  };
};

const createRecipe = (state, payload): RecipesState => {
  return {
    payload.id = generateUUID(); // For demonstration purposes only!
    recipes: [...state.recipes, payload],
    currentRecipe: state.currentRecipe,
  };
};

const updateRecipe = (state, payload): RecipesState => {
  return {
    recipes: state.recipes.map((recipe) => {
      return recipe.id === payload.id
        ? Object.assign({}, recipe, payload)
        : recipe;
    }),
    currentRecipe: state.currentRecipe,
  };
};

const deleteRecipe = (state, payload): RecipesState => {
  return {
    recipes: state.recipes.filter((recipe) => recipe.id !== payload.id),
    currentRecipe: state.currentRecipe,
  };
};
```
