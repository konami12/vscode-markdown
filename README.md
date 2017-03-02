# Markdown Support for Visual Studio Code

All you need for Markdown.

## Features

- Keyboard shortcuts (toggle bold, italic, heading)
- Table of contents
  - **No additional annoying tags like `<!-- TOC -->`**
- Automatically show preview when openning a Markdown file (Disabled by default)
- ~~Print your Markdown to PDF~~ (coming soon)
- Continue list item (when pressing <kbd>Enter</kbd> at the end of a list item) (also work for quote block)
  - Blank list item won't be continued
  - (Planed: Pressing <kbd>Tab</kbd> on the blank list item will indent it) (**Help wanted**)
- Word completion (for words that are long but frequently used)

Note: After version 1.10.0, the language specific default setting for Markdown disables quick suggestions. To enable this, put
```
"[markdown]": {
    "editor.quickSuggestions": true
}
```
into `settings.json`.

### Keyboard Shortcuts

![shortcuts](images/gifs/shortcuts.gif)

### Table of Contents

![toc](images/gifs/toc.gif)

<!-- ### Print to PDF

![print to pdf](images/gifs/pdf.gif) -->

## Shortcuts

| Key | Command |
| --- | --- |
| <kbd>ctrl</kbd> + <kbd>b</kbd> | Toggle bold |
| <kbd>ctrl</kbd> + <kbd>i</kbd> | Toggle italic |
| <kbd>ctrl</kbd> + <kbd>shift</kbd> + <kbd>]</kbd> | Toggle heading (uplevel) |
| <kbd>ctrl</kbd> + <kbd>shift</kbd> + <kbd>[</kbd> | Toggle heading (downlevel) |

## Available Commands

- Markdown: Toggle Bold
- Markdown: Toggle Italic
- Markdown: Toggle Heading Uplevel
- Markdown: Toggle Heading Downlevel
- Markdown: Create Table of Contents
- Markdown: Update Table of Contents
- Markdown: Print to PDF

## Supported Settings

| Name | Default | Description |
| --- | --- | --- |
| `markdown.extension.toc.depth` | `6` | Control the heading level to show in the table of contents. |
| `markdown.extension.toc.orderedList` | `false` | Use ordered list in the table of contents. |
| `markdown.extension.toc.plaintext` | `false` | Just plain text. |
| `markdown.extension.toc.updateOnSave` | `false` | Automatically update the table of contents on save. |
| `markdown.extension.preview.autoShowPreviewToSide` | `false` | Automatically show preview when openning a Markdown file. |
| `markdown.extension.completion.enabled` | `true` | Show word suggestions or not. |

## Changelog

### Latest 0.4.0 (2017.02.23)

- NEW: Word completion (for words that are long but frequently used)
- NEW: Continue quote block `>`

### 0.3.0 (2017.02.08)

- ~~NEW: Print your Markdown to PDF~~ (Need more tests for the installation of required library)
- NEW: At the end of a list item, pressing <kbd>Enter</kbd> will automatically insert the new list item bullet
  - Blank list item won't be continued
  - (Planed: Pressing <kbd>Tab</kbd> on the blank list item will indent it) (Help wanted)
- FIX: LF and CRLF in TOC
- OTHER: Override `blockComment` (`<!--`, `-->` to <code>&lt;!--&nbsp;</code>, <code>&nbsp;--&gt;</code>)

See [CHANGELOG](CHANGELOG.md) for more information.

## Roadmap

These depend on the feedback and user requests.

## Contributing

Bugs, feature requests and more, in [GitHub Issues](https://github.com/neilsustc/vscode-markdown/issues).

## Known Issues

- To avoid distractive HTML comments, this extension will 'guess' where the TOC is. Currently, a TOC will be recognized if
  - It's a list block in Markdown syntax
  - Its first list item title matches the first heading in the file
- CJK in TOC anchors (A more complex slugify function is needed)
- (**Help wanted**) Because of the using of `html-pdf` package,
  - Anchors within PDF won't work
  - No bookmarks generated

## Acknowledgement

Inspired by and part of codes from,

- [mdickin/vscode-markdown-shortcuts](https://github.com/mdickin/vscode-markdown-shortcuts)
- [AlanWalk/Markdown-TOC](https://github.com/AlanWalk/Markdown-TOC)
- [hnw/vscode-auto-open-markdown-preview](https://github.com/hnw/vscode-auto-open-markdown-preview)
- [yzane/vscode-markdown-pdf](https://github.com/yzane/vscode-markdown-pdf)

## Useful Links

- [CommonMark](http://commonmark.org/): A strongly defined, highly compatible specification of Markdown
