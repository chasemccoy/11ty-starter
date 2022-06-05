# @chasemccoy/11ty-starter

A starter repository for building a website with the [Eleventy](https://github.com/11ty/eleventy) static site generator.

## Getting Started

### 1. Clone this Repository

```
git clone https://github.com/chasemccoy/11ty-starter.git my-site-name
```

### 2. Navigate to the directory

```
cd my-site-name
```

### 3. Install dependencies

```
yarn install
```

### 4. Edit _data/metadata.json

### 5. Run Eleventy

```
yarn start
```

Or build automatically when a template changes:

```
yarn watch
```

Or in debug mode:

```
yarn debug
```

### Implementation Notes

* `about/index.md` shows how to add a content page.
* `posts/` has the blog posts but really they can live in any directory. They need only the `post` tag to be added to this collection.
* Add the `nav` tag to add a template to the top level site navigation. For example, this is in use on `index.njk` and `about/index.md`.
* Content can be any template format (blog posts needn’t be markdown, for example). Configure your supported templates in `.eleventy.js` -> `templateFormats`.
	* Because `css` and `png` are listed in `templateFormats` but are not supported template types, any files with these extensions will be copied without modification to the output (while keeping the same directory structure).
* The blog post feed template is in `feed/feed.njk`. This is also a good example of using a global data files in that it uses `_data/metadata.json`.
* This example uses three layouts:
  * `_includes/layouts/base.njk`: the top level HTML structure
  * `_includes/layouts/home.njk`: the home page template (wrapped into `base.njk`)
  * `_includes/layouts/post.njk`: the blog post template (wrapped into `base.njk`)
* `_includes/postlist.njk` is a Nunjucks include and is a reusable component used to display a list of all the posts. `index.njk` has an example of how to use it.
