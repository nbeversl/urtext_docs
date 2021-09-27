 

# Urtext  Version: 1.0-alpha  Usage Guide and ReferencesUrtext | Version: 1.0-alpha | Usage Guide and References
License: GNU General Public License 3.0

## About This Documentation

This is a documentation of Urtext written in Urtext. The             on it was exported from the text files in this repository. Clone or download the repository to use it as both reference and example project. 

This documentation is in active development. It may be incomplete or behind features/functionality of Urtext. Edits and revisions are encouraged in the form of issues and pull requests (https://github.com/nbeversl/urtext-docs/pulls, https://github.com/nbeversl/urtext-docs/issues).

Many of the examples rely on syntax and formatting that are stripped out in export to Markdown. These are replaced with screenshots as necessary (see | Linking to Files and Other Resources >00q and | Exporting >ezg)

Inside an Urtext implementation, such as the Sublime Text with the Urtext package, you can navigate the project directly. Most of the key commands utilize Control-Shift as the modifier. 

- Control-Shift-/ to follow any link
- Control-Shift-H at any time to return to this "home" node. 
- View the readme: [readme.md ;](readme.md ;)

## Quick Start, Guides and Examples >z7t
  ├── Installation and Setup (Sublime Text / Desktop) >6cd
  ├── Basic Syntax >znj
  └── Dynamic Definitions : Syntax and Parameters >87g
Reference >ac5
  ├── About Urtext >013
  │   ├── Description >yv2
  │   ├── Comparison To Other Tools >h8z
  │   ├── Uses >lhs
  │   └── Features and Philosophy >006
  │       ├── Plain Text >7rg
  │       ├── Freeform, Flexible Syntax >wzk
  │       ├── Open source >u8o
  │       ├── Extensibile >gn8
  │       ├── Future Proof >xat
  │       ├── Local >2yx
  │       └── Other Features >kne
  ├── Projects >dce
  │   └── Using/Adding Existing Files >rij
  ├── Nodes >01j
  │   ├── Types of Nodes >07q
  │   │   ├── File Nodes >ekz
  │   │   ├── Bracket Nodes >004
  │   │   │   ├── Example Bracket Node >ywi
  │   │   │   └── Escaping Curly Brackets >8a8
  │   │   └── Compact Nodes >kpz
  │   │       ├── Example Compact Node >d7b
  │   │       └── Example inline node within compact node. >9up
  │   └── Node Titles >ue2
  ├── Dynamic Nodes >k8p
  │   ├── Dynamic Definitions >07u
  │   ├── Lists >twz
  │   │   └── Example: Nodes from the Documentation >m1r
  ├── Links and Pointers >00j
  │   ├── Links >0y2
  │   │   └── Sublime Text tools to help with linking >00m
  │   ├── Dynamic Titles >4vu
  │   ├── Opening Links >01w
  │   │   ├── Sublime >osu
  │   │   └── Pythonista >iy8
  │   ├── Linking to Files and Other Resources >00q
  │   │   ├── Web / HTTP(S) >00o
  │   │   └── Files >00p
  ├── Exporting >ezg
  │   ├── Example : Urtext Documentation Exported in Markdown to a File >m9d
  │   └── Example : Fragment Exported to HTML >baq
  ├── File Naming >01m
  ├── History >prp
  ├── This node now has special reserved metadata keys that will be parsed as follows: >00l
  ├── Errors and Warnings >bpk
  ├── Using Multiple Projects >ipy
  │   ├── Project Naming (Identification) >tgp
  │   └── Cross-Project Linking >7lx
  └── User Interface Elements >3n6
      ├── The Node Browser >01i
      └── Traverse Mode >00w
          └── Word Wrap in Traverse Mode >xci
About This Documentation >p23
((>a5m:111))

## Quick Start, Guides and Examples



### Installation and Setup (Sublime Text / Desktop)

For desktop use (PC/Mac/Linux) Urtext is implemented in Sublime Text.

1. Download Sublime Text. (https://www.sublimetext.com/).

2. Download Urtext and all its dependencies from the monorepo at                                          . You can either download this repository as a .ZIP file and unzip it, or if you want to maintain version control, use                                                                         . Put the contents of the cloned/unzipped folder (important: not the folder itself) directly into your                                folder.

3. Download the Sublime Urtext package at                                             . Place it in your Packages folder (Sublime Text 3/Packages)

4. Clone/download this documentation repository and open its folder in Sublime. It will automatically be read as an Urtext project.

Once the Sublime package is installed, it will always look for any files with the .txt extension in open folders and attempt to compile them into a project. To open an existing Urtext project, open the folder, a file in the folder, or a Sublime project that includes the folder, and any feature described in this documentation will work.

To make a new project, open an empty folder and select Select                               from the Sublime Command Palette. For more information, see | Projects >dce.


### Basic Syntax

All text is plain content unless inside a timestamp wrapper, dynamic definition wrapper, or preceded by a metadata assignment operator and keyname.


Bracket Node Wrappers. Can appear anywhere. Can be nested aribrarily deep.
More information: | Bracket Nodes >004


Node Link. Links to the specified node by ID, like a hyperlink. 
More information: | Links >0y2


Node Pointer: Embeds the specified node as though it were included bracket using wrappers       (see above)
More information: [ MISSING LINK : lmu ] 


Title Pipe. Placed immediately before a node link or node pointer (whitespace is ok), dynamically populates the linked node title.
Example and more info: | Dynamic Titles >4vu


Bullet Node marker. Must be the first non-whitespace character on a line. Must include an ID in order to parse as a node.
More information: | Bullet Nodes >j6t


Timestamp wrapper. Parses user-defined datetime strings, with many default formats built in.
The first character inside the brackets may not be    , '-', or whitespace.
Example: 
More information: | Syntax and Format >005


Metadata assignment operator. Accepts a user-defined key on the left, and values and timestamps on the right.
Metadata may appear anywhere. They attach to their containing (parent) node, remember their exact location, and can serve as anchors/bookmarks to context. Keys must be single words (underscore permitted), values may be any characters, terminated with a semicolon or newline. The pipe character (   ) separates multiple values for a single key.
Example:


### Dynamic Definitions : Syntax and Parameters

Dynamic definitions are instructions for dynamically building nodes from other nodes. Definitions can be written anywhere; it is not necessary to store a definition in the same file to which it refers. (Definitions cannot, however, be stored in the node they target, since they would overwrite themselves.)

Dynamic definitions are wrapped with double left and right square brackets(    ,    ). There are no restrictions on spacing, indentation, newlines, or other arbitrary text or whitespace. The order of parameters within a definition is unimportant; they are evaluated as a group.

This dynamic definition below is for documentation and does not actually do anything. It rather lists every parameter along with an explanation of its use and purpose. For example uses, see | Dynamic Nodes >k8p


[[ 	ID() 			Target node to dynamically populate with output.
Accepts a link to a node [ MISSING LINK : eee ] )

INCLUDE()  		Nodes to include. Accepts one or more key/value pairs and optional parameters.
or +()
Comparisons:

means equal to
INCLUDE(key = value)	
Includes all nodes with the given key containing the given value

means "contains"
INCLUDE(_contents ? some text or content)
Includes all nodes containing "some text or content" in their text contents.
(See also -search)

means "anything"
INCLUDE(index = *)
Includes all nodes containing the key        

Use semicolon or newline to separate entries, as everywhere in Urtext.

Additional Flags:

Additional flags can be included in 

INCLUDE(*) or +(*)
Includes all nodes in the project									

or     
INCLUDE(-all_projects) or +(*p)
Expands included nodes to include all projects in the project list.


Includes all nodes that contain only whitespace as their content

Note these additional flags substitute for semicolons/newlines as separators between entries.

System keys

Urtext includes some built-in keys whose values are generated automatically. 
These may also be used in INCLUDE(): 


INCLUDE(_links_to = 46d)
Includes all nodes that contain links to node ID      


INCLUDE(_links_from = 46d)
Includes all nodes to which node ID       links

: Refers to a node's text contents. 
Can be used, for instance, for full text search or comparison.
INCLUDE(_contents ? Western Civilization)
Includes any node that contents the text "Western Civilization"
(comparisons are case-insensitive)

EXCLUDE()		Accepts all the same parameters as INCLUDE()
or -()			Always evaluated after INCLUDE(), excludes the specified nodes from the result.



SORT()			Sorts the results. Entries can be keynames (include system-defined ones, see below)
or flags, with multiple keys separated by semicolon or newline.

SORT(

[ key name ]		Sorts by the value of the given key. Default is alphabetical.

-num or -n  		Sorts the results numerically if possible.
The default sort is alphabetical.

-timestamp or -t  	Sort by timestamp

-reverse or -r 		Reverses the sort order. Applicable to any of the above.

)

Note that system-assigned keys are also available:




Example:
SORT(title -reverse)

LIMIT()			Limits the output to the specified number of results.
Limit is applied after SORT().

Example:
LIMIT(30)
Will only show 30 results of nodes with the specified INCLUDE()/EXCLUDE() parameters.


LIST()			This is the default output if no other is specified. 
It outputs a list of (unique) nodes specified by the combination of INCLUDE() with EXCLUDE(). 
To see instead a tree representation of each node and its descendants, if any, provide a level of depth as
a parameter. Example: LIST(5). 

To show unlimited depth (until recursion, if it occurs), use the asterisk: LIST(*)

COLLECT()		Aggregates occurrences of metadata, including timestamps, and surrounding contents.
Accepts key/value pais 
Returns a seperate item for each occurence.

Example:
COLLECT(timestamp=*)


SHOW()			Supplies a template for the output of each result. 
Accepts keynames, denoted with    , arbitrary text, and Unicode characters including \n, \r, \t.

Words preceded by     are are evaluated as metadata keys, replaced in the output by their value(s).
Note that key names themselves are not displayed in the output. Add keynames manually if you want them included.

Example:
SHOW(Author: $author, Date: $date\n)

In addition to all user-defined metadata keys, the following tokens are included:

SHOW(

$title 
Displays the node title, default or via the         meta key

$link
Displays a link to the node

$date 
Displays the node's date in the project's default timestamp format

$meta
Shorthand to show all metadata for every node, formatted as by "consolidate metadata"

$contents:120
Displays the contents of the node. Optional excerpt/length specifier after the colon
)

HEADER()		Adds additional arbitrary/freeform text to the beginning of the output. This can include any syntax 
valid inside Urtext nodes, including metadata.

FOOTER()		Adds additional arbitrary/freeform text to the end of the output. Same as for HEADER().

MARKDOWN()		Outputs a Markdown representaion of the node(s) into another node or into an external file.
Will include all hierarchically nested nodes using Markdown heading format.
See FORMAT() for ways to preformat the output.

Accepts one or more semicolon- or newline-separated links to nodes or files (see | Linking to outside 
resources >00q)

To include all nodes pointed to from the root file, recursively, use the flag:


HTML()			As for MARKDOWN(), but outputs as HTML.

PLAINTEXT()		As for MARKDOWN(), but outputs Plaintext (Urtext syntax stripped out, 
including metadata and dynamic definitions.)

Can be used, for instance, to export a node or nodes to a non-Urtext text file.

FORMAT()		Specificies additional global formatting of the output. There are intended primarily for formatting 
exported text, but can be applied to any output. Accepts one or more predefined flags:

-preformat or -pre
Wraps preformatted text (trees, etc.) in backticks to preserve preformatting, 
for instance, for Markdown contenxts.

-multiline_meta or -mm
Places dynamic node metadata on separate lines instead of separated by;

-indent: or -i
Indents the dynamic node by the number of spaces specified in parentheses.
Example: FORMAT(-indent:20)

]]
| Sublime Text Key Bindings and Operations >1vs

## Reference


### About Urtext

#### Description

Urtext is a syntax and interpreter for writing, connecting and organizing text.

Urtext's basic unit is a "node", which is a range or set of ranges of text within a file. A folder of nodes is a "project". The Urtext interpreter is aware of all the nodes in a project at once, so nodes can reference, modify, and organize one another, across hundreds or thousands of files. The | Basic Syntax >znj permits instructions embedded into the text itself. 

The present interpreter for Urtext is in Python and can be used wherever Python 3.3 or later runs. Equivalent or variant interpreters could be created in any language or editing environment. 

Urtext has no built-in user interface; it only compiles and manages the files. Using Urtext requires an implementation within a text editor or text view, with a wrapper to pass messages between back and forth. Currently there is a package for Sublime Text (Mac/Windows/Linux) and a script for Pythonista (iOS).

#### Comparison To Other Tools

Urtext shares some characteristics with markup languages such as Markdown and LaTeX, with the important difference that it is author-facing, rather than reader-facing. It is not primarily a document conversion or document generation tool, though it can export to some other formats (currently Markdown and HTML). 

Urtext's syntax combines content, structure and instructions all together. Unlike HTML or other markup languages, there is no additional code or markup "behind" the visible syntax. Everything the interpreter reads is visible to the user.

#### Uses

Including but not limited to:

- prose writing
- research
- documentation
- knowledge/information base
- journaling
- Zettelkasten
- project/personal organization
- notetaking
- lightweight database
- any other writing or information management that can be done in text form

#### Features and Philosophy

##### Plain Text

Plaintext is fast, human-readable, flexible, cross-platform, device-portable, and future-proof. It can be easily diffed and version-controlled (using Git, for example). Using theming and syntax highlighting, the text forms its own user interface without relying on graphic elements.

It can also incorporate (embed) other plaintext syntaxes, including other markup languages and other programming language syntaxes.

##### Freeform, Flexible Syntax

Urtext is like an inverse programming language. Whereas most programming languages provide a "comment" syntax to insert freeform text around the code, Urtext works the opposite way: all content is text unless it matches syntax for structural or instructional code.

Text can be supplemented with user-defined metadata independent of the file system's metadata (datetime stamps, comments, etc.). It can even be used as a flat-file database.

Similar to code projects, an Urtext project can be spread across dozens or thousands of files, with individual files providing "routes", or connections, to other other files or parts of files (nodes) via their node IDs. Text elements can be linked in tree-like, recursive (tangled), and other non-hierarchical ways.

However, the basics are very simple, and you can use only the parts you need.

##### Open source

- Usable across multiple platforms and devices.

- Decoupled from any particular text editor or interface ; it can be incorporated into any environment that runs Python, including any scriptable text editor or Python-scriptable environment capable of displaying a text editing view.

##### Extensibile

Urtext Actions, Directives, and ___ all inherit from base classes that can be user-extended to add or modify functionality limited only by the power of the Python language. 

At present these features are undocumented, but can be understood if you know Python by reading the code.

##### Future Proof

No reliance on anything that may not exist in 5 or 1000 years. 

The interpreter/compiler could be implemented in any sufficiently capable language, current, past or future.

##### Local

The Urtext parser is made primarily to operate on files present locally on the device. It is not dependent on a cloud or other subscription service. 

Cloud services can be used to sync project files among devices if desired.

##### Other Features

Urtext is designed to make direct interaction with file system mostly unnecessary. Creating, naming, saving, and organizing files is handled for you.


### Projects

An Urtext project is a single folder. The folder must contain at least file with an Urtext Node ID.

To make an new empty project:

- make a new folder and open the folder in Sublime Text. 
- Select Urtext : Initialize Project from the Sublime Command Palette. 
- The folder how has one Urtext file and a           folder for tracking edits. (See | History >prp )

#### Using/Adding Existing Files

Once a folder contains at least one file with a node ID, you can add and use existing plaintext files in the project without any modification. However for most of the benefits of Urtext you must minimally an ID (| Node IDs >01q) in each file.

To do so, select                           from the Sublime Command palette.

Note the append will occur without a confirmation dialog, so if you are just experimenting with this system, consider making a copy of your file folder so you can revert without having to manually remove the metadata.


### Nodes

A node is region, or set of regions, of a file, up to and including the entire file. 
A file is itself a node. 
All nodes can contain other nodes.

The identity of an Urtext node persists no matter its containing filename. This is accomplished by assigning each node a three-character identifier using alpha-numeric characters, providing over 46,000 possible nodes per project. See | Node IDs >01q for more information.

Urtext generates IDs automatically on creation of new nodes. ID's can be changed without affecting functionality, though links must then be manually updated as well. 

It is possible to use files containing no IDs in an Urtext project, but then most of the features of Urtext are lost.

#### Types of Nodes



##### File Nodes

The most basic node is a single file. It may or may not contain other nodes nested inside it.

To create a new file-level node: | New Node: ctrl + shift + ; >ve3. A new file is created and named automatically. It contains a single node ID and (by default) a creation timestamp.


##### Bracket Nodes                                                       

Nodes can be nested arbitrarily deep inside other nodes, whether the parent node is a file or another bracket node. For all purposes in Urtext, bracket nodes' identities are unique from their containing files, parent nodes, and child nodes.   

The syntax for bracket nodes is to wrap the content in curly braces:

###### Example Bracket NodeCreate an bracket nodes with | Insert Inline Node: >rzx. Inside the inserted double curly braces is a new node with an auto-generated ID.   

To wrap existing content into an bracket node, first select the content and use the same keypress.

When syntax highlighting is active, bracket node wrappers are tinted to showing nesting level:

###### Example first level

####### second level

######## third test level

######### fourth level

########## fifth level(The following metadata excludes this example from the Table of Contents tree. See [ MISSING LINK : v7r ]  for information)(For Markdown export, a screenshot is provided showing indentation and highlighting:) [./files/node-nesting-example.png](./files/node-nesting-example.png)

Note that every opening curly bracket must be closed in the same file. Every node requires an ID between its opening and closing brackets. Nodes at the file level (| File Nodes >ekz) do not use curly-braces, as their region boundaries are the file itself.

###### Escaping Curly Brackets

If you need to use curly brackets in your text, you can escape the Urtext syntax by preceding the bracket with a backward slash; this will prevent them from being parsed: \{ \}

To ignore syntax elements more globally, and/or to embed other syntaxes that use Urtext characters, such as JSON, PHP, and JavaScript, see [ MISSING LINK : oy5 ] 


##### Compact Nodes

Key: | Insert Compact Node: >1qq

For text content requiring only a single line, such as list items, very short notes and similar, use the caret character (   ) as the first non-whitesoace character on a new line. This defines a new node as a child of the node in which the character appears, with the closing wrapper being the end of the same line. 

Like all nodes, a compact node requires an ID. Like all nodes, it can contain metadata and even inline nodes, as long as the entire contents, including wrappers and metadata, are contained on a single line. (Note that "line" in this case refers to consecutive characters between explicit line breaks, and not to lines in the editor, which may be arbitrarily wrapped.)

###### Example Compact Node

####### Example inline node within compact node.[./files/example-compact-node.png](./files/example-compact-node.png)

#### Node Titles

By default, the full first non-whitespace line of any node is the node's title. This can be overridden using the         metadata key or by following the desired text with the underscore (   ) character as used in this document.


### Dynamic Nodes

Dynamic nodes contain content aggregated from the contents of other nodes. Dynamic content stays up to date with its source content "dynamically" (on file save). A dynamic node can be seen as a "view into" other content.

#### Dynamic Definitions

Dynamic nodes are created using a Dynamic Definition. Dynamic Definitions are specified with double square brackets , and have there own syntax, including scoping and highlighting. Dynamic definitions can query, sort, filter, and format the output of nodes in a variety of ways, making them adaptable to many purposes. This section illustrates some example uses of dynamic nodes. It will be helpful to reference | Dynamic Definitions : Syntax and Parameters >87g.

Dynamic Definitions can be written anywhere; it is not necessary to store the definition in the same file to which it refers. (Note that they cannot, however, be stored in the node they target, since they would overwrite themselves.)

The key | Insert Dynamic Definition with Node:                    >jsc creates a new dynamic definition in Sublime, auto-populated with a corresponding empty inline node. You can also write a definition manually, providing the ID of an existing node. For example, if you want the contents to replace an existing node, assign this key the value of that node's ID. If you want it to populate new inline node, create that node and then copy/paste its ID. Note that Dynamic Definitions do not create their target nodes automatically ; the target node must exist, or the definition will have no effect.There are two main kinds of dynamic output, Lists and Collections:

"Lists" are lists of nodes, with each node displayed not more than once. Lists can optionally expand into trees, showing the hierarchy of nested relationships from each root node in the list.



#### Lists

##### Example: Nodes from the Documentation

Dynamic Definitions >07u
Generating a node ID manually >rfp
Other Features >kne
Node Browser, Backlinks: >1ea
Identifies the home node for the project, connected to the "Home" key >d6u
Extensibile >gn8
History >prp
General Syntax >8dw
Nav Forward: >yan
Future Proof >xat
Download Dependencies from a Monorepo >arl
Insert Link to New Node: >sxk
Errors and Warnings >bpk
Cross-Project Linking >7lx
History >a8q
Quick Start, Guides and Examples >z7t
Search Using Dynamic Nodes >uy4
Example Compact Node >d7b
Comparison To Other Tools >h8z
tag_all >yin
((>twz:7))[./files/example-list-1-definition.png](./files/example-list-1-definition.png)
[./files/example-list-1.png](./files/example-list-1.png)

Note that the at the bottom of the node is the reserved key       which refers to the node containing the definition.

Lists can be expanded into trees that show the outline of many nodes across many files at any specified depth, up to. In fact, a list is a tree with depth 1.

| Trees >>w8u

"Collections" aggregate metadata entries with their context; the same node may appear many times in a collection if it contains many metadata entries matching the queried parameters.

| Collections >>00k


### Links and Pointers

#### Links 

To make a "hyperlink" from one node to another, use the right angle bracket (>) followed immediately by a node ID. Linking does not require a filename or any other information, only the node ID. Any other surrounding text is ignored.

##### Sublime Text tools to help with linking 


Two Sublime Command Palette commands can make linking quick and easy:

Urtext : Link To ...
Links from the currently viewed node to another node which you can select in the selection panel. When you select a node in the quick panel, a link to that node will be inserted at the cursor.

Urtext: Link From ...
Links TO the current node FROM another node. When you select this command, a link to the current node will be copied to the clipboard. You can then paste the reference into the node you open in the quick panel.

#### Dynamic Titles

Prepending a pipe character to any node link will populate the space between the pipe and link with the node's title, from its metadata or default title. Examples are found throughout this documentation. Titled links are updated at the single file level whenever the file is saved.

#### Opening Links

##### Sublime
Key : | Open Urtext Link: >ngh on a line containing a link to open the node with the linked ID. If the link is to an inline node, Sublime will scroll to and center its starting point.

##### Pythonista 

Use the     botton when the cursor is on any line containing a link.Note that Urtext reads node regions on every save, so cursor location may be imprecise if the file has been altered since the last save.

#### Linking to Files and Other Resources

##### Web / HTTP(S)

HTTP(S) links are recognized automatically and will open in the default browser.    
Example: pressing | Open Urtext Link: >ngh on this line will open the link: http://github.com

##### Files

Links to files can be made by writing     , followed immediately with a file path relative to the folder of the project:
Example: [README.md](README.md)
|  ?  >>lmu


### Exporting
Urtext can export to plaintext, Markdown and HTML. Output can be written to a file or back into another node in the project. Exporting is dynamic; when changes are made to the source files, exports are immediately updated.

#### Example : Urtext Documentation Exported in Markdown to a File

This dynamic definition exports the entire documentation from its root node | Urtext  Version: 1.0-alpha  Usage Guide and References >a5m ) in Markdown format to a file called [./README.md:](./README.md:)


