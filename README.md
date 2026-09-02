# Marzieh Fadaee

A small Jekyll site. Edit YAML and markdown, then push to `main`.

## Update content

| What | Where |
| --- | --- |
| Intro / bio | `index.md` |
| Name, role, social links | `_config.yml` |
| Research highlights | `_data/highlights.yml` |
| Papers | `_data/papers.yml` — add a paper at the top; set `selected: true` for the featured list |
| Talks | `_data/talks.yml` — add an item under `items` |
| Press / in the news | `_data/press.yml` — newest first |
| Mentorship | `_data/mentorship.yml` |
| Books | `_data/books.yml` — set `for_everyone: true` for the ones you press into people's hands |
| Blog post | `_posts/YYYY-MM-DD-title.md` |

Paper entry shape:

```yaml
- id: short-unique-id
  title: Paper title
  authors:
    - First Author
    - Marzieh Fadaee
  year: 2026
  venue: ACL
  selected: false
  links:
    pdf: https://arxiv.org/abs/....
    code: https://github.com/...
```

## Run locally

```bash
bundle install
bundle exec jekyll serve
```

Then open http://127.0.0.1:4000
