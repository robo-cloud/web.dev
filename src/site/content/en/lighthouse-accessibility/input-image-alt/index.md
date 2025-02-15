---
layout: post
title: Ensure input types with a value "image" have alternate text
description: |
  Learn about input-image audit.
date: 2019-05-02
web_lighthouse:
  - input-image-alt
---

When an image is being used as an `<input>` button,
providing alternative text helps screen reader users understand the purpose of the button.
Lighthouse reports when any `<input type="image">` elements do not have `alt` text':

<figure class="w-figure">
  <img class="w-screenshot w-screenshot--filled" src="input-image-alt.png" alt="Lighthouse audit showing input types with a value of 'image' do not have alt attributes">
  <figcaption class="w-figcaption">
    <code>&lt;input type="image"></code> elements do not have <code>alt</code> attributes.
  </figcaption>
</figure>


## How to fix this problem

To fix this problem,
provide `alt` attributes for every `<input type="image">` element.
Decribe the action that occurs when the user clicks on the button
in the `alt` text
(see also [Include text alternatives for images and objects](/labels-and-text-alternatives#include-text-alternatives-for-images-and-objects)):

```html
<form>
  <label>
    Username:
    <input type="text">
  </label>
  <input type="image" alt="Sign in"
             src="./sign-in-button.png">
</form>
```

Even if the image contains only text, provide alternate text.
Screen readers can't translate images of words into output.
Learn more in [Image buttons must have alternate text](https://dequeuniversity.com/rules/axe/3.3/input-image-alt).

{% Aside 'note' %}
You can also use ARIA labels to describe your image buttons,
for example,
`<input type="image" aria-label="Sign in">`
See also
[Using the aria-label attribute](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute) and
[Using the aria-labelledby attribute
](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute).
{% endAside %}

## Tips for writing effective `alt` text

- As previously mentioned, describe the action that occurs when the user clicks on the button.
- `alt` text should give the intent, purpose, and meaning of the image.
- Blind users should get as much information from alt text as a sighted user gets from the image.
- Avoid non-specific words like "chart", "image", or "diagram".

Learn more in
[WebAIM's guide to Alternative Text](https://webaim.org/techniques/alttext/).

<!--
## How this audit impacts overall Lighthouse score

Todo. I have no idea how accessibility scoring is working!
-->
## More information

- [Ensure image buttons have `alt` text audit source](https://github.com/GoogleChrome/lighthouse/blob/master/lighthouse-core/audits/accessibility/input-image-alt.js)
- [axe-core rule descriptions](https://github.com/dequelabs/axe-core/blob/develop/doc/rule-descriptions.md)
