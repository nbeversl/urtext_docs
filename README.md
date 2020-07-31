Urtext  Version: 0.4.0-alpha  Usage Guide and ReferencesUrtext | Version: 0.4.0-alpha | Usage Guide and References
License: GNU General Public License 3.0

This is a documentation of Urtext, written in Urtext. If you're reading this as a `README.MD` (on Github, etc.), this file was generated from the text files in this repository. The repository is an Urtext project. Clone or download it to use it as both a reference and an example project. If you are reading this in an Urtext implementation, such as in Sublime Text, you can navigate the project directly. Most of the key commands utilize Control-Shift as the modifier. 
- Control-Shift-/ to follow any link
- Control-Shift-h at any time to return to this "home" node.
# Urtext  Version: 0.4.0-alpha  Usage Guide and References[Urtext  Version: 0.4.0-alpha  Usage Guide and References](#urtext--version:-0.4.0-alpha--usage-guide-and-references)
├── Urtext  Version: 0.4.0-alpha  Usage Guide and References[Urtext  Version: 0.4.0-alpha  Usage Guide and References](#urtext--version:-0.4.0-alpha--usage-guide-and-references)
├── Quick Start, Guides and Examples[Quick Start, Guides and Examples](#quick-start,-guides-and-examples)
│   ├── Installation and Setup (Desktop)[Installation and Setup (Desktop)](#installation-and-setup-desktop)
│   ├── Urtext Syntax Guide[Urtext Syntax Guide](#urtext-syntax-guide)
│   ├── Urtext Operations Guide[Urtext Operations Guide](#urtext-operations-guide)
│   └── Sublime Text Interface Tips[Sublime Text Interface Tips](#sublime-text-interface-tips)
│       ├── Syntax Highlighting[Syntax Highlighting](#syntax-highlighting)
│       ├── Hiding Tabs[Hiding Tabs](#hiding-tabs)
│       ├── Hiding Line Numbers[Hiding Line Numbers](#hiding-line-numbers)
│       ├── Full Screen / Distraction Free Mode[Full Screen / Distraction Free Mode](#full-screen-/-distraction-free-mode)
│       ├── Disable Prompts for File Reload[Disable Prompts for File Reload](#disable-prompts-for-file-reload)
│       ├── Remove Indent Guides[Remove Indent Guides](#remove-indent-guides)
│       ├── Save on Focus Lost[Save on Focus Lost](#save-on-focus-lost)
│       └── Using a Sublime Project for an Urtext Project[Using a Sublime Project for an Urtext Project](#using-a-sublime-project-for-an-urtext-project)
└── Reference[Reference](#reference)
    ├── About Urtext[About Urtext](#about-urtext)
    │   ├── Description[Description](#description)
    │   ├── Comparison To Other Tools[Comparison To Other Tools](#comparison-to-other-tools)
    │   ├── Uses[Uses](#uses)
    │   └── Requirements and Features[Requirements and Features](#requirements-and-features)
    ├── Making a New Project[Making a New Project](#making-a-new-project)
    │   └── Using/Adding Existing Files[Using/Adding Existing Files](#using/adding-existing-files)
    ├── Nodes[Nodes](#nodes)
    │   ├── Files[Files](#files)
    │   ├── Inline Nodes[Inline Nodes](#inline-nodes)
    │   │   ├── Example Inline Node[Example Inline Node](#example-inline-node)
    │   │   └── Syntax Highlighting[Syntax Highlighting](#syntax-highlighting)
    │   ├── ? (Missing Node): >! (Missing Node)[ MISSING LINK : kpz ] 
    │   └── Generating a node ID manually[Generating a node ID manually](#generating-a-node-id-manually)
    ├── Metadata[Metadata](#metadata)
    │   ├── Wrapped[Wrapped](#wrapped)
    │   ├── Inline[Inline](#inline)
    │   ├── Timestamps[Timestamps](#timestamps)
    │   │   ├── Collection / Timeline View[Collection / Timeline View](#collection-/-timeline-view)
    │   │   └── Time Zones[Time Zones](#time-zones)
    │   │       └── Timezone List[Timezone List](#timezone-list)
    │   ├── Case-sensitivity[Case-sensitivity](#case-sensitivity)
    │   │   └── **Needs edit/organization here about Node Titles.[**Needs edit/organization here about Node Titles.](#**needs-edit/organization-here-about-node-titles.)
    │   └── Reserved Keys[Reserved Keys](#reserved-keys)
    │       ├── `index`[`index`](#`index`)
    │       └── `flags`[`flags`](#`flags`)
    │           └── `exclude_from_tree`[`exclude_from_tree`](#`exclude_from_tree`)
    ├── Collection / Timeline View[Collection / Timeline View](#collection-/-timeline-view)
    ├── Trees[Trees](#trees)
    │   ├── From any given node[From any given node](#from-any-given-node)
    │   └── From the root[From the root](#from-the-root)
    ├── Links and Pointers[Links and Pointers](#links-and-pointers)
    │   ├── Links[Links](#links)
    │   │   └── Sublime Text tools to help with linking[Sublime Text tools to help with linking](#sublime-text-tools-to-help-with-linking)
    │   ├── Dynamically Titled Links[Dynamically Titled Links](#dynamically-titled-links)
    │   ├── Opening Links[Opening Links](#opening-links)
    │   │   ├── Sublime[Sublime](#sublime)
    │   │   └── Pythonista[Pythonista](#pythonista)
    │   ├── Viewing Linked Relationships[Viewing Linked Relationships](#viewing-linked-relationships)
    │   ├── Linking to outside resources[Linking to outside resources](#linking-to-outside-resources)
    │   │   ├── Web[Web](#web)
    │   │   └── Files[Files](#files)
    │   ├── Pointers[Pointers](#pointers)
    │   │   ├── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
    │   │   ├── Duplicate Pointers[Duplicate Pointers](#duplicate-pointers)
    │   │   │   └── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
    │   │   └── Recursive Node Pointers[Recursive Node Pointers](#recursive-node-pointers)
    │   │       ├── ? (Missing Node): > !RECURSION 3:
    │   │       └── Pointers[Pointers](#pointers)
    │   └── Traverse Mode[Traverse Mode](#traverse-mode)
    │       └── Word Wrap in Traverse Mode[Word Wrap in Traverse Mode](#word-wrap-in-traverse-mode)
    ├── Using Multiple Projects at a Time[Using Multiple Projects at a Time](#using-multiple-projects-at-a-time)
    │   ├── Project Naming (Identification)[Project Naming (Identification)](#project-naming-identification)
    │   └── Linking Between Projects[Linking Between Projects](#linking-between-projects)
    ├── Converting and Exporting[Converting and Exporting](#converting-and-exporting)
    │   ├── Example : Urtext Documentation Exported in Markdown to a File[Example : Urtext Documentation Exported in Markdown to a File](#example-:-urtext-documentation-exported-in-markdown-to-a-file)
    │   └── Example : Fragment Exported to HTML[Example : Fragment Exported to HTML](#example-:-fragment-exported-to-html)
    ├── Search[Search](#search)
    │   └── Full Text Search[Full Text Search](#full-text-search)
    │       ├── Searching[Searching](#searching)
    │       └── Search Using Dynamic Nodes[Search Using Dynamic Nodes](#search-using-dynamic-nodes)
    │           └── Description[Description](#description)
    ├── Filenames[Filenames](#filenames)
    ├── Development[Development](#development)
    │   └── Make Installation Easier[Make Installation Easier](#make-installation-easier)
    └── File History[File History](#file-history)
# Quick Start, Guides and Examples  

This documentation is in progress, still contains many formatting issues, and is somewhat behind development and features. Please post any questions as issues (https://github.com/nbeversl/urtext-docs/issues).

## Installation and Setup (Desktop)

For desktop use (PC/Mac/Linux) Urtext is implemented in Sublime Text.

1. Download Sublime Text. (https://www.sublimetext.com/).

2. Download Urtext and all its dependencies from the monorepo at `https://github.com/nbeversl/urtext_deps`. You can either download this repository as a .ZIP file and unzip it, or if you want to maintain version control, use `git clone --recurse-submodules https://github.com/nbeversl/urtext_deps`. Put the contents of the cloned/unzipped folder (important: not the folder itself) directly into your `Sublime Text 3/Lib/python3.3` folder.

3. Download the Sublime Urtext package at `https://github.com/nbeversl/urtext_sublime`. Place it in your Packages folder (Sublime Text 3/Packages)

4. Clone/download this documentation repository and open its folder in Sublime. It will automatically be read as an Urtext project.

Once the Sublime package is installed, it will always look for any files with the .txt extension in open folders and attempt to compile them into a project. To open an existing Urtext project, open the folder, a file in the folder, or a Sublime project that includes the folder, and any feature described in this documentation will work.

To make a new project, open an empty folder and select Select `Urtext : Initialize Project` from the Sublime Command Palette. For more information, see [Making a New Project](#making-a-new-project).

See also:

[Sublime Text Interface Tips](#sublime-text-interface-tips)
[Details on the Sublime Implementation](#details-on-the-sublime-implementation)
[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)

[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)
## Urtext Syntax Guide

Basic Text Syntax

All text is plain content unless inside a timetamp wrapper or dynamic definition wrapper. 
The following syntax applies:
[Links](#links)	Link to another node by ID. 
More information: [Links](#links)

| 		Placed before a node link, dynamically populates the linked node title.
Example and more info: [Dynamically Titled Links](#dynamically-titled-links)
More information: [ MISSING LINK : j6t ]
Subnode	wrappers. Can appear anywhere. Can be nested aribrarily deep.
More information: [Inline Nodes](#inline-nodes)

### This node is just here as a destination from the node pointer in  Urtext Syntax GuideThis node is just here as a destination from the node pointer in [Urtext Syntax Guide](#urtext-syntax-guide)
Note it has the `exclude_from_tree` flag, which prevents it from showing up in the table of contents.
	Node Pointer
Embeds the specified node as though it were included inline using wrappers
(see above)
More information: [Pointers](#pointers)

Timestamp enclosure. Accepts and parses user-defined datetime strings, with some default formats built in.
Example: 
More information: [Timestamps](#timestamps)

::		Metadata assignment operator. Accepts a user-defined key on the left, and values and timestamps on the right, anywhere inside node contents. 

Keys must be single words (underscore permitted), values may be any characters, terminated with a semicolon or newline.
Example: 

The pipe character (`|`) separates multiple values.
Example: 

Metadata entries remember their location and can serve as anchors to their 

More information [Metadata](#metadata)


Dynamic Definitions

Dynamic definitions contain instructions for dynamically building nodes from the contents of other nodes. They can be written anywhere inside node content. It is not necessary to store the definition in the same file to which it refers.

Dynamic definitions are wrapped using double left and right square brackets:

Dynamic Definition Wrapper

Template:



Note the dynamic definition syntax ignores whitespace and arbitrary text outside of functions.

Examples:

[[ 	TARGET() 		Target Node ID or external file to dynamically populate with output
Accepts either a link to a node [ MISSING LINK : eee ] ) or file( f>example.file)

Accepts any one (only) of the following flags:

-list (default)

Outputs a list of nodes determined by INCLUDE() and EXCLUDE() (see below)

Example:
TARGET[ MISSING LINK : er3 ]  -list)


-tree

Outputs a tree of the hierarchy of nested nodes, with node specified in INCLUDE() as root.
For information see [Trees](#trees)

TARGET[ MISSING LINK : er3 ]  -tree)

- Ignores INCLUDE() and EXCLUDE().
- Ignores SORT()

-collection

TARGET[ MISSING LINK : er5 ]  -collection)		
Returns a list of all metadata tags and their context, as specified in INCLUDE().


INCLUDE()  		Nodes to include. Accepts one or multiple parameters.

Comparisons:

`=` means equal to
INCLUDE(key = value)	
Includes all nodes with the given value in the given key

`~` means fuzzy match, which is something that needs to be added anyway.
INCLUDE(key ~ value)	

`?` means "contains"
INCLUDE(_contents ? some text or content)

Comparison Operators:

-or (default)
INCLUDE(key:value -or other_key:other_value)
Includes any nodes matching either or both of `

-and
INCLUDE(key = value -and other_key = other_value)
Includes nodes matching both `

Additional Flags:


Additional flags can be included in 

-all
INCLUDE(-all)	
Includes all nodes in the project									

-all_projects
INCLUDE(-all_projects)
Expands included nodes to include all projects in the project list.

Optional Timestamp:

INCLUDE(tags = cello: -or tags = teaching:)
Includes any nodes matching either or both of the key/value pairs within the corresponding timestamp.


System keys

Urtext includes some built-in keys whose values are generated automatically. 
These may also be used in INCLUDE(): 

_links_to			
INCLUDE(_links_to = 46d)
Includes all nodes that contain links to node ID `46d`

_links_from
INCLUDE(_links_from = 46d)
Includes all nodes to which node ID `46d` links

_contents
Refers to the text contents of the node. Can be used to for full text search or comparison.
INCLUDE(_contents ? Western Civilization)
Includes any node that contents the text "Western Civilization"

EXCLUDE()		Accepts all the same parameters as INCLUDE()
Always evaluated after INCLUDE(), excludes the specified nodes from the result.

SORT()			Sorts the results. Accepts multiple parameters:

SORT(
$[key_name]		Sorts by the value of the given key. Default is alphabetical.	
timestamp   	Sort by timestamp instead of alphabetical
last_accessed	Sort by last accessed
reverse			Reverse sort order 
)

Example:
SORT($title, reverse)


_last_accesssed		Timestamp when the node was last accessed.

LIMIT()			Limits the output to the specified number of results.

Example:
LIMIT(30)

SHOW()			Supplies a template for the output. 
Accepts arbitrary text, unicode newline characters (\n, \r).

Words preceded (without whitespace) by `$` are are evaluated as metadata key, whose value(s) will appear in the output.
Note that key names are not displayed in the output, only values. Add keynames manually if you want them included.

Example:
SHOW(Author: $author, Date: $date\n)

In addition to user-defined metadata keys, the following tokens are valid:

SHOW(

$title 
Displays the node title, default or via the `title` meta key

$link
Displays a link to the node

$date 
Displays the node's date in the project's default timestamp format

$meta
Shorthand to show all metadata for every node, formatted as by "consolidate metadata"

$contents:120
Displays the contents of the node. Optional excerpt/length specifier after the colon

)

METADATA()		Applies the given metadata to the output node. Accepts any number of key/value
pairs with optional timestamps.

FORMAT()		Formats the output. 
Accepts one or more predefined arguments:

FORMAT(preformat) 	
Wraps preformatted text (trees, etc.) in backticks to preserve formatting in 
Markdown contexts. Only used with EXPORT().

FORMAT(multiline_meta)
Places dynamic node metadata on separate lines instead of separated by;

FORMAT(indent:30)
Indents the dynamic node by the specified number of spaces


EXPORT()		Exports the specified node id to a file and/or other node in the project.

- Ignores everything except ID() and FILE().

EXPORT (
source:xxx		Specifies the source node id
plaintext 		Export as plaintext (default)
markdown		Export as markdown
html			Export as HTML
)
]] 




Urtext includes some built-in metadata keys. Built-in keys all begin with an underscore character `_`

title  				Overrides the Node Title. 
more info:  TO BE ADDED 

flags  				Sets node behavior. More info:[`flags`](#`flags`)



flags = [ 

'-rr', 
'-recursive',

'-use_timestamp',
'-t',

'-last-accessed',
'-la',

'-r',
'-reverse',

'-and',
'-&',

'-all-projects',
'-*p',

'-markdown',
'-md',

'-html',

'-plaintext',
'-txt',

'-preformat',
'-p',

'-multiline_meta',
'-mm',

'-indent',
'-i',

'-num',
'-n',

'-alpha',
'-a'
]

## Urtext Operations Guide

Urtext has some built-in operations that bound to either hotkeys or to UI menus. They are described here with their suggested hotkey:

Project Management:

Multiple Projects
Import Project
Reload Project
Reindex All Files
Rename File(s) from Meta
Delete This Node
Initialize Project
Pop Node
Move File to Other Project


Navigation: 

`h` 	Home  
Go to the designated home page of the project. Define the home node in [project_settings](#project_settings)

`` 	Navigate Forward 
Go to the next visited node (web-browser-like navigation)

`e`		Node List :
Show a quick search bar of all nodes in the current project

`*`		Global Node List:
Show a quick search bar of all nodes in all known projects.

(none) 	Jump to Source:
When attempting to type or modify any dynamic node (export, tree, search, etc), the editor will jump to the source node of the text at the cursor's position.

Insertions:

`t` 	Timestamp:
Insert a timestamp at the cursor's location, in the project's default format. For setting timestamp format defaults, see [project_settings](#project_settings)

`i` 	ID:
Insert an arbitrary (unallocated) Node ID with metadata wrapper at the cursor position.


Editing:

`g`: 	Editing History
View the editing history for the currently viewed file.
For more informatino see [File History](#file-history)

(menu)	Consolidate Metadata
Consolidates all metadata tags in the node of the current cursor position, into a single wrapper.


Scratch Views

Several outputs performed by dynamic definitions (see [Urtext Syntax Guide](#urtext-syntax-guide)) can also be written into "scratch" (unsaved) views for temporary use, with the intention of discarding them afterward.

(menu)	Timeline

`n`		Search:
See "SEARCH()" in [Urtext Syntax Guide](#urtext-syntax-guide)

(menu)	Interlinks

(menu)	Tree



Sublime Text Only:
Traverse Mode




Node Access History

## Sublime Text Interface Tips  

Here are some tips for best leveraging Sublime's great UI features.
### Syntax Highlighting 

This package comes with a .YML file (`sublime_urtext.sublime_syntax`) defining the Urtext syntax, along with two color schemes that provide syntax highlighting. Syntax highlighting makes everything easier by showing depth of node nesting and dimming certain elements of the syntax. Select the Sixteen (for light) or Monokai (for dark) color schemes in Preferences -> Color Scheme ... 

Then change to the Urtext syntax by selecting it in View -> Syntax -> Urtext. To avoid having to do this for every file, select View -> Syntax -> Open All with Current Extension As ... -> Urtext. (You can undo this later by repeating the same but selecting Plain Text.)
### Hiding Tabs	

If you prefer a clean, terminal-like view, hide tabs: View -> Hide Tabs
This preference can also be set on a per-(Sublime)-project basis. See the Sublime documentation.
### Hiding Line Numbers  

For an extra-clean look, hide line numbers by adding:
"settings" : {
"line_numbers": false,
},

... to your Sublime project settings file.
### Full Screen / Distraction Free Mode  

Since you can navigate entirely from within files, Urtext works great in Sublime's Distraction Free Mode. View -> Enter Distraction Free Mode
### Disable Prompts for File Reload 

Urtext does a lot of writing to files on the fly, often when they are already open. To avoid seeing a dialog every time, add add the following to your Sublime project settings or User Preferences file:
"settings" : {
"always_prompt_for_file_reload": false,
},
### Remove Indent Guides  

Formatting plaintext using tab indentions can look messy if indent guides are on. To turn them off, add to your Sublime project settings file:

"settings" : {
"draw_indent_guides": false,
}
### Save on Focus Lost  

Urtext recompiles your project every time a file changes. To make this more automatic, addto your Sublime settings file:

{ "save_on_focus_lost": true }
### Using a Sublime Project for an Urtext Project  

( see https://www.sublimetext.com/docs/3/projects.html )

You don't need to define a Sublime Project for the Urtext Project, but if you intend to do more than one thing at a time in Sublime, it's convenient to have one; you can then use Select Project -> Quick Switch Project (Ctrl-Super-P) to switch among them.

# Reference 

## About Urtext
### Description 

Urtext is a syntax and interpreter for plaintext. Urtext's basic unit is a "node", which is a range or set of ranges of text within a file. A collection of nodes constitutes a "project"; the interpreter is aware of all the nodes in a project at once, so that nodes can reference, modify, and organize one another, across hundreds or thousands of files. The syntax permits embedding of structural and instructional code into the text itself. 

The present interpreter for Urtext is in Python and can be used wherever Python is running. Equivalent or variant interpreters could be created in any language or editing environment. Using Urtext in a text editor requires an additional wrapper to pass messages between the text editor and Urtext. Currently there is a package for Sublime Text (Mac/Windows/Linux) and a script for Pythonista (iOS).
### Comparison To Other Tools 

Urtext shares some characteristics with markup languages such as Markdown and LaTeX, with the important difference that it is author-facing, rather than reader-facing. Though it can be made to export to HTML, Urtext is not primarily a document conversion or document generation tool. It is rather a tool for organizing text.

Urtext consolidates content, markup and instructions (scripting) into a single compilable syntax. Though it can hyperlink many documents or parts of documents together, unlike HTML, there is no additional code or markup "behind" the visible content. Everything the interpreter reads is visible at all times.
### Uses  

Urtext has many uses, including but limited to:

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
### Requirements and Features   

Many of the following features and benefits were core requirements when creating Urtext. Others came about indirectly. Though many can be found in other tools, they cannot be found together in one single existing tool; this was the motivation for creating Urtext.

- It uses plain text files. Plaintext is fast, human-readable, flexible, cross-platform, device-portable, and future-proof.

- It can compile, organize, and link content spread across hundreds or thousands of files.

- Urtext files and content elements can be linked to one another in tree-like, recursive (tangled), and other non-hierarchical ways.

- It has customizable and extensible metadata that does not rely on the file system.

- It is decoupled from any particular text editor or interface ; it can be incorporated into any environment that runs Python, including any scriptable text editor or Python-scriptable environment capable of displaying a text editing view.

- It is usable across multiple platforms and devices.

- It can incorporate other plaintext syntaxes, including other markup languages and programming languages.

- There is no need to interact directly with the file system (creating, naming, saving, organizing files). File creation, naming and management is handled for you, unless you want to manually name files.

- Cascading complexity; use only the parts you need. Does not take months/years to learn.

- Future-proof. No reliance on anything that may not exist in 5 or 100 years. Urtext files themselves are in plaintext, which will never become unusable. The interpreter/compiler could theoretically be implemented in any sufficiently capable language desired, current, past or future.

- Does not depend on a cloud service. Though cloud services can be used to sync project files among devices, the interpreter itself is made to operate locally; content wholly resides on the device being used.

- Being open source, Urtext is extensible, hackable and customizable to specific needs.

Being in plaintext and having a syntax specification, it can also be used with:

- Themes and syntax highlighting.

- Version control (using Git, for example).


## Making a New Project

An Urtext project is a single folder. The folder must contain at least file with an Urtext Node ID.

To make an new empty project:
- make a new folder and open the folder in Sublime Text. 
- Select Urtext : Initialize Project from the Sublime Command Palette. 
- The folder how has one Urtext file and a `history` folder (for tracking edits. See [File History](#file-history)  for more information)
### Using/Adding Existing Files 

Once a folder contains at least one file with a node ID, you can add and use existing plaintext files in the project without any modification. However for most of the benefits of Urtext you must minimally an ID ([More About Node IDs](#more-about-node-ids)) in each file.

To do so, select `Urtext : Import Project` from the Sublime Command palette.

Note the append will occur without a confirmation dialog, so if you are just experimenting with this system, consider making a copy of your file folder so you can revert without having to manually remove the metadata.

## Nodes

A node is region, or set of regions, of a file, up to and including the entire file. A file is itself a node. All nodes can contain other nodes.

The identity of an Urtext node persists no matter its containing filename, even when moved from one file to another. This is accomplished by assigning each node a unique identifier of alphanumeric characters, providing over 46,000 possible nodes per project. It is possible to use files containing no IDs in an Urtext project, but then most of the benefits of Urtext are lost. 

Each node's ID is generated automatically on creation and placed into its initial metadata region. ID's can be changed without affecting functionality, though links must then be manually updated as well. 

Node IDs are assigned in random order and have no special meaning except as a unique identifier. [More About Node IDs](#more-about-node-ids) .
### Files 

The most basic node is a single file. It may or may not contain other nodes nested inside it.

To create a new file, press `Urtext-;`. A new file is created, named and saved automatically. It has whitespace on top and a metadata block at the bottom containing a node ID and (by default) a creation timestamp.
By default, the first non-whitespace line of any node is the node's title. 


### Inline Nodes                                                                 

Nodes can be nested arbitrarily deep inside other nodes, whether the parent node is a file or another inline node. The syntax for inline nodes is to wrap the content in double curly braces like this:
#### Example Inline Node
Create an inline nodes with `Ctrl-Shift-{`. Inside the inserted double curly braces is a new node with an auto-generated ID. 

To wrap existing content into an inline node, first select the content and use the same keypress.

Like everything in Urtext syntax, you can do this manually by typing the curly braces and generating a new metadata region with an ID by pressing Ctrl-Shift-i. 

Urtext requires attention to syntax. Every opening doubly curly bracket must be closed in the same file and requires an ID metadata tag between its opening an closing brackets.

NOTE that nodes at the file level (see [Files](#files)) do not use curly-braces, as their region boundaries are defined by the file itself.

For all purposes in Urtext, inline nodes' identity is unique from their containing file, parent nodes, and child nodes.
#### Syntax Highlighting  

When syntax highlighting is used 


( see  | |  ?  >d), inline nodes are colored to showing nesting.
tags::

| Compact Nodes >>kpz
### Generating a node ID manually 
If you accidentally delete a Node ID or need to insert one arbitrarily, press Urtext-i.







tags::

## Metadata

Every node can have an unlimited number of metadata entries. Metadata is indexed and becomes searchable and sortable. Other than a few reserved key/value pairs, metadata is user-defined. 

Metadata can be added to text in two ways: using wrapped blocks, or using inline notation:
### Wrapped 

Wrapped metadata blocks can be inserted arbitrarily anywhere inside a node. Metadata blocks open with a forward-slash followed by two dashes and close with two dashes followed by a forward slash: 


Wrapped metadata can be either free-form, such as the example above, or structured in colon-separated key/value pairs, with the value (to the right of the colon) containing an optional timestamp. Examples:




Separated multiple entries using either a new line or a semicolon. Using the semicolon option, several entries may be strung together on a single line. 

Note that:

-   A colon separates the key from the value 

-   All three components are optional; any content preceding a colon (if one is present) is interpreted as a key. Content following the (first) colon is interpreted as a value. 

-   If no colon is present, the entry is read as a value with the default key `comment`.

-   A timestamp anywhere in the value will be indexed as the timestamp for the whole metadata entry. If more than on timestamp appears in an entry, only the first one is indexed.
### Inline 

Individual metadata key/value pairs can also be inserted anywhere in the text without a wrapper, using a double colon (` :: `) notation. 


Inline metadata entries remember their location in the text, making them double as contextual markers and sort indexes.

Inline metadata entries do not include the option of timestamps. Instead, you may insert inline timestamp notation. See [Timestamps](#timestamps)
### Timestamps                                                                                  

Reliance on the operating system's file-created or file-modified date metadata is avoided, since it can be too easily and involuntarily overwritten under ordinary file system operations, such as copying and moving files or folders. 

Text between two angled brackets () is interpreted as a timestamp. 

To insert a timestamp in Sublime, press Control-Shift-O. 

Node timestamps are part of metadata (see Metadata[Metadata](#metadata)). Urtext also utilizes a "loose" parsing of inline timestamps, meaning they can be placed anywhere and will be recognized and parsed.

Timestamps are read and written utilizing Python's `strftime` directives. The default format is:

%%-PYTHON
`.%a., %b. %d, %Y, %I:%M %p`
%%-END

which creates timestamps like: . The format can be customized in the project_settings node (see project_settings[project_settings](#project_settings)). For more information on `strftime` directives and options, see https://docs.python.org/2/library/datetime.html#strftime-and-strptime-behavior.


| Timeline View >>00k
Timestamps                                                                                  

Reliance on the operating system's file-created or file-modified date metadata is avoided, since it can be too easily and involuntarily overwritten under ordinary file system operations, such as copying and moving files or folders. 

Text between two angled brackets () is interpreted as a timestamp. 

To insert a timestamp in Sublime, press Control-Shift-O. 

Node timestamps are part of metadata (see Metadata[Metadata](#metadata)). Urtext also utilizes a "loose" parsing of inline timestamps, meaning they can be placed anywhere and will be recognized and parsed.

Timestamps are read and written utilizing Python's `strftime` directives. The default format is:

%%-PYTHON
`.%a., %b. %d, %Y, %I:%M %p`
%%-END

which creates timestamps like: . The format can be customized in the project_settings node (see project_settings[project_settings](#project_settings)). For more information on `strftime` directives and options, see https://docs.python.org/2/library/datetime.html#strftime-and-strptime-behavior.


| Timeline View >>00k
#### Time Zones 	  


Time zones are not required in timestamps. If no time zone is present, Coordinated Universal Time (UTC) is added by default for parsing and comparison purposes. To modify this default, set the `timezone` key in project settings to another valid value. (Timezone List ##### Timezone List

Africa/Abidjan
Africa/Accra
Africa/Addis_Ababa
Africa/Algiers
Africa/Asmara
Africa/Asmera
Africa/Bamako
Africa/Bangui
Africa/Banjul
Africa/Bissau
Africa/Blantyre
Africa/Brazzaville
Africa/Bujumbura
Africa/Cairo
Africa/Casablanca
Africa/Ceuta
Africa/Conakry
Africa/Dakar
Africa/Dar_es_Salaam
Africa/Djibouti
Africa/Douala
Africa/El_Aaiun
Africa/Freetown
Africa/Gaborone
Africa/Harare
Africa/Johannesburg
Africa/Juba
Africa/Kampala
Africa/Khartoum
Africa/Kigali
Africa/Kinshasa
Africa/Lagos
Africa/Libreville
Africa/Lome
Africa/Luanda
Africa/Lubumbashi
Africa/Lusaka
Africa/Malabo
Africa/Maputo
Africa/Maseru
Africa/Mbabane
Africa/Mogadishu
Africa/Monrovia
Africa/Nairobi
Africa/Ndjamena
Africa/Niamey
Africa/Nouakchott
Africa/Ouagadougou
Africa/Porto-Novo
Africa/Sao_Tome
Africa/Timbuktu
Africa/Tripoli
Africa/Tunis
Africa/Windhoek
America/Adak
America/Anchorage
America/Anguilla
America/Antigua
America/Araguaina
America/Argentina/Buenos_Aires
America/Argentina/Catamarca
America/Argentina/ComodRivadavia
America/Argentina/Cordoba
America/Argentina/Jujuy
America/Argentina/La_Rioja
America/Argentina/Mendoza
America/Argentina/Rio_Gallegos
America/Argentina/Salta
America/Argentina/San_Juan
America/Argentina/San_Luis
America/Argentina/Tucuman
America/Argentina/Ushuaia
America/Aruba
America/Asuncion
America/Atikokan
America/Atka
America/Bahia
America/Bahia_Banderas
America/Barbados
America/Belem
America/Belize
America/Blanc-Sablon
America/Boa_Vista
America/Bogota
America/Boise
America/Buenos_Aires
America/Cambridge_Bay
America/Campo_Grande
America/Cancun
America/Caracas
America/Catamarca
America/Cayenne
America/Cayman
America/Chicago
America/Chihuahua
America/Coral_Harbour
America/Cordoba
America/Costa_Rica
America/Creston
America/Cuiaba
America/Curacao
America/Danmarkshavn
America/Dawson
America/Dawson_Creek
America/Denver
America/Detroit
America/Dominica
America/Edmonton
America/Eirunepe
America/El_Salvador
America/Ensenada
America/Fort_Nelson
America/Fort_Wayne
America/Fortaleza
America/Glace_Bay
America/Godthab
America/Goose_Bay
America/Grand_Turk
America/Grenada
America/Guadeloupe
America/Guatemala
America/Guayaquil
America/Guyana
America/Halifax
America/Havana
America/Hermosillo
America/Indiana/Indianapolis
America/Indiana/Knox
America/Indiana/Marengo
America/Indiana/Petersburg
America/Indiana/Tell_City
America/Indiana/Vevay
America/Indiana/Vincennes
America/Indiana/Winamac
America/Indianapolis
America/Inuvik
America/Iqaluit
America/Jamaica
America/Jujuy
America/Juneau
America/Kentucky/Louisville
America/Kentucky/Monticello
America/Knox_IN
America/Kralendijk
America/La_Paz
America/Lima
America/Los_Angeles
America/Louisville
America/Lower_Princes
America/Maceio
America/Managua
America/Manaus
America/Marigot
America/Martinique
America/Matamoros
America/Mazatlan
America/Mendoza
America/Menominee
America/Merida
America/Metlakatla
America/Mexico_City
America/Miquelon
America/Moncton
America/Monterrey
America/Montevideo
America/Montreal
America/Montserrat
America/Nassau
America/New_York
America/Nipigon
America/Nome
America/Noronha
America/North_Dakota/Beulah
America/North_Dakota/Center
America/North_Dakota/New_Salem
America/Ojinaga
America/Panama
America/Pangnirtung
America/Paramaribo
America/Phoenix
America/Port-au-Prince
America/Port_of_Spain
America/Porto_Acre
America/Porto_Velho
America/Puerto_Rico
America/Rainy_River
America/Rankin_Inlet
America/Recife
America/Regina
America/Resolute
America/Rio_Branco
America/Rosario
America/Santa_Isabel
America/Santarem
America/Santiago
America/Santo_Domingo
America/Sao_Paulo
America/Scoresbysund
America/Shiprock
America/Sitka
America/St_Barthelemy
America/St_Johns
America/St_Kitts
America/St_Lucia
America/St_Thomas
America/St_Vincent
America/Swift_Current
America/Tegucigalpa
America/Thule
America/Thunder_Bay
America/Tijuana
America/Toronto
America/Tortola
America/Vancouver
America/Virgin
America/Whitehorse
America/Winnipeg
America/Yakutat
America/Yellowknife
Antarctica/Casey
Antarctica/Davis
Antarctica/DumontDUrville
Antarctica/Macquarie
Antarctica/Mawson
Antarctica/McMurdo
Antarctica/Palmer
Antarctica/Rothera
Antarctica/South_Pole
Antarctica/Syowa
Antarctica/Troll
Antarctica/Vostok
Arctic/Longyearbyen
Asia/Aden
Asia/Almaty
Asia/Amman
Asia/Anadyr
Asia/Aqtau
Asia/Aqtobe
Asia/Ashgabat
Asia/Ashkhabad
Asia/Baghdad
Asia/Bahrain
Asia/Baku
Asia/Bangkok
Asia/Barnaul
Asia/Beirut
Asia/Bishkek
Asia/Brunei
Asia/Calcutta
Asia/Chita
Asia/Choibalsan
Asia/Chongqing
Asia/Chungking
Asia/Colombo
Asia/Dacca
Asia/Damascus
Asia/Dhaka
Asia/Dili
Asia/Dubai
Asia/Dushanbe
Asia/Gaza
Asia/Harbin
Asia/Hebron
Asia/Ho_Chi_Minh
Asia/Hong_Kong
Asia/Hovd
Asia/Irkutsk
Asia/Istanbul
Asia/Jakarta
Asia/Jayapura
Asia/Jerusalem
Asia/Kabul
Asia/Kamchatka
Asia/Karachi
Asia/Kashgar
Asia/Kathmandu
Asia/Katmandu
Asia/Khandyga
Asia/Kolkata
Asia/Krasnoyarsk
Asia/Kuala_Lumpur
Asia/Kuching
Asia/Kuwait
Asia/Macao
Asia/Macau
Asia/Magadan
Asia/Makassar
Asia/Manila
Asia/Muscat
Asia/Nicosia
Asia/Novokuznetsk
Asia/Novosibirsk
Asia/Omsk
Asia/Oral
Asia/Phnom_Penh
Asia/Pontianak
Asia/Pyongyang
Asia/Qatar
Asia/Qyzylorda
Asia/Rangoon
Asia/Riyadh
Asia/Saigon
Asia/Sakhalin
Asia/Samarkand
Asia/Seoul
Asia/Shanghai
Asia/Singapore
Asia/Srednekolymsk
Asia/Taipei
Asia/Tashkent
Asia/Tbilisi
Asia/Tehran
Asia/Tel_Aviv
Asia/Thimbu
Asia/Thimphu
Asia/Tokyo
Asia/Tomsk
Asia/Ujung_Pandang
Asia/Ulaanbaatar
Asia/Ulan_Bator
Asia/Urumqi
Asia/Ust-Nera
Asia/Vientiane
Asia/Vladivostok
Asia/Yakutsk
Asia/Yekaterinburg
Asia/Yerevan
Atlantic/Azores
Atlantic/Bermuda
Atlantic/Canary
Atlantic/Cape_Verde
Atlantic/Faeroe
Atlantic/Faroe
Atlantic/Jan_Mayen
Atlantic/Madeira
Atlantic/Reykjavik
Atlantic/South_Georgia
Atlantic/St_Helena
Atlantic/Stanley
Australia/ACT
Australia/Adelaide
Australia/Brisbane
Australia/Broken_Hill
Australia/Canberra
Australia/Currie
Australia/Darwin
Australia/Eucla
Australia/Hobart
Australia/LHI
Australia/Lindeman
Australia/Lord_Howe
Australia/Melbourne
Australia/NSW
Australia/North
Australia/Perth
Australia/Queensland
Australia/South
Australia/Sydney
Australia/Tasmania
Australia/Victoria
Australia/West
Australia/Yancowinna
Brazil/Acre
Brazil/DeNoronha
Brazil/East
Brazil/West
CET
CST6CDT
Canada/Atlantic
Canada/Central
Canada/East-Saskatchewan
Canada/Eastern
Canada/Mountain
Canada/Newfoundland
Canada/Pacific
Canada/Saskatchewan
Canada/Yukon
Chile/Continental
Chile/EasterIsland
Cuba
EET
EST
EST5EDT
Egypt
Eire
Etc/GMT
Etc/GMT+0
Etc/GMT+1
Etc/GMT+10
Etc/GMT+11
Etc/GMT+12
Etc/GMT+2
Etc/GMT+3
Etc/GMT+4
Etc/GMT+5
Etc/GMT+6
Etc/GMT+7
Etc/GMT+8
Etc/GMT+9
Etc/GMT-0
Etc/GMT-1
Etc/GMT-10
Etc/GMT-11
Etc/GMT-12
Etc/GMT-13
Etc/GMT-14
Etc/GMT-2
Etc/GMT-3
Etc/GMT-4
Etc/GMT-5
Etc/GMT-6
Etc/GMT-7
Etc/GMT-8
Etc/GMT-9
Etc/GMT0
Etc/Greenwich
Etc/UCT
Etc/UTC
Etc/Universal
Etc/Zulu
Europe/Amsterdam
Europe/Andorra
Europe/Astrakhan
Europe/Athens
Europe/Belfast
Europe/Belgrade
Europe/Berlin
Europe/Bratislava
Europe/Brussels
Europe/Bucharest
Europe/Budapest
Europe/Busingen
Europe/Chisinau
Europe/Copenhagen
Europe/Dublin
Europe/Gibraltar
Europe/Guernsey
Europe/Helsinki
Europe/Isle_of_Man
Europe/Istanbul
Europe/Jersey
Europe/Kaliningrad
Europe/Kiev
Europe/Kirov
Europe/Lisbon
Europe/Ljubljana
Europe/London
Europe/Luxembourg
Europe/Madrid
Europe/Malta
Europe/Mariehamn
Europe/Minsk
Europe/Monaco
Europe/Moscow
Europe/Nicosia
Europe/Oslo
Europe/Paris
Europe/Podgorica
Europe/Prague
Europe/Riga
Europe/Rome
Europe/Samara
Europe/San_Marino
Europe/Sarajevo
Europe/Simferopol
Europe/Skopje
Europe/Sofia
Europe/Stockholm
Europe/Tallinn
Europe/Tirane
Europe/Tiraspol
Europe/Ulyanovsk
Europe/Uzhgorod
Europe/Vaduz
Europe/Vatican
Europe/Vienna
Europe/Vilnius
Europe/Volgograd
Europe/Warsaw
Europe/Zagreb
Europe/Zaporozhye
Europe/Zurich
GB
GB-Eire
GMT
GMT+0
GMT-0
GMT0
Greenwich
HST
Hongkong
Iceland
Indian/Antananarivo
Indian/Chagos
Indian/Christmas
Indian/Cocos
Indian/Comoro
Indian/Kerguelen
Indian/Mahe
Indian/Maldives
Indian/Mauritius
Indian/Mayotte
Indian/Reunion
Iran
Israel
Jamaica
Japan
Kwajalein
Libya
MET
MST
MST7MDT
Mexico/BajaNorte
Mexico/BajaSur
Mexico/General
NZ
NZ-CHAT
Navajo
PRC
PST8PDT
Pacific/Apia
Pacific/Auckland
Pacific/Bougainville
Pacific/Chatham
Pacific/Chuuk
Pacific/Easter
Pacific/Efate
Pacific/Enderbury
Pacific/Fakaofo
Pacific/Fiji
Pacific/Funafuti
Pacific/Galapagos
Pacific/Gambier
Pacific/Guadalcanal
Pacific/Guam
Pacific/Honolulu
Pacific/Johnston
Pacific/Kiritimati
Pacific/Kosrae
Pacific/Kwajalein
Pacific/Majuro
Pacific/Marquesas
Pacific/Midway
Pacific/Nauru
Pacific/Niue
Pacific/Norfolk
Pacific/Noumea
Pacific/Pago_Pago
Pacific/Palau
Pacific/Pitcairn
Pacific/Pohnpei
Pacific/Ponape
Pacific/Port_Moresby
Pacific/Rarotonga
Pacific/Saipan
Pacific/Samoa
Pacific/Tahiti
Pacific/Tarawa
Pacific/Tongatapu
Pacific/Truk
Pacific/Wake
Pacific/Wallis
Pacific/Yap
Poland
Portugal
ROC
ROK
Singapore
Turkey
UCT
US/Alaska
US/Aleutian
US/Arizona
US/Central
US/East-Indiana
US/Eastern
US/Hawaii
US/Indiana-Starke
US/Michigan
US/Mountain
US/Pacific
US/Pacific-New
US/Samoa
UTC
Universal
W-SU
WET
Zulu
)
tags::

### Case-sensitivity  

-   Values are not case-sensitive, except those with the following keys:

`title`             Manually overrides the node's title.
#### **Needs edit/organization here about Node Titles.
`comments           ( This key is assumed when no key is present; used for freeform comments. )
`notes`             ( as for `comments` )
`weblink`           ( used for HTTP/S links. See [Linking to outside resources](#linking-to-outside-resources) )

The rest are used only in the project_settings node (see [project_settings](#project_settings)) :

`timestamp_format`  
`filenames`         
`project_title`
`timezone`
`timestamp_format`
### Reserved Keys 

There are two reserved keys that Urtext interprets in a special way:
#### `index`   

Provides a way to give nodes a sort order in [The Node Browser](#the-node-browser).  Indexed nodes will sort before (above) the others, lowest numbers appearing first. To utilize, add a two-digit sort index (00-99) to a node, such as: 


You can give the same index number to multiple nodes; in this case they sort first by index, then by timestamped, newest first.

Unindexed nodes will display underneath indexed nodes, by timestamp, newest first.
#### `flags`  

Used to set node behavior for specific purposes withing Urtext. At present only the following exists:

-
##### `exclude_from_tree`  

Excludes a node from being included in a tree. For an example, see Example 2 in "Dynamic Nodes" [Example 2 : Tree](#example-2-:-tree). For more on tree, see [Trees](#trees)
-

## Collection / Timeline View 


Urtext will parse node timestamps along with inline timestamps into a project timeline. Press Ctrl-Shift-T or select Urtext: Show Timeline in the Sublime command palette. Each node and inline timestamp is shown in chronological order with nearby text. You can try it with this example project, but note that since many nodes in this document are undated, they have a default date of Thu., Jan. 01, 1970, 12:00AM.

As everywhere in a project, node IDs shown are links that can be opened using Ctrl-Shift-/.

## Trees

In Sublime, you can view a tree of node hierarchies in two ways:
### From any given node 

Position the cursor in the node you want to see as root (outermost) and select "Urtext: Show Tree From Current Node" from the Sublime Command Palette. This will add a new split view to the left side of the current view in Sublime, containing a tree with the selected node as root.
### From the root  

Position the cursor anywhere in the node/file and select "Urtext: Show Tree From Root". This will do the same as above, but the tree will include everything back to the node's root. If the tree extends upward beyond the current file, that will also be included.
Note that each branch of the resulting file tree contains Node ID that works like a link. You can navigate the links on the tree using Shift-Control-/ (see [Links](#links)) or using [Traverse Mode](#traverse-mode).

File trees are displayed in Sublime's scratch views, meaning they will never report as being "dirty" (unsaved). They are intended for one-time/temporary use, will not have a filename, and will not update when a node/file changes. To make permanent and dynamically updated trees, see [ MISSING LINK : e82 ] .

You can extend node trees beyond the file level by using [Pointers](#pointers).

Thanks to the `anytree` module (https://pypi.org/project/anytree/) for the plaintext node tree diagrams.

## Links and Pointers
### Links   

To make a "hyperlink" from one node to another, use the right angle bracket (>) followed immediately by a node ID. Linking does not require a filename or any other information, only the node ID. Any other surrounding text is ignored.
#### Sublime Text tools to help with linking   


Two Sublime Command Palette commands can make linking quick and easy:

Urtext : Link To ...
Links from the currently viewed node to another node which you can select in the selection panel. When you select a node in the quick panel, a link to that node will be inserted at the cursor.

Urtext: Link From ...
Links TO the current node FROM another node. When you select this command, a link to the current node will be copied to the clipboard. You can then paste the reference into the node you open in the quick panel.
### Dynamically Titled Links  

Prepending a pipe character to any node link will populate the space between the pipe and link with the node's title, from its metadata or default title. Examples are found throughout this documentation. 

Note that node link titles are not updated globally throughout the project whenever any node's title changes; rather, titled links are updated at the single file level whenever that file is saved.
### Opening Links
#### Sublime 

Press Shift-Ctrl-/ on a line containing a link to open the node with the linked ID. If the link is to an inline node, Sublime will scroll to and center its starting point.
#### Pythonista  

Use the `>` key when the cursor is on any line containing a link.
Note that Urtext reads node regions on every save, so cursor location may be imprecise if the file has been altered since the last save.
### Viewing Linked Relationships

Elaborate writing and reference systems such as wikis often linking nodes together in tangled and intricate ways. While Urtext cannot draw diagrams of this kind (called acyclic graphs) in plaintext, it can represent these relationships from the perspective of any one node: Position the cursor in the desired node and select "Urtext : Show Linked Relationships..." The currently selected node will be displayed as root; all nodes linking into this nodes, and recursively into those nodes, will be displayed above the root; all files linked from this node, and recursively from those nodes, will be displayed below. Circular references are represented up to one iteration.

These diagrams are displayed as Sublime "scratch" views, meaning they will never report as being dirty (unsaved). They are intended for one-time/temporary use and will not update when a node/file changes. To make permanent and dynamically updated diagrams, see [ MISSING LINK : e82 ] .

### Linking to outside resources
#### Web 

HTTP links are recognized automatically and will open in the default browser.

Example: http://fantutti.com
#### Files 

COMING.

### Pointers          

You can extend trees beyond the file level to create node relationships spanning many files. Preceding a link to a node with two right angle brackets instead of one creates a Pointer. In addition to being a hyperlink, this connects the targeted node, and all of its subchildren, as children of the node containing the Pointer. Example:

Here is an example Child Node:

##### Example Child Node Using a Node Pointer

Pointers          

You can extend trees beyond the file level to create node relationships spanning many files. Preceding a link to a node with two right angle brackets instead of one creates a Pointer. In addition to being a hyperlink, this connects the targeted node, and all of its subchildren, as children of the node containing the Pointer. Example:

Here is an example Child Node:

 

The example Pointer above becomes a child of this node, visible in the [ MISSING LINK : 01a ]  or using the other tree views described in [Trees](#trees).

The advantages to Node Pointers are many, including:

- The tree represents a hierachy of actual content, rather than the files containing the content.

- The tree permits nesting both within and beyond file level.

- The tree can be displayed from any arbitrary starting point, whether or not its branches are within or beyond a particular file.
#### Duplicate Pointers  

Node Pointers may point more than once to the same node, so that content can be reused or referenced across multiple trees within the same project:

Here is the same example child node from above: 
#### Recursive Node Pointers  

Recursive Node Pointers would be ones that point to one of their containing node's own ancestors, causing a circular reference.

These are not prohibited, but the recursion will not be drawn if it is already contained in the tree. Instead, the point of recursion will show RECURSION, with a link to the Node ID of the node causing the recursion.

For example, this Node Pointer points back to the root node of the table of contents: | Urtext  Version: 0.4.0-alpha  Usage Guide and References >>a5m. Instead of the table of contents being drawn recursively from this node, you can see the recursion point in the table of contents.

Note, however, that if you view the entire tree with another node as root, one full iteration will still appear, with the point of recursion falling elsewhere in the tree. For instance, below is the table of contents with the node "Pointers" ([Pointers](#pointers)) as root. See Dynamic Nodes ([ MISSING LINK : e82 ] ) for more information on how to generate trees like this in dynamic nodes.
##### Pointers[Pointers](#pointers)
├── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
├── Duplicate Pointers[Duplicate Pointers](#duplicate-pointers)
│   └── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
└── Recursive Node Pointers[Recursive Node Pointers](#recursive-node-pointers)
    ├── Urtext  Version: 0.4.0-alpha  Usage Guide and References[Urtext  Version: 0.4.0-alpha  Usage Guide and References](#urtext--version:-0.4.0-alpha--usage-guide-and-references)
    │   ├── Urtext  Version: 0.4.0-alpha  Usage Guide and References[Urtext  Version: 0.4.0-alpha  Usage Guide and References](#urtext--version:-0.4.0-alpha--usage-guide-and-references)
    │   ├── Quick Start, Guides and Examples[Quick Start, Guides and Examples](#quick-start,-guides-and-examples)
    │   │   ├── Installation and Setup (Desktop)[Installation and Setup (Desktop)](#installation-and-setup-desktop)
    │   │   ├── Urtext Syntax Guide[Urtext Syntax Guide](#urtext-syntax-guide)
    │   │   ├── Urtext Operations Guide[Urtext Operations Guide](#urtext-operations-guide)
    │   │   └── Sublime Text Interface Tips[Sublime Text Interface Tips](#sublime-text-interface-tips)
    │   │       ├── Syntax Highlighting[Syntax Highlighting](#syntax-highlighting)
    │   │       ├── Hiding Tabs[Hiding Tabs](#hiding-tabs)
    │   │       ├── Hiding Line Numbers[Hiding Line Numbers](#hiding-line-numbers)
    │   │       ├── Full Screen / Distraction Free Mode[Full Screen / Distraction Free Mode](#full-screen-/-distraction-free-mode)
    │   │       ├── Disable Prompts for File Reload[Disable Prompts for File Reload](#disable-prompts-for-file-reload)
    │   │       ├── Remove Indent Guides[Remove Indent Guides](#remove-indent-guides)
    │   │       ├── Save on Focus Lost[Save on Focus Lost](#save-on-focus-lost)
    │   │       └── Using a Sublime Project for an Urtext Project[Using a Sublime Project for an Urtext Project](#using-a-sublime-project-for-an-urtext-project)
    │   └── Reference[Reference](#reference)
    │       ├── About Urtext[About Urtext](#about-urtext)
    │       │   ├── Description[Description](#description)
    │       │   ├── Comparison To Other Tools[Comparison To Other Tools](#comparison-to-other-tools)
    │       │   ├── Uses[Uses](#uses)
    │       │   └── Requirements and Features[Requirements and Features](#requirements-and-features)
    │       ├── Making a New Project[Making a New Project](#making-a-new-project)
    │       │   └── Using/Adding Existing Files[Using/Adding Existing Files](#using/adding-existing-files)
    │       ├── Nodes[Nodes](#nodes)
    │       │   ├── Files[Files](#files)
    │       │   ├── Inline Nodes[Inline Nodes](#inline-nodes)
    │       │   │   ├── Example Inline Node[Example Inline Node](#example-inline-node)
    │       │   │   └── Syntax Highlighting[Syntax Highlighting](#syntax-highlighting)
    │       │   ├── ? (Missing Node): >! (Missing Node)[ MISSING LINK : kpz ] 
    │       │   └── Generating a node ID manually[Generating a node ID manually](#generating-a-node-id-manually)
    │       ├── Metadata[Metadata](#metadata)
    │       │   ├── Wrapped[Wrapped](#wrapped)
    │       │   ├── Inline[Inline](#inline)
    │       │   ├── Timestamps[Timestamps](#timestamps)
    │       │   │   ├── Collection / Timeline View[Collection / Timeline View](#collection-/-timeline-view)
    │       │   │   └── Time Zones[Time Zones](#time-zones)
    │       │   │       └── Timezone List[Timezone List](#timezone-list)
    │       │   ├── Case-sensitivity[Case-sensitivity](#case-sensitivity)
    │       │   │   └── **Needs edit/organization here about Node Titles.[**Needs edit/organization here about Node Titles.](#**needs-edit/organization-here-about-node-titles.)
    │       │   └── Reserved Keys[Reserved Keys](#reserved-keys)
    │       │       ├── `index`[`index`](#`index`)
    │       │       └── `flags`[`flags`](#`flags`)
    │       │           └── `exclude_from_tree`[`exclude_from_tree`](#`exclude_from_tree`)
    │       ├── Collection / Timeline View[Collection / Timeline View](#collection-/-timeline-view)
    │       ├── Trees[Trees](#trees)
    │       │   ├── From any given node[From any given node](#from-any-given-node)
    │       │   └── From the root[From the root](#from-the-root)
    │       ├── Links and Pointers[Links and Pointers](#links-and-pointers)
    │       │   ├── Links[Links](#links)
    │       │   │   └── Sublime Text tools to help with linking[Sublime Text tools to help with linking](#sublime-text-tools-to-help-with-linking)
    │       │   ├── Dynamically Titled Links[Dynamically Titled Links](#dynamically-titled-links)
    │       │   ├── Opening Links[Opening Links](#opening-links)
    │       │   │   ├── Sublime[Sublime](#sublime)
    │       │   │   └── Pythonista[Pythonista](#pythonista)
    │       │   ├── Viewing Linked Relationships[Viewing Linked Relationships](#viewing-linked-relationships)
    │       │   ├── Linking to outside resources[Linking to outside resources](#linking-to-outside-resources)
    │       │   │   ├── Web[Web](#web)
    │       │   │   └── Files[Files](#files)
    │       │   ├── ? (Missing Node): >! RECURSION 2:lmu
    │       │   └── Traverse Mode[Traverse Mode](#traverse-mode)
    │       │       └── Word Wrap in Traverse Mode[Word Wrap in Traverse Mode](#word-wrap-in-traverse-mode)
    │       ├── Using Multiple Projects at a Time[Using Multiple Projects at a Time](#using-multiple-projects-at-a-time)
    │       │   ├── Project Naming (Identification)[Project Naming (Identification)](#project-naming-identification)
    │       │   └── Linking Between Projects[Linking Between Projects](#linking-between-projects)
    │       ├── Converting and Exporting[Converting and Exporting](#converting-and-exporting)
    │       │   ├── Example : Urtext Documentation Exported in Markdown to a File[Example : Urtext Documentation Exported in Markdown to a File](#example-:-urtext-documentation-exported-in-markdown-to-a-file)
    │       │   └── Example : Fragment Exported to HTML[Example : Fragment Exported to HTML](#example-:-fragment-exported-to-html)
    │       ├── Search[Search](#search)
    │       │   └── Full Text Search[Full Text Search](#full-text-search)
    │       │       ├── Searching[Searching](#searching)
    │       │       └── Search Using Dynamic Nodes[Search Using Dynamic Nodes](#search-using-dynamic-nodes)
    │       │           └── Description[Description](#description)
    │       ├── Filenames[Filenames](#filenames)
    │       ├── Development[Development](#development)
    │       │   └── Make Installation Easier[Make Installation Easier](#make-installation-easier)
    │       └── File History[File History](#file-history)
    └── Pointers[Pointers](#pointers)

### Traverse ModeTraverse Mode   




This feature is currently implemented in Sublime Text only.

You can navigate a node tree or list of nodes by turning on Traverse mode (Shift-Ctrl-R). This will open another pane next to the one you are currently in. As you navigate the nodeview in the left side with the cursor or mouse, the selected node shows on the right. Use Sublime's Focus Group navigation keys, or the mouse, to switch between left and right panes.

Toggle Traverse Mode off by pressing Shift-Ctrl-R again. The status bar at the bottom of the Sublime window indicates whether Traverse is on or off. 

Note that if Traverse mode is off, you can also open a link manually (Shift-Ctrl-/) as normal. 

This feature is not built into Urtext; it is a feature of the Sublime package only.
#### Word Wrap in Traverse Mode 

Since Traverse Mode splits the window into two or more panes, it is suggested to set Word Wrap Column to "Auto" in Sublime Settings. This will cause the edited views to wrap correctly no matter the screen or window/pane size, as well as in Sublime's Distraction Free Mode.

Whenever Traverse Mode is enabled on a view, word wrap for that view is turned off altogether to prevent awkward wrapping of trees. It is restored when Traverse Mode is turned off.





tags::

## Using Multiple Projects at a Time

To use multiple projects at once, there is a project context manager. When you initially pass a path to Urtext, it looks recursively in all sub folders for additional projects. If it finds a compilable Urtext project in any one, it adds these to the context manager.  You can then freely switch among projects, either explicitly, or using links between the projects (described below). When switching projects, all Urtext's features, content and behavior, including links, compiling, and all functions linked to UI buttons, will operate in the context of the selected project. 

You can put all your Urtext projects into sub folders of a single path. Alternatively, you may put them anyplace in the file system and choose as your Urtext root a folder that encompasses them all. Compiling may take longer if Urtext has to search through many unused directories. 

Using Python, it is possible to only instantiate a single project, without the context manager. The current implementations in Sublime and Pythonista, however, use the context manager by default, even if you are only using a single project.

Recall that what defines a project is a folder. This is also what separates it from other projects. If you add other Urtext project folders into the initial path, they will all be accessible from the same project list.

To switch between projects in Sublime, select Urtext: Select Project from the command palette.
In Pythonista, use "Switch Projects" from the feature menu.
### Project Naming (Identification) 

Unlike nodes, projects are uniquely identified by name. For this reason, each project must have an unique name within the running instance of Urtext. Projects can be named using the project_title key in the project's project_settings node. If no name is present, the project's name becomes its absolute path in the file system.
### Linking Between Projects 

You may also link from one project to another within the text. To so this, use the following syntax:

{"name or path of the other project"}[ MISSING LINK : idj ] 
(This link is only an example and is non-functioning)

Following this link will change the project context to the named project and open its specified node.

## Converting and Exporting

Urtext can convert (export) nodes, and sets of nodes, to plaintext, Markdown and HTML. Results can be either output to a file or written back into another node within the same project. Like other dynamic functions, exporting is dynamic ; that is, when changes are made to the source nodes, exports are immediately updated, whether they are in a project node or an external file.

Exporting is not implemented in user-interface menus/buttons. Instead, export by utilizing dynamic definitions.

The export command has three components:

export : (format) : ( source_node_id )

(format) : One of `plaintext`, `markdown` or `html`
(source_id): The source node to export.
### Example : Urtext Documentation Exported in Markdown to a File  

The following dynamic definition exports this entire documentation (from its root node [Urtext  Version: 0.4.0-alpha  Usage Guide and References](#urtext--version:-0.4.0-alpha--usage-guide-and-references) ) in Markdown format to a file called documentation.md:
### Example : Fragment Exported to HTML  

The following Dynamic Definition exports the [Links and Pointers](#links-and-pointers) section of the documentation to HTML, into a node inside this one:




defined

## Search
### Full Text Search   

Fuzzy and Full Text Search are already implemented in many modern desktop text editors and some mobile text editors. However Urtext has a built-in search and index capability to avoid reliance on editors and environments.
#### Searching
#### Search Using Dynamic Nodes 	

Search results can populate a dynamic node by using the key-value pair:

- search:(string)

For example, the following definition targets node[Description](#description) (below) and populates it with all nodes containing the word "urtext".
##### Description[Description](#description)
Quick Start, Guides and Examples[Quick Start, Guides and Examples](#quick-start,-guides-and-examples)
This node is just here as a destination from the node pointer in  Urtext Syntax Guide[This node is just here as a destination from the node pointer in  Urtext Syntax Guide](#this-node-is-just-here-as-a-destination-from-the-node-pointer-in--urtext-syntax-guide)
Urtext Operations Guide[Urtext Operations Guide](#urtext-operations-guide)
Details on the Sublime Implementation[Details on the Sublime Implementation](#details-on-the-sublime-implementation)
`flags`[`flags`](#`flags`)
More About Node IDs[More About Node IDs](#more-about-node-ids)
Opening Links[Opening Links](#opening-links)
Full Screen / Distraction Free Mode[Full Screen / Distraction Free Mode](#full-screen-/-distraction-free-mode)
Projects, Structure and Compiling[Projects, Structure and Compiling](#projects,-structure-and-compiling)
iPhone/iPad/iOS[iPhone/iPad/iOS](#iphone/ipad/ios)
Generating a node ID manually[Generating a node ID manually](#generating-a-node-id-manually)
Syntax Highlighting[Syntax Highlighting](#syntax-highlighting)
Nodes[Nodes](#nodes)
The Node Browser[The Node Browser](#the-node-browser)
Filenames[Filenames](#filenames)
Viewing Linked Relationships[Viewing Linked Relationships](#viewing-linked-relationships)
Requirements and Features[Requirements and Features](#requirements-and-features)
Python[Python](#python)
Using Multiple Projects at a Time[Using Multiple Projects at a Time](#using-multiple-projects-at-a-time)
Using Urtext in iOS with Pythonista[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)
Timestamps[Timestamps](#timestamps)
Download Dependencies from a Monorepo[Download Dependencies from a Monorepo](#download-dependencies-from-a-monorepo)
Example : Urtext Documentation Exported in Markdown to a File[Example : Urtext Documentation Exported in Markdown to a File](#example-:-urtext-documentation-exported-in-markdown-to-a-file)
About Urtext[About Urtext](#about-urtext)
Traverse Mode[Traverse Mode](#traverse-mode)
Using/Adding Existing Files[Using/Adding Existing Files](#using/adding-existing-files)
Download and Install Dependencies Manually[Download and Install Dependencies Manually](#download-and-install-dependencies-manually)
Converting and Exporting[Converting and Exporting](#converting-and-exporting)
From any given node[From any given node](#from-any-given-node)
0.1.11-alpha[0.1.11-alpha](#0.1.11-alpha)
Sublime Text tools to help with linking[Sublime Text tools to help with linking](#sublime-text-tools-to-help-with-linking)
Using a Sublime Project for an Urtext Project[Using a Sublime Project for an Urtext Project](#using-a-sublime-project-for-an-urtext-project)
Collection / Timeline View[Collection / Timeline View](#collection-/-timeline-view)
Files[Files](#files)
Reference[Reference](#reference)
Python[Python](#python)
Project Naming (Identification)[Project Naming (Identification)](#project-naming-identification)
Reserved Keys[Reserved Keys](#reserved-keys)
Installation and Setup (Desktop)[Installation and Setup (Desktop)](#installation-and-setup-desktop)
Full Text Search[Full Text Search](#full-text-search)
From the root[From the root](#from-the-root)
Recursive Node Pointers[Recursive Node Pointers](#recursive-node-pointers)
Save on Focus Lost[Save on Focus Lost](#save-on-focus-lost)
Making a New Project[Making a New Project](#making-a-new-project)
Disable Prompts for File Reload[Disable Prompts for File Reload](#disable-prompts-for-file-reload)
0.1.14-alpha[0.1.14-alpha](#0.1.14-alpha)
tag_all[tag_all](#tag_all)
Inline Nodes[Inline Nodes](#inline-nodes)
Make Installation Easier[Make Installation Easier](#make-installation-easier)
Comparison To Other Tools[Comparison To Other Tools](#comparison-to-other-tools)
Search Using Dynamic Nodes[Search Using Dynamic Nodes](#search-using-dynamic-nodes)
project_settings[project_settings](#project_settings)
Urtext  Version: 0.4.0-alpha  Usage Guide and References[Urtext  Version: 0.4.0-alpha  Usage Guide and References](#urtext--version:-0.4.0-alpha--usage-guide-and-references)
Urtext Syntax Guide[Urtext Syntax Guide](#urtext-syntax-guide)
File History[File History](#file-history)
Dependencies and Installation[Dependencies and Installation](#dependencies-and-installation)
Uses[Uses](#uses)

## Filenames


Since node identities are independent of their containing filenames, you can use any naming convention you want. Urtext can also rename files automatically in convenient formats based on their title and/or index. Renaming by index is useful, for instance, if you want file-level nodes easily readable inside a file system, mobile app, or other file browser.

To rename a file, select "Rename File from Meta" from the command palette (Command-P). This will rename the file in one of the following schema:

If an index is present:

.txt

If no index is present:

.txt

This system preserves automatic numerical sorting within the filesystem, such that the most recent un-indexed nodes appear first. If you want to use another system, such as putting the title first, you can do so.




tags::

## Development
### Make Installation Easier  

The way Sublime Text is currently set up, manually installing all the dependency modules is the easiest way to get it set up. Alternatives such as using git subtrees, wrapping each individual dependency in a separate Sublime Package and then making those Packages dependencies of the Urtext Package, etc., all end up involving both more maintenance and more legwork for the end user than just manually installing everything.

If any developer can suggest a better solution, please submit a pull request.

Here are some relevant links:

https://forum.sublimetext.com/t/dependencies-in-package-control-3/14646
https://packagecontrol.io/docs/dependencies

https://forum.sublimetext.com/t/how-to-add-python-modules-to-sublime-text-3/41558

There is a method described in this thread which has not been explored yet:
https://forum.sublimetext.com/t/dependencies-in-package-control-3/14646/5
Example:
https://github.com/packagecontrol/requests
tags::

## File History

Urtext files, being in plaintext, can be versioned using tools such as Git, Subversion, Mercurial, and others. Those tools are intended mainly for coding, when it is generally considered bad practice to commit non-working/non-compiling iterations of a project. Though Urtext files do compile, their actual text content is not a factor in this, so is reasonable to track changes at all stages of a project, even at granular levels.

Though use of powerful version control tools is not discouraged, Urtext has its own, lighter versioning system that tracks edits in the background at discrete intervals so it is not necessary to make explicit "commits" to have access to file history. Urtext creates a single, linear, nondestructive history of each file's content, with each snapshot being a "diff", or record of changes since the previous snapshot. When a previous state is restored, no "checkout" or "rewind" occurs; rather, the newly restored state is appended to the end of the history. Therefore, in addition to functioning as version control, the feature can also be used as a non-destructive "undo/redo" editing history that saves state after the file is closed.

The default interval is 10 seconds, and can be modified in project_settings. 
To access a file's timeline, use Control-Shift-G in Sublime Text. 

Histories are stored in the /history folder inside the project, as .pkl ("pickle") files. This folder requires no user involvement. If using another version control tool such as Git, you may wish to add the /history folder to your .gitignore file, so that only explicitly committed versions of your project are visible in distributed repositories.

