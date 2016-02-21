# Translator [ ![Codeship Status for Sage/translator](https://codeship.com/projects/5639e6d0-49d0-0133-3370-6efb14cdab3b/status?branch=master)](https://codeship.com/projects/105735) [![Code Climate](https://codeclimate.com/github/Sage/translator/badges/gpa.svg)](https://codeclimate.com/github/Sage/translator) [![Coverage Status](https://coveralls.io/repos/github/knugie/translator/badge.svg?branch=master)](https://coveralls.io/github/knugie/translator?branch=master)

Translator is based on [IYE](https://github.com/firmafon/iye).
Translator makes it easy to translate your Rails I18N files and keep them up to date.
YAML files instead of keeping a separate database in sync. This has several benefits:

* Branching and diffing is trivial
* It does not alter the workflow for developers etc., whom can continue editing the
  YAML files directly
* If your YAML files are organized in subfolders, this structure is kept intact

![Translator](https://cloud.githubusercontent.com/assets/1446195/10295880/1f829dd6-6bc4-11e5-9a08-bb79d9864bdb.png)

## Prerequisites

You need to understand a few things about Translator for it to make sense, mainly:

* Translator does not create new keys - keys must exist for at least one locale in the YAML files
* Translator does not create new locales - at least one key must exist for each locale in the YAML files

## Workflow

1. Install Translator:

        $ git clone git@github.com:Sage/translator.git
        $ cd translator
        $ gem build translator.gemspec
        $ gem install translator-1.3.1.gem

2. The `translator` executable is now available, use it wherever you want.

        $ translator path/to/i18n/locales [port]

    At this point Translator loads all translation keys for all locales, and creates any
    keys that might be missing for existing locales, the default port is 5050

3. Point browser at [http://localhost:5050](http://localhost:5050)
4. Make changes and press 'Save' - each time you do this, all the keys will be
   written to their original YAML files.
5. Review your changes before committing files, e.g. by using `git diff`.
