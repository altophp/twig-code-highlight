# Options

The tag and filter accept the same options:

| Option | Type | Default | Effect |
| --- | --- | --- | --- |
| `line_numbers` | `bool` | `false` | Adds a numbered span to every source line. |
| `highlight_lines` | `array<int>` | `[]` | Adds `alto-highlighted` to the selected line numbers. |

Set defaults when creating the extension:

```php
use Alto\Twig\CodeHighlight\CodeHighlightExtension;

$extension = new CodeHighlightExtension(defaultOptions: [
    'line_numbers' => true,
    'highlight_lines' => [2],
]);
```

Options passed by a tag or filter replace matching defaults for that call. The
`highlight_lines` array is replaced rather than combined. Only positive integers
are retained; a non-array value becomes an empty list. Enable `line_numbers` to
make the selected line styling visible.

## Themes

Pass a configured Code Highlight instance to the extension, then use that same
instance when registering the runtime:

```php
use Alto\Code\Highlight\Highlighter;
use Alto\Code\Highlight\Theme\AltoTheme;
use Alto\Twig\CodeHighlight\CodeHighlightExtension;

$highlighter = new Highlighter(new AltoTheme());
$extension = new CodeHighlightExtension($highlighter);
```

The default is `AltoTheme`. See Code Highlight's [themes](https://altophp.com/code-highlight/themes)
for built-in themes, adapters, custom themes, and stylesheet output. Emit the
chosen theme's stylesheet once per page.

Line-number appearance is controlled by application CSS. Target
`.alto-line-number` and `.alto-line-number.alto-highlighted` when customizing it.
