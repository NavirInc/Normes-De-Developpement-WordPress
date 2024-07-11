# CSS NAMING CONVENTIONS
We utilize a combination of BEM (Block, Element, Modifier) and namespaced CSS, making the markup slightly more complex to write but significantly enhancing its extensibility over time.

This guide is inspired by the work of Harry Roberts and his two articles:

[More Transparent UI Code with Namespaces](https://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/)

[MindBEMding – getting your head ’round BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)


The work of York's University:

[York's css naming convention](https://www.york.ac.uk/pattern-library/about/css.html)


And finaly, the work of Andy Barnes:

[BEM and SASS: A Perfect Match](https://andrew-barnes.medium.com/bem-and-sass-a-perfect-match-5e48d9bc3894)


## CLASSES VS ID
We exclusively use classes for applying styles, reserving IDs solely for document fragment identifiers, form/input names. IDs should not be used in our CSS.


## USE HYPHEN DELIMITED STRINGS

Class name should always be hyphen delimited `.red-box` and not camel case `.redBox`.


## THE ANATOMY OF A CLASS NAME

#### `.c-utility-nav__link`

`c-` : this is the namespace (component)

`utility-nav` : this is part of the **utility-nav** block

`__link` : this is the **link** element inside the **utility-nav** block


#### `.o-wrapper--main`

`o-`: this is the namespace (object)

`wrapper`: this is the **wrapper** block

`--main`: this is the modified **main** version of the **wrapper** block


## NAMESPACE
Namespaces are a useful way to separate out CSS in two differents types. In a large-scale website, it can be hard to know what CSS it's possible to mess with, and what knock-on effects it might have. Namespaces give us that information.

The namespaces we use are:

#### Objects `o-`

Be careful modifying these: objects can be used in many different contexts in the site, so changing the CSS may change more than your local context. Examples are: the media object, the grid layout

#### Components `c-`

The bread and butter of our CSS. Most parts of the site are components. A component should be able to live in any context and not change, so updating the CSS for a component should bear in mind that capability. Examples: buttons, icons, pagination.

#### Utilities `u-`

Utility classes usually have a single piece of functionality. Therefore they shouldn't be altered or amended.

#### Themes `t-`

This signifies that the styles are to be applied on a themed page. Theme pages might be signifying a different page colour, or a different layout. Theme styles should be cosmetic changes, not structural. Examples: 404 page, dark UI, departmental colours.

#### Scopes `s-`

Scopes are the only time that you will see HTML elements being directly styled in our CSS. It is for areas of the site where the content is user-managed (such as a rich text area) and will not have classes attached. They should give default styling for generic user input. Examples: CMS rich text editors.

#### States `is-` and `has-`

Movable styles that can be applied either when the page is loaded or by JS when the state changes. It shows a temporary, optional or short-lived style. Examples: .is-open, .is-active.

#### Hacks `_`

An underscore at the start of a class name shows that we're only putting this class here as a hack, it should be used sparingly, and never extended.

#### Javascript `js-`

We separate classes used for Javascript hooks from CSS classes. This means they are not bound together. Examples: .c-tabs also has a .js-tabs class to allow JS to apply tab behaviour.


## SASS
To enhance the development experience and simplify the stylesheet, we use the Sass extension language with the SCSS syntax.

Here is an example of using the above naming convention with Sass:


```
.c-parent {
    margin: 3rem 0 2.5rem 0;

    &__first-child {
        width: 1.5rem;
        height: auto;
    }

    &__second-child {
        width: 3rem;
        height: auto;
    }
}
```

This code will be compiled into this code:

```
.c-parent {
  margin: 3rem 0 2.5rem 0;
}
.c-parent__first-child {
  width: 1.5rem;
  height: auto;
}
.c-parent__second-child {
  width: 3rem;
  height: auto;
}
```