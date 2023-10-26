---
layout: page
title: About
permalink: /about/
---

# [MAMBO Documentation](https://alphadaze.github.io/mambo-docs/)

Work-in-progress documentation for [MAMBO](https://github.com/beehive-lab/mambo)

View Github [here](https://github.com/AlphaDaze/mambo-docs/)
___

### Add Pages
Write markdown pages!

#### Add new section
1. Create new folder | e.g. example

2. Create new markdown file with same name inside folder | e.g. example/example.md

3. Fill out top of file with following

  ```
  ---
  layout: default
  title: example        # replace with file name
  nav_order: 3          # set priority of section/page
  has_children: true    # Important for section!
  permalink: /example   # set link to this folder
  ---
  # <YOUR MARKDOWN HERE>
  ```

#### Add new child page
1. Create new markdown file
2. Fill out top of file with following

  ```
  ---
  layout: default
  title: test         # replace with file name
  parent: example     # Important for sub-page!
  nav_order: 2        # set priority of section/page
  ---
  # <YOUR MARKDOWN HERE>
  ```

___

[just-the-docs](https://just-the-docs.com/) supports much more!