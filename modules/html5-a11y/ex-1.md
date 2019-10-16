# HTML 5 and Accessibility - Exercise 1

In this exercise we will setup a semantically correct `html` template and fill it with some unstyled content.

## Getting Started

Make sure you have the development environment up and running.

```sh
npm start
```

## Basic Page Structure

There are a few basic elements that every HTML page needs in order to ensure it is properly rendered by the browser. In this exercise, we are going to take a look at these structural elements:

* `!DOCTYPE`
* `html`
* `head`
* `body`

Open up the file located at `src/index.html` in your IDE of choice (mine is [VS Code](https://code.visualstudio.com/)). Currently, `index.html` only has one line of code `<h1>Hello World!</h1>`. If you look in your browser at `localhost:8080`, it seems to work fine. But notice how none of those important structural elements above are included. Let's add them

### !DOCTYPE

The first thing we need to include in any HTML page, is a `!DOCTYPE` declaration. The purpose of this declaration is to instruct the browser how it should render the page. The most important thing to understand here is that there are different versions of HTML, which are based on different specifications. In order to ensure the browser knows how to interpret our page, we tell it which version of HTML we are using with the `!DOCTYPE` tag. See Mozilla, for a more [detailed description](https://developer.mozilla.org/en-US/docs/Glossary/Doctype).

Let's add our declaration at the top of `index.html` now.

```html
<!DOCTYPE html>

...
```

### `html` Element

Inside of a correctly structure HTML document, we need to make use of the `<html>` tag. According to [Mozilla's description of the html element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)

> The HTML `<html>` element represents the root (top-level element) of an HTML document, so it is also referred to as the root element. All other elements must be descendants of this element.

Let's include the `<html>` element on our page. We will place the `<h1>Hello World!</h1>` inside the tags.

```html
<!DOCTYPE html>
<html lang="en">
  ...
</html>
```


**Notice:** We have also added an attribute `lang` to the `<html>` element. This is a very important addition as it helps the screen reader to: 
* determine the proper language to use when reading the page
* recognize and announce meta data on the page

Again, Mozilla has a very [good explanation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html#Accessibility_concerns) of this.
