# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The router identifies (and assigns custom URLs to) the various routes. The routes themselves define the data and behavior to be loaded when that route is loaded.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    You might add something like
    {{#link-to 'campus'}}Back to All Campuses{{/link-to}}
    in your template file under /campus/boston
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    In the former, the 'product' route is nested inside the 'products' route. When going to a particular product ID page, the template for products will also be displayed. Later is its own custom route (that happens to have the same URL). It will display only the information associated with its own template.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    In the movie route.js file, we can pass params to the model function and get the movie_id from the params object.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    We can access the data provided by a route by referencing 'model' inside HTMLbars braces. For example, '{{model.title}}' or '{{#each model as |book|}}'
    ```
