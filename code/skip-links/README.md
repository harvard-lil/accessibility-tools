Help Keyboard Users and Screen Reader Users Get to the Good Stuff
=================================================================

Keyboard users and screen reader users are presented with each element of
a page, in order, like a giant telephone menu.

That means, unless you help them, they have to navigate through your
entire banner and navigation menu on every page load: before logging
in, while logging in, after logging in, after using the navigation, etc.

To Fix
======

Include a small number of "skip links" in convenient places so people can
jump over content they don't need at the moment, straight to interesting
content.

1. [Make sure links to hashes/fragments work in your project.](../fix-links/README.md)

2. [Make sure your project has css for hiding text, and for hiding text
until people focus on it.](../hidden-text/README.md)

3. Add skip links like this:

   `<a href="#main" class="sr-only sr-only-focusable>Skip to main content</a>`

   That point to specially-added targets like this:

   `<p id="main" tabindex="-1" class="sr-only">Main Content</p>`

   Adding a special destination element is much better than having a
   skip link point to an element already in your DOM, for instance,
   `<main id="main">`, for two reasons.

   1) The element that you skip to needs to have tabindex="-1", which means
   the element is programmatically focusable. If a user accidentally clicks
   on such an element, it and all it's contents will be highlighted by the browser, which is not normally what you want here. By skipping to a
   specially-added element, hidden with the css via the .sr-only class,
   the skipping working without distracting all your sighted users.

   2) If you skip to an element like `<main id="main">`, you don't have
   much control over what is read to screen reader users upon their
   arrival: most likely, nothing will be read. By skipping to a specially-
   added element, you can add a meaningful label. If the link said,
   "skip to main content", you can guarantee that "Main content" is
   announced, when the visitor has reached their destination.


Where to Put Skip Links
-----------------------

1. Almost always, add a "skip to main" link as the first element in the DOM.

2. On almost all long pages, add "skip to top" or similar at regular
   intervals. One good measure: if the page has a table of contents so
   that you can skip to sections, follow each section with a "back to top"
   link that takes you to the top of the table of contents.

3. On pages with interactive sections, like fancy data tables, include
   links so that users can easily jump back and forth between the
   controls and the content. E.g. if the controls are at the top,
   let people skip them over, straight to the content, and give people
   the option to skip back up to the controls once they've reached the
   bottom of the content. If the controls are at the bottom, give people
   the option to skip straight to the tools before reading the content,
   and give people the option to skip back up to the top of the data
   after using the controls.

Where else are you skipping over content with your eyes?
