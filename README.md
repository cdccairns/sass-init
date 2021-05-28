# sass-init

## Directory structure

The directory structure is derived from [ITCSS](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/).

* **Settings**: configuration switches and global variables.
* **Tools**: mixins and functions.
* **Base**: global reset rules and document-level (`html`, `body`) selectors.
* **Elements**: basic styles for *unclassed* element selectors (e.g. `h1`, `a`, `ol`).
* **Objects**: abstract, extendable [layout primitives](https://every-layout.dev/layouts/) (e.g. grids, containers, the media object).
* **Components**: discrete UI components.
* **Scope**: add or override styles in a specific context, for example when styling content from a rich text editor.
* **Utilities**: utility classes. Rules in this layer are usually declared `!important` and are intended to override styles in preceding layers.

## Naming convention

Class selectors employ the [BEMIT](https://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces) naming convention, i.e. [BEM](https://en.bem.info/methodology/css/) (*Block*, *Element*, *Modifier*) classes prefixed according to the layer in which they originate:

* `o-` denotes an *Object*
* `c-` denotes a *Component*
* `s-` denotes a *Scope*
* `u-` denotes a *Utility* class

### Stateful classes and attribute selectors

Although the prefixes `is-` and `has-` *can* be used to indicate a component's state, it is often possible and preferable to use an ARIA [attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors/), e.g.:

* `[aria-current="page"]` instead of `.is-current`
* `[aria-expanded="true"]` instead of `.is-expanded`
* `[aria-hidden="true"]` instead of `.is-hidden`

The advantage of this method is that it relies upon (and therefore requires) the implementation of ARIA attributes, which are fundamental to the development of accessible websites.

Other (data) attribute selectors can also be useful in certain contexts, as an alternative to a modifier or *Utility* class and/or as a JavaScript hook. Use for example:

* `[data-aspect-ratio="3:1"]` to adjust a component's aspect ratio
* `[style*="background-image"]` to style a component with an inline background image
* `a[href="#main"]` to style a [skip link](https://www.w3.org/TR/WCAG20-TECHS/G1.html)
* `a[target="_blank"]` to style links which open in a new window

## Resources

* [Xfive: ITCSS: Scalable and Maintainable CSS Architecture](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/) by Lubos Kmetko
* [CSS Wizardry: More Transparent UI Code with Namespaces](https://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/)
* [CSS Wizardry: BEMIT: Taking the BEM Naming Convention a Step Further](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)
* [GOV.UK Frontend](https://github.com/alphagov/govuk-frontend/tree/master/src/govuk/) by the GOV.UK Design System team
* [Every Layout](https://every-layout.dev/)
* [Grid By Example](https://gridbyexample.com) (see [Resources](https://gridbyexample.com/resources/))
* [The A11Y Project](https://www.a11yproject.com/)
* [Accessibility Developer Guide](https://www.accessibility-developer-guide.com/)
* [Inclusive Components](https://inclusive-components.design/)
