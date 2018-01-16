Make Links Work Properly, Because the Browsers Don't
====================================================

When you follow a link with a hash (e.g. http://example.com/faq/#question1),
your browser ordinarily scrolls to bring the element with id="question1"
into visual focus.

Common uses:
-  Tables of Contents
-  Footnotes
-  [Skip links](https://webaim.org/techniques/skipnav/) for keyboard users

However, there is a long-standing issue with many popular web browsers:
a lot of times, the screen scrolls, but keyboard focus doesn't, making
the link worse than useless. Either:
1) the focus remains on the link element... so the user STILL has to tab
through everything, skipping nothing, AND now they can't even see what
they are tabbing through, since the screen scrolled; or
2) the page refreshes and the keyboard focus is set at the very start of
the page... so the user has to start all over again.

To Fix
------
Include hash-focus.js (or its source, [https://github.com/Automattic/\_s/blob/master/js/skip-link-focus-fix.js](https://github.com/Automattic/_s/blob/master/js/skip-link-focus-fix.js)) in every web project. EVERY web project.

And then you won't have to worry about this.
