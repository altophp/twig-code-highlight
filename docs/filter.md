# Filter

Use the `code_highlight` filter for source supplied by the application:

```twig
{{ source|code_highlight('javascript') }}
```

The language can be a variable, and options are passed as the second argument:

```twig
{{ source|code_highlight(language, {line_numbers: true, highlight_lines: [1, 3]}) }}
```

Pass plain, unescaped source. The highlighter escapes source markup and the
filter marks only its generated result as safe HTML, so `raw` is unnecessary.

Leading and trailing whitespace in the source and language is trimmed. A missing
or empty language raises an exception, while an unknown identifier raises Code
Highlight's `LanguageNotFoundException`. See the supported
[languages](https://altophp.com/code-highlight/languages).
