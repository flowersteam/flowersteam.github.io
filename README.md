# Few tips to add a post on the page

## Table of Contents
- [Fast launch](#fast-launch)
- [More details](#more-details)
  - [0. Ask permission for pull and push](#0-ask-permission-for-pull-and-push)
  - [1. Create the post file](#1-create-the-post-file)
  - [2. Front matter reference](#2-front-matter-reference)
  - [3. Images](#3-images)
  - [4. Available tags](#4-available-tags)
  - [5. Markdown Cheatsheet](#5-markdown-cheatsheet)
- [TODO](#todo)


## Fast launch
If you want to run the server locally clone the repo and install jekyll:

https://jekyllrb.com/

Then add the following lines to the Gemfile:

```
gem 'jekyll-sitemap'
gem 'jekyll-paginate'
gem 'jekyll-admin', group: :jekyll_plugins
```

Before running the command 
```
bundle exec jekyll serve
```

you might have to delete the Gemfile.lock.

Be carefull you should not push the modifications to the Gemfile on the repo when you add your post.

When pushing, only add the files you modified '.md', '.css', images etc..

***
## More details
### 0. Ask permission for pull and push

TODO

Julien R: I have no idea. For now, Julien P granted me access to the repository as collaborator. Yet, I see only Cédric and I as collaborators, and 25 unidentified members that I don't trace back to *flowersteam* either. By default, you can send your blog to me and I update the website.

---

### 1. Create the post file

All posts live in `_posts/`. Create a new Markdown file named:

```
_posts/YYYY-MM-DD-your-post-slug.md
```

The date prefix controls the publication date and sort order. The slug becomes part of the URL unless overridden by `permalink`.

---

### 2. Front matter reference

Every post starts with a YAML front matter block between `---` delimiters.

#### Standard post

```yaml
---
layout:     post
title:      'Your Post Title' (to change)
date:       2026-04-14 (to change)
summary:    One or two sentences describing the post (shown in listings). (to change)
categories: jekyll
permalink:  your_post_slug (will be in the URL) (to change)
use_math:   true
thumbnail:  /images/posts/YYYY-MM-DD-your-post-slug/thumbnail.png (to change)
tags:       [machine-autotelic-learning, language-models] (use at least one of human-autotelic-learning, machine-autotelic-learning, assisted-scientific-discovery and educational-technologies) (to change)
authors:
- name: 'First Author' (to change)
  link: https://first-author-website.com (to change)
  next: ', '
- name: 'Second Author' (to change)
  link: https://second-author-website.com (to change)
  next: ' and '
- name: 'Last Author' (to change)
  link: https://last-author-website.com (to change)
  next: ''
---
```

#### External post (links out to another site)

For posts that redirect to an external URL (e.g. a Google Site or project page), omit `summary`, `categories`, `permalink`, `use_math`, and `thumbnail`, and add `external_url` instead:

```yaml
---
layout: post
title: 'Your Post Title' (to change)
date: 2026-04-14 (to change)
external_url: https://your-external-site.com (to change)
tags: [human-autotelic-learning, developmental-learning] (to change)
authors:
- name: 'First Author' (to change)
  link: https://first-author-website.com (to change)
  next: ' and '
- name: 'Last Author' (to change)
  link: https://last-author-website.com (to change)
  next: ''
---
```

#### Field descriptions

| Field | Required | Description |
|---|---|---|
| `layout` | Yes | Always `post`. |
| `title` | Yes | Post title shown in listings and the page header. Use single quotes if it contains colons or special characters. |
| `date` | Yes | Publication date in `YYYY-MM-DD` format. Must match the filename date. |
| `summary` | For local posts | Short description shown in the post listing and meta tags. |
| `categories` | For local posts | Always `jekyll` (required by the paginator). |
| `permalink` | For local posts | Slug for the post URL (e.g. `permalink: glam` → `developmentalsystems.org/glam`). Omit the leading slash. |
| `use_math` | Optional | Set to `true` to enable MathJax rendering. Can be omitted if the post has no equations. |
| `thumbnail` | Optional | Path to a preview image shown in listings (e.g. `/images/posts/2026-02-27-phylolm/full_dendrogram.png`). |
| `tags` | Optional | List of topic tags (see [available tags](#available-tags)). |
| `external_url` | For external posts | Full URL the post card links to instead of an internal page. |
| `authors` | Yes | List of author entries (see below). |

#### Authors

Each entry in `authors` has three keys:

| Key | Description |
|---|---|
| `name` | Author's display name. |
| `link` | URL for the author's personal or academic page. Leave blank (`link: `) if none. |
| `next` | Text inserted **after** this author's name: `', '` between authors, `' and '` before the last, and `''` (empty string) on the last author. |

---

### 3. Images

Store post images in a dedicated subdirectory:

```
images/posts/YYYY-MM-DD-your-post-slug/
```

Reference them in the post with an absolute path:

```markdown
![Alt text](/images/posts/2026-02-27-phylolm/my-figure.png)
*Figure caption goes here.*
```

For more control over layout and captions, use the HTML pattern used in other posts:

```html
<div align="center" style="margin-bottom:40px">
  <img src="/images/posts/YYYY-MM-DD-your-post-slug/my-figure.png" width="75%" alt="Alt text" />
  <div>
    <sub style="display: block; line-height: 1.5em">
      <i>Figure caption here.</i>
    </sub>
  </div>
</div>
```

---

### 4. Available tags (so far but to update/reduce)

Use existing tags when possible to ensure posts appear under the right theme pages.

| Tag | Theme |
|---|---|
| `machine-autotelic-learning` | Machine learning, RL, curiosity-driven agents |
| `human-autotelic-learning` | Human curiosity, cognitive science, education |
| `developmental-AI` | Developmental approaches to AI |
| `developmental-learning` | Learning and development (human or machine) |
| `intrinsic-motivation` | Intrinsic motivation and curiosity |
| `language-models` | Large language models, NLP |
| `reinforcement-learning` | Reinforcement learning methods |
| `curriculum-learning` | Curriculum and self-paced learning |
| `cognitive-science` | Cognitive science and psychology |
| `cultural-evolution` | Cultural transmission and evolution |
| `grounding` | Symbol grounding, embodiment |
| `embodiment` | Embodied AI and robotics |
| `interactive-learning` | Interactive and social learning |
| `social-learning` | Multi-agent and social settings |
| `interpretability` | Model interpretability and analysis |
| `self-determination-theory` | SDT and well-being |
| `ecology` | Ecological AI, niche construction |
| `educational-technologies` | Education, conversational agents |
| `discovery` / `assisted-scientific-discovery` | Automated scientific discovery |
| `deep-RL` | Deep reinforcement learning |
| `reproducibility` | Reproducibility and statistics |
| `emergence` / `self-organization` | Emergent behaviour, cellular automata |
| `multi-agent` | Multi-agent systems |
| `communication` | Language emergence, communication |

---

### 5. Markdown Cheatsheet

See https://www.markdown-cheatsheet.com/

---

## TODO

0. Ask permission for pull and push