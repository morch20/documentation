# Markdown Cheat Sheet

Thanks for visiting [The Markdown Guide](https://www.markdownguide.org)!

This Markdown cheat sheet provides a quick overview of all the Markdown syntax elements. It can’t cover every edge case, so if you need more information about any of these elements, refer to the reference guides for [basic syntax](https://www.markdownguide.org/basic-syntax) and [extended syntax](https://www.markdownguide.org/extended-syntax).

## Basic Syntax

These are the elements outlined in John Gruber’s original design document. All Markdown applications support these elements.

### Heading

# H1

```markdown
# H2
```

## H2

```markdown
## H2
```

### H3

```markdown
### H3
```

### Bold

**bold text**

```markdown
**bold text**
```

### Italic

*italicized text*

```markdown
*italicized text*
```

### Blockquote

> blockquote

```markdown
> blockquote
```

### Ordered List

1. First item
2. Second item
3. Third item

```markdown
1. First item
2. Second item
3. Third item
```

### Unordered List

- First item
- Second item
- Third item

```markdown
- First item
- Second item
- Third item
```

### Code

`code`

```markdown
`code`
```

### Horizontal Rule

---

```markdown
---
```

### Link

[Markdown Guide](https://www.markdownguide.org)

```markdown
[Markdown Guide](https://www.markdownguide.org)
```

### Image

![alt text](https://www.markdownguide.org/assets/images/tux.png)

```markdown
![alt text](https://www.markdownguide.org/assets/images/tux.png)
```

## Extended Syntax

These elements extend the basic syntax by adding additional features. Not all Markdown applications support these elements.

### Table

| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |

```markdown
| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |
```

### Fenced Code Block

```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

### Syntax Highlighting

```json
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

### Footnote

Here's a sentence with a footnote. [^1]

```markdown
Here's a sentence with a footnote. [^1]
```

[^1]: This is the footnote.

```markdown
[^1]: This is the footnote.
```

### Heading ID

### My Great Heading {#custom-id}

```markdown
### My Great Heading {#custom-id}
```

### Definition List

term
: definition

```markdown
term
: definition
```

### Strikethrough

~~The world is flat.~~


```markdown
~~The world is flat.~~
```

### Task List

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media

```markdown
 - [x] Write the press release
 - [ ] Update the website
 - [ ] Contact the media
```

### Emoji

That is so funny! :joy:

```markdown
That is so funny! :joy:
```

(See also [Copying and Pasting Emoji](https://www.markdownguide.org/extended-syntax/#copying-and-pasting-emoji))

### Highlight

I need to highlight these ==very important words==.

```markdown
I need to highlight these ==very important words==.
```

### Subscript

H~2~O

```markdown
H~2~O
```

### Superscript

X^2^

```markdown
X^2^
```
