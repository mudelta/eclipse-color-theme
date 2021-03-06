Eclipse Color Theme
===================

Color themes for Eclipse.

Eclipse Color Theme makes it possible to import and switch color
themes conveniently and without side effects.

You can install the plugin from the
[update site](http://eclipse-color-theme.github.com/update).  After
installing, go to *Window->Preferences->General->Appearance->Color
Theme* to change the color theme.

**Please note:**

* When updating the plugin via Eclipse, go to the preferences page and
  press *OK* once, otherwise you won't see any changes. We're planning
  to fix this.
* When updating from an earlier version than 0.6, please uninstall the
  plugin and the update site, add the site listed above and install it
  again from there. Otherwise you won't see any updates.

Rationale
---------

While Eclipse allows you to change the syntax coloring in great
detail, there is no support for managing multiple color themes. It is
possible to achieve that by importing and exporting preferences files,
but this is inconvenient and likely to mess up your preferences.
Furthermore, color themes have to be created for every single editor,
a theme for the Java editor does not change the XML, JavaScript or
any other editors. This plugin solves these issues by mapping a
generic color theme format to specific preferences entries for each
supported editor.

Editors and themes
------------------

Eclipse Color Theme currently supports the following editors:

* Text
* Java
* Java properties
* XML
* HTML
* CSS
* JavaScript
* C++
* PHP
* Ant
* SQL
* Python
* JSP

Available themes:

* [Inkpot](http://www.eclipsecolorthemes.org/?view=theme&id=4)
* [Zenburn](http://www.eclipsecolorthemes.org/?view=theme&id=2)
* [Vibrant Ink](http://www.eclipsecolorthemes.org/?view=theme&id=3)
* [Oblivion](http://www.eclipsecolorthemes.org/?view=theme&id=19)
* [Obsidian](http://www.eclipsecolorthemes.org/?view=theme&id=21)
* [Tango](http://www.eclipsecolorthemes.org/?view=theme&id=27)
* [Havenjark](http://www.eclipsecolorthemes.org/?view=theme&id=25)

You can download additional themes or create your own on
[eclipsecolorthemes.org](http://eclipsecolorthemes.org).

Adding a theme
--------------

To create a new theme, go to
[eclipsecolorthemes.org](http://eclipsecolorthemes.org), create it,
download it in *.xml format and import it from the Color Theme
preference page.

Adding an editor
----------------

If you would like to add an editor, proceed as follows:

1. Go to the *syntax coloring* preferences page of the editor,
e.g. *C/C++->Editor->Syntax Coloring*.

2. Look at the colour theme keys of one theme (See `ColorThemeKeys`
for all available keys) and set up the syntax colouring using the
colours defined there.

3. Open the editor's preferences file, e.g. *workspace/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.eclipse.cdt.ui.prefs*
and create a new subclass of `ThemePreferenceMapper` where you map the
colour theme's keys to those of the editor. In the future, all mappings will be defined as XML, so you might as well see if the capabilities of the `GenericMapper` are sufficient for your mapping (it doesn't support custom entries or dependent entries right yet). If so, just create a new xml file named after the plugin ID in the `mapper` package.

4. Instantiate and add your mapper in `ColorThemeManager`.

License
-------

Copyright (C) 2011 Felix H. Dahlke and Roger Dudler

This is open source software, licensed under the Eclipse Public
License. See the file COPYING for details.
