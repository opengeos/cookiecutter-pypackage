{% set is_open_source = cookiecutter.open_source_license != 'Not open source' -%}

# {{ cookiecutter.github_repo_name }}

{% if is_open_source %}
[![image](https://img.shields.io/pypi/v/{{ cookiecutter.github_repo_name }}.svg)](https://pypi.python.org/pypi/{{ cookiecutter.github_repo_name }})
[![image](https://img.shields.io/conda/vn/conda-forge/{{ cookiecutter.github_repo_name }}.svg)](https://anaconda.org/conda-forge/{{ cookiecutter.github_repo_name }})
{%- endif %}
{% if cookiecutter.add_pyup_badge == 'y' %}
[![image](https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.github_repo_name }}/shield.svg)](https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.github_repo_name }})
{% endif %}

**{{ cookiecutter.project_short_description }}**
{% if is_open_source %}

-   Free software: {{ cookiecutter.open_source_license }}
-   Documentation: https://{{ cookiecutter.github_username }}.github.io/{{ cookiecutter.github_repo_name }}
    {% endif %}

## Features

-   TODO
