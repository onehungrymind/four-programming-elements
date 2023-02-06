---
title: Simple Thought Exercise
layout: post.njk
templateEngineOverride: njk,md
date: 2023-01-01
---

# {{ title }}

---

Imagine you have a laundry basket full of freshly cleaned clothes

<div class="flex">
  <img src="/assets/laundry/messy-laundry-basket.png" class="w-24 h-24">
</div>

You have a bunch of different items of clothing to fold and put away

<div class="flex">
  <img src="/assets/laundry/pants.png" class="w-24 h-24">
  <img src="/assets/laundry/shorts.png" class="w-24 h-24">
  <img src="/assets/laundry/skirt.png" class="w-24 h-24">
  <img src="/assets/laundry/socks.png" class="w-24 h-24">
  <img src="/assets/laundry/dark-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/patterned-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/white-shirt.png" class="w-24 h-24">
</div>

We will fold the clothes and sort them into separate baskets

<div class="flex">
  <img src="/assets/laundry/clean-laundry-basket.png" class="w-24 h-24">
  <img src="/assets/laundry/clean-laundry-basket.png" class="w-24 h-24">
  <img src="/assets/laundry/clean-laundry-basket.png" class="w-24 h-24">
</div>

Do we know the different between these items of clothing?

<div class="flex">
  <img src="/assets/laundry/pants.png" class="w-24 h-24">
  <img src="/assets/laundry/skirt.png" class="w-24 h-24">
  <img src="/assets/laundry/socks.png" class="w-24 h-24">
  <img src="/assets/laundry/dark-shirt.png" class="w-24 h-24">
</div>

What about these items of clothing? 

<div class="flex">
  <img src="/assets/laundry/dark-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/patterned-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/white-shirt.png" class="w-24 h-24">
</div>

Do we fold these the same way? 

<div class="flex">
  <img src="/assets/laundry/pants.png" class="w-24 h-24">
  <img src="/assets/laundry/skirt.png" class="w-24 h-24">
  <img src="/assets/laundry/socks.png" class="w-24 h-24">
  <img src="/assets/laundry/dark-shirt.png" class="w-24 h-24">
</div>

Depending on the item of clothing, we will fold it differently

```javascript
if(item === 'pants') {
  // fold pants
} else if(item === 'shorts') {
  // fold shorts
} else if(item === 'skirt') {
  // fold skirt
} else if(item === 'socks') {
  // fold socks
} else if(item === 'shirt') {
  // fold dark shirt
}
```

Depending on who the item of clothing belongs to, we will sort it into a different basket

```javascript
if(owner === 'dad') {
  // sort into dad's basket
} else if(owner === 'mom') {
  // sort into mom's basket
} else if(owner === 'sister') {
  // sort into sister's basket
} else if(owner === 'brother') {
  // sort into brother's basket
} else if(owner === 'me') {
  // sort into my basket
}
```

We will do the same thing for each item of clothing

<div class="flex">
  <img src="/assets/laundry/dark-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/patterned-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/white-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/dark-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/patterned-shirt.png" class="w-24 h-24">
  <img src="/assets/laundry/white-shirt.png" class="w-24 h-24">
</div>

```javascript
shirts.forEach(shirt => fold(shirt));
```

## The entire process might look something like this... 

First, we decide how we are going to fold each item of clothing

```javascript
const foldPants = pants => {
  // fold pants
};

const foldShorts = shorts => {
  // fold shorts
};

const foldSkirt = skirt => {
  // fold skirt
};

const foldSocks = socks => {
  // fold socks
};

const foldShirt = shirt => {
  // fold shirt
};
```

Next, we loop through each item of clothing and fold it

```javascript
const foldedItems = items.forEach(item => {
  if(item === 'pants') {
    return foldPants(item);
  } else if(item === 'shorts') {
    return foldShorts(item);
  } else if(item === 'skirt') {
    return foldSkirt(item);
  } else if(item === 'socks') {
    return foldSocks(item);
  } else if(item === 'shirt') {
    return foldShirt(item);
  }
});
```

Finally, we loop through the folded clothing and put it in the correct basket

```javascript
const sortedItems = foldedItems.forEach(item => {
  if(item.owner === 'dad') {
    dadBasket.add(item);
  } else if(item.owner === 'mom') {
    momBasket.add(item);
  } else if(item.owner === 'sister') {
    sisterBasket.add(item);
  } else if(item.owner === 'brother') {
    brotherBasket.add(item);
  } else if(item.owner === 'me') {
    myBasket.add(item);
  } 
});
```

🎉 We have just covered the four elements of programming! 🎉