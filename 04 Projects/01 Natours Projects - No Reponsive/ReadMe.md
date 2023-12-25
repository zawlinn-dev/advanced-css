## What you will learn in this lecture &mdash;

- How to architect and build a simple grid system;

- How the attribute selector works;

- How the `:not` pseudo-class works;

- How `calc()` works, and what's the difference between calc() and simple Sass operations.

```scss
// Variables

$grid-width: 114rem;

$gutter-vertical: 8rem;
// $gutter-horizontal: 6rem;
$gutter-horizontal: 3rem;

// Mixin Method

@mixin clearFix {
  &::after {
    content: "";
    display: table;
    clear: both;
  }
}

// Grid system by using legacy Float CSS property *

.row {
  max-width: $grid-width;
  margin: 0 auto;

  &:not(:last-child) {
    margin-bottom: $gutter-vertical;
  }

  @include clearFix;

  [class^="col-"] {
    // background-color: crimson;

    float: left;

    &:not(:last-child) {
      margin-right: $gutter-horizontal;
    }
  }

  // 1 of 2 columns in a row

  .col-1-of-2 {
    width: calc((100% - #{$gutter-horizontal}) / 2);
  }

  // 1 of 3 columns in a row

  .col-1-of-3 {
    width: calc((100% - 2 * #{$gutter-horizontal}) / 3);
  }

  // 1 of 4 columns in a row

  .col-1-of-4 {
    width: calc((100% - 3 * #{$gutter-horizontal}) / 4);
  }

  // 2 of 3 columns in a row

  .col-2-of-3 {
    width: calc(
      (2 * (100% - 2 * #{$gutter-horizontal}) / 2) + #{$gutter-horizontal}
    );
  }

  // 2 of 4 columns in a row

  .col-2-of-4 {
    width: calc(
      (2 * (100% - 3 * #{$gutter-horizontal}) / 4) + #{$gutter-horizontal}
    );
  }

  // 3 of 4 columns in a row

  .col-3-of-4 {
    width: calc(
      (3 * (100% - 3 * #{$gutter-horizontal}) / 4) + (2 * #{$gutter-horizontal})
    );
  }
}
```

## What you will learn in this lecture &mdash;

- Thinking about components;

- How and why to use utility classes;

- How to use the `background-clip` property.

- How to transform multiple properties simultaneously;

- How to use the `outline-offset` property together with outline;

- How to style elements that ar NOT hovered while others are.

## What you will learn in this lecture &mdash;

- How to build an amazing, rotating card:

- How to use `perspective` in CSS;

- How to use the `backface-visibility` property:

- Using Background blend modes:

- How and when to use `box-decoration-break`:

