## A TRUE REVOLUTION &mdash;

## Flexbox &mdash;

- Flexbox is a new module in CSS3 that makes it easy to align elements to one another, in different directrions and orders

- The main idea behind flexbox is to give the container the ability to expand and to shrink elements to best use all the available space:

- Flexbox replaces float layouts, using less, and more readable and logical code:

- Flexbox completely changes the way that we build one-dimensional layouts:

- A true revolution in CSS!

<br />

![Flex Box](./assets/img/screenshot/s2.png)

<br />

![Flex Properties](./assets/img/screenshot/s3.png)

## Flex Direction &mdash;

<br />

```css
.container {
  display: flex;
  // flex-direction: row; // default
  // flex-direction: row-reverse;
  // flex-direction: column;
  // flex-direction: column-reverse;
}
```

<br />

Flex-direction &mdash; row

<br />

![flex direction : row](./assets/img/screenshot/row.png)

Flex-direction &mdash; row-reverse

<br />

![flex direction : row](./assets/img/screenshot/row-reverse.png)

<br />

Flex-direction &mdash; column

<br />

![flex direction : row](./assets/img/screenshot/column.png)

<br />

Flex-direction &mdash; column-reverse

<br />

![flex direction : row](./assets/img/screenshot/column-reverse.png)

## Flex Justify-Content &mdash;

Acts vertical in column and horizontal in row &mdash;

```css
.container {
  justify-content: space-between;
  justify-content: space-around; // twice of space than both side
  // justify-content: space-evenly; // equal space size
  // justify-content: flex-start;
  // justify-content: flex-end;
  // justify-content: center;
}
```

Justify-content &mdash; space-between

![Flex Properties](./assets/img/screenshot/jc-sb.png)

<br />

Justify-content &mdash; space-around

![Flex Properties](./assets/img/screenshot/jc-sa.png)

<br />

Justify-content &mdash; space-evenly

![Flex Properties](./assets/img/screenshot/jc-se.png)

<br />

Justify-content &mdash; flex-start

![Flex Properties](./assets/img/screenshot/jc-fs.png)

<br />

Justify-content &mdash; flex-end

![Flex Properties](./assets/img/screenshot/jc-fe.png)

<br />

Justify-content &mdash; center

![Flex Properties](./assets/img/screenshot/jc-c.png)

## Align-Item &mdash;

Acts vertical in row and horizontal in column

<br />

Align-item &mdash;

```css
.container {
  // align-items: flex-start;
  // align-items: flex-end;
  // align-items: stretch;
  // align-items: baseline; // adjust baseline of the text
  // align-items: center;
}
```

<br />

align-item &mdash; flex-start

<br />

![align-item: flex-start ](./assets/img/screenshot/ai-fs.png)

<br />

align-item &mdash; flex-end

<br />

![align-item : flex-end](./assets/img/screenshot/ai-fe.png)

<br />

align-item &mdash; center

<br />

![align-item : flex-end](./assets/img/screenshot/ai-c.png)

<br />

align-item &mdash; flex-end

```css
.i4 {
  font-size: 70px;
}
```

<br />

![align-item : flex-end](./assets/img/screenshot/ai-fe.png)