[ MISSING LINK : l0i ] 

#### Example : Fragment Exported to HTML

The following Dynamic Definition is identical to the above, except it exports to HTML.


### File Naming                                                                                

Since node identities are independent of their filenames, you can use any naming convention you want. Urtext can also rename files automatically in convenient formats based on their title and/or index. Renaming by index is useful, for instance, if you want file-level nodes easily readable inside a file system, mobile app, or other file browser.

To rename a file, select "Rename File from Meta" from the command palette (Command-P). This will rename the file in one of the following schema:

If an index is present:

.txt

If no index is present:

.txt

This system preserves automatic numerical sorting within the filesystem, such that the most recent un-indexed nodes appear first. If you want to use another system, such as putting the title first, you can do so.


### History

Though use of powerful version control tools (such as Git, Mercurial, etc.) is possible, Urtext has a lighter built-in versioning system that tracks edits at intervals. It is not necessary to make explicit "commits" in order to utilize this. Urtext creates a single, linear history of each file's content, with each snapshot being a "diff", or record of changes, since the previous snapshot. When a previous state is restored, no "checkout" or "rewind" occurs; rather, the newly restored state is appended to the history. Therefore, in addition to functioning as version control, the feature can also be used as an infinite and non-destructive "undo/redo" editing history that saves state when the file is closed. The default interval is 10 seconds, and can be modified in project_settings. 

