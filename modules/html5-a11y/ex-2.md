# HTML 5 and Accessibility - Exercise 2 - Semantic Elements

In this exercise we will add content to our page using semantically correct elements. Thereby taking advantage of browsers' built-in accessibility features.

## Getting Started

Make sure you have the development environment up and running.

```sh
npm start
```

## Semantic Page Elements

*What does Semantic HTML mean?*

Semantic HTML is markup that introduces meaning to the page rather than just presentation.

```html
<!-- Not Sematic -->
<div>
  <span>Menu</span>
  <span>Navigation Item 1</span>
  <span>Navigation Item 2</span>
  <span>Navigation Item 3</span>
</div>
<div>
  <span>Section Title</span>
  <span>Some very nicely written prose about some topic in this section...</span>
</div>

<!-- Semantic -->
<header>
  <button>Menu</button>
  <nav>
    <ul>
      <li><a href="#">Navigation Item 1</a></li>
      <li><a href="#">Navigation Item 2</a></li>
      <li><a href="#">Navigation Item 3</a></li>
    </ul>
  </nav>
</header>
<section>
  <h1>Section Title</h1>
  <p>Some very nicely written prose about some topic in this section...</p>
</section>
```

HTML 5 introduced numerous new elements that allow for more descriptive segmentation of content on a page. Using these new elements provides instant improvements to screen readers ability to interpret page content as well as makes it easier for web crawlers to index content for SEO.

In this Exercise we will focus on seven new elements:

1. `header` - defines a section which typically contains the logo, title, and navigation. The header can also be used in other semantic elements such as `article` or `section` — or section header, containing perhaps the section's heading, author name, etc. `article`, `section`, `aside`, and `nav` can have their own `header`. Despite its name, it is not necessarily positioned at the beginning of the page or section.
2. `nav` - defines a section that contains navigation links that appear often on a site. You can have primary and secondary menus, but you never nest, or put a `nav` element inside a `nav` element.
3. `main` - represents the dominant content of the `body` of a document. The main content area consists of content that is directly related to or expands upon the central topic of a document, or the central functionality of an application.
4. `section` - defines a section of a document to indicate a related grouping of semantic meaning. Utilize the section element providing extra context from the parent element makes sense.
5. `article` - defines a piece of self-contained content. It does not refer to the main content alone and can be used for comments and widgets.
6. `aside` - defines a section that, though related to the main element, doesn't belong to the main flow, like an explanation box or an advertisement. It has its own outline, but doesn't belong to the main one.
7. `footer` - defines a page footer which typically contains the copyright, legal notices and sometimes some links — or section footer, containing perhaps the section's publication date, license information, etc. `article`, `section`, `aside`, and `nav` can have their own `footer`. Despite its name, it is not necessarily positioned at the end of the page or section.

[Descriptions taken from Mozilla](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines)

## `header` and `nav` Element

Now that you have been introduced to a some of the new elements in HTML 5, let's get started adding them to our page. We are going to start with the `header` and `nav` elements. Note that we are creating a `header` element which is different from the `head` element we worked on in the previous exercise.

To get started, we are going to add the `header` element as the first item inside of the `body` of our page, and then move the `h1` inside of it. We are also going to change the text inside of the `h1`. From this point forward we are building a website for the newly founded company **Coffee and Cats AG**.

```html
...
<body>
  <header>
    <h1>Coffee and Cats AG</h1>
  </header>
</body>
...
```

At the moment we only have one page, but we will add more in the future. In anticipation of these pages, let's add some navigation to our site. We are going to do this using the `nav` element. Inside of the `nav` element, we will use an unordered list (`ul`) element to list each of our navigation links.

Let's add a `nav` element inside of our `header`.

```html
<header>
  ...
  <nav aria-label="Primary Navigation">
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
  ...
</header>
...
```

Notice the attribute we have added to the `nav`element, `aria-label`. This attribute let's us provide a description of the content inside of an element. It is only necessary to provide an `aria-label` when we have multiple tags of the same type on a page. For example, later in this exercise, we will use the `nav` tag again to create "Footer Navigation".

In this specific case, we have told the browser that our `nav` element in the `header` is the "Primary Navigation". When visually impaired users visit our page, as they navigate our page, this label will be read to the user, giving them insight into the type of navigation with which they are interacting.

