# Main Keys :  #obsidian 

Documentation on Basic : [LINK!](https://help.obsidian.md/Editing+and+formatting/Basic+formatting+syntax)

## Online Link

use ctrl + k to make link [link!](www.google.com)

use ! before online link and add image as link to view in the page  
![Hello](https://www.shutterstock.com/image-photo/beach-beautiful-coastline-palm-trees-caribbean-1066803878)
`![Engelbart](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)`
(may not work because of the file format)

can also edit the size mentioning the height and width
` ![Engelbart|100x145](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg) `

------ ----

## Back Links

### Mapping note as link to Text

use square bracket inside another square bracket to make connection between notes
[[Jul 2 2023]]

using # along with heading name after the file name maps the heading to the link
[[Jul 2 2023#Morning]]

use ^ along with specific note after the file name maps the topic to the link 
[[Jul 2 2023#^24ad18]]

using of ! before the double square brackets will bring the specific note to the current page

![[Jul 2 2023#Morning]]

---- ---- 

## Headings

use # and leave a space and type the name of your heading to create heading , use two or more hash ## or ### up to 5# to reduce the size of the heading 

--- ---

## Tags

use # without leaving space to create a tag , which will be useful while ==searching== for the notes 

### Nested Tags
use / to have nested tags `#example/example`

### Tag Format
 - Must contain atleast one non-number character
 - Hyphen - , underscore __  are allowed
 - Forward slash for Nested Tags `/`

--- ---

## Bold  

use __ __ or ** ** to Bold
__Example__ **Example**

--- ---

## Italic

use * * to Italic
*Example*

--- --- 

## Strike Out

use ~~ ~~ to Strike Out
~~Example~~ 

---- ---- 

## Highlight

use == == to Highlight
==example==

---- ---

## Quotes 

use > to Quote a text

> HelloPeoples

\-Praveen


--- ---

## For Coding

### Inline Code 
use ` `` `(backtip '` `` `') to inline code 
### Code Block
use three backtip for codeblock
```HTML
<--- Mention the Language and Type the code as in the example--->

```

```JavaScript
//Example for JS
function Hello(){
	console.log('HelloWorld')
}
Hello();
```

--- ---- 

## Creating List

use - and space to make unordered list
- First
- Second

use (no). and space to make ordered list
1. First
2. Second

use tab for indentation and add nested lists

1. First OL
	- Nested
- Second 
	1. Nested
==OL and UL can be nested between them==

---- ---- 

## Task List

use - and a space followed by [ ] as not finished Task and [x] to finished task
- [x] hello
- [ ] hello

---- ---- 

## Horizontal Bars

Use *** followed by another *** to make horizontal Bar : Not only *** , can use  --- and ____

*** ***
---- -----
## Comments

This is a %% Inline command %% 

%%
This is Multi line command 
Line two
%%

--- --- 
## Callouts

use `>[!Content]` to make Callouts

> [!Click to view]

--- --- 

## Embedded Web Page

<iframe src="www.google.com"></iframe>
--- ----
