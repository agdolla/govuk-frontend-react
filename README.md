# govuk-frontend-react

[govuk-frontend](https://github.com/alphagov/govuk-frontend) as React components.


This is proof of concept, showing how <a href="https://github.com/alphagov/govuk-frontend">govuk-frontend</a> can be used as <a href="https://github.com/css-modules/css-modules">CSS modules</a> via a <a href="https://github.com/penx/govuk-frontend-react">set of React components</a> that is <a href="https://www.npmjs.com/package/govuk-frontend-react">published to npm</a>, in a way that is compatible with
<a href="https://github.com/facebook/create-react-app">create-react-app</a>,
<a href="https://nextjs.org">Next.js</a>,
<a href="https://github.com/final-form/react-final-form">Final Form</a>,
<a href="https://github.com/jaredpalmer/formik">Formik</a>,
<a href="https://github.com/ReactTraining/react-router">React Router</a>
and <a href="https://github.com/reach/router">Reach Router</a>,
with support for <a href="https://webpack.js.org/guides/tree-shaking/">tree shaking</a> and <a href="https://reactjs.org/docs/code-splitting.html">code splitting/lazy loading</a>.

See:

https://github.com/govuk-react/govuk-react/issues/76

## Conventions

Common conventions on where our React prop names differ from the nunjucks macro option names.

| nunjucks | react |
| --- | --- |
| element | as  |
| attributes | rest props (where appropriate) |
| text | children (where appropriate) |
| html | children (where appropriate) |
| describedBy | aria-describedby |

## Create React App support

Works! Including:

- Lazy loading/path splitting
- Tree shaking of CSS

See https://github.com/penx/govuk-frontend-react-example

## TODO:

I aim to complete the following as part of the PoC:

- [x] Button
- [x] Header compatible with React Router
- [x] Support for js-enabled class, used by Header, plus any associated JS required by Header
- [x] Input with Final Form and Formik examples.
- [x] Date Input with Final Form and Formik examples.
- [ ] Radios
- [ ] Tables
- [ ] Error summary with Formik and Final Form examples, following govuk design system guidelines.
- [ ] Reach router fixtures
- [x] Code coverage checks in CI
- [ ] 100% code coverage
- [x] Meaningful unit tests
- [x] Use/match govuk-frontend template tests
- [x] Prettier
- [x] Flow
- [x] [Create React App example](https://github.com/penx/govuk-frontend-react-example) with lazy loading/path splitting and tree shaking
- [x] [Next.js example](https://github.com/penx/govuk-frontend-react-example-next)
  - [ ] Support for path splitting blocked by [zeit/next-plugins#190](https://github.com/zeit/next-plugins/pull/190) ([related](https://spectrum.chat/next-js/general/dynamic-css-splitting~03351ba8-e4aa-4788-a8ce-2d765b1b1f61?m=MTUzNzE1NDM5ODQ5OQ==))
- [ ] Server side only example with form submit and display of form errors
- [ ] Separate styling and templates, e.g. so the same templates could be used by plain CSS classes, CSS modules or CSSinJS classes passed in as props

Other TODO:

- [ ] Script to convert govuk-frontend attributes to prop types (or Flow types)
- [ ] Export standalone templates, CSS includes and CSS modules separately, e.g. `import { Button } from 'govuk-frontend-react'` `import { Button } from 'govuk-frontend-react-templates'`, `import { Button } from 'govuk-frontend-react-modules'`
- [ ] Use Jest snapshots from govuk-frontend rather than manually copying
- [ ] refactor render.js so that it is easier to scale


## Grey areas

Things that I'm not 100% on how to deal with:

- custom CSS classes such as "width-2" class on Input being passed in as props but are actually CSS modules - could look up via a classNames object first?
- should we allow shortcuts so that `label={{children: 'Label'}}` can just be specified as `label="Label"`? Or should we separate in to two props, `label` and `labelProps`?

### govuk-frontend related issues

- https://github.com/alphagov/govuk-frontend/issues/1095
- https://github.com/alphagov/govuk-frontend/issues/1150
- https://github.com/alphagov/govuk-frontend/issues/1151
- https://github.com/alphagov/govuk-frontend/issues/460
