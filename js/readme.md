## Contents

- [Contents](#contents)
- [General](#general)
- [Prefer custom-elements](#prefer-custom-elements)


## General
Allways prefer to make modular code . 
```js
// Bad
function doSomeWork() {
    // some work
}

doSomeWork();

// good
class WorkerClass {
    constructor(){

    }

    doWork() {

    }
}

new WorkerClass().doWork();

```

## Prefer custom-elements
We prefer custom elements above plain html/css/js. Custom elements can more easily be reused across projects.

html
```html
<custom-header header="header-text"></custom-header>
```
js

```js
class CustomHeader extends HTMLElement {
    constructor() {
        super();
    }
    
    connectedCallback() {
        const header = this.getAttr("header");
        this.innerHTML = `<h2>${header}</h2>`;
    }

}

customElements.define('custom-header', CustomHeader);
```
