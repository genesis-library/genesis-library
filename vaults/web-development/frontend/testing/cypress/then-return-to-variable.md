Window object method worked for me.

https://filiphric.com/working-with-api-response-data-in-cypress

The code below won't work
```js
  let res
  cy.request('POST', '/api/boards', { name: 'new board' })
    .then( ({ body }) => {
      res = body
    })
  console.log(res)
```

It is actually ran in blocks. 
`beforeEach()` block, 
`it()` block 
and `.then()` block.


then is our only solution is callback hell?

```js
it('creates a new list within a board', () => {
  cy.request('POST', '/api/boards', { name: 'new board' })
    .then((board) => {
      cy.request('POST', '/api/lists', {
          title: 'new list',
          boardId: board.body.id
        })
    })
})
```

Solutions
- aliases
- window object


- aliases
```js

it('creates a new task on a list within a board', function() {
  cy.request('POST', '/api/boards', { name: 'new board' })
    .as('board')
    
  cy.then(() => {
      cy.request('POST', '/api/lists', {
          title: 'new list',
          boardId: this.board.body.id
        })
        .as('list')

    })
})
```

- window object
```js
it('creates a board', () => {
  cy.request('POST', '/api/boards', { name: 'new board' })
    .then((board) => {
      window.board = board.body;
    })
})
```

cons:
tests can be dependent to eachother.