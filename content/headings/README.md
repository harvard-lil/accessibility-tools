Your Page, at a "Glance"
========================

All page sections should begin with a heading.
https://www.w3.org/WAI/tutorials/page-structure/headings/
http://www.webpagemistakes.ca/heading-hierarchy/

Reason 1: For Navigation
------------------------
The stats vary by study, but the consensus seems to be that at least half of people who use screen readers navigate web pages primarily by heading: there are screen reader shortcuts for leaping from heading to heading, and also features that expose a Table of Contents of headings for people to skim and jump to the desired heading. Kind of like skimming over a page with your eyes, to look for what seems relevant.

If your page doesn't have many headings, has improperly nested headings
(h4 -> h2 -> h1 -> h2), or has visual headings (e.g. bold text) that aren't
marked up as headings, people's experience will be significantly affected.

Reason 2: For Context
---------------------
It's often possible to visually assimilate a lot of information at once.
For example, you may be able to look at a page, observe from visual clues
that you are looking at a list, observe that each list item begins with
numerals formatted in one of three ways, "1", "1.1", or "1.1.1", and
observe that each numeral or set of numerals is followed by text
formatted in title case, e.g. "Your Page at a Glance."
Without any effort at all, most of you can probably parse many visual
targets at once, notice patterns in or formulate abstractions
about those items, and come to the reasonable conclusion that you are
in fact looking at a Table of Contents.

People using screen readers are presented with elements of a web page
one at a time, in sequence, like listening to a telephone menu when you
call customer service. After listening to a few list items in the imaginary
sequence of elements described above, they'll have enough context to notice
patterns as well, and will be able to tell that they have been, for the
past several elements, been navigating within a Table of Contents.

Much better to include a heading at the start, "Table of Contents", so
that no guesswork, no abstracting, and no retracing of steps is necessary.
People are most comfortable when they know exactly where they are:
they'll enjoy your site most if you provide immediate context for all
forthcoming content.

To Fix
------

Add headings to all "sections", even if they aren't marked up as sections.
A good hint: if you've wrapped content in a div/block element and given
it a class name, it might be a good candidate for an introductory heading.

Consider adding subheadings to break up long blocks of text; people
benefit from shorter sections on the web, with more frequent subheadings,
than they tend to need in print.

Make sure that you are using the heading level (h1-h6) that makes sense
semantically, rather than for purely visual reasons. You can use
plugins like the [HTML5 Outliner](https://chrome.google.com/webstore/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo?hl=en)
and similar tools to get a high-level picture of the structure of your
page, if the source code is overwhelming. It can sometimes be a CSS
hassle to follow this rule... but if you write the necessary CSS/SCSS
once, you'll benefit from it throughout the whole project.

If desired, headings can be [hidden](../../code/hidden-text/), if you
decide that the extra context is unnecessary for people who can see the
visual cues.
