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
- add an event listener to the search bar that fires when characters are typed into the search bar
	- the function it calls should call and store the search/filter function results, then display those results
- create a `li` list item for each matched place
	- add the city, state to one span in the `li` then add the population to a second span in the `li`
	- join the list items together into a string so that the `searchResults.innerHTML` can be set to a single string, not an array of list items - otherwise a bunch of `,` commas will be displayed as well
- last 2 goals
	- highlight the search input **in** the search results
		- in the display function, swap out the matched search phrase with a `span` of class `.hl` (highlight)
		- hmmmm it seems to automatically preserve the capitalization when replacing the highlighted bit
	- format the population number to be comma seperated (hint: use the `Number.toLocalString()` method)