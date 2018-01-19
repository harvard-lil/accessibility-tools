Get Errors Fixed Faster
=======================

The coding of accessible web forms is a big topic.
- https://webaim.org/techniques/forms/
- https://webaim.org/techniques/formvalidation/

Here, we're going to assume your form is more-or-less accessible
already and you just need to spruce up your error messages.

Accessible form validation errors can be a little tricky:

- You need to make it easy for people to visually spot the fields
  with errors, even if they are color-blind and even if they
  have visual difficulties.

- You need to make it easy to understand what the problems are and
  how to fix them.

- You need to make it clear whether people need to fix multiple
  problems or just one, so that they don't repeatedly submit the
  form and keep failing validation, an infuriating experience.

- You need to make sure that people using screen readers are informed
  that the form has failed validation and are told what the errors are.

  (Often times, forms fail in silence, or, after failure, the user
  is just dumped at the top of the page, with no indication of what
  happened; when they realize they are still on the page with the
  form, they then need to navigate back to the form and explore to
  discover what the problems are... and perhaps repeat, if the form
  contains multiple errors and they didn't realize it.)

- You need to make sure that it's easy for people to move between
  fields with errors and any error descriptions. Assistive technology
  may provide some extra tools to help certain people do this, but
  you can improve the experience for people navigating with standard
  keyboards and for people with dyslexia or cognitive disabilities
  with a little extra effort.


(One Way) How To
----------------

See [example.html](./example.html) for a complete sample implementation.
Open the source in your browser to see how it works!

1. [Make sure links to hashes/fragments work in your project.](../fix-links/)

2. [Make sure your project has css for hiding text, and for hiding text
until people focus on it.](../hidden-text/)

3. Add a list of validation errors to the top of the page with:
   - a [heading](../../content/headings/), which will to assist people
     using screen readers.
   - an error count
   - a list of validation errors, where each list item links directly to
     the form input in question

4. Add javascript to set the keyboard focus to an appropriate spot in
   the error list, if present, on page load, so that people using screen
   readers are informed that validation errors are present, and so that
   people navigating with a keyboard can conveniently access fields with
   errors.

5. Add redundant, inline error messages to the labels of all fields
   with errors, and make sure the inputs have `aria-invalid="true"` .

6. Make sure it is easy to visually identify fields with errors, and
   that visual cues are not limited to color.
