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

This repo requires **Ruby 3.x** (CI uses Ruby 3.1). If you see an error like “requires ruby version >= 3.0”, upgrade Ruby.

### macOS (recommended: rbenv)

```bash
brew install rbenv ruby-build
rbenv install 3.1.0
rbenv local 3.1.0
gem install bundler
```

```bash
bundle install
bundle exec jekyll serve
```

Published URL: https://derrybirkett.github.io/pip-blog/

## Notes

- This repo intentionally owns site content and presentation.
- The PIP framework/kernel lives in https://github.com/derrybirkett/pip and should be updated via the `.pip` submodule pointer.

## Automation

- The workflow `.github/workflows/sync-pip-genome.yml` polls the genome and, when `docs/changelog.md` gains a new dated release section, opens an autogen PR that bumps `.pip`, syncs `docs/changelog.md`, and generates a matching blog post.
