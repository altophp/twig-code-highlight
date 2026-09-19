# Installation

Install the Twig integration with Composer:

```bash
composer require alto/twig-code-highlight
```

The package requires PHP 8.4 or later, Twig 3.28 or later, and ALTO Code
Highlight 1.x. Composer installs Code Highlight and its `mbstring` and
`tokenizer` extension requirements.

In a standalone script, load `vendor/autoload.php`. Then register both the
extension and its runtime loader as shown in [Getting started](getting-started.md).
