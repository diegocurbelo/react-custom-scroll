[![NPM version][npm-image]][npm-url]

# React-Custom-Scroll
An easily designable, cross browser (!!), custom scroll with ReactJS  
Animations and scroll rate **exactly** like native scroll 

##### See a [working demo](http://rommguy.github.io/react-custom-scroll/example/demo.html) ###

### Why do I need this ?  
- Same design on all browsers
- Scrollbar is above the content instead of floating to the side - same layout on scrolled content as not scrolled content

### How to use ?
Custom scroll component is available in commonJS format so you can just require it after installing.  
There is also a UMD version - inside dist directory.  
In both cases **you have to include the customScroll.css** file in your page.  

Wrap your content with the custom scroll component  
Remove any overflow style properties from your content root component - The custom scroll will take care of it


```
import CustomScroll from 'react-custom-scroll';
```

```html
<CustomScroll>
  your content
</CustomScroll>
```
  
### How to change the design ?  
Your own custom design can be applied by styling these 2 classes in your css:  

- custom-scrollbar - this class styles the container of the scroll handle, you can use it if your handle width is greater than the default.  
- inner-handle - this class stlyes the handle itself, you can use it to change the color, background, border and such of the handle  

You can see a usage example in example/firstComp/firstComp.scss  

### Options (react props)

- allowOuterScroll : boolean, default false. Blocks outer scroll while scrolling the content
- heightRelativeToParent : string, default undefined. Content height limit is relative to parent - the value should be the height limit.
- onScroll - function, default undefined. Listener that will be called on each scroll.
- addScrolledClass - boolean, default false. If true, will add a css class 'content-scrolled' while being scrolled.
- freezePosition - boolean, default false. When true, will prevent scrolling. 
- minScrollHandleHeight - number, sets the mimimum height of the scroll handle. Default is 38, as in Chrome on OSX.

##### Example for heightRelativeToParent

```html
<CustomScroll heightRelativeToParent="calc(100% - 20px)">
  your content
</CustomScroll>  
```

### It doesn't work, please help me

- Check if you forgot to remove 'overflow' properties from the content root element.
- If you're using JSX, make sure you use Pascal case and not camelCase \<CustomScroll\> and not \<customScroll\>.  
starting with lower case causes JSX to treat the tag as a native dom element
- Check if your height limit is relative to parent, and you didn't use heightRelativeToParent prop.

### Tests
```bash
npm install
npm test
# Or for continuous run
karma start
```

[npm-image]: https://img.shields.io/npm/v/react-custom-scroll.svg?style=flat-square
[npm-url]: https://npmjs.org/package/react-custom-scroll
[travis-image]: https://img.shields.io/travis/wix/react-custom-scroll/gh-pages.svg?style=flat-square
[travis-url]: https://travis-ci.org/wix/react-custom-scroll
[coveralls-image]: https://img.shields.io/coveralls/wix/react-custom-scroll/gh-pages.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/wix/react-custom-scroll?branch=gh-pages
[downloads-image]: http://img.shields.io/npm/dm/react-custom-scroll.svg?style=flat-square
[downloads-url]: https://npmjs.org/package/react-custom-scroll
