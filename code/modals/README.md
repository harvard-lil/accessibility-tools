Modals Are Hard
===============

There's no getting around it: modals are tricky. They can seem very simple, but when you start digging into the details, the UX is surprisingly nuanced. And, unfortunately, there just aren't a lot of ready-made accessible solutions out there: when you use modals, you generally have the privilege of coding your very own accessible custom widget!

The Spec
--------

### Opening and closing

- The modal needs to be opened via a [real button](https://github.com/rebeccacremona/a11y-games/blob/master/app/buttons-and-links/info.md).

- You need to be able to close the modal by pressing the escape key.

- You need to be able to close the modal by pressing a (real) close button prominently located inside the modal. Depending, it can be good style to include TWO close buttons, one at the top (the ubiquitous "x" button) and a second at the bottom (labeled "cancel" or "dismiss" or "close"), especially if the modal is complex or includes a form.

- You need to be able to close the modal by clicking "in the background", if the modal is anything but 100% full screen (and the modal should never be 100% full screen).

### Keyboard focus

- When a person closes the modal, you need to set keyboard focus to the button that opens the modal (or to whatever element had keyboard focus when the modal appeared).

- When a person opens the modal, you need to set keyboard focus to the first element in the modal (or something else that makes sense).

- When the modal is open, it must be impossible to navigate to any of the content "behind" the modal, either via the tab key or using assistive technology.

- When the modal is closed, it must be impossible to navigate to any of the content inside the modal, either via the tab key or using assistive technology.

### Appropriate descriptions

- The markup needs to include certain `role` attributes and other `aria-*` attributes to make sure assistive technology understands what's going on and can appropriately convey context to the user.


Let's Do It!
------------

[Scott O'Hara's](https://www.smashingmagazine.com/2014/09/making-modal-windows-better-for-everyone/)[archived at https://perma.cc/P49Q-MFGE] approach to modals is the best I've seen. If you are rolling your own, I recommend you make heavy use of his code.

Since most of our apps are built on top of Bootstrap, we're going to start with a Bootstrap 3 modal and fix it up. Check out [example.html](../example.html) for a working example with detailed instructions.

1. We'll make a container to hold the contents of the modal window. We'll make it the very first element of the body (even before our [skip link](../skip-links/)). This ensures that, when the modal window is open (and everything else on the screen is hidden), that users can press shirt + tab to interact with their browser's controls, like the address bar, in the usual way.

2. We'll wrap up all the rest of the contents of the body tag (excluding scripts, if you like) in a div with a unique id. This will make it easy to ensure that when the modal is open, people can only interact with the modal, and not with the content underneath.

3. We'll add a few extra styles.

4. We'll add javascript to a) make sure keyboard focus stays inside an open
modal, and b) to make sure assistive technology doesn't navigate outside either (yes, assistive technology can sometimes do things keyboards alone can't!).

  Note on b):

  I'm not sure how well [`aria-modal`](https://www.w3.org/TR/wai-aria-1.1/#aria-modal) is supported at the moment: it's a relative newcomer to the scene, and [has a reputation for causing problems](https://labs.ssbbartgroup.com/index.php/ARIA_region_role_with_aria-modal). In a spirit of caution, I think we shouldn't rely on it yet, instead using the older practice of [making all non-modal content `aria-hidden`](https://www.w3.org/TR/wai-aria-practices/examples/dialog-modal/dialog.html)

5. We'll add javascript and tweak out markup to make focus more reliable
for screen reader users.
