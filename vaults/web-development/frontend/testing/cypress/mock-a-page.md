```
it.only("can mock the index.html itself", () => {
    const mock = `
    <head>
      <script>document.domain = 'localhost';
      var Cypress = window.Cypress = parent.Cypress;
      Cypress.action('app:window:before:load', window);
      </script>
    </head>
    <p>hi there</p>
    `
    cy.route("/index.html", mock)
    cy.visit("index.html")
  }) 
```