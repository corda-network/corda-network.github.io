# CONTENT RELATED FILES:

---

`folders containing markdown files and some asset files`

```
about
governance
home
minutes
participation
policy
trust-root
```

`folder contains some log, pdf and other assets files`

```
assets
```

`google site verification`

```
google2fa716ab789ec378.html
```

# SITE RELATED FILES and FOLDERS - files/folder coming from the react app build folder (ie the source repository):

---

`folder containing builded and minified css and js files from the react app source`

```
static
```

`file to tell git which files and folders to ignore`

```
.gitignore
```

`rest of the files, note the file precache-manifest... has new name on every next build`

```
robots.txt
service-worker.js
asset-manifest.json
favicon.ico
index.html
manifest.json
precache-manifest.2b30b4b161e617cf12126bf018b09f0a.js
```

# Content Creation Instructions

This document contains instructions on content creation. If you whant the content to be desplayed correctly on the website, you should follow this instructions:

## Headings

1. When you are creating headings, use the "#" symbol/s infront of the copy.
2. **Don't** use the alternate syntax whith "===" and "---", otherwise the headings won't be displayed correctly.
3. Leave an empty row after each heading.
4. Use `# Heading level 1` only for page titles.
5. If you place a paragraph below Heading 1, it will become part of the grey page header.

- `# Heading level 1`
- `## Heading level 2`
- `### Heading level 3`
- `#### Heading level 4`
- `##### Heading level 5`

## Paragraphs

To create paragraphs, use a blank line to separate one or more lines of text. You should not indent paragraphs with spaces or tabs.

## **Internal links (IMPORTANT!)**

To make sure internal links will work, use the following structure `/folder/file-name`.

1. **Do not put ".md" or ".html" at the end of the link.**
2. **Do not put the domain name infront of the link.**
3. Example:

`[Governance Guidelines](/governance/governance-guidelines)`

## Emphasis

1. Bold: To bold text, add two asterisks or underscores before and after a word or phrase.

- `This is **bold text**.` -> This is **bold text**.
- `This is __bold text__.` -> This is **bold text**.

2. Italic: To italicize text, add one asterisk or underscore before and after a word or phrase.

- `This is *italic text*.` -> This is _italic text_.
- `This is _italic text_.` -> This is _italic text_.

## Blockquotes

1. To create a blockquote, add a ">"" in front of a paragraph.

> Dorothy followed her through many of the beautiful rooms in her castle.

2. Blockquotes can contain multiple paragraphs. Add a > on the blank lines between the paragraphs.

Example:

> Corda Network Foundation Stichting
>
> Johan Huizingalaan 763A
>
> 1066 VH
>
> Amsterdam
>
> Netherlands

## Lists

You can organize items into ordered and unordered lists using the standard markdawn syntaxis.

## Code

1. To denote a word or phrase as code, enclose it in backticks (`).

`Code example`

2. To create code blocks, use three backticks above and three bacticks below the code block.

```
Example
Example
Example
```

## Tables

To add a table, use three or more hyphens (---) to create each column’s header, and use pipes (|) to separate each column. You can optionally add pipes on either end of the table.

_We recommend using this table generator - https://www.tablesgenerator.com/markdown_tables_

### Table alignment

You can align text in the columns to the left, right, or center by adding a colon (:) to the left, right, or on both side of the hyphens within the header row.

```
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |
```

## Horisontal rules

To add a horisontal rule use three hyphens (---) whit an empty line above and below the hyphens.
