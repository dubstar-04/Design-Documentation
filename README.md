# Design Documentation

[![Documentation Status](https://readthedocs.org/projects/design-app/badge/?version=latest)](https://design-app.readthedocs.io/en/latest/)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)

Official documentation for [Design](https://github.com/dubstar-04/Design) — a free and open source 2D computer aided design (CAD) application for Linux and the web.

📖 **Read the docs:** [design-app.readthedocs.io](https://design-app.readthedocs.io/en/latest/)

---

## Building Locally

Requirements: Python 3.12+

```bash
pip install -r requirements.txt
sphinx-build -b html . _build/html
```

Then open `_build/html/index.html` in a browser.

## Contributing

Contributions are welcome. To fix a typo or improve an explanation, edit the relevant `.rst` file and open a pull request.

Documentation source is in reStructuredText format. Each page lives under `pages/`:

```
index.rst               ← home page
pages/
  commands.rst          ← commands overview and shortcut tables
  commands/             ← one page per command
  dxf.rst               ← DXF format reference
```

## Related Repositories

| Repository | Description |
|---|---|
| [Design](https://github.com/dubstar-04/Design) | Desktop application (GNOME / Linux) |
| [Design-Web](https://github.com/dubstar-04/Design-Web) | Web application |
| [Design-Core](https://github.com/dubstar-04/Design-Core) | Shared CAD engine |

## License

[GPL-3.0](LICENSE)
