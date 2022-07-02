Page object model

Cypress.Commands.add('getSession', sessionName => {  
  cy.intercept('/session', {fixture: `${sessionName ?? 'session'}.json`}).as('getSession');  
});
cy.getSession(FIXTURE)