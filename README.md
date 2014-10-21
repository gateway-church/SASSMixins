SASSMixins
==========

A collection of helpful SASS mixins

#### @mixin triangle
The triangle mixin is a handy shorthand for creating 100% pure CSS triangles/arrows. It is commonly used inside of a &:before or &:after pseudo element in order to append a triangle to an element.
  
| Argument     | Values                                                                | Defaults  |
| ------------ | :-------------------------------------------------------------------- | :-------- |
| direction    | up, down, left, right, downComm                                       | up        |
| color        | *(any valid CSS color value)*                                         | white     |
| width        | a numeric value that represents the desired width of the triangle     | 100       |
| height       | a numeric value that represents the desired height of the triangle    | $width    |
  
**Example Usage**
```scss
.element {
  &:before {
    @include triangle(down,white,10,10);
  }
}
```

#### @mixin trans-bg
The trans-bg mixin is a quick and easy way to generate a background color with support for alpha transparency. 

| Argument  | Values                                                                  | Default  |
| --------- | :--------                                                               | :------- |
| color     | Any valid CSS color value                                               | --       |
| alpha     | a numeric value from 0 to 1 representing the opacity for the background | 1        |

**Example Usage**
```scss
.element {
  @include trans-bg(#ffffff,.5);
}
```

#### @mixin gradient
Allows quick and easy creation of CSS-based gradients for the background of an element.

| Argument    | Values                    | Default  |
| ---------   | :--------                 | :------- |
| start_color | Any valid CSS color value | --       |
| end_color   | Any valid CSS color value | --       |

**Example Usage**
The following style would generate a gradient that goes from white to black.
```scss
.element {
  @include gradient(white,black);
}
```

#### @mixin gradient-trans
Allows quick and easy creation of CSS-based gradients for the background of an element.

| Argument    | Values                                                                  | Default           |
| ---------   | :--------                                                               | :-------          |
| start_color | Any valid CSS color value                                               | darken($grey,20%) |
| start_alpha | a numeric value from 0 to 1 representing the opacity for the background | 0                 |
| end_color   | Any valid CSS color value                                               | darken($grey,60%) |
| end_alpha   | a numeric value from 0 to 1 representing the opacity for the background | .5                |

**Example Usage**
The following style would generate a gradient that goes from fully opaque white to 20% opaque white.
```scss
.element {
  @include gradient-trans(white,1,white,.2);
}
```

#### @mixin transitions
A quick shorthand mixin for adding a transition property to an element.

| Argument  | Values                                                       | Default     |
| --------  | :------                                                      | :-------    |
| selector  | attribute/property to which you want to apply the transition | all         |
| animation | the easing method to use for the transition                  | ease-in-out |

**Example Usage**
```scss
a { // Apply transitions to all attributes
  background: red;
  @include transitions();

  &:hover {
    background: blue;
  }
}
```

#### @mixin outer-glow
Used to create a subtle outer-glow effect similar to Adobe's Photoshop.

| Argument | Values                                                        | Default           |
| -------- | :------                                                       | :-------          |
| size     | The number of pixels the glow should eminate from the element | 10                |
| spread   | The number of pixels the glow should spread from the element  | 0                 |
| color    | The color of the glow, any valid CSS color value              | rgba(0, 0, 0, .4) |

**Example Usage**
```scss
.element {
  @include outer-glow($color:red);
}
```

#### @mixin bevel
Used to create a beveled effect on a given element.

| Argument | Values                                                         | Default  |
| -------- | :------                                                        | :------- |
| size     | The thickness of the bevel (in pixels)                         | 1        |
| strength | How strong/opaque the bevel should be (opacity)                | .3       |
| reverse  | true/false - wether or not the bevel effect should be reversed | false    |

**Example Usage**
```scss
.element {
  @include bevel();
}
```

#### @mixin border-radius
Used to create cross-browser css-based rounded corners

| Argument | Values                   | Default                                        |
| -------- | :------                  | :-------                                       |
| b-radius | The radius of the border | $b-radius-default (defined in _variables.scss) |

**Example Usage**
```scss
.circle { // Create a circle
  width: 100px;
  height: 100px;
  @include border-radius(50%);
}

.round-box { // Create a soft rounded box
  @include border-radius(3px);
}
```

In addition to the border-radius mixin we've also included a few useful mixins for generating a border radius on individual corners as well as top, bottom, left and right corners.

```scss
@mixin border-top-radius($b-radius:$b-radius-default);

@mixin border-bottom-radius($b-radius:$b-radius-default);

@mixin border-left-radius($b-radius:$b-radius-default);

@mixin border-right-radius($b-radius:$b-radius-default);

@mixin border-top-left-radius($b-radius:$b-radius-default);

@mixin border-bottom-left-radius($b-radius:$b-radius-default);

@mixin border-top-right-radius($b-radius:$b-radius-default);

@mixin border-bottom-right-radius($b-radius:$b-radius-default);
```