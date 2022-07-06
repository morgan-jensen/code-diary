# Markdown Cheat Sheet

Headers
---
```
# H1
## H2
### H3
#### H4

## H2 (Underlined)
--- 
```

Text Formating
---
```
Underline with *Asterisks* or _Underlines_

Bold with double **Asterisks** or __Underline__

Strike through with ~~Two Tildes~~
```

Lists
---
```
1. Ordered
2. List
3. Example

* Unordered
* List 
* Example

+ Unordered
+ List
+ Two

- Unordered
- List
- Three
```

Links
---
```
[Inline style link](https://www.google.com)
[Inline link with title](https://www.goog.com "Google Homepage")

URLs in angle brackets will automatically turn into links
https://www.example.com vs <https://www.example.com>
```

Images
---
```
Inline:
![alt text](https://exampleurl.com/directory.png "Logo Title Text")

Reference Style:
![alt text][logo]

[logo]: https://exampleurl.com/thing.png "Logo Title Text"
```

Code
---
```
Inline code `has single back-ticks`

Block code is done with three back-ticks \`\`\`
 - This can include a language for syntax highlighting
```

```javascript
var s = "JavaScript syntax";
alert(s);
```

```python
s = "Python syntax"
print s
```

Tables
---
```
|Table	| Example	|
|:---:	| :---:		|
|This	| is		|
|super	| cool		|
```
The must be at least 3 dashes to seperate the headers.

Colons align columns like this:
	`:---` Left
	`:---:` Center
	`---:` Right



