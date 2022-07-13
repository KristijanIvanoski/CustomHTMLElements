# How to define custom dom element

```js
class KristijanHelloElement extends HTMLElement {
  static get observedAttributes() {
    return ['name'];
  }

  constructor() {
    super();
  }

  attributeChangedCallback(name, oldValue, newValue) {
    this.sayHi();
  }

  sayHi = () => {
    this.innerText = "Hi " + this.attributes.getNamedItem("name")?.value;
  }
}

customElements.define('kristijan-hello', KristijanHelloElement);

const changeName = (e) => {
  document.querySelectorAll('kristijan-hello')?.forEach(element =>
    element.setAttribute('name', e.target.value)
  );
}
```

