# Css Clean 1.3.3
#### License: [MIT](https://opensource.org/licenses/MIT)

#### ✅ [All 22 tests pass](#tests)
##  css-clean package


We all write code a little quickly sometimes. This is a package which offers a helping hand to sort, align and clean your CSS and SASS.

## Configuration

example settings
```
cleanCss({
  css : String
  lineBreak : Number, // Optional
  tabSize : 2,  // Optional, default is 2
  tabChar : ' ',  // Optional, default is ' '
})
```

## Sorting properties

##### Before

```css
.comment-module {
  font-size: 16px;
  color: red;
  position: 'relative';
  z-index: 0;
  font-family: 'sans-serif';
}
```

##### After

```css
.comment-module {
  z-index     : 0;
  position    : 'relative';
  color       : red;
  font-family : 'sans-serif';
  font-size   : 16px;
}
```

## Clearly format your `@media` queries

##### Before

```css
@media only screen and (min-device-width: 320px) and (device-width: 320px) and (max-device-width: 736px),
       tv and (min-width: 320px) and (device-width: 320px) and (width: 736px) {
  .comment-module {
   font-size: 18px;
  }
}
```

##### After
```css
@media only screen
       and (min-device-width : 320px)
       and (device-width     : 320px)
       and (max-device-width : 736px),
       tv
       and (min-width        : 320px)
       and (device-width     : 320px)
       and (width            : 736px) {
  .comment-module {
    font-size : 18px;
  }
}
```

## Sort multiple selector names and automatic placement to one line per selector

##### Before

```css
input[type="text"], [class*="btn-grey"], input[type="date"], input[type="number"], textarea {
  color : $grey6;
}
```

##### After
```css
[class*="btn-grey"],
input[type="date"],
input[type="number"],
input[type="text"],
textarea {
  color : $grey6;
}
```

# SASS

## Grouping of variables which are pushed to the top of the file

##### Before

```css
$box-style2 : (bStyle: dotted, bColor: blue, bWidth: medium);
$i : 6;

@mixin does-parent-exist { @if & { &:hover { color : red; } } @else { a { color : red; } } }

$gutter-width : 10px;
```

##### After

```css
$box-style2   : (bStyle: dotted, bColor: blue, bWidth: medium);
$i            : 6;
$gutter-width : 10px;

@mixin does-parent-exist {
  @if & {
    &:hover {
      color : red;
    }
  } @else {
    a {
      color : red;
    }
  }
}
```

## Merging of multiple imports

##### Before

```css
@import "buttons.scss";
@import "forms.scss";
@import "variables.scss";
```

##### After

```css
@import "variables.scss",
        "buttons.scss",
        "forms.scss";
```

## Make your `@each` statements easier to read

##### Before

```css
@each $animal, $color, $cursor in (puma, black, default), (sea-slug, blue, pointer), (egret, white, move) {
  .#{$animal}-icon {
    background-image : url('/images/#{$animal}.png');
    border : 2px solid $color;
    cursor : $cursor;
  }
}
```

##### After

```css
@each $animal,
      $color,
      $cursor in (puma, black, default),
      (sea-slug, blue, pointer),
      (egret, white, move) {
  .#{$animal}-icon {
    border           : 2px solid $color;
    background-image : url('/images/#{$animal}.png');
    cursor           : $cursor;
  }
}
```

## Gradients

##### Before

```css
  .class {
    background : linear-gradient(rgba(33, 34, 30, 0.1), rgba(33, 34, 30, 0.1));
  }
```

##### After

```css
  .class {
    background : linear-gradient(
                   rgba(33, 34, 30, 0.1),
                   rgba(33, 34, 30, 0.1)
                 );
  }
```

Feel free to contribute.


***

## Tests

```
   1. Background......................................................... ✅
   2. basic test......................................................... ✅
   3. acid test.......................................................... ✅
   4. Block Comment...................................................... ✅
   5. bug report......................................................... ✅
   6. CSS variables...................................................... ✅
   7. Empty selector..................................................... ✅
   8. SASS Each (basic).................................................. ✅
   9. SASS for........................................................... ✅
  10. SASS function...................................................... ✅
  11. SASS Import (basic)................................................ ✅
  12. SASS @mixin........................................................ ✅
  13. SASS nested (basic)................................................ ✅
  14. SASS Placeholders (basic).......................................... ✅
  15. SASS while......................................................... ✅
  16. Section title...................................................... ✅
  17. Sorted Selectors (basic)........................................... ✅
  18. Special comment.................................................... ✅
  19. test 10............................................................ ✅
  20. Nested multiple selectors.......................................... ✅
  21. SASS @mixin (arguments)............................................ ✅
  22. SASS Selector Eval (basic)......................................... ✅
```
