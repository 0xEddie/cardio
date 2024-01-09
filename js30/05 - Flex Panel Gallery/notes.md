# 05 - Flex Panel Gallery
- flexbox will autosize the width of children to min-content, set `flex: 1` to let `flex-grow` to get the flex children to expand and share the full available space
- good to throw the ol `border: 1px solid red;` on the text blocks when adjusting their layout
- good example of nesting flexboxes
	- `.panel` is the parent flex container of children `.panels`
	- `.panels` is the parent flex container of the `<p>` elements
- checking for `transitionend` of a flex event transition is kinda scuffed
	- Safari transitionend `event.propertyName === flex`
	- Chrome + FF transitionend `event.propertyName === flex-grow`
	- therefore just check if e.propertyName `includes` 'flex', don't check for a specific property