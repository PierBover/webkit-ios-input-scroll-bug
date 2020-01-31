# Webkit iOS scroll bug

When focusing on an `<input>` with `position: fixed;` Safari for iOS presents unexpected scroll jumps.

Another issue with fixed elements is that the user can still scroll while the input is focused and disappear from the viewport (even though it shouldn't as it is fixed).

See the bug in action here: https://www.youtube.com/watch?v=Daa_ctnhG00

See the bug report here: https://bugs.webkit.org/show_bug.cgi?id=207049

This non-standard behavior can be somewhat remedied with this hack:

```css
html, body {
	-webkit-overflow-scrolling : touch !important;
	overflow: auto !important;
	height: 100% !important;
}
```
