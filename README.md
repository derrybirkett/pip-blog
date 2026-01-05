# pip-blog (organism)

This repository is the public blog/website organism for PIP.

- `.pip/` is the PIP genome (added as a git submodule)
- The Jekyll site lives at the repo root (`_posts/`, `_includes/`, `_config.yml`, etc.)

## Setup

```bash
git submodule add https://github.com/derrybirkett/pip.git .pip
git submodule update --init --recursive

./.pip/hooks/install-hooks.sh
```

## Run locally

```bash
bundle install
bundle exec jekyll serve
```

## Notes

- This repo intentionally owns site content and presentation.
- The PIP framework/kernel lives in https://github.com/derrybirkett/pip and should be updated via the `.pip` submodule pointer.
