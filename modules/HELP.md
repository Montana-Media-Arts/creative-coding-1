# Content in Modules

This folder is where you should put the content for your course. Every module in your course should have a subfolder inside this folder, eg. `learning`.


## Posts

Inside every module folder, you should create a special folder called `_posts`, eg. `learning/_posts`. Inside the folder called `_posts`, you should create a file for every section in the module. The name of the file should start with the date in the format `YYYY-MM-DD-sectionname.md`. The date determines the order of the sections in your module.

We prepend an underscore `_` infront of posts, because this tells the Jekyll engine to "render" this directory.

An example of the file layout for this course:

```
modules/week-01/_posts/2000-01-01-concepts.markdown
modules/week-01/_posts/2000-01-02-projects.markdown
modules/week-01/_posts/2000-01-03-resources.markdown
modules/week-01/_posts/2000-01-04-tools.markdown
modules/week-01/_posts/2000-01-05-reflect.markdown
modules/week-02/_posts/2000-01-01-concepts.markdown
modules/week-02/_posts/2000-01-02-projects.markdown
modules/week-02/_posts/2000-01-03-resources.markdown
modules/start/_posts/2000-01-01-about-this-course.markdown
modules/references/_posts/2000-01-01-introduction.markdown
modules/references/_posts/2000-01-02-github-cheatsheet.markdown
modules/references/_posts/2000-01-02-markdown-cheatsheet.markdown
modules/references/_posts/2000-01-03-glossary.markdown
modules/references/_posts/2000-01-04-course-template.markdown
modules/references/_posts/2000-01-05-resources.markdown
modules/feedback/_posts/2000-01-01-concepts.markdown
modules/feedback/_posts/2000-01-02-projects.markdown
modules/feedback/_posts/2000-01-03-resources.markdown
modules/content/_posts/2000-01-01-concepts.markdown
modules/content/_posts/2000-01-02-projects.markdown
modules/content/_posts/2000-01-03-resources.markdown
```

## Images

At the same level as the `_posts/` directory, you should create an `imgs/` directory (notice the lack of underscore) where you will place any images used for that modules posts.

To include an image, use standard markdown syntax, along with a relative URL that points up and then into the `imgs/` directory.

```markdown
![](../imgs/ "")
```

NOTE: You should fill in a description for the photo in between the square brackets and in between the parenthesis. The first of these is used by screen readers and other accessibility software. The second will pop-up as a screen-tip when a mouse hovers over the image.

```markdown
![Demonstrating how to use images in markdown](../imgs/md-img-example.jpg "markdown image example")
```


## Front Matter

Every post needs "front matter" in order for the Jekyll engine to render it correctly. Front matter is placed between two sets of dashes `---`. The metadata that is placed there comes in "key: value" pairs.

Depending on how the course is organized, you should include the following metadata in your "front matter" section.

- `title: `
    - This is the title of the post or page.
    - This will often be the 'topic' of the page.
- `module: `
    - If following the previous model established during the creation of mart341, then the value for this key should be the week number of the module.
    - This is used to present active dates for each module.

An example of front matter at the top of a post might look like;

```markdown
---
title: Course Intro
module: 1
---

# Introduction to Interactive Media

This is your first paragraph...
```


## Videos

Videos should be hosted via an external service such as youtube or vimeo. To include a video, wrap it in the following code.

```markdown
<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/replace-me-with-video-ID" frameborder="0" allowfullscreen></iframe></div>
```

You would replace the source link (`src="link"`) with the correct URL for the video you want.

This code allows the videos to be rendered correctly for RWD.
