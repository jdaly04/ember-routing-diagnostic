# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Router creates url paths and points to directory to look for template in.
    Route - define the model hook and defines what happens when you visit that URL route.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember generate route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'boston'}}Boston{{/link-to}}
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
    1) The top one has a nested route for product within products whereas bottom one does not.
    2) The url paths are different (even though they point to same template directory)

    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    Hmm... not entirely sure but based on training repo from yesterday,
    maybe something like this:
      const id = params.movie_id;
      params would then get passed into the model hook as an argument.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    We use handlebars to define what we want to refer to each item returned by the model as. For example, with movies (assuming that movies have a name and title attribute):
    <ul>
      {{#each model as |movie|}}
        <li>Name: {{movie.name}} Title: {{movie.title}}</li>
      {{/each}}
    </ul>
    ```
