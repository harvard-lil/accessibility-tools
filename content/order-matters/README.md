1-D vs 2-D Browsing
===================

It's possible for some people to process a fair bit of visual information
all at once. For example, when looking at a web page with a sign-up form,
a person might:

- perceive all at once that there are two columns: a form on the left,
  and more information about the service on the right (without actually
  reading either), and accordingly decide whether they wanted to read
  more, or proceed straight to signing up

- from the placement, size, and color of text on the form, perceive
  that there are a number of fields with labels, and little snipets
  of help text beneath each field to help them if they get confused

- perceive legalese or other necessary-but-not-necessarily-interesting
  details down at the bottom of the form or the page, out of the way.

But, the elements of a web page are presented one-by-one in order to
people using screen readers.

If the form is first in the DOM, before the extra info, it's unlikely
they'll ever find it (imagine, listening until the end of a long
telephone menu, even after you've heard "press 2 to sign up", when
your goal is to sign up).

If the help text is in the DOM after the input field, they will only
hear the help text after they've filled out the field.

It's important to place elements in the DOM in the order they should be
read to people, or, failing that, use more sophisticated techniques to
ensure that all users are exposed to your content when they need to be.

How to Address
--------------

### DOM order for meaning; CSS for visual effect

Most of the time, you can arrange the DOM so that information is
presented in the most logical order.

Then, you can use CSS to move elements around to suit your design (e.g.,
placing help text beneath a form element, if you decide that's a good
UX for sighted people; placing legalese at the bottom of a page; etc.).

If you think you then put a lot of junk in front of the most important
part of the page (e.g., most people just want to get to the sign up
form and don't want to read the extra info, so won't want to tab
through it), you can use [skip links](../../code/skip-links/) to improve
the keyboard-user's UX further.

### When that's not practical

Changing the DOM order is not always practical, for a number of reasons.
Maybe a small change trashes your layout for some reason, and you don't
have time to fix it, or maybe it's legitimately unclear if any particular
order solves all your problems.

In that case, you sometimes have to get creative.

When you are dealing with large sections, [proper headings](../headings/)
go a long way, as does good navigation. In certain situation, a
[skip link](../../code/skip-links/) or [pair of skip links](../../footnotes/)
might do the trick.

#### Help text, tool tips, and similar

But in the case of form help text and other similar components, where
you want to supply extra detail in an inobtrusive way, you may have
recourse to the `aria-describedby` attribute. Aria-describedby is
[Boostrap's recommended](https://v4-alpha.getbootstrap.com/components/forms/#help-text)
technique for associating help text with form fields. You simply add
the aria attribute to the input field being described, and set it equal
to the id of the element doing the describing. Then, the help text is
read to people, when their assistive technology focuses on the form
field, or when the person uses special keyboard shortcuts to request
help text, if there is any.

Check out the Bootstrap docs for a few examples!
