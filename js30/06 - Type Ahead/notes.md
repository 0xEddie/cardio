# 06 - Type Ahead

- getting the data
```js
const endpoint = '<url>';
const cities = [];
fetch(endpoint) // returns promise, so use `.then` to work with the resolved promise
	.then(blob => blob.json()) // the promise returns a blob object with a json parse method
	.then(data => cities.push(...data)) // spread each city's data before pushing into the `cities` array
```

- create a callback function that is fired when user types into the search bar
	- function should filter `cities` array down into a subset of search-matching cities (or states) that are then displayed