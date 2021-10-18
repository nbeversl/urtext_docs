 

# Basic Syntax


All text is plain content unless inside a timestamp wrapper, dynamic definition wrapper, or preceded by a metadata assignment operator and keyname.

`{  }`
Bracket Node Wrappers. Can appear anywhere. Can be nested aribrarily deep.
More information: | Bracket Nodes >004

`>`
Node Link. Links to the specified node by ID, like a hyperlink. 
More information: | Links >0y2

`>>`		
Node Pointers: Embeds the specified node as though it were included bracket using wrappers `{ }` (see above)
More information: 
¡
`|`
Title Pipe. Placed immediately before a node link or node pointer (whitespace is ok), dynamically populates the linked node title.
Example and more info: | Dynamic Titles >4vu

`•`
Bullet Node marker. Must be the first non-whitespace character on a line. Must include an ID in order to parse as a node.
More information: | Bullet Nodes >j6t

`< >`
Timestamp wrapper. Parses user-defined datetime strings, with many default formats built in.
The first character inside the brackets may not be `!`, `-`, or whitespace.
Example: 

More information: | Syntax and Format >005

`::`
Metadata assignment operator. Accepts a user-defined key on the left, and values and timestamps on the right.
Metadata may appear anywhere. They attach to their containing (parent) node, remember their exact location, and can serve as anchors/bookmarks to context. Keys must be single words (underscore permitted), values may be any characters, terminated with a semicolon or newline. The pipe character (`|`) separates multiple values for a single key. 