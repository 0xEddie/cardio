# Notes - Day 1 Drum Kit

- ASDFG HJKL keys should play their sound when pressed.
- a CSS class of "playing" should also be applied when the key is pressed
- playing class should also be removed after key is unpressed

- playing class should emphasize the key pressed with a small transform
- CSS is all already written, just add JS

## Solution
- we are using a data-attribute `data-key` to keep track of which sound belongs to which key
- add an event listener to the window, to grab `keydown` events

**Playing audio sound**
- use the event's `keyCode` attribute as a query selector to grab the matching audio element
- if there is a matching audio element, play it, otherwise return nothing.
- before playing the audio element, reset its player time to 0 to rewind it to the start, otherwise it will *only* play if the previous time the button was pressed is *finished* playing

**Emphasizing key pressed**
- use the event's `keyCode` attribute as a query selector to grab the matching drum key element
- add `playing` class to that element

**Removing key emphasis:**

Option 1: Window event listener for `keyup` events, remove class if keyCode matches

Option 2: Listen for a `transitionend` event on each drum key element, then remove class

