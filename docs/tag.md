# Tag

Use the `code_highlight` block tag when the source belongs in the Twig template:

```twig
{% code_highlight 'php' %}
<?php

echo 'Hello, Alto!';
{% endcode_highlight %}
```

Pass options after `with`:

```twig
{% code_highlight 'php' with {line_numbers: true, highlight_lines: [3]} %}
<?php

echo 'Hello, Alto!';
{% endcode_highlight %}
```

The language can be any Twig expression:

```twig
{% code_highlight language %}
const answer = 42;
{% endcode_highlight %}
```

The block captures rendered Twig content before highlighting it. Twig expressions
inside the block are therefore evaluated. Wrap literal Twig source in `verbatim`,
or provide it as data through the [filter](filter.md), when it must stay unchanged.

Leading and trailing whitespace is trimmed. A missing or empty language raises an
exception. See [Options](options.md) for defaults and the complete option list.