To access a file's history, use | Toggle History Traverse: >ndc.

Histories are stored in the /history folder inside the project, as .pkl ("pickle") files. This folder requires no user involvement. If using another version control tool such as Git, you may wish to add the /history folder to your .gitignore file, so that only explicitly committed versions of your project are visible in distributed repositories.


### This node now has special reserved metadata keys that will be parsed as follows:
imestamp


### Errors and Warnings


### Using Multiple Projects

To use multiple projects at once, there is a project context manager. When you initially pass a path to Urtext, it looks recursively in all sub folders for additional projects. If it finds a compilable Urtext project in any one, it adds these to the context manager.  You can then freely switch among projects, either explicitly, or using links between the projects (described below). When switching projects, all Urtext's features, content and behavior, including links, compiling, and all functions linked to UI buttons, will operate in the context of the selected project. 

You can put all your Urtext projects into sub folders of a single path. Alternatively, you may put them anyplace in the file system and choose as your Urtext root a folder that encompasses them all. Compiling may take longer if Urtext has to search through many unused directories. 

Using Python, it is possible to only instantiate a single project, without the context manager. The current implementations in Sublime and Pythonista, however, use the context manager by default, even if you are only using a single project.

Recall that what defines a project is a folder. This is also what separates it from other projects. If you add other Urtext project folders into the initial path, they will all be accessible from the same project list.

