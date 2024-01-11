# Welcome to {{ cookiecutter.project_slug }}

{% set is_open_source = cookiecutter.open_source_license != 'Not open source' -%}
{% if is_open_source %}
[![image](https://img.shields.io/pypi/v/{{ cookiecutter.project_slug }}.svg)](https://pypi.python.org/pypi/{{ cookiecutter.project_slug }})
{%- endif %}
{% if cookiecutter.add_pyup_badge == 'y' %}
[![image](https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/shield.svg)](https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }})
{% endif %}

**{{ cookiecutter.project_short_description }}**
{% if is_open_source %}

-   Free software: {{ cookiecutter.open_source_license }}
-   Documentation: <https://{{ cookiecutter.github_username }}.github.io/{{ cookiecutter.project_slug }}>
    {% endif %}

## Features

-   TODO
