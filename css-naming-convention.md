# CSS NAMING CONVENTIONS
We're using a mixture of BEM (Block, Element, Modifier) and namespaced CSS, which means that the markup is slightly more complicated to write but much more extensible over time.


## CLASSES VS ID
We use classes in our markup. IDs are used for document fragment identifiers, form and input names, but should not appear in our CSS.


## THE ANATOMY OF A CLASS NAME
#### Example 1

`.c-utility-nav__link`

`c-` : this is a component

`utility-nav` : this is part of the **utility-nav** block

`__link` : this is the **link** element inside the **utility-nav** block

#### Example 2

`.o-wrapper--main`

`o-`: this is an object

`wrapper`: this is the **wrapper** block

`--main`: this is the modified **main** version of **wrapper**


## USE HYPHEN DELIMITED STRINGS

Class name should always be hyphen delimited and not camel case.

This is wrong :

`.redBox`

This is good :

`.red-box`

## NAMESPACE
Namespaces are a useful way to separate out CSS in two differents types. In a large-scale website, it can be hard to know what CSS it's possible to mess with, and what knock-on effects it might have. Namespaces give us that information.

The namespaces we have are:

Objects `o-`
Be careful modifying these: objects can be used in many different contexts in the site, so changing the CSS may change more than your local context. Examples are: the media object, the grid layout

Components `c-`
The bread and butter of our CSS. Most parts of the site are components. A component should be able to live in any context and not change, so updating the CSS for a component should bear in mind that capability. Examples: buttons, icons, pagination.

Utilities `u-`
Utility classes usually have a single piece of functionality. Therefore they shouldn't be altered or amended.

Themes `t-`
This signifies that the styles are to be applied on a themed page. Theme pages might be signifying a different page colour, or a different layout. Theme styles should be cosmetic changes, not structural. Examples: 404 page, dark UI, departmental colours.

Scopes `s-`
Scopes are the only time that you will see HTML elements being directly styled in our CSS. It is for areas of the site where the content is user-managed (such as a rich text area) and will not have classes attached. They should give default styling for generic user input. Examples: CMS rich text editors.

States `is-` and `has-`
Movable styles that can be applied either when the page is loaded or by JS when the state changes. It shows a temporary, optional or short-lived style. Examples: .is-open, .is-active.

Hacks `_`
An underscore at the start of a class name shows that we're only putting this class here as a hack, it should be used sparingly, and never extended.

Javascript `js-`

We separate classes used for Javascript hooks from CSS classes. This means they are not bound together. Examples: .c-tabs also has a .js-tabs class to allow JS to apply tab behaviour.


