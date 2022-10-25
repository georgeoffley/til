# `calledWith` Assertion in Cypress

Source: https://docs.cypress.io/guides/references/assertions#Sinon-Chai

The `calledWith` is an assertion you put into a `should()` function as an argument.

`calledWith` is used with the `spy()` function in cypress.

One such example is below.

```javascript
cy.get('@windowOpen').should(
      'be.calledWith',
      Cypress.sinon.match('academy'),
);
```

This is used to check that the next called function is called with the word “academy” in it.

#JavaScript
	#Cypress