To switch between projects in Sublime, select Urtext: Select Project from the command palette.
In Pythonista, use "Switch Projects" from the feature menu.

#### Project Naming (Identification)

Unlike nodes, projects are uniquely identified by name. For this reason, each project must have an unique name within the running instance of Urtext. Projects can be named using the project_title key in the project's project_settings node. If no name is present, the project's name becomes its absolute path in the file system.

#### Cross-Project Linking

You may also link from one project to another within the text. To so this, use the following syntax:

=>"name or path of the other project[ MISSING LINK : idj ] 
(This link is only an example and is non-functioning)

Following this link will change the project context to the named project and open its specified node.


### User Interface Elements

Urtext is made to require minimal user interface elements. They mostly serve as conveniences that duplicate 



#### The Node Browser

The Node browser shows a list of all nodes in the project. It can be implemented in plaintext using a dynamic definition such as: . However, 

also be implemented 

Opening the Node List

Ctrl-Shift-E 




In Sublime Text there is also the alternative of using the UI dropdown. Press Control-Shift-E or select "Urtext: Node List" from the Sublime command palette (Shift-Super-P). Here you can find a node by typing part of its title.

In the Node List, nodes are sorted by their time of creation, with most recent first. They can also be sorted by index (see |  ?  >00z).


#### Traverse Mode   



This feature is currently implemented in Sublime Text only.

You can navigate a node tree or list of nodes by turning on Traverse mode (Shift-Ctrl-R). This will open another pane next to the one you are currently in. As you navigate the nodeview in the left side with the cursor or mouse, the selected node shows on the right. Use Sublime's Focus Group navigation keys, or the mouse, to switch between left and right panes.

Toggle Traverse Mode off by pressing Shift-Ctrl-R again. The status bar at the bottom of the Sublime window indicates whether Traverse is on or off. 

Note that if Traverse mode is off, you can also open a link manually (Shift-Ctrl-/) as normal. 

This feature is not built into Urtext; it is a feature of the Sublime package only.

##### Word Wrap in Traverse Mode

Since Traverse Mode splits the window into two or more panes, it is suggested to set Word Wrap Column to "Auto" in Sublime Settings. This will cause the edited views to wrap correctly no matter the screen or window/pane size, as well as in Sublime's Distraction Free Mode.

Whenever Traverse Mode is enabled on a view, word wrap for that view is turned off altogether to prevent awkward wrapping of trees. It is restored when Traverse Mode is turned off.((>a5m:209)) @t5j