# Transitioning from an "auto" value in CSS does not work in some cases

Today I ran into an issue that a transition on the `top` property of a relative element did not work.

```css
/* style.css */
.my-element {
	position: relative;
	transition: top 1s ease-in-out; 
}
```

```javascript
/* script.js */
document.getElementById('actionbutton')
	.addEventListener('click', e => e.target.style.top = '300px' );
```

If I click the button, I'd expect the element to transition the `top` property from `0` to `300`. But my expectation is wrong: when I don't set `top` explicitly in the CSS, it has the value `auto` instead of `0`. The browser behavior of transitions to and from `auto` values clearly defined and as of 2020 has been [under debate for 4 years][1]. Different properties have different [workarounds][2]. In my case, the workaround is to set `top:0;` in the CSS.

You can try for yourself in this fiddle: [https://jsfiddle.net/8g6ay7sr/](https://jsfiddle.net/8g6ay7sr/)

Looking at the [workarounds][2], I ended up learning about [`getComputedStyle`][3], and in the annotations for that method the rabbit hole of CSS [resolved values][4], [computed values][5], and [used values][6].

[1]: https://github.com/w3c/csswg-drafts/issues/626
[2]: https://n12v.com/css-transition-to-from-auto/
[3]: https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle
[4]: https://developer.mozilla.org/en-US/docs/Web/CSS/resolved_value
[5]: https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value
[6]: https://developer.mozilla.org/en-US/docs/Web/CSS/used_value

