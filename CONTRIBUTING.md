# Contributing as a project owner

This guide assumes you are attempting to contribute to the IGSR website as an owner. If not you should fork the project, continue with the guide and then submit a pull request to integrate the new changes.

## Creating a new Page

<img alt="Editing a page" src="https://raw.githubusercontent.com/igsr/igsr.github.io/HEAD/_readme_imgs/addpage.png"/>

Once on the GitHub website click on the + icon and make sure you are working on the `master` branch. Any changes committed to the master branch will not be reflected on the live website.

### Adding the Front Matter

Each GitHub page in Jekyll requires a section of YAML injected at the top of each document. This is called the [http://jekyllrb.com/docs/frontmatter/](Front Matter).

```markdown
---
layout: page
title: This is my title
---
```

Front matter tells Jekyll and our templates how to render the page, what to call it and how to order it. Front matter is customisable by the site so not all Front Matter is the same in every Jekyll site. The full list of available tags are below:

| Tag       | Type             | Required | Description                                                                                      | Example              |
|-----------|------------------|----------|--------------------------------------------------------------------------------------------------|----------------------|
| layout    | Enum(page, post) | Yes      | The layout to apply to this Markdown page. Normally set to page                                  | layout: page         |
| title     | String           | Yes      | The title to use. This is also used when generating top links                                    | title: My Page Title |
| permalink | URL              | No       | A permanent link to provide the page under. Useful if the normal page.md == /page/ does not work | permalink: /about/   |
| order     | Integer          | No       | Set the order of how links are displayed at the top                                              | order: 10            |

## Editing a Page

You can click on the pencil icon when on a Markdown page. This is shown below

<img alt="Editing a page" src="https://raw.githubusercontent.com/igsr/igsr.github.io/HEAD/_readme_imgs/editpage.png"/>

## Writing the Page

By default pages are rendered using Markdown. A lightweight markup language. GitHub provides some good guides on [how to write pages in Markdown](https://help.github.com/articles/markdown-basics/). You can also write content in HTML should you wish. All Jekyll pages are templates. Content can be injected into them using [pre-set lists of data](http://jekyllrb.com/docs/datafiles) and written using [filters](http://jekyllrb.com/docs/templates/). They are exceptionally configurable. [Jekyll docs](http://jekyllrb.com/docs/) are a good place to find more information.

#### Inserting Internal HTML links

When using Markup you can inject internal links by adding the site's baseurl to ensure good links are always formed. You do this by using a filter like so

```markdown
[About this site]({{ "/about" | prepend: site.baseurl }})
```

#### Inserting External HTML links

When using Markup you can inject new attributes into the target links. When creating links that move away from the main site it is recommended they start up a new browser window or tab. You do this by adding a `target=_blank` attribute by adding curly brackets and key/value attributes like so:

```markdown
[Ensembl](http://ensembl.org){:target=_blank}
```

## Committing into GitHub

Write your content and scroll down to the bottom of the page. Enter in a short summary of your changes and a longer summary should you need to describe more about what you have done.

<img alt="Committing the change" src="https://raw.githubusercontent.com/igsr/igsr.github.io/HEAD/_readme_imgs/commit.png"/>

You have two options when committing. You can commit directly to the repositiory. Changes will be live in a few seconds. Otherwise you can start a [Pull Request](https://help.github.com/articles/using-pull-requests). Pull requests allow you to submit a change but to have others view, comment, suggest fixes if required and then merge your code into the master branch. Pull requests are a good idea if you are not confident in your changes or they are substantial in what they change.
