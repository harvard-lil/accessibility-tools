Your HTML needs to be valid, always and everywhere (even after JS)
==================================================================

At a bare minimum, browsers and assistive technology expect to interact
with valid HTML. If your HTML is invalid, all bets are off.

For instance, some people like to make buttons/pretend links using
anchor tags, but without "href" attributes. E.g.
`<a onclick="alert('clicked!')">I'm an inaccessible link or button!</a>`

Links/buttons like these might work if you click on them with a mouse,
but unlike validly-coded links/buttons, they are totally inaccessible
to people using keyboards: they cannot receive focus, will not be
announced as actionable, etc...and conveniently, as invalid HTML, they
will be flagged for correction by a validator.

There's always a way to accomplish your needs within the spec: ignore
what Google does (=anything they want). In using valid HTML, a whole
class of bugs will be eliminated, and your job will be easier.


What to Do
----------

### Step 1

Run every page of your site through an HTML5 validator, fixing all the
mistakes. The gold standard is
[validator.nu](https://about.validator.nu/). There are lots of ways
to interact with the validator, including a
[public web interface](https://about.validator.nu/) that you can
point at public urls or upload files to.

Here's one easy way to use the validator on a Mac. First, install the
validator:

```
brew tap caskroom/versions
brew cask install java8
brew install vnu
```

Then, spin up your local dev instance of your project. Then, point the
validator at any page you'd like to validate!

```
vnu --format text http://localhost/the-page/
```

For more usage options, see [the docs](https://validator.github.io/validator/).


### Step 2

But wait, there's more!

The validator works like curl. It's only going to be able to see your
source markup: if you change the DOM at all with javascript, say,
inserting content via AJAX, or via a fancy library like React, it's
not going to know anything about it.

To validate the markup of pages like that, you are going to have to
get a complete copy of the DOM as rendered and pass that to the validator.

Some options:
- You can load the desired page in your browser, and then pop into your
  browser's dev tools. In the javascript console, run
  `copy(document.documentElement.outerHTML)`. This will put the whole
  rendered DOM in your clipboard. You can then paste it into a
  file (e.g. `the-page.html`), and pass that file to the validator.
- ... There's probably a faster way. If I think of one, I'll post it
  here :-)
