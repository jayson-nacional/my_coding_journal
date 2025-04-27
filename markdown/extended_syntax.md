
# Tables  

Use hypens(\-\-\-) to create column's header. Use pipes(|) to separate each column.  

| Syntax    | Description |
|-----------|-------------|
| Header    | Title       |
| Paragraph | Text        |

Alignment can be done by using combination of colon and dashes.  

- :--- align left
- ---: align right
- :---: center alignment

Links and code(in backticks `) can be added. Headings, blockquotes, lists, horizontal rules, images and most HTML tags cannot be used.  

To escape pipes(|) in tables, use it's HTML character code ($#124;)


# Fenced Code Blocks  

Enclose code blocks in either three(3) backticks(`) or three(3) tilde(~). See sample below:
```
{
    "firstName": "John",
    "lastName": "Smith",
    "age": 25
}
```  

Language can be added on the opening backticks or tilde for readers syntax highlighting to work.  

\`\`\`json
    {
        ...object properties  here...
    }
\`\`\`  


# Footnotes  

Use the syntax \[\^\] to create footnote reference. Identifiers can be numbers or words but they cannot contain spaces or tabs.

This is a note on my journal, [^1] and it is explained below. [^context]  

[^1]: This is the first footnote  

[^context]: This is a sample footnote on my coding journal.  


# Heading IDs  

Ids can be added on heading like how HTML elements work.

    ### Custom Heading {#custom-id}  

You can link to the heading Ids by creating a standard markdown link
    \[This is a sample markdown link\](#custom-id)  


# Definition Lists  

Creates a list of term definitions  

First term
: definition for the first term  

Second term
: definition for the second term
: another definition for the second term  


# Strikethroughs  

Can be created by enclosing a word inside two tildes(~~)  

~~crossed out~~  


# Task Lists  

Resembles a list that can be marked one by one. To create, just simple create a list that adds combination of dash(-), space and a square bracket with an space in betweeen ([ ]). Add an *x* inside to mark.  

- [x] create learning journal
- [ ] build something out of what is learned
- [ ] make plans on what to learn next  


# Emoji  

Can be created by enclosing the name of the emoji inside a colon.  

:joy:  

Gone camping! :tent: Be back soon


# Highlight  

Put the word inside two equal signs(==)  

The last word for this sentence is ==highlighted==.  


# Subscript  

Put one or more character inside a tilde(~).  

H~2~O  


# Superscript  

Place one or more characters inside a caret(^) symbol.  

c^2^ = a^2^ + b^2^  