Mozilla provides a very good explanation about [labelling sections](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements#Labeling_section_content). As does [w3](https://www.w3.org/WAI/tutorials/page-structure/labels/).

Our website for Coffee and Cats AG is starting to take shape. We now have a title and some navigation links on the page. And the best news is that it is completely accessible. For the moment, we will leave these elements unstyled while we continue to add some more semantic markup to our page.

## `main` Element and Hero `section`

At this point, we are now ready to add some content to our home page. In order to inform the browser that this section of the page is, as defined, "the dominant content of the `body` element", we are going to use the `main` element to wrap this page's content.

Have a look at Mozilla's Documentation on the [`main` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main).

Inside of our `main` element, we are going to create a Hero image in order to get website visitors emotionally charged. At the moment, our hero image will be unstyled, so it won't be so emotionally moving, but let's get the content up there anyway.

We are going to give our hero graphic its own `section` which contains an image (`img`), a title (`h2`) and a paragraph (`p`). We are going to use some random images courtesy of [loremflickr](https://loremflickr.com/).

Let's add the `main` element after the closing `header` tag and before the closing `body` tag. Inside of it, we will create our Hero `section`.

```html
...
<main id="main" role="main">
  <section aria-labelledby="hero-label">
    <img src="https://loremflickr.com/1620/800/cat,coffee" alt="a cute cat with coffee" />
    <h2 id="hero-label">Snuggle up with a Cat and some Coffee</h2>
    <p>Whether the weather is hot, cold, rain, snow or sun a cat and some coffee is always fun.</p>
  </section>
</main>
...
```

*Note that our `main` element has an `id` and `role` attribute defined. The `role` is defined in order to support Internet Explorer which otherwise does not know how to interpret the `main` element. We will use the `id` to link directly to the main content of the page from a skiplink next.*

*Note as well the `aria-labelledby` attribute. The `aria-labelledby` attribute is used in combination with an `id` attribute on another element. In this case, it connects the label for the section with the heading with `id="hero-label"`.*

### Skip Navigation Links (skiplinks)

Now that we have a `main` content section on the page, lets go back to our "Primary Navigation" `nav` element and add a skiplinks item to allow screen reader users to jump straight to the main content of the page. To read more about the motivation and implementation details, check out this [Skip Navigation Links Guide](https://webaim.org/techniques/skipnav/).

```html
<nav aria-label="Primary Navigation">
  <ul>
    <li><a href="#main">Skip to Main Content</a></li>
    <!-- the rest of the nav links -->
  </ul>
</nav>
```

When we start to add CSS to our site in Module 2, we will make this skiplink `visually-hidden` so that it does not negatively impact the User Experience for non-visually impaired users.

### Products `section`

Now that our site visitors are emotionally charged to snuggle their cats and drink coffee, let's show them some of our products. To do this, we will create another `section` on the page below our hero `section`. Inside we will add another title (`h2`) and some descriptive text (`p`) to let the user know what they can expect to find in this section of the page.

We will of course continue to develop accessible sections by using the `aria-labelledby` attribute.

```html
<section aria-labelledby="products-label">
  <h2 id="products-label">Coffee and Cats Products</h2>
  <p>Coffee and Cats is here to satisfy all of your Coffee and Cat needs</p>
</section>
```

### Product `article`

We previously defined an `article` as:

> defines a piece of self-contained content. It does not refer to the main content alone and can be used for comments and widgets.

According to that definition, a product card can be implemented as an `article`. For example, if we were to rip the product card our of context, take it off of the home page and put it somewhere else, a user could still figure out what this piece of content is by the content contained inside of the card alone.

So let's create a few product cards as an `article`'s inside of the products `section`. As always, let's provide labels for the `article`'s to allow screen readers to easily understand what is being displayed.

```html
<section aria-labelledby="products-label">
  <h2 id="products-label">Coffee and Cats Products</h2>
  <p>Coffee and Cats AG is here to satisfy all of your foamy and fuzzy needs</p>
  <article aria-labelledby="product-1">
    <img src="https://loremflickr.com/320/320/cappuccino" alt="foamy cappuccino">
    <h3 id="product-1">A Delicious Cappuccino</h3>
    <p>The combination of creamy frothed milk and strong, dark coffee. Cappuccino's are a must for a cold and rainy day.</p>
  </article>
  <article aria-labelledby="product-2">
    <img src="https://loremflickr.com/320/320/siamese,cat" alt="siamese cat">
    <h3 id="product-2">Siamese Cat</h3>
    <p>Siamese cats are very social and affectionate. They meow like its going out of style and can snuggle the whole day long.</p>
  </article>
  <article aria-labelledby="product-3">
    <img src="https://loremflickr.com/320/320/espresso" alt="espresso">
    <h3 id="product-3">Espresso</h3>
    <p>Sometimes the best way to enjoy a coffee is short and intense. Enter the Espresso; pressure extracted pleasure in a demitasse.</p>
  </article>
</section>
```

### Shipping Info `aside`

Coffee and Cats wants to provide some information about their shipping policy. As you have just discovered when creating the product `article`'s they seem to sell live animals! These can obviously not be shipped like the coffee. So we need to explain that somewhere in the products `section`.

While this information is related to the content inside of the products `section`, it is not a product itself and therefore not a part of the main theme. Therefore it fits the definition of an `aside` perfectly.

> defines a section that, though related to the main element, doesn't belong to the main flow, like an explanation box or an advertisement. It has its own outline, but doesn't belong to the main one.

Let's add this shipping information in an `aside` at the end of the products `section`.

```html
<section aria-labelledby="products-label">
  ...
  <aside aria-labelledby="shipping-label">
    <h3 id="shipping-label">Shipping Information</h3>
    <section aria-labelledby="live-animal-shipping">
      <h4 id="live-animal-shipping">Live Animal Shipping</h4>
      <p>As should be clear to you, we cannot ship live animals. Should you be interested in purchasing one of our snuggly cats, please feel free to pay us a visit in the South Pole.</p>
    </section>
    <section aria-labelledby="coffee-shipping">
      <h4 id="coffee-shipping">Coffee Shipping</h4>
      <p>In contrast to our cats, we do ship our coffee worldwide. However, the roads around the South Pole are not always safe to navigate. Depending on the time of year, you may need to wait several months before your coffee arrives.</p>
    </section>
  </aside>
</section>
```

## `footer` Element

Our home page is coming together quite nicely. Although it won't win any design awards, yet, it is extremely well built from an accessibility standpoint. Let's add one more element to the page before wrapping up Exercise 2.

Coffee and Cats would like to provide site vistors with information about their location as well as provide links to some additional pages that were not added to the primary navigation.

This sounds like the perfect use for a `footer`. Let's write the markup for a `footer` with two `sections`; location and footer navigation. We will add the footer after the closing `main` tag and before the closing `body` tag.

```html
...
  </main>
  <footer>
    <nav aria-label="Footer Navigation">
      <ul>
        <li><a href="#">Corporate Information</a></li>
        <li><a href="#">Careers</a></li>
      </ul>
    </nav>
    <section aria-labelledby="location-label">
      <h2 id="location-label">Office Location</h2>
      <address>
        <span>1 Snowy Road</span>
        <span>South Pole, Antarctica</span>
      </address>
    </section>
  </footer>
</html>
```

### `address` Element

For the sake of completeness, you can read more about the [`address` element from Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address).

## Wrapping up

Congratulations! You have completed Exercise 2 of the Junior Front End Developer Skills Tutorial. Please make sure you took the time to read through all of the linked resources in this tutorial. The instructions in this document are brief and focus mostly on implementation. However, to develop a deeper understanding on the underlying concepts, it is important to explore the more detailed resources linked thorughout the tutorial.

To recap, we learned about seven new HTML elements; `header`, `nav`, `main`, `section`, `article`, `aside`, and `footer`. Along the way, we also explored a couple ARIA attribute; `aria-label` and `aria-labelledby`. We setup a skiplink, which will allow screen reader users to skip over the content in the `header` and jump straight to the main content on the page.

By properly using these elements and attributes, we can take advantage of a lot of the native accessibility features built in to browsers. Leaving us with small, manageable tasks like skiplinks to enhance accessible interactions.

In [Exercise 3](/ex-3.md), we will look at the `img` attributes `srcset` and `sizes` to control the size of images that are requested based on the size of the viewport being used to access the site. By using these attribtues, we will improve the performance of our web site when viewed on portable devices by reducing the amount of data transferred.
