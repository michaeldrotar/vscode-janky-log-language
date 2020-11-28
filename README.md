# Janky Log Language

The `Log` language and grammar files are a little, well... janky. Let's make things look awesome with proper colors that help more than confuse!

## Inspiration

The default Log grammar files work pretty decently for the built-in logs, but after writing `janky-output-channels` to also apply them to extension logs, some of their issues started to really shine. Other log solutions I've found make pretty logs but they don't apply to the output channels because they create a new log syntax rather than improve the existing one.

## Features

### Improved Log Syntax

Replaces the built-in `Log` syntax with one that's more specific so that fewer things are mis-colored and logs are easier to scan.

Uses sensible tokens that follow recommended [Naming Conventions](https://macromates.com/manual/en/language_grammars#naming_conventions) for grammar files.

### JSON Support

Some logs include JSON structures in their output. This extension will detect those structures and defer to Javascript Syntax (`source.js`) to handle tokenization and coloring.

### Log Syntax Tokens

This section will cover how log syntaxes are parsed and what tokens are made available for coloring/formatting.

An important facet of this extension is that it's very specific to avoid confusing mis-colors, so examples will try to show what gets colored as well as what does not

### Tags

Most logs commonly have tagged data between sets of square brackets at the start of each line. This section covers the syntax for those tags and the data within them.

- Brackets (`constant.other.log`)

  - `[`one tag`]` `[`two tags`]` other text [not a tag]

- Log Levels: Verbose (`constant.language.verbose.log`)

  - [`verbose`] not verbose or [verbose]
  - [`VERBOSE`] more content

- Log Levels: Debug (`constant.language.debug.log`)
  - [`debug`] not debug or [debug]
  - [`DEBUG`] more content
- Log Levels: Info (`constant.language.info.log`)
  - [`info`] not info or [info]
  - [`INFO`] more content
- Log Levels: Warn (`constant.language.warn.log`)
  - [`warn`] not warn or [warn]
  - [`WARN`] more content
- Log Levels: Error (`constant.language.error.log`)

  - [`error`] not error or [error]
  - [`ERROR`] more content

- Timestamps: Dates (`constant.numeric.timestamp.date.log`)

  - [`2020-11-28`] not 2020-11-28
  - [`2020-11-28` 10:45:15.833] more content

- Timestamps: Time (`constant.numeric.timestamp.time.log`)
  - [`10:45:15.833`] not 10:45:15.833
  - [2020-11-28 `10:45:15.833`] more content
  - [2020-11-28 `10:26:12 AM`] 12 hour clock
  - [30:45:15.8333] invalid hour

### Terminal Output

Some logs, like the Git extension, include terminal output.

- Terminal Prompt (`keyword.operator.prompt.terminal.log`)

  - `>` git info
  - `$` git info

- Terminal Command (`entity.name.function.terminal.log`)
  - \> `git` info
  - $ `git` info

## Requirements

None.

## Extension Settings

None.

## Known Issues

None.
