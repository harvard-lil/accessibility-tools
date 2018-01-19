Jump to footnotes without losing your spot
==========================================

Footnotes, references, and other parenthetical notes are usually read in
context: it must be easy to navigate back and forth between each note
and the referencing text.

To Do
-----

1. [Make sure links to hashes/fragments work in your project.](../fix-links/)

2. [Make sure your project has css for hiding text, and for hiding text
until people focus on it.](../hidden-text/)

3. See [example.html](./example.html) for a basic implementation of
   accessible footnotes. Open the source in your browser to see how it
   works! Sample css, html, and js is included, along with explanatory
   comments. Of note:

   - The marker of each note is a link.
   - It is easy to see when the marker has keyboard focus.
   - The marker contains hidden text, contextualizing the visible label
     in a non-visual manner. E.g., the marker is read "Footnote 1",
     by a screen reader, rather than merely "1", providing context for
     users who cannot perceive that the marker is in superscript.
   - After following a footnote marker link, one can easily follow a
     link back to the citing text.
   - Again, it is easy to see when the link back to the citing text has
     keyboard focus, and there is hidden text contextualizing the link.
   - A nice usability feature for all people is included: when you jump
     to a footnote, it is clearly highlighted, making it easier to locate
     in the list.
