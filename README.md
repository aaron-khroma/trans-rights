# trans-rights
CSS Transition properties are tedious to say the least. For every single property that you wish to transition, you must separately define the property to transition, the duration, the easing, and the delay. This is doable, but for webpages with many different animations (such as https://styleeyescreative.com), it can be a pain to coordinate and manage everything. This library harnesses the power of Sass to easily standardize and manage CSS transition properties in one place. 

## Rights
Within the context of this utility, the word "right" refers to a reusable animation profile. These profiles define the duration, delay, and easing of a CSS property. This allows you to reuse these definitions independently of whatever properties you may wish to apply them to.

To configure this utility, you should first `@import` it, and then you may define any animation profiles you want within a 2D Sass map named `$trans-rights`. A simple example is shown below:

```
$trans-rights: (
  "example": (
    "duration": 1s, 
    "ease": linear,
    "delay": 0.5s
  ),
);
```

In addition to the functional code of this library, a few variables are defined which can be passed as a value for easing. These cubic bezier data are taken from https://easings.net, and allow for more appealing motion than the standard "linear" and "swing" timing functions.

## Usage
The library includes both a mixin and function, both named `trans()`. The documentation is identical for both, and having both of these utilities lets transition statements be chained for more complex definitions. Always begin by including the mixin, and then define additional animation profiles with the function. The details for each argument are listed below:

- $rights: A string that matches the key of the animation profile you wish to apply. This key must exist within the `$trans-rights` map detailed above.
- $props: A space-delimited, unquoted list of CSS property names. Needless to say, these must all be animatable properties.
- $sub: This is where the duality of the mixin and function comes into play. If you wish to apply a different animation profile to a different set of CSS properties, then pass the function version of the utility as this argument. Chaining subs is very useful and allows for more intricate and appealing movement.

For an example of this library's implementation, see the provided index.scss file as a starting point.

## Transgender Rights
While developing the Style Eyes Creative website, I wrote the word "transition" many times. As a result, I found myself regularly reminded of the struggles of my trans friends and family. In recent years we have seen wave after wave of hatred and intolerance crashing against the transgender community, and I can scarcely imagine the overwhelming weight they bear knowing that much of the world wishes them harm. I live in progressive California, where this vileness is rarely seen, but I will still speak up whenever possible for the hard-working and kind-hearted trans people in my life.

So when began writing this utility that could manage transitions, the name was obvious to me. No matter how obscure it may be, I want to remind anyone who may `@import` it that TRANS RIGHTS ARE HUMAN RIGHTS!