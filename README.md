
Quick Start, Guides and Examples  

# Installation and Setup (Desktop)

For desktop use (PC/Mac/Linux) Urtext is implemented in Sublime Text.

1. Download Sublime Text. (https://www.sublimetext.com/).

2. Download Urtext and all its dependencies from the monorepo at `https://github.com/nbeversl/urtext_deps`. You can either download this repository as a .ZIP file and unzip it, or if you want to maintain version control, use `git clone --recurse-submodules https://github.com/nbeversl/urtext_deps`. Put the contents of the cloned/unzipped folder (important: not the folder itself) directly into your `Sublime Text 3/Lib/python3.3` folder.

3. Download the Sublime Urtext package at `https://github.com/nbeversl/urtext_sublime`. Place it in your Packages folder (Sublime Text 3/Packages)

4. Clone/download this documentation repository and open its folder in Sublime. It will automatically be read as an Urtext project.

Once the Sublime package is installed, it will always look for any files with the .txt extension in open folders and attempt to compile them into a project. To open an existing Urtext project, open the folder, a file in the folder, or a Sublime project that includes the folder, and any feature described in this documentation will work.

To make a new project, open an empty folder and select Select `Urtext : Initialize Project` from the Sublime Command Palette. For more information, see [Projects](#projects).

See also:

[Sublime Text Interface Tips](#sublime-text-interface-tips)
[Details on the Sublime Implementation](#details-on-the-sublime-implementation)
[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)

[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)

# Operations

Built-in operations are bound to either hotkeys or to UI menus.

Hotkeys differ among operating systems and can be reassigned according to your preference by
modifiying

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

Several outputs performed by dynamic definitions (see [Syntax](#syntax)) can also be written into "scratch" (unsaved) views for temporary use, with the intention of discarding them afterward.

(menu)	Timeline

`n`		Search:
See "SEARCH()" in [Syntax](#syntax)

(menu)	Interlinks

(menu)	Tree



Sublime Text Only:
Traverse Mode


Node Access History

# Sublime Text Interface Tips  

Here are some tips for best leveraging Sublime's great UI features.
## Syntax Highlighting 

This package comes with a .YML file (`sublime_urtext.sublime_syntax`) defining the Urtext syntax, along with two color schemes that provide syntax highlighting. Syntax highlighting makes everything easier by showing depth of node nesting and dimming certain elements of the syntax. Select the Sixteen (for light) or Monokai (for dark) color schemes in Preferences -> Color Scheme ... 

Then change to the Urtext syntax by selecting it in View -> Syntax -> Urtext. To avoid having to do this for every file, select View -> Syntax -> Open All with Current Extension As ... -> Urtext. (You can undo this later by repeating the same but selecting Plain Text.)
## Hiding Tabs	

If you prefer a clean, terminal-like view, hide tabs: View -> Hide Tabs
This preference can also be set on a per-(Sublime)-project basis. See the Sublime documentation.
## Hiding Line Numbers  

For an extra-clean look, hide line numbers by adding:

%%-JSON

"settings" : 
"line_numbers": false,
,

%%-END-JSON

... to your Sublime project settings file. (Ignore the JSON syntax pass makers above beginning with `%%`
See [Pass Markers and Embedded Syntaxes](#pass-markers-and-embedded-syntaxes) )
## Full Screen / Distraction Free Mode  

Since you can navigate entirely from within files, Urtext works great in Sublime's Distraction Free Mode. View -> Enter Distraction Free Mode.
## Disable Prompts for File Reload 

Urtext does a lot of writing to files on the fly, often when they are already open. To avoid seeing a dialog every time, add add the following to your Sublime project settings or User Preferences file:
%%-JSON
"settings" : 
"always_prompt_for_file_reload": false,
,
%%-END-JSON
## Remove Indent Guides  

Formatting plaintext using tab indentions can look messy if indent guides are on. To turn them off, add to your Sublime project settings file:
%%-JSON
"settings" : 
"draw_indent_guides": false,

%%-END-JSON
## Save on Focus Lost  

Urtext recompiles your project every time a file changes. To make this more automatic, addto your Sublime settings file:
%%-JSON
"save_on_focus_lost": true 
%%-END-JSON
## Using a Sublime Project for an Urtext Project  

( see https://www.sublimetext.com/docs/3/projects.html )

You don't need to define a Sublime Project for the Urtext Project, but if you intend to do more than one thing at a time in Sublime, it's convenient to have one; you can then use Select Project -> Quick Switch Project (Ctrl-Super-P) to switch among them.


Reference 	
# About Urtext
## Description 

Urtext is a syntax and interpreter for plaintext. Urtext's basic unit is a "node", which is a range or set of ranges of text within a file. A folder of nodes is called a "project". The Urtext interpreter is aware of all the nodes in a project at once, so that nodes can reference, modify, and organize one another, across hundreds or thousands of files. The [Syntax](#syntax) permits embedding of structural and instructional code into the text itself. 

The present interpreter for Urtext is in Python and can be used wherever Python 3.3 or later runs. Equivalent or variant interpreters could be created in any language or editing environment. 

Urtext has no built-in user interface; it only compiles and manages the files. Using Urtext in a text editor requires an additional wrapper to pass messages between the text editor and Urtext. Currently there is a package for Sublime Text (Mac/Windows/Linux) and a script for Pythonista (iOS).
## Comparison To Other Tools 

Urtext shares some characteristics with markup languages such as Markdown and LaTeX, with the important difference that it is author-facing, rather than reader-facing. Though it can be made to export to HTML, Urtext is not primarily a document conversion or document generation tool. It is rather a tool for writing, connecting and organizing text.

Urtext consolidates content, structure and instructions (scripting) into a single compilable syntax. Although it can link documents or parts of documents together, unlike HTML, there is no additional code or markup "behind" the visible syntax. Everything the interpreter reads is visible to the user at all times.
## Uses  

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
## Requirements and Features   

Many of the following features and benefits were core requirements when creating Urtext. Others came about indirectly. Though many can be found in other tools, they are not currently found together in one single existing tool; this was the motivation for creating Urtext.

- It uses plain text files. Plaintext is fast, human-readable, flexible, cross-platform, device-portable, and future-proof.

- It is usable across multiple platforms and devices.

- Cascading complexity; use only the parts you need. Does not take months/years to learn.

- Being open source, Urtext is extensible, hackable and customizable to specific needs.

- It can compile, organize, and link content spread across hundreds or thousands of files. Files and content elements can be linked to one another in tree-like, recursive (tangled), and other non-hierarchical ways.

- It has customizable and extensible metadata that does not rely on the file system.

- It is decoupled from any particular text editor or interface ; it can be incorporated into any environment that runs Python, including any scriptable text editor or Python-scriptable environment capable of displaying a text editing view.

- It can incorporate (embed) other plaintext syntaxes, including other markup languages and other programming language syntaxes.

- There is no need to interact directly with the file system (creating, naming, saving, organizing files). File creation, naming and management is handled for you.

- Future-proof. No reliance on anything that may not exist in 5 or 1000 years. Urtext files themselves are in plaintext, which is future-proof. The interpreter/compiler could be implemented in any sufficiently capable language desired, current, past or future.

- Does not depend on a cloud service. Though cloud services can be used to sync project files among devices, the interpreter itself is made to operate locally; content wholly resides on the device being used.

Being in plaintext and having a syntax specification, it can also be used with:

- Themes and syntax highlighting.
- Version control (Git, for example).

# Projects

An Urtext project is a single folder. The folder must contain at least file with an Urtext Node ID.

To make an new empty project:
- make a new folder and open the folder in Sublime Text. 
- Select Urtext : Initialize Project from the Sublime Command Palette. 
- The folder how has one Urtext file and a `history` folder (for tracking edits. See [File History](#file-history) )
## Using/Adding Existing Files 

Once a folder contains at least one file with a node ID, you can add and use existing plaintext files in the project without any modification. However for most of the benefits of Urtext you must minimally an ID ([Node IDs](#node-ids)) in each file.

To do so, select `Urtext : Import Project` from the Sublime Command palette.

Note the append will occur without a confirmation dialog, so if you are just experimenting with this system, consider making a copy of your file folder so you can revert without having to manually remove the metadata.

# Nodes

A node is region, or set of regions, of a file, up to and including the entire file. A file is itself a node. All nodes can contain other nodes.

The identity of an Urtext node persists no matter its containing filename, even when copied/pasted entire from one file into another. This is accomplished by assigning each node a unique identifier of three alphanumeric characters, providing over 46,000 possible nodes per project. It is possible to use files containing no IDs in an Urtext project, but then most of the benefits of Urtext are lost. 

Urtext generates node IDs automatically on creation of a new node. ID's can be changed without affecting functionality, though links must then be manually updated as well. 

Node IDs are assigned in random order and have no special meaning except as a unique identifier. [Node IDs](#node-ids).
## Files 

The most basic node is a single file. It may or may not contain other nodes nested inside it.

To create a new file, press `Urtext-;`. A new file is created, named and saved automatically. It has whitespace on top and a metadata block at the bottom containing a node ID and (by default) a creation timestamp.
By default, the first non-whitespace line of any node is the node's title. 

## Inline Nodes                                                                 

The syntax for inline nodes is to wrap the content in curly braces:
### Example Inline Node
Create an inline nodes with `Ctrl-Shift-squiggly-brace. Inside the inserted double curly braces is a new node with an auto-generated ID.   

To wrap existing content into an inline node, first select the content and use the same keypress.

Nodes can be nested arbitrarily deep inside other nodes, whether the parent node is a file or another inline node. When syntax highlighting is active, inline node wrappers are tinted to showing nesting level:
### Example first level
#### second level
##### third level
###### fourth level
####### fifth level
Note that every opening doubly curly bracket must be closed in the same file and requires an ID between its opening and closing brackets. The examples above use [Trailing Node IDs](#trailing-node-ids). You can also use regular [Metadata](#metadata) as at the bottom of this file.

Note that nodes at the file level ([Files](#files)) do not use curly-braces, as their region boundaries are defined by the file itself.

For all purposes in Urtext, inline nodes' identity is unique from their containing file, parent nodes, and child nodes.

## Compact Nodes

For text content requiring only a single line, such as list items, very short notes and similar, use the caret character (`^`) as the first non-whitesoace character on a new line. This defines a new node as a child of the node in which the ^ character appears, with the closing wrapper being the end of the same line. 

Like all nodes, a compact node requires an ID. Like all nodes, it can contain metadata and even inline nodes, as long as the entire contents, including wrappers and metadata, are contained on a single line. (Note that "line" in this case refers to consecutive characters between explicit line breaks, and not to lines in the editor, which may be arbitrarily wrapped.)

To create a new compact node, use ^
### Example Compact Node
#### Example inline node within the compact node.

[Node IDs](#node-ids)

## Generating a node ID manually 
If you accidentally delete a Node ID or need to insert one arbitrarily, press Urtext-i.


# Metadata
## Syntax 

Every node can have an unlimited number of metadata entries. Metadata gets indexed and becomes searchable and sortable from anywhere within the project. Metadata entries also "remember" their location in the text, making them operate as contextual markers. Other than a few reserved key/value pairs, metadata is user-defined.  

Metadata is structured in double-colon-separated key/value pairs, with the value (to the right of the colon) containing an optional timestamp. Examples:




Keys must be single words, though characters such as dash and underscore are allowed. Values may include spaces. Terminate metadata entries using either a new line or a semicolon. Using the semicolon option, several entries may be strung together on a single line:



Note that a timestamp anywhere in the value will be indexed as the timestamp for the whole metadata entry. If more than on timestamp appears in an entry, only the first one is indexed.
## Case-sensitivity  

-   Values are not case-sensitive, except those with the following keys:

`title`             Manually overrides the node's title. 

The rest are used only in the project_settings node (see [project_settings](#project_settings)) :

`timestamp_format`  
`filenames`         
`project_title`
`timezone`
`timestamp_format`
## Reserved Keys 

There are two reserved keys that Urtext interprets in a special way:
### `index`   

Provides a way to give nodes a sort order in [The Node Browser](#the-node-browser).  Indexed nodes will sort before (above) the others, lowest numbers appearing first. To utilize, add a two-digit sort index (00-99) to a node, such as:  
You can give the same index number to multiple nodes; in this case they sort first by index, then by timestamped, newest first.

Unindexed nodes will display underneath indexed nodes, by timestamp, newest first.
### `_flags`  

Used to set node behavior for specific purposes withing Urtext. At present only the following exists:
#### `exclude_from_tree`  

Excludes a node from being included in a tree. For an example, see Example 2 in "Dynamic Nodes" [Example 2 : Tree](#example-2-:-tree). For more on tree, see [Trees](#trees)
#### `exclude_from_export` 

Excludes a node from being exported, when project content is exported. See [Converting and Exporting](#converting-and-exporting).
## Timestamps
### Syntax and Format   

Text between two angled brackets () is parsed as a timestamp.  To insert the current date and time anywhere, press Control-Shift-t: 

Timestamps are read and written utilizing Python's `strftime` directives. The following formats are included by default:

%%-PYTHON # (<- for info about this marker see [Pass Markers and Embedded Syntaxes](#pass-markers-and-embedded-syntaxes) )

# Sat., Sep. 12, 2020, 09:35 AM
'%a., %b. %d, %Y, %I:%M %p' 

# September 12, 2020
'%B %-d, %Y' 

# September 2020
'%B %Y'

# 09-12-2020
'%m-%d-%Y'

# Sat., Sep. 12, 2020, 09:35 AM '
'%a., %b. %d, %Y, %I:%M %p %z' 

# Sat., Sep. 12, 2020, 09:35 AM'
'%a., %b. %d, %Y, %I:%M %p'

# Saturday, September 12, 2020, 09:35 AM'
'%A, %B %d, %Y, %I:%M %p'

# 'September 12, 2020, 09:35 AM'
'%B %d, %Y, %I:%M %p'

# 'September 12, 2020, 09:35AM'
'%B %d, %Y, %I:%M%p'

# 2020
'%Y'

# September 12, 2020'
'%B %d, %Y'

# Saturday, September 12, 2020, 09:35AM
'%A, %B %d, %Y, %I:%M%p'

%%-END-PYTHON 

Additional formats can be added in the [project_settings](#project_settings) node.
Node timestamps are part of metadata (see [Metadata](#metadata)). 
Urtext also utilizes a "loose" parsing of inline timestamps, meaning they can be placed anywhere and will be recognized and parsed.
### Tracking Node Dates and Times    

Reliance on the operating system's "created" or "modified" date metadata is avoided entirely in Urtext, since these values can be easily and inadvertently overwritten during ordinary file system operations, such as copying and moving files/folders. Instead, new nodes  receive by default a "timestamp" metadata key when created:
### Time Zones 	  

Time zones are not required. If no time zone is present, Coordinated Universal Time (UTC) is added by default  for parsing and comparison purposes. To modify this default, set the `timezone` key in [project_settings](#project_settings) to another valid value.


# Collection

Urtext will parse node timestamps along with inline timestamps into a project timeline. Press Ctrl-Shift-T or select Urtext: Show Timeline in the Sublime command palette. Each node and inline timestamp is shown in chronological order with nearby text. You can try it with this example project, but note that since many nodes in this document are undated, they have a default date of Thu., Jan. 01, 1970, 12:00AM.

As everywhere in a project, node IDs shown are links that can be opened using Ctrl-Shift-/.

# Trees

In Sublime Text, you can view a tree of node hierarchies in two ways:
## From any given node 

Position the cursor in the node you want to see as root (outermost) and select "Urtext: Show Tree From Current Node" from the Sublime Command Palette. This will add a new split view to the left side of the current view in Sublime, containing a tree with the selected node as root.
## From the root  

Position the cursor anywhere in the node/file and select "Urtext: Show Tree From Root". This will do the same as above, but the tree will include everything back to the node's root. If the tree extends upward beyond the current file, that will also be included.
Note that each branch of the resulting file tree contains Node ID that works like a link. You can navigate the links on the tree using Shift-Control-/ (see [Links](#links)) or using [Traverse Mode](#traverse-mode).

File trees are displayed in Sublime's scratch views, meaning they will never report as being "dirty" (unsaved). They are intended for one-time/temporary use, will not have a filename, and will not update when a node/file changes. To make permanent and dynamically updated trees, see [ MISSING LINK : e82 ] .

You can extend node trees beyond the file level by using [Pointers](#pointers).

Thanks to the `anytree` module (https://pypi.org/project/anytree/) for the plaintext node tree diagrams.

# Links and Pointers
## Links   

To make a "hyperlink" from one node to another, use the right angle bracket (>) followed immediately by a node ID. Linking does not require a filename or any other information, only the node ID. Any other surrounding text is ignored.
### Sublime Text tools to help with linking   


Two Sublime Command Palette commands can make linking quick and easy:

Urtext : Link To ...
Links from the currently viewed node to another node which you can select in the selection panel. When you select a node in the quick panel, a link to that node will be inserted at the cursor.

Urtext: Link From ...
Links TO the current node FROM another node. When you select this command, a link to the current node will be copied to the clipboard. You can then paste the reference into the node you open in the quick panel.
## Dynamically Titled Links  

Prepending a pipe character to any node link will populate the space between the pipe and link with the node's title, from its metadata or default title. Examples are found throughout this documentation. 

Titled links are updated at the single file level whenever that file is saved.
## Opening Links
### Sublime 

Press Shift-Ctrl-/ on a line containing a link to open the node with the linked ID. If the link is to an inline node, Sublime will scroll to and center its starting point.
### Pythonista  

Use the `/` key when the cursor is on any line containing a link.
Note that Urtext reads node regions on every save, so cursor location may be imprecise if the file has been altered since the last save.
## Linking to outside resources
### Web / HTTP(S) 

HTTP(S) links are recognized automatically and will open in the default browser.    
Example: pressing Ctrl/Command-Shift-/ on this line below will open the link: http://github.com
### Files 

Links to files can be made by writing f> , followed immediately with a file path relative to the folder of the project:
Example:   f>./README.md

## Pointers          

By preceding a link to a node with two right angle brackets instead of one, you can extend trees beyond the file level to create node relationships spanning many files. In addition to being a hyperlink, this connects the targeted node, and all of its subchildren, as descendants of the node containing the Pointer:

#### Example Child Node Using a Node Pointer
 

The example Pointer above becomes a child of this node, visible in the [Table of Contents](#table-of-contents) or using the other tree views described in [Trees](#trees).

The advantages to Node Pointers are many, including:

- The tree represents a hierachy of actual content, rather than the files containing the content.

- The tree permits nesting both within and beyond file level.

- The tree can be displayed from any arbitrary starting point, whether or not its branches are within or beyond a particular file.
### Duplicate Pointers  

Node Pointers may point more than once to the same node, so that content can be reused or referenced across multiple trees within the same project:

Here is the same example child node from above: 
### Recursive Node Pointers  

If the tree of a Node Pointer includes to one of its own ancestors, the recursion will not be drawn again if it is already contained in the tree. Instead, the point of recursion will incidate "RECURSION", with a link to the Node ID of the node causing the recursion.

For example, this Node Pointer points back to the root node of the table of contents: 
#### Urtext  Version: 0.5-alpha  Usage Guide and ReferencesUrtext | Version: 0.5-alpha | Usage Guide and References
License: GNU General Public License 3.0

This is a documentation of Urtext, written in Urtext. If you're reading this as a `README.MD` (on Github, etc.), this file was generated from the text files in this repository. The repository is an Urtext project. Clone or download it to use it as both a reference and an example project. If you are reading this in an Urtext implementation, such as in Sublime Text, you can navigate the project directly. Most of the key commands utilize Control-Shift as the modifier. 
- Control-Shift-/ to follow any link
- Control-Shift-h at any time to return to this "home" node.
##### Table of Contents Quick Start, Guides and Examples[Quick Start, Guides and Examples](#quick-start,-guides-and-examples)
├── Installation and Setup (Desktop)[Installation and Setup (Desktop)](#installation-and-setup-desktop)
├── Syntax[Syntax](#syntax)
│   ├── Basic Syntax[Basic Syntax](#basic-syntax)
│   ├── Dynamic Definitions[Dynamic Definitions](#dynamic-definitions)
│   └── Built-in Metadata Keys[Built-in Metadata Keys](#built-in-metadata-keys)
├── Operations[Operations](#operations)
└── Sublime Text Interface Tips[Sublime Text Interface Tips](#sublime-text-interface-tips)
    ├── Syntax Highlighting[Syntax Highlighting](#syntax-highlighting)
    ├── Hiding Tabs[Hiding Tabs](#hiding-tabs)
    ├── Hiding Line Numbers[Hiding Line Numbers](#hiding-line-numbers)
    ├── Full Screen / Distraction Free Mode[Full Screen / Distraction Free Mode](#full-screen-/-distraction-free-mode)
    ├── Disable Prompts for File Reload[Disable Prompts for File Reload](#disable-prompts-for-file-reload)
    ├── Remove Indent Guides[Remove Indent Guides](#remove-indent-guides)
    ├── Save on Focus Lost[Save on Focus Lost](#save-on-focus-lost)
    └── Using a Sublime Project for an Urtext Project[Using a Sublime Project for an Urtext Project](#using-a-sublime-project-for-an-urtext-project)
Reference[Reference](#reference)
├── About Urtext[About Urtext](#about-urtext)
│   ├── Description[Description](#description)
│   ├── Comparison To Other Tools[Comparison To Other Tools](#comparison-to-other-tools)
│   ├── Uses[Uses](#uses)
│   └── Requirements and Features[Requirements and Features](#requirements-and-features)
├── Projects[Projects](#projects)
│   └── Using/Adding Existing Files[Using/Adding Existing Files](#using/adding-existing-files)
├── Nodes[Nodes](#nodes)
│   ├── Files[Files](#files)
│   ├── Inline Nodes[Inline Nodes](#inline-nodes)
│   │   ├── Example Inline Node[Example Inline Node](#example-inline-node)
│   │   └── Example first level[Example first level](#example-first-level)
│   │       └── second level[second level](#second-level)
│   │           └── third level[third level](#third-level)
│   │               └── fourth level[fourth level](#fourth-level)
│   │                   └── fifth level[fifth level](#fifth-level)
│   ├── Compact Nodes[Compact Nodes](#compact-nodes)
│   │   └── Example Compact Node[Example Compact Node](#example-compact-node)
│   │       └── Example inline node within the compact node.[Example inline node within the compact node.](#example-inline-node-within-the-compact-node.)
│   └── Generating a node ID manually[Generating a node ID manually](#generating-a-node-id-manually)
├── Metadata[Metadata](#metadata)
│   ├── Syntax[Syntax](#syntax)
│   ├── Case-sensitivity[Case-sensitivity](#case-sensitivity)
│   ├── Reserved Keys[Reserved Keys](#reserved-keys)
│   │   ├── `index`[`index`](#`index`)
│   │   └── `_flags`[`_flags`](#`_flags`)
│   │       ├── `exclude_from_tree`[`exclude_from_tree`](#`exclude_from_tree`)
│   │       └── `exclude_from_export`[`exclude_from_export`](#`exclude_from_export`)
│   └── Timestamps[Timestamps](#timestamps)
│       ├── Syntax and Format[Syntax and Format](#syntax-and-format)
│       ├── Tracking Node Dates and Times[Tracking Node Dates and Times](#tracking-node-dates-and-times)
│       └── Time Zones[Time Zones](#time-zones)
├── Collection[Collection](#collection)
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
│   ├── Linking to outside resources[Linking to outside resources](#linking-to-outside-resources)
│   │   ├── Web / HTTP(S)[Web / HTTP(S)](#web-/-https)
│   │   └── Files[Files](#files)
│   ├── Pointers[Pointers](#pointers)
│   │   ├── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
│   │   ├── Duplicate Pointers[Duplicate Pointers](#duplicate-pointers)
│   │   │   └── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
│   │   └── Recursive Node Pointers[Recursive Node Pointers](#recursive-node-pointers)
│   │       ├── ! RECURSION 3:
│   │       └── Example Recursive Node Tree[Example Recursive Node Tree](#example-recursive-node-tree)
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
│       │   ├── Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lo[Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lo](#sublime-:-select-`urtext:-search`-from-the-command-pallete.-this-provides-an-input-panel-on-the-lo)
│       │   └── Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind th[Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind th](#pythonista-:-use-the-"?"-urtext-button.-results-will-be-updated-in-real-time-in-the-view-behind-th)
│       └── Search Using Dynamic Nodes[Search Using Dynamic Nodes](#search-using-dynamic-nodes)
│           └── Example Search Results[Example Search Results](#example-search-results)
├── Filenames[Filenames](#filenames)
├── Development[Development](#development)
│   └── Make Installation Easier[Make Installation Easier](#make-installation-easier)
├── File History[File History](#file-history)
└── User Interface Elements[User Interface Elements](#user-interface-elements)
    └── The Node Browser[The Node Browser](#the-node-browser)
##### Quick Start, Guides and Examples  

###### Installation and Setup (Desktop)

For desktop use (PC/Mac/Linux) Urtext is implemented in Sublime Text.

1. Download Sublime Text. (https://www.sublimetext.com/).

2. Download Urtext and all its dependencies from the monorepo at `https://github.com/nbeversl/urtext_deps`. You can either download this repository as a .ZIP file and unzip it, or if you want to maintain version control, use `git clone --recurse-submodules https://github.com/nbeversl/urtext_deps`. Put the contents of the cloned/unzipped folder (important: not the folder itself) directly into your `Sublime Text 3/Lib/python3.3` folder.

3. Download the Sublime Urtext package at `https://github.com/nbeversl/urtext_sublime`. Place it in your Packages folder (Sublime Text 3/Packages)

4. Clone/download this documentation repository and open its folder in Sublime. It will automatically be read as an Urtext project.

Once the Sublime package is installed, it will always look for any files with the .txt extension in open folders and attempt to compile them into a project. To open an existing Urtext project, open the folder, a file in the folder, or a Sublime project that includes the folder, and any feature described in this documentation will work.

To make a new project, open an empty folder and select Select `Urtext : Initialize Project` from the Sublime Command Palette. For more information, see [Projects](#projects).

See also:

[Sublime Text Interface Tips](#sublime-text-interface-tips)
[Details on the Sublime Implementation](#details-on-the-sublime-implementation)
[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)

[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)

###### Operations

Built-in operations are bound to either hotkeys or to UI menus.

Hotkeys differ among operating systems and can be reassigned according to your preference by
modifiying

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

Several outputs performed by dynamic definitions (see [Syntax](#syntax)) can also be written into "scratch" (unsaved) views for temporary use, with the intention of discarding them afterward.

(menu)	Timeline

`n`		Search:
See "SEARCH()" in [Syntax](#syntax)

(menu)	Interlinks

(menu)	Tree



Sublime Text Only:
Traverse Mode


Node Access History

###### Sublime Text Interface Tips  

Here are some tips for best leveraging Sublime's great UI features.
####### Syntax Highlighting 

This package comes with a .YML file (`sublime_urtext.sublime_syntax`) defining the Urtext syntax, along with two color schemes that provide syntax highlighting. Syntax highlighting makes everything easier by showing depth of node nesting and dimming certain elements of the syntax. Select the Sixteen (for light) or Monokai (for dark) color schemes in Preferences -> Color Scheme ... 

Then change to the Urtext syntax by selecting it in View -> Syntax -> Urtext. To avoid having to do this for every file, select View -> Syntax -> Open All with Current Extension As ... -> Urtext. (You can undo this later by repeating the same but selecting Plain Text.)
####### Hiding Tabs	

If you prefer a clean, terminal-like view, hide tabs: View -> Hide Tabs
This preference can also be set on a per-(Sublime)-project basis. See the Sublime documentation.
####### Hiding Line Numbers  

For an extra-clean look, hide line numbers by adding:

%%-JSON

"settings" : 
"line_numbers": false,
,

%%-END-JSON

... to your Sublime project settings file. (Ignore the JSON syntax pass makers above beginning with `%%`
See [Pass Markers and Embedded Syntaxes](#pass-markers-and-embedded-syntaxes) )
####### Full Screen / Distraction Free Mode  

Since you can navigate entirely from within files, Urtext works great in Sublime's Distraction Free Mode. View -> Enter Distraction Free Mode.
####### Disable Prompts for File Reload 

Urtext does a lot of writing to files on the fly, often when they are already open. To avoid seeing a dialog every time, add add the following to your Sublime project settings or User Preferences file:
%%-JSON
"settings" : 
"always_prompt_for_file_reload": false,
,
%%-END-JSON
####### Remove Indent Guides  

Formatting plaintext using tab indentions can look messy if indent guides are on. To turn them off, add to your Sublime project settings file:
%%-JSON
"settings" : 
"draw_indent_guides": false,

%%-END-JSON
####### Save on Focus Lost  

Urtext recompiles your project every time a file changes. To make this more automatic, addto your Sublime settings file:
%%-JSON
"save_on_focus_lost": true 
%%-END-JSON
####### Using a Sublime Project for an Urtext Project  

( see https://www.sublimetext.com/docs/3/projects.html )

You don't need to define a Sublime Project for the Urtext Project, but if you intend to do more than one thing at a time in Sublime, it's convenient to have one; you can then use Select Project -> Quick Switch Project (Ctrl-Super-P) to switch among them.

. 
Instead of the table of contents being drawn recursively from this node, you can see the recursion point in the table of contents.

Note that if you view the entire tree with another node selected as root, one full iteration will still appear, with the point of recursion falling elsewhere in the tree. Below is the Table of Contents with [Pointers](#pointers) as root.
#### Example Recursive Node Tree           
Pointers[Pointers](#pointers)
See [Dynamic Definitions](#dynamic-definitions) for more information on how to generate trees like this in dynamic nodes.

## Traverse ModeTraverse Mode   




This feature is currently implemented in Sublime Text only.

You can navigate a node tree or list of nodes by turning on Traverse mode (Shift-Ctrl-R). This will open another pane next to the one you are currently in. As you navigate the nodeview in the left side with the cursor or mouse, the selected node shows on the right. Use Sublime's Focus Group navigation keys, or the mouse, to switch between left and right panes.

Toggle Traverse Mode off by pressing Shift-Ctrl-R again. The status bar at the bottom of the Sublime window indicates whether Traverse is on or off. 

Note that if Traverse mode is off, you can also open a link manually (Shift-Ctrl-/) as normal. 

This feature is not built into Urtext; it is a feature of the Sublime package only.
### Word Wrap in Traverse Mode 

Since Traverse Mode splits the window into two or more panes, it is suggested to set Word Wrap Column to "Auto" in Sublime Settings. This will cause the edited views to wrap correctly no matter the screen or window/pane size, as well as in Sublime's Distraction Free Mode.

Whenever Traverse Mode is enabled on a view, word wrap for that view is turned off altogether to prevent awkward wrapping of trees. It is restored when Traverse Mode is turned off.


# Using Multiple Projects at a Time

To use multiple projects at once, there is a project context manager. When you initially pass a path to Urtext, it looks recursively in all sub folders for additional projects. If it finds a compilable Urtext project in any one, it adds these to the context manager.  You can then freely switch among projects, either explicitly, or using links between the projects (described below). When switching projects, all Urtext's features, content and behavior, including links, compiling, and all functions linked to UI buttons, will operate in the context of the selected project. 

You can put all your Urtext projects into sub folders of a single path. Alternatively, you may put them anyplace in the file system and choose as your Urtext root a folder that encompasses them all. Compiling may take longer if Urtext has to search through many unused directories. 

Using Python, it is possible to only instantiate a single project, without the context manager. The current implementations in Sublime and Pythonista, however, use the context manager by default, even if you are only using a single project.

Recall that what defines a project is a folder. This is also what separates it from other projects. If you add other Urtext project folders into the initial path, they will all be accessible from the same project list.

To switch between projects in Sublime, select Urtext: Select Project from the command palette.
In Pythonista, use "Switch Projects" from the feature menu.
## Project Naming (Identification) 

Unlike nodes, projects are uniquely identified by name. For this reason, each project must have an unique name within the running instance of Urtext. Projects can be named using the project_title key in the project's project_settings node. If no name is present, the project's name becomes its absolute path in the file system.
## Linking Between Projects 

You may also link from one project to another within the text. To so this, use the following syntax:

=>"name or path of the other project[ MISSING LINK : idj ] 
(This link is only an example and is non-functioning)

Following this link will change the project context to the named project and open its specified node.

# Converting and Exporting

Urtext can convert (export) nodes, and sets of nodes, to plaintext, Markdown and HTML. Results can be either output to a file or written back into another node within the same project. Like other dynamic functions, exporting is dynamic ; that is, when changes are made to the source nodes, exports are immediately updated, whether they are in a project node or an external file.

Exporting is not implemented in user-interface menus/buttons. Instead, export by utilizing dynamic definitions.

The export command has three components:

export : (format) : ( source_node_id )

(format) : One of `plaintext`, `markdown` or `html`
(source_id): The source node to export.
## Example : Urtext Documentation Exported in Markdown to a File  

The following dynamic definition exports this entire documentation (from its root node [Urtext  Version: 0.5-alpha  Usage Guide and References](#urtext--version:-0.5-alpha--usage-guide-and-references) ) in Markdown format to a file called documentation.md:
## Example : Fragment Exported to HTML  

The following Dynamic Definition exports the [Links and Pointers](#links-and-pointers) section of the documentation to HTML, into a node inside this one:
defined

# Search
## Full Text Search   

Fuzzy and Full Text Search are already implemented in many modern desktop text editors and some mobile text editors. However Urtext has a built-in search and index capability to avoid reliance on editors and environments.
### Searching
#### Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lo wer edge of the screen. Dynamically search results will be shown in a scratch view as you enter search terms. Press ESC to cancel.  Results include links to source nodes.
#### Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind th e search field. To exit, tap outside the search field.
### Search Using Dynamic Nodes 	

Search results can populate a dynamic node by using the key-value pair:

- search:(string)

For example, the following definition targets node[Example Search Results](#example-search-results) (below) and populates it with all nodes containing the word "urtext".
#### Example Search Results

# Filenames


Since node identities are independent of their containing filenames, you can use any naming convention you want. Urtext can also rename files automatically in convenient formats based on their title and/or index. Renaming by index is useful, for instance, if you want file-level nodes easily readable inside a file system, mobile app, or other file browser.

To rename a file, select "Rename File from Meta" from the command palette (Command-P). This will rename the file in one of the following schema:

If an index is present:

.txt

If no index is present:

.txt

This system preserves automatic numerical sorting within the filesystem, such that the most recent un-indexed nodes appear first. If you want to use another system, such as putting the title first, you can do so.

# Development
## Make Installation Easier  

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

# File History

Urtext files, being in plaintext, can be versioned using tools such as Git, Subversion, Mercurial, and others. Those tools are intended mainly for coding, when it is generally considered bad practice to commit non-working/non-compiling iterations of a project. Though Urtext files do compile, their actual text content is not a factor in this, so is reasonable to track changes at all stages of a project, even at granular levels.

Though use of powerful version control tools is not discouraged, Urtext has its own, lighter versioning system that tracks edits in the background at discrete intervals so it is not necessary to make explicit "commits" to have access to file history. Urtext creates a single, linear, nondestructive history of each file's content, with each snapshot being a "diff", or record of changes since the previous snapshot. When a previous state is restored, no "checkout" or "rewind" occurs; rather, the newly restored state is appended to the end of the history. Therefore, in addition to functioning as version control, the feature can also be used as a non-destructive "undo/redo" editing history that saves state after the file is closed.

The default interval is 10 seconds, and can be modified in project_settings. 
To access a file's timeline, use Control-Shift-G in Sublime Text. 

Histories are stored in the /history folder inside the project, as .pkl ("pickle") files. This folder requires no user involvement. If using another version control tool such as Git, you may wish to add the /history folder to your .gitignore file, so that only explicitly committed versions of your project are visible in distributed repositories.

# User Interface Elements  
## The Node Browser

Opening the Node List

Ctrl-Shift-E 






In Sublime Text there is also the alternative of using the UI dropdown. Press Control-Shift-E or select "Urtext: Node List" from the Sublime command palette (Shift-Super-P). Here you can find a node by typing part of its title.

In the Node List, nodes are sorted by their time of creation, with most recent first. They can also be sorted by index (see [`index`](#`index`)).

