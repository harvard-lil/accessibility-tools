It's All About Context
======================

Totally Hidden
--------------

It's often useful to supply a little information behind the scenes
to screen reader users, information conveyed via layout or other
visual cues to sighted users.

For instance, if you use an icon depicting a floppy disk to indicate a
"save" button, screen reader users should hear the word "save" when
focusing on the button.

It is easy to reveal text to screen reader users and hide it from
sighted users using css... though finding the correct css
more difficult than you would expect. Don't try to roll your own.

Sometimes Hidden
----------------

It's sometimes useful to have text that is hidden until keyboard
focus lands on it, at which point it is revealed: this is how [skip
links](../skip-links/README.md) should work. That way, people using
keyboards without the help of a screen reader (for instance, people
with motor disabilities, or your site's power users!) can get the
benefit of your skip links.


To Do It
--------

Option (1): use Bootstrap. It includes the classes `.sr-only` and
`.sr-only-focusable` by default.

Option (2): go grab the `.sr-only` and
`.sr-only-focusable` from the [Bootstrap source](https://github.com/twbs/bootstrap/blob/v4-dev/scss/mixins/_screen-reader.scss), and include it in
your project's css. ([Local copy](./sr-text-bootstrap.css))

Option (3): grab the `.screen-reader-text` class from
[Underscores](https://github.com/Automattic/_s/blob/master/sass/modules/_accessibility.scss)
and include it in your project's css and use it in place of both `.sr-only`
and `sr-only-focusable` in all the examples in this repo. ([Local copy](./sr-text-wordpress.scss))

Option (4): there may be other libraries out there that do this well,
but make sure you do your research before trusting them. Many libraries
attempt to do this, but do it poorly. There are also LOTS of outdated
or inaccurate blogs/tutorials on the web about this topic. So be careful.

Even in projects where (1) and (2) are your go-to, in certain
situations you might prefer the appearance of (3) for skip links: they
are always rendered in the upper-left of the screen, on top of all
other content. Bootstrap-style elements cause the DOM to shift when
revealed. One or the other may be more suited for skip links and other
reveal-on-focus text in your project's design. Compare
[https://osc.hul.harvard.edu/](https://osc.hul.harvard.edu/) (Bootstrap-style)
and [http://copyright.lib.harvard.edu/](http://copyright.lib.harvard.edu/)
(Wordpress style).


When To Do It
-------------

Whenever something is obvious because of visual cues rather than page
content, and you decide adding visible content isn't a good option.
