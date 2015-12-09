# Arcmedia Sass Structure Boilerplate

Please follow these rules to keep the CSS/Sass files and the the CSS itself more structured and maintainable. There are a lot of different approaches to achieve this. We took out some of them. Please feel free to give us (Arcmedia Frontend Team) some input if you have better solutions.

Ressources:

* Folder Structure: [ITCSS](http://itcss.io/)
* BEM: [BEM – Getting started](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/) / [BEM 101](https://css-tricks.com/bem-101/)
* Naming Convention: [BEMIT](http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)

<br>

## Sass Directories

* **01_settings**<br>
Contains colors, variables and mixins. No CSS declarations at this point.
<br>
* **02_reset**
	* Basic ([html5doctor](http://html5doctor.com/html-5-reset-stylesheet/))
	* Custom: Some custom resets by Arcmedia (like border-box)
	* Form: Cuts out all the browser style for buttons, inputs etc.
<br>    
* **03_vendor**<br>
Contains 3rd partie vendor files (like CSS styles from jQuery-Plugins, Grids  etc.)
<br>
* **04_global**<br>
Styles and classes for global use:
	* basics: Contains some basic styles like links or background-color
	* layout: Layout styles, e.g. a section-wrapper, wrapper with different backgrund-colors etc.
	* print: Styles for the print stylesheet, contains some default styles
	* typography: Place for all default font stylings and all font classes.
<br>
* **05_components**<br>
Contains all BEM components. Each component should be in a sepparated file. 

* **06_utilities**<br>
Utility classes with just a single declaration (e.g. u-mb-20 -> margin-bottom: 20px;).

* **07_overwrites**<br>
Just in case nothing else worked.

<br>

``temp.scss``: is used for temporary CSS declarations such as fixes from the developers etc. This should be reviewed and moved into the correct files/components.

``main.scss``: imports all the files from above. You need to add new files manually.

<br>

## CSS/Sass

We should all write CSS resp. Sass the same way to keep it maintainable. To achieve this, please follow the [Sass Guidlines](http://sass-guidelin.es) (except Architecture part)

#### Naming conventions

To give the classes more sense, we use theme with prefixes

* ``.g-xxx`` for all grid classes (not necessary in every case).
* ``.l-xxx`` for all layout specific classes that may be used in any number of unrelated contexts to the one you can currently see it in.
* ``.t-xxx`` for all typographical classes.
* ``.c-xxx`` for all components (specific piece of UI).
* ``js-xxx`` for classes wich are used for JS (no style declaration on this classes). Removing this classes could break JS functionality.
* ``.has-xxx``, ``.is-xxx`` classes with current state because of a certain condition.
* ``u-xxx``  classes with a very specific role (often providing only one declaration).

#### Please also keep the following rules in mind:

* All Sass files of a project should be added in this folder structure so there is only one file to load from the client
* Avoid using IDs throughout. Using Classes avoids having to use !important 
* Don't nest classes if not neccessary, see [BEM – Getting started](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
* Break files out into small modules/components (avoid having a Sass file that is larger than 100 lines)
* Be generous with commenting
* If a ```:hover``` pseudo class is styled, ```:focus``` should also be styled for accessibility.

<br>

---
Date modified: 2015-10-05

