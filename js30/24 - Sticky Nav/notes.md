# 24 - Sticky Nav
- use the scroll event, trigger an event on every page scroll event, depending on how far the top of the navbar is from the top of the viewport
	- on page load, figure out where the top of the navbar is `element.offsetTop`
	- compare that to `window.scrollY`, the distance down the page the user has scrolled, then add/remove a class that will change the CSS `position` to/from `fixed`/`relative`
		- New: don't use `position: fixed` anymore, since we have `position: sticky`
		- The reason is that making an element `fixed` will remove it from the document flow, meaning the page content will jerk up unless you also compensate for the height of the `nav` element by adding top padding to the content
- for animating the logo sliding out
	- we can't transition animate going from `0 => auto`, so we have to use a pixel value
	- we can't transition animate `width` so we have to use `max-width`

```css
li.logo {
  max-width: 0;
  overflow: hidden;
  background: white;
  transition: all .5s;
  font-weight: 600;
  font-size: 30px;
}
.fixed-nav li.logo {
  max-width: 500px;
}
```

- a low effort embelleshment is using `scale` to pop the content a little as the page scrolls into view

```css
.site-wrap {
  max-width: 700px;
  margin: 70px auto;
  background: white;
  padding: 40px;
  text-align: justify;
  box-shadow: 0 0 10px 5px rgba(0, 0, 0, 0.05);
  transform: scale(0.98);
  transition: transform 0.5s;
}
.fixed-nav .site-wrap {
  transform: scale(1);
}
```