```scss
// Card Design

.card {
  perspective: 150rem;
  -moz-perspective: 150rem;
  cursor: pointer;

  height: 52rem;

  position: relative;

  &__side {
    transition: all 0.3s;
    width: 100%;
    height: inherit;
    backface-visibility: hidden;
    border-radius: 0.3rem;
    overflow: hidden;
    box-shadow: 0 1.5rem 4rem rgba($color-black, 0.15);

    position: absolute;
    top: 0;
    left: 0;

    &--front {
      background-color: $color-white;
    }

    &--back {
      transform: rotateY(180deg);

      &--1 {
        background: linear-gradient(
          to right bottom,
          $color-secondary-light,
          $color-secondary-dark
        );
      }
      &--2 {
        background: linear-gradient(
          to right bottom,
          $color-primary-light,
          $color-primary-dark
        );
      }
      &--3 {
        background: linear-gradient(
          to right bottom,
          $color-tertiary-light,
          $color-tertiary-dark
        );
      }
    }
  }

  &:hover &__side--front {
    // transform: perspective(1000px) rotateY(180deg);
    transform: rotateY(-180deg);

    // backface-visibility: hidden;
  }
  &:hover &__side--back {
    // transform: perspective(1000px) rotateY(180deg);
    transform: rotateY(0);
    // backface-visibility: hidden;
  }

  &__pic {
    background-size: cover;
    height: 23rem;
    background-blend-mode: screen;
    border-top-left-radius: 3px;
    border-top-right-radius: 3px;
    -webkit-clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);
    clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);

    &--1 {
      background-image: linear-gradient(
          to right bottom,
          $color-secondary-light,
          $color-secondary-dark
        ), url(../img/nat-5.jpg);
    }
    &--2 {
      background-image: linear-gradient(
          to right bottom,
          $color-primary-light,
          $color-primary-dark
        ), url(../img/nat-6.jpg);
    }
    &--3 {
      background-image: linear-gradient(
          to right bottom,
          $color-tertiary-light,
          $color-tertiary-dark
        ), url(../img/nat-7.jpg);
    }
  }

  &__heading {
    font-size: 2.8rem;
    font-weight: 300;
    text-transform: uppercase;
    text-align: right;
    color: $color-white;
    width: 65%;

    position: absolute;
    top: 12rem;
    right: 2rem;
  }

  &__heading--span {
    padding: 1rem 1.5rem;
    -webkit-box-decoration-break: clone;
    box-decoration-break: clone;
    &-1 {
      background-image: linear-gradient(
        to right bottom,
        rgba($color-secondary-light, 0.85),
        rgba($color-secondary-dark, 0.85)
      );
    }
    &-2 {
      background-image: linear-gradient(
        to right bottom,
        rgba($color-primary-light, 0.85),
        rgba($color-primary-dark, 0.85)
      );
    }
    &-3 {
      background-image: linear-gradient(
        to right bottom,
        rgba($color-tertiary-light, 0.85),
        rgba($color-tertiary-dark, 0.85)
      );
    }
  }

  &__details {
    padding: 3rem;

    ul {
      list-style: none;
      width: 80%;
      margin: 0 auto;

      li {
        text-align: center;
        font-size: 1.5rem;
        padding: 1rem;

        &:not(:last-child) {
          border-bottom: 1px solid $color-grey-light-2;
        }
      }
    }
  }

  &__cta {
    position: absolute;
    top: 50%;
    left: 50%;

    transform: translate(-50%, -50%);
    text-align: center;
  }

  &__price-box {
    color: $color-white;
    margin-bottom: 8rem;
  }

  &__price-only {
    font-size: 1.4rem;
    text-transform: uppercase;
  }

  &__price-value {
    font-size: 6rem;
    font-weight: 100;
  }
}
```

## What you will learn in this lecture &mdash;

- How to make text flow around shapes with `shape-outside` and `float`;

- How to apply a `filter` to images:

- How t create a background video covering an entire section:

- How to use the `<video>` HTML element:

- How and when to use the `object-fit` property.

## What you will Learn in the Lecture &mdash;

- How to Implement `solid-color gradients`:

- How the general and adjacent sibling selectors work and why we need them:

- How to use the `::input-placeholder` pseudo-element:

- How and when to se the `:focus, :invalid, placeholder-shown` and `:checked` pseudo-classes;

- Techiques to build custom radio buttons.

```scss
// Form Design

.form {
  // Margin Bottom

  &__group:not(:last-child) {
    margin-bottom: 2rem;
  }

  // Input Design

  &__input {
    font-family: inherit;
    font-size: 1.5rem;
    padding: 1.5rem 2rem;
    background-color: rgba($color-white, 0.5);
    border: none;
    border-radius: 2px;
    border-bottom: 3px solid transparent;

    width: 90%;
    display: block;

    &:focus {
      outline: none;
      box-shadow: 0 1rem 2rem rgba($color-black, 0.1);
      border-bottom: 3px solid $color-primary;
    }

    &:focus:invalid {
      border-bottom: 3px solid $color-secondary-dark;
    }

    &::-webkit-input-placeholder {
      color: $color-grey-dark-2;
    }
  }

  &__label {
    font-size: 1.2rem;
    font-weight: 700;
    margin-left: 2rem;
    margin-top: 0.7rem;
    display: block;
    transition: all 0.3s;
  }

  &__input:placeholder-shown + &__label {
    opacity: 0;
    transform: translateY(-4.2rem);
    visibility: hidden;
  }
}
```

## What you will learn in this lecture &mdash;

- What the `checkbox hack` is and how it works:

- How to create custom animation timing functions using `cubic bezier curves`:

- How to animate `solid-color gradients`:

