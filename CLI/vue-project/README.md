````markdown
# 📘 Vue.js Notes

## 1. Introduction to Vue.js
- **What is Vue.js?**  
  Vue.js is a progressive JavaScript framework for building user interfaces and single-page applications (SPAs). It is lightweight, easy to learn, and provides reactive data binding and a component-based architecture.  

- **Benefits of Vue.js**  
  - Easy to integrate with existing projects.  
  - Clear separation of concerns using `template`, `script`, and `style`.  
  - Two-way data binding (MVVM pattern).  
  - Reactive and declarative rendering with minimal code.  
  - Component-based architecture (reusable and modular code).  
  - Rich ecosystem and community support (Vue Router, Vuex, Pinia).  

---

## 2. Vue.js vs React.js
| Feature | Vue.js | React.js |
|---------|--------|----------|
| **Type** | Framework | Library |
| **Learning Curve** | Easier (HTML-like templates) | Steeper (JSX required) |
| **Syntax** | Uses HTML templates with directives (`v-if`, `v-for`, `v-bind`) | Uses JSX (JavaScript + XML) |
| **State Management** | Vuex / Pinia (official) | Redux / Zustand (external) |
| **Two-way Binding** | Yes (`v-model`) | No (one-way binding only) |
| **Flexibility** | Less boilerplate, opinionated | More flexible, unopinionated |
| **Performance** | Similar to React | Similar to Vue |

---

## 3. Installation of Vue.js
There are **two main ways** to use Vue.js:

### 3.1 CDN Method (Quick start for small projects)  
```html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
<div id="app">{{ message }}</div>
<script>
  const app = Vue.createApp({
    data() {
      return { message: "Hello Vue!" }
    }
  });
  app.mount("#app");
</script>
````

### 3.2 Vue CLI (Recommended for large projects)

* Install Node.js first.
* Run:

```bash
npm install -g @vue/cli
vue create my-project
cd my-project
npm run serve
```

---

## 4. Project Structure in Vue

In Vue `.vue` files, we have **three blocks**:

1. `<template>` → For HTML structure.
2. `<script>` → For component logic (JS).
3. `<style>` → For CSS styling (scoped or global).

Example:

```vue
<template>
  <h1>{{ title }}</h1>
</template>

<script>
export default {
  data() {
    return { title: "Welcome to Vue.js" }
  }
}
</script>

<style>
h1 { color: blue; }
</style>
```

---

## 5. Main.js

* `main.js` is the **entry point** of a Vue app.
* It creates the root app and mounts it to an HTML element (`#app`).

```javascript
import { createApp } from 'vue'
import App from './App.vue'

createApp(App).mount('#app')
```

---

## 6. Interpolation & Data Binding

* **Interpolation** → Embedding JS expressions inside template using `{{ }}`.
* Used to pass data from `script` to `template`.

Example:

```vue
<template>
  <h1>Email: {{ email }}</h1>
  <h1>Mobile: {{ mobile }}</h1>
</template>

<script>
export default {
  data() {
    return {
      email: "satyam@gmail.com",
      mobile: 9999
    }
  }
}
</script>
```

---

## 7. Methods in Vue

* Functions are defined inside the `methods` property.
* They can be used inside the template with event bindings.

Example:

```vue
<template>
  <button v-on:click="alertBtn">Click Me</button>
</template>

<script>
export default {
  methods: {
    alertBtn() {
      alert("Button clicked!")
    }
  }
}
</script>
```

---

## 8. Events in Vue

* Vue supports DOM events with `v-on:event` or the shorthand `@event`.

### Common Events:

* `@click` → when button clicked
* `@input` → when user types in input box
* `@keyup` → when a key is pressed
* `@mouseover` → when mouse hovers

### Example: Counter App

```vue
<template>
  <div>
    <h1>Counter: {{ count }}</h1>
    <button @click="increase">+</button>
    <button @click="decrease">-</button>
  </div>
</template>

<script>
export default {
  data() {
    return { count: 0 }
  },
  methods: {
    increase() { this.count++ },
    decrease() { this.count-- }
  }
}
</script>
```

---

## 9. Two-Way Binding

* **Definition:** Two-way binding means data is synced between **model (JavaScript data)** and **view (UI)**.
* In Vue, it is achieved using `v-model`.

Example:

```vue
<template>
  <input v-model="name" placeholder="Enter name" />
  <h2>Hello, {{ name }}</h2>
</template>

<script>
export default {
  data() {
    return { name: "" }
  }
}
</script>
```

* **Model** → Data inside the Vue component (`data()`).
* **View** → The template/UI displayed to the user.

---

