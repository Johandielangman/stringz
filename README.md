<p align="center">
  <a href="https://johandielangman.github.io/stringz/">
    <img src="https://raw.githubusercontent.com/johandielangman/stringz/main/docs/static/images/banner_light.svg" alt="stringz">
  </a>
</p>
<p align="center">
  <em>Utilities library for working with strings.</em>
</p>
<p align="center">
  <a href="https://pypi.org/project/stringz"><img src="https://img.shields.io/pypi/v/stringz.svg" alt="PyPI - Version"></a>
  <a href="https://pypi.org/project/stringz"><img src="https://img.shields.io/pypi/pyversions/stringz" alt="PyPI - Python Version"></a>
  <a href="https://pypi.org/project/stringz"><img src="https://img.shields.io/pypi/l/stringz" alt="PyPI - License"></a>
  <a href="https://pypi.org/project/stringz"><img src="https://img.shields.io/pypi/dw/stringz" alt="PyPI - Downloads"></a>
  <a href="https://github.com/johandielangman/stringz/actions/workflows/ci.yml"><img src="https://github.com/johandielangman/stringz/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
  <a href="https://codecov.io/gh/johandielangman/stringz"><img src="https://codecov.io/gh/johandielangman/stringz/graph/badge.svg" alt="codecov"></a>
  <a href="https://johandielangman.github.io/stringz/"><img src="https://img.shields.io/badge/docs-latest-blue" alt="Docs"></a>
</p>

---

Simply install this amazing utilities package:

```console
uv add stringz
```

And immediately get the benefits

```python
from stringz import trunc_str

result = trunc_str("Hello world!", max_chars=10)
print(result)  # Output: 'Hello w...'
```

## Roadmap

only the future will know!

- [x] Pretty truncation and truncation string type
- [ ] `mask` for sensitive information masking
- [ ] converters (`to_snake`, `to_camel`, etc)
- [ ] `join_human` that joins using Oxford comma
- [ ] `ordinal(22)` should give `22nd`
- [ ] `pluralize("box", n)` gives "boxes"... maybe
- [ ] `slugify`
- [ ] `is_blank`

## License

`stringz` is distributed under the terms of the [MIT](https://spdx.org/licenses/MIT.html) license.