- How and why to use `transform-origin`:

- In general: create an amazingly creative effect!

```scss
// Variables

$color-grey-dark-3: #333;

// Navigation Design

.navigation {
  &__checkbox {
    display: none;
  }

  &__button {
    background-color: $color-white;
    width: 7rem;
    height: 7rem;
    border-radius: 50%;
    text-align: center;
    cursor: pointer;

    position: fixed;
    top: 6rem;
    right: 6rem;
    z-index: 30;
    box-shadow: 0 1rem 3rem rgba($color-black, 0.1);
  }

  &__background {
    width: 6rem;
    height: 6rem;
    border-radius: 50%;

    position: fixed;
    top: 6.5rem;
    right: 6.5rem;
    z-index: 20;

    background-image: radial-gradient(
      $color-primary-light,
      $color-primary-dark
    );
    // transform: scale(80);
    transition: transform 0.8s cubic-bezier(0.86, 0, 0.07, 1);
  }

  &__nav {
    width: 0;
    height: 100vh;
    opacity: 0;
    transition: all 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    // background-color: crimson;

    position: fixed;
    top: 0;
    left: 0;
    z-index: 25;
  }

  &__list {
    position: absolute;
    top: 50%;
    left: 50%;

    transform: translate(-50%, -50%);
    text-align: center;
    list-style: none;
    width: 100%;
  }

  &__item {
    margin: 1rem;
  }
  &__links {
    &:link,
    &:visited {
      font-size: 3rem;
      font-weight: 300;
      padding: 1rem 2rem;
      color: $color-white;
      text-decoration: none;
      text-transform: uppercase;
      background-image: linear-gradient(
        120deg,
        transparent 0 50%,
        $color-white 0%
      );
      background-size: 220%;
      transition: all 0.4s;
      display: inline-block;

      span {
        margin-right: 1rem;
        display: inline-block;
      }
    }

    &:hover,
    &:active {
      background-position: 100%;
      color: $color-primary;
      transform: translateX(1rem);
    }
  }

  // show background

  &__checkbox:checked ~ &__background {
    transform: scale(80);
  }

  // show navigation

  &__checkbox:checked ~ &__nav {
    opacity: 1;
    width: 100%;
  }

  // ICON

  &__icon {
    position: relative;
    top: 3.5rem;

    &,
    &::after,
    &::before {
      width: 3rem;
      height: 2px;
      background-color: $color-grey-dark-3;
      display: inline-block;
    }
    &::before,
    &::after {
      content: "";
      transition: all 0.2s;

      position: absolute;
      left: 0;
    }

    &::before {
      top: -0.8rem;
      //   transform-origin: right;
    }
    &::after {
      top: 0.8rem;
    }
  }
  &__button:hover &__icon::before {
    top: -1rem;
  }
  &__button:hover &__icon::after {
    top: 1rem;
  }

  &__checkbox:checked + &__button &__icon {
    background-color: transparent;
  }
  &__checkbox:checked + &__button &__icon::before {
    top: 0;
    transform: rotate(135deg);
  }
  &__checkbox:checked + &__button &__icon::after {
    top: 0;
    transform: rotate(-135deg);
  }
}
```

## What you will learn in this lecture &mdash;

- How to build a nice popup with only CSS:

- How to use the `:target pseudo-class`:

- How to create boxes with equal height using `display: table-cell`:

- How to create CSS text columns:

- How to automatically hyphenate words using `hypens`.

[![How To Run](https://img.shields.io/badge/How_to_Run-000?style=for-the-badge&logo=ko-fi&logoColor=white)](#)

1. Open terminal
2. Type this command in terminal and <kbd> Enter</kbd>

   ```sh
   sudo npm install live-server -g
   npm install
   npm run compile:sass
   ```

3. `live-server` on terminal

   `OR`

4. Open with `VS Code` Live Server

> ## Tools &mdash;

- [Easing Function](https://www.easings.net) &mdash;

- [linea icons](https://www.github.com/linea-io/Linea-Iconset) &mdash;

- [Cubic Bezier](https://www.cubic-bezier.com) &mdash;

- [Lorem Genearator](https://www.loremipsumgenerator.com) &mdash;
