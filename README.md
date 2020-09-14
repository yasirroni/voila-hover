# voila-hover

[![Join the Gitter Chat](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/QuantStack/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Voilà default theme that work seamlessly for bqplot tooltip

## Feature

Modification from index.css to index-hover.css:

```css
.jp-OutputPrompt {
  ...
  /* Disable prompt display, edited from default index.css to index-hover.css*/
  display: none;
}

.jp-RenderedText {
  ...
  /* edited from left only padding to all, from index.css to index-hover.css 
  padding-left: var(--jp-code-padding);
  */
  padding: var(--jp-code-padding);
}
```

`voila.tpl` and other `.tpl` used in this template are based on [voila 0.1.23](https://pypi.org/project/voila/0.1.23/) with little modification on `share/jupyter/voila/templates/hover/nbconvert_templates/voila.tpl`:

```html
<link rel="stylesheet" type="text/css" href="{{resources.base_url}}voila/static/index-hover.css">
```

## Installation

```bash
pip install voila-hover
```

## Requirement

```python
setup_args = {
    ...
    'install_requires': [
        'voila>=0.1.6,<0.2'
    ],
    ...
}
```

## Example usage

To use the `voila-hover` template, pass option `--template=hover` to the `voila` command line.


## Development/contributing

The actual template files can be found in `share/jupyter/voila/templates/hover/nbconvert_templates/`.

To view the result of the template locally without having to install this repo as a Python package you can just run:
```
make serve
```
This will start Voila in the `example-notebooks/` directory.
Voila will be default be served on http://localhost:8866.
You can change the port mapping in `docker/docker-compose.yml': If you want to have it run on http://localhost:8877, change it to '8877:8866`.

Auto-reload is enabled by default, so all your changes are immediately (well, wait untill it re-rendered...) visible in Voila.

Development of multiple templates within this repo is currently not fully supported, but that may change in the future...

## License

We use a shared copyright model that enables all contributors to maintain the
copyright on their contributions.

This software is licensed under the BSD-3-Clause license. See the
[LICENSE](LICENSE) file for details.
