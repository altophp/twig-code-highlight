# Getting started

Create `highlight.php` beside the `vendor` directory:

```php
<?php

require __DIR__.'/vendor/autoload.php';

use Alto\Twig\CodeHighlight\CodeHighlightExtension;
use Alto\Twig\CodeHighlight\Runtime\CodeHighlightRuntime;
use Twig\Environment;
use Twig\Loader\ArrayLoader;
use Twig\RuntimeLoader\FactoryRuntimeLoader;

$twig = new Environment(new ArrayLoader([
    'example' => "{{ source|code_highlight('html') }}",
]), ['autoescape' => 'html']);

$extension = new CodeHighlightExtension();
$twig->addExtension($extension);
$twig->addRuntimeLoader(new FactoryRuntimeLoader([
    CodeHighlightRuntime::class => static fn (): CodeHighlightRuntime => new CodeHighlightRuntime(
        $extension->getHighlighter(),
        $extension->getDefaultOptions(),
    ),
]));

echo $twig->render('example', ['source' => '<strong>Hello</strong>']), "\n";
```

Run it:

```console
$ php highlight.php
<pre class="alto-highlight language-html"><code class="language-html"><span class="alto-keyword">&lt;</span><span class="alto-keyword">strong</span><span class="alto-keyword">&gt;</span><span class="alto-punctuation">Hello</span><span class="alto-keyword">&lt;/</span><span class="alto-keyword">strong</span><span class="alto-keyword">&gt;</span></code></pre>
```

The result is highlighted HTML. The original `<strong>` source is escaped inside
the code block, so it is displayed rather than interpreted as page markup.

Add the theme stylesheet once to the page to see the syntax colors:

```php
echo '<style>', $extension->getHighlighter()->getTheme()->getStylesheet(), '</style>';
```

Continue with the [tag](tag.md) for template-owned snippets, the
[filter](filter.md) for dynamic source, and [options](options.md) for line numbers
and themes.
