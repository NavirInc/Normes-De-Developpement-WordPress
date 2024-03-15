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

