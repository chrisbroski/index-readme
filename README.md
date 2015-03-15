README Index
============

An index.html page that automatically imports and displays the README.md converted to HTML.

Uses the [spec](http://daringfireball.net/projects/markdown/syntax) from Daring Fireball.

Requirements
------------

###Headers

All header types h1 - h6 with the = and - types for h1 and h2

####H4

#####H5

######H6

###Paragraphs

It should handle adding &lt;p&gt; tags properly, plus add &lt;br&gt; tags for two spaces at the end of a line.

###Code

Code block should start with 4 spaces

    function getEventTarget(e) {
        var targ;
        targ = e.target || e.srcElement;
        if (targ.nodeType === 3) { // defeat Safari bug
            targ = targ.parentNode;
        }
        return targ;
    }

###Block Quotes

It should do this, plus nesting.

> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.

It should also dealing with all other MD stuff inside of a quote.

> ## This is a header.
> 
> 1.   This is the first list item.
> 2.   This is the second list item.
> 
> Here's some example code:
> 
>     return shell_exec("echo $input | $markdown_script");

###Lists

####Unordered Lists

Should use asterisks, pluses and hyphens interchangeably (do hyphens later)

*   Red
+   Green
*   Blue

Ordered lists use numbers followed by periods

1.  Bird
2.  McHale
3.  Parish

###Inline Elements

####Hyperlinks

Linked text should start with [ and end with ], then have its URL target in parenthesis ()

####Bold

Two asterisks should surround **bold text**. It should also handle two __underscores__.

####Italics

One asterisk should surround *italicized text* It should also handle _underscores_.

###Automatic Escaping of Special Characters

It should escape this:

AT&T

But still be OK with manually escaped characters

&copy;

It should deal with less-than and greater than in a similar way

4 < 5

Except in in code block where it should **always** HTML encode.

###Escaping

The back slash should make any MD character be displayed as a literal:

\\   backslash  
\`   backtick  
\*   asterisk  
\_   underscore  
\{\}  curly braces  
\[\]  square brackets  
\(\)  parentheses  
\#   hash mark  
\+   plus sign  
\-   minus sign (hyphen)  
\.   dot  
\!   exclamation mark  

###HTML

It should handle HTML properly (by ignoring normal md parsing.) Here is an example from the [spec](http://daringfireball.net/projects/markdown/syntax) for dealing with block-level HTML

This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

This is another regular paragraph.
