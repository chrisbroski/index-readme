README Index
============

An index.html page that automatically imports and displays the README.md converted to HTML. Just copy the *index.html* page in the root directory of your GitHub repository, and when you deploy to GitHub Pages, your README.md file will converted to HTML and used as the default web page.

It uses [Showdown.js](https://github.com/showdownjs/showdown) for conversion (Most recent version from 2015-1-3) [Simple.css](https://github.com/chrisbroski/simple-css) for basic page layout and a little extra CSS so styles are similar in how your GitHub README is displayed from your repository. 

The examples on this page are from the [spec](http://daringfireball.net/projects/markdown/syntax) by Daring Fireball. The styles are based on [Github style markdown](https://help.github.com/articles/github-flavored-markdown/)

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

Code blocks should start with 4 spaces

    function getEventTarget(e) {
        var targ;
        targ = e.target || e.srcElement;
        if (targ.nodeType === 3) { // defeat Safari bug
            targ = targ.parentNode;
        }
        return targ;
    }

###HTML comment blocks

Do you see anything just below? that's good then.

<!--
This is some comments -->

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
-   Blue

Ordered lists use numbers followed by periods

1.  Bird
2.  McHale
333.  Parish

###Inline Elements

####Hyperlinks

Linked text should start with [ and end with ], then have its URL target in parenthesis ()

####Bold

Two asterisks should surround **bold text**. It should also handle two __underscores__.

####Italics

One asterisk should surround *italicized text* It should also handle _underscores_.

####Code

If you want to demo some code inline like so `if (x < y)` use back ticks. If you use double back ticks it will allow single ones inside inline code.

``There is a literal backtick (`) here.``

###Images

Like links, they start with !\[ then have alt text ending with ], then have its SRC attribute in parenthesis () ![spinner](/img/spinner.gif)

####Autolinking

Like GitHub flavored markdown: https://help.github.com/articles/github-flavored-markdown/ it will auto-link anything starting with http:// or https://

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

This is a table built with real HTML.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>
