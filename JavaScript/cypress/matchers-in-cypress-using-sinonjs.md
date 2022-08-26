# Matchers in Cypress Using SinonJS

Source: https://sinonjs.org/releases/latest/matchers/

For one of my tests, I used the `match()` function to make sure the arguments being passed in match the words I pass into the `match()` function.

This was used like so `Cypress.sinon.match('academy')`:

```javascript
cy.get('@windowOpen').should(
      'be.calledWith',
      Cypress.sinon.match('academy'),
);
```

Matchers can be passed as args to `spy.calledOn`,  `spy.calledWith`,  `spy.returned` and the corresponding `sinon.assert` functions as well as `spy.withArgs`.

There are bunch more too. This can be used not only for matching words but also regex and types. As well as functions.