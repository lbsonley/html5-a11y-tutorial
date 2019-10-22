# HTML 5 and Accessibility - Exercise 1 - Document Structure and Meta Data

In this exercise we will setup a semantically correct `html` page structure and provide it with some important meta data.

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

## Meta Data

### `head` Element

Now that we have defined our `!DOCTYPE` and wrapped everything in an `html` tag, its time to add some meta data to our page. Meta data is information that we want to give the browser about our page. In order to do this, we will use the `head` tag. Inside of the `head` tag, we can include a lot of information, like links to stylesheets or javascript assets, search engine optimization (SEO) information, the character set to use, and more. For now, lets focus on the SEO part. Here is a link to [Mozilla 's description of the `head` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) for completeness.

#### `title` Element

First, our page needs a `title`. If you noticed, the browser tab displaying our page currently says the name `localhost:8080`. It would be better if the title in the browser tab described the content on the page. Let's add a `head` element, and inside of it, a `title` tag to tell the browser how it should call our page.

```html
...
<head>
  <title>Junior Front End Developer Skills Tutorial - Part 1</head>
</head>
...
```

Now, the browser tab title is looking better. In addition to the browser tab title accurately describing the content on our page, Search Engines use the `title` property to display search results. So now, when someone searches for our page on Google, they will see a descriptive title for our Home Page.

The SEO implications of the page title and best practices are very well described in [Mozilla's description of the `title` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title).

#### `meta` Element

If you take a look at a google search result, you will notice that along with the page title, there is normally a nice brief description providing more information about the content on the page. We can add this description and a lot more to our Home Page by using a `meta` tag.

Since we are currently on the topic of SEO, let's add a `description` and some `keywords` to our page. We will do this by writing a `meta` tag with two attributes. The `name` attribute defines what information we are providing to the browser, in this case it will be *description* or *keywords*. The second we will add is going to be the `content` attribute. This is the content to be used for the `name` we provide.

```html
...
<head>
  ...
  <meta name="description" content="My implementation of the Unic Front End Skills repository exercises." />
  <meta name="keywords" content="html5, css, javascript, front end, coding, tutorial" />
</head>
...
```

There is a lot more information we can provide to the browser via the `meta` tag. For a complete list, refer to [Mozilla's documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta).

Before we move on, let's add one more imporant piece of `meta` data to our page, the `charset`. `charset` is short for Character Set. Mozilla has the following to say regarding `charset`.

> The <meta> element declaring the encoding must be inside the <head> element and within the first 1024 bytes of the HTML as some browsers only look at those bytes before choosing an encoding.

> The declared character encoding must match the one the page was saved with to avoid garbled characters and security holes.

> Authors are encouraged to use UTF-8.

Let's follow these best practice and add a `charset` to our page.

```html
...
<head>
  <meta charset="UTF-8" />
  ...
</head>
...
```

## Wrapping Up

Congratulations, you have completed Exercise 1 of the Junior Front End Developer Skills Tutorial. You now know the correct way to structure and HTML page to ensure that it is properly interpreted by the browser. Make sure you took the time to browse through the complete documentation in the links provided above.

### Saving your work

If you haven't already, you should create a branch to hold your work so it can be reviewed during the promotion process.

```sh
# create branch
git checkout -b developer/<your-name>

# create branch on remote and set upstream tracking
git push -u origin $(git rev-parse --abbrev-ref HEAD)

# add your code changes
git add .

# commit them
git commit -m 'html5-a11y-ex-1'

#push them
git push origin
```

In the next exercise, we will add some content to our home page using semantically correct HTML 5 elements. [Instructions for Exercise 2](/ex-2.md).
