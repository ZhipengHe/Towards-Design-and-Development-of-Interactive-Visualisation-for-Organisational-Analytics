# Web Design

## 1. JavaScript

### [1] Add event listener to detect window resize

#### `resize` event

The `resize` event fires when the document view (window) has been resized.

Example:

```html
<p>Resize the browser window to fire the <code>resize</code> event.</p>
<p>Window height: <span id="height"></span></p>
<p>Window width: <span id="width"></span></p>
```

```JavaScript
const heightOutput = document.querySelector('#height');
const widthOutput = document.querySelector('#width');

function reportWindowSize() {
  heightOutput.textContent = window.innerHeight;
  widthOutput.textContent = window.innerWidth;
}

window.onresize = reportWindowSize;
```

```JavaScript
window.addEventListener('resize', reportWindowSize);
```
