---
title: "Understanding the react context system"
author: Lin
date: 2024-01-31 12:36:23 +0200
categories: [React, Context]
tags: [front-end development, react, context, props] # TAG names should always be lowercase
---

The following article aims to answer the following question about React's context system:

- What’s context?
- What’s the difference btn React and Props?
- What the advantages of using Context in React?
- How is Context used in React?
- What issues to watch out off when using context?

If you needed answers to them, here you go. ⬇️

### **What is Context?**

Context is a system that allows us to share data across unrelated components

### **The difference between Context and Props:**

Context is an alternative to Props.

While Props is a system that shares data btn strictly parent and child components, Context is a system that allows sharing of data btn unrelated components.

**_Note:_** Context is not a replacement for Props or Redux

### **How is Context used in React?**

Say we want to share the number 5 across our App() component Here is how we would go about it;

We first create Context as follows;

```jsx
import { useContext } from "react";

const BookContext = createContext();
```

Here is how context is passed between components;

```jsx
<BookContext.Provider value={5}>
	{component we wanna share the data with}
</BookContext.Provider>
```

And here is how Context is consumed/used;

```jsx
import { useContext } from 'react';
import BookContext from 'Whichever component we created context in';

function Component() {
	const num = useContext(BookContext);
	return (
		<div>{num}</div>
	)
```

### Advantages of using Context in React

The most straight forward advantage is that unlike Props which passes data only between parent and child components (_usually in a one way flow, i.e. only from parent to child_), Context can pass data to any component as long as it’s wrapped in `BookContext.Provider`
