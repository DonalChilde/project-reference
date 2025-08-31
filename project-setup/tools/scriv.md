# Scriv

[Scriv](https://github.com/nedbat/scriv) is a command-line tool for helping developers maintain useful changelogs. It manages a directory of changelog fragments. It aggregates them into entries in a CHANGELOG file.


## Install scriv
```bash
uv add --dev scriv
```

## Add pyproject.toml config

```toml
[tool.scriv]
#version = "literal: pyproject.toml: project.version"
version = "literal: src/PROJECT_NAME/__init__.py: __version__"
format = "md"
md_header_level = "2"
entry_title_template = "file: changelog.d/templates/entry_title_template.md.j2"
new_fragment_template = "file: changelog.d/templates/new_fragment.${config:format}.j2"
```


## Define custom templates

./changelog.d/templates/new_fragment.md.j2
```html
{% if version %}[{{ version }}](https://github.com/REPO_OWNER/PROJECT_NAME/compare/_previous_version_tag_...{{ version }}) — {% endif %} {{ date.strftime('%Y-%m-%d') }}

### Whats Changed in {{ version }}

Talk about the changes in general
```


./changelog.d/templates/new_fragment.md.j2
```jinja2
<!--
A new scriv changelog fragment.

Uncomment the section that is right (remove the HTML comment wrapper).

pull request link [#_num_](https://github.com/REPO_OWNER/PROJECT_NAME/pull/_num_)
issue link [#_num_](https://github.com/REPO_OWNER/PROJECT_NAME/issues/_num_)
-->

{% for cat in config.categories -%}
<!--

### {{ cat }}


- __issue_or_PR_description__[#_num_](https://github.com/REPO_OWNER/PROJECT_NAME/pull/_num_)
  - closes
    - __desc__[#_num_](https://github.com/REPO_OWNER/PROJECT_NAME/issues/_num_)

-->
{% endfor -%}
```