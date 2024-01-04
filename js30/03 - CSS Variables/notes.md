# CSS Variables Notes

- variables are commonly defined in the root element

```css
:root {
	--spacing: 10px;
	--blur: 10px;
	--base: #ffc600;
}
```

- the root element can be targeted multiple ways in JS

```js
const root = document.querySelector(':root');
const root = document.documentElement; // same thing
```

- CSS variables can be updated in JS using `setProperty` and `getProperty`
- the first argument is the variable to be updated, the second arg is the value to update to

```js
document.documentElement.style.setProperty(`--${this.name}`, `${this.value}${suffix}`)
```

- for the event handlers, using `onchange` will only trigger on `mouseup`
- therefore to continuously update the CSS variables as the slider is moved around (ie. before `mouseup` is fired), use `mouseover`
- `mouseover` will fire every time the pixel position of the mouse changes, so an additional check (such as if `mousedown`) can be used

```js
inputs.forEach(input => input.addEventListener('change', handleChange));
inputs.forEach(input => input.addEventListener('mousemove', handleChange));
```
