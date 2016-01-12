trillemarka.github.io
=====================

New Trillemarka webpages made with Jekyll and hosted by Github Pages.

Server
------
To run local server: `bundle install` and then `jekyll serve`
(serve watch for changes automcatically).

Layout/Structure
----------------

The overall structure of the site is something like this:

    /(root): index.html - landing-page.
     |- history/index.html - list of posts under the "history" category
     |- hiking/index.html - 
     ...
     ...

Translations/i18n
-----------------

All info is available in English and Norwegian.
This means there must be two versions of top-menu and content.

### Menu

The two versions of the top-menu is achieved by using the following template structure:

    layout/default.html - Norwegian main-layout.
     |- includes/header.html - Norwegian top-menu with Norwegian links.
     |- includes/footer.html - Norwegian footer.
     ^
     |- layout/page.html - Norwegian page-layout, uses 'default' layout.
     |- layout/post.html - Norwegian post-layout, uses 'default' layout.

    layout/default_en.html - English main-layout.
     |- includes/header_en.html - English top-menu with English links.
     |- includes/footer_en.html - English footer.
     ^
     |- layout/page_en.html - English page-layout, uses 'default_en' layout.
     |- layout/post_en.html - English post-layout, uses 'default_en' layout.


### Content

There are two alternative approaches for the content
- I have yet to decide on one:

**a.** Have English and Norwegian versions of each category.
They can be called either "history" and "history\_en"
or "historie" and "history".
The English and Norwegian content will then be separate posts
using either of the versions of the category.
One advantage with this approach
is that we can get fully Norwegian paths (category names).
Even better -
all English posts can be put under _subcategories_
of an "en" top-level category.

**b.** Have both English and Norwegian text in the same post,
contained in two _div_s
- one with class "norwegian-content"
and one with class "english-content".
The wrapping _div_ in _post.html_ can then have a class "norwegian-language"
and in _post\_en.html_ "english-language".
Styling will make sure the correct _div_s are shown and hidden.
The advantage with this approach is that
the Norwegian and English versions of the text
is right next to each other,
in the same file.
The _post\_en.html_ layout can also use a title\_en
front-matter attribute for the English version of the title.

I tend toward alternative **a**,
because of the possibility of
having all english content
under the path trillemarka.no/en/xx.

