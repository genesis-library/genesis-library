Situation:
- Project feature flags comes from ```/session``` endpoint
- We are mocking ```/session``` with fixtures.
- I need to read data from that fixture json Which will allow me to decide to run some of the tests or not.
- However, I tried to reach it intercepting my own mocked endpoint


Normally:
```
cy.request().as("myRequest");
cy.get('@myRequest').its('headers')...
```



> cy.intercept() cannot be debugged using cy.request()! Cypress only intercepts requests made by your front-end application.

Which means the `cy.request()` will not fire the `cy.intercept()`



solution:
- Visit a page which will hit ```/session``` endpoint.
```js
Cypress.Commands.add('getSession', sessionName => {  
  // TODO remove /session interception after migration to commonSession  
  cy.intercept('/session', {fixture: `${sessionName ?? 'session'}.json`}).as('getSession');  
  cy.intercept('/common-session', {fixture: `${sessionName ?? 'session'}.json`}).as('getSession');  
});

beforeEach(() => {  
  cy.getSession();  
  cy.visitTaaAdsDetailPage('ferf3f-f34f3-34f34-343f8', '2022-06-02', '2022-06-30')  
  cy.wait('@getSession')  
      .then(intercept => {  
        window.taaEditEnabled = intercept.response.body.seller.eligibility.featureFlags.taaEditEnabled  
      }) 
});

it("Should update budget", () => {
	cy.log(window.taaEditEnabled) // true
})
```


if you don't insist reading config from response, just import the file and read it from there.

Problem with this upper solution:
- I needed ```taaEditEnabled``` before each test. It's a feature flag.
- But I need to open a page which hits ```/session``` endpoint which will slow tests.
- I could put it in ```before()``` but still a bad decision because its a complicated walkaround.
- Reading from json is the best solution.