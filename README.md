# ALTO Twig Code Highlight

Highlight source code directly from Twig templates with a tag or filter powered
by [ALTO Code Highlight](https://github.com/altophp/code-highlight).

&nbsp; ![PHP Version](https://img.shields.io/badge/PHP-8.4%2B-00B7FF?logoColor=00B7FF&labelColor=050608)
&nbsp; ![CI](https://img.shields.io/github/actions/workflow/status/altophp/twig-code-highlight/CI.yml?branch=main&label=Tests&labelColor=050608&color=00B7FF)
&nbsp; [![Packagist](https://img.shields.io/packagist/v/alto/twig-code-highlight?label=Packagist&labelColor=050608&color=00B7FF)](https://packagist.org/packages/alto/twig-code-highlight)
&nbsp; ![License](https://img.shields.io/github/license/altophp/twig-code-highlight?label=License&labelColor=050608&color=00B7FF)
&nbsp; [![GitHub Sponsors](https://img.shields.io/github/sponsors/smnandre?logo=githubsponsors&logoColor=00B7FF&label=%20Sponsor&labelColor=050608&color=00B7FF)](https://github.com/sponsors/smnandre)

Use the block tag for source written in a template or the filter for source
provided by your application:

```twig
{% code_highlight 'php' %}
<?php echo 'Hello, Alto!';
{% endcode_highlight %}

{{ source|code_highlight('javascript') }}
```

## Installation

```bash
composer require alto/twig-code-highlight
```

The package requires PHP 8.4 or later, ALTO Code Highlight 1.x, and Twig 3.28
or later.

## Documentation

- [Installation](docs/installation.md)
- [Getting started](docs/getting-started.md)
- [Tag](docs/tag.md)
- [Filter](docs/filter.md)
- [Options](docs/options.md)

## Contributing

Contributions of all kinds are welcome. Visit the
[project on GitHub](https://github.com/altophp/twig-code-highlight) to
[report a bug](https://github.com/altophp/twig-code-highlight/issues/new),
[suggest a feature](https://github.com/altophp/twig-code-highlight/issues/new), or
[open a pull request](https://github.com/altophp/twig-code-highlight/pulls).

Before submitting code, run:

```bash
# Runs PHP CS Fixer, PHPStan, and PHPUnit
composer qa
```

Changes to public behavior should include tests and documentation.

## Support

ALTO Twig Code Highlight is open source and independently maintained by
[Simon André](https://smnandre.dev). If it is useful to your work, you can
support its continued development through
[GitHub Sponsors](https://github.com/sponsors/smnandre).

Sharing the package or
[starring it on GitHub](https://github.com/altophp/twig-code-highlight) also helps.

## License

ALTO Twig Code Highlight is released by [ALTO PHP](https://altophp.com) under the
[MIT License](LICENSE).
