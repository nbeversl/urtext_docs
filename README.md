
# About Urtext
## Description 

Urtext is a syntax and interpreter for plaintext. Urtext's basic unit is a "node", which is a range or set of ranges of text within a file. A folder of nodes is called a "project". The Urtext interpreter is aware of all the nodes in a project at once, so that nodes can reference, modify, and organize one another, across hundreds or thousands of files. The [Basic Syntax](#basic-syntax) permits embedding of structural and instructional code into the text itself. 

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

# Quick Start, Guides and Examples  

## Installation and Setup (Desktop)

For desktop use (PC/Mac/Linux) Urtext is implemented in Sublime Text.

1. Download Sublime Text. (https://www.sublimetext.com/).

2. Download Urtext and all its dependencies from the monorepo at `https://github.com/nbeversl/urtext_deps`. You can either download this repository as a .ZIP file and unzip it, or if you want to maintain version control, use `git clone --recurse-submodules https://github.com/nbeversl/urtext_deps`. Put the contents of the cloned/unzipped folder (important: not the folder itself) directly into your `Sublime Text 3/Lib/python3.3` folder.

3. Download the Sublime Urtext package at `https://github.com/nbeversl/urtext_sublime`. Place it in your Packages folder (Sublime Text 3/Packages)

4. Clone/download this documentation repository and open its folder in Sublime. It will automatically be read as an Urtext project.

Once the Sublime package is installed, it will always look for any files with the .txt extension in open folders and attempt to compile them into a project. To open an existing Urtext project, open the folder, a file in the folder, or a Sublime project that includes the folder, and any feature described in this documentation will work.

To make a new project, open an empty folder and select Select `Urtext : Initialize Project` from the Sublime Command Palette. For more information, see [Projects](#projects).

See also:

[Sublime Text Interface Tips](#sublime-text-interface-tips)

[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)
## Basic Syntax

All text is plain content unless inside a timestamp wrapper, dynamic definition wrapper, or preceded by a metadata assignment operator and keyname.

`{  }` 
Inline Node Wrappers. Can appear anywhere. Can be nested aribrarily deep.
More information: [Inline Nodes](#inline-nodes)

`>`		
Node Link. Links to the specified node by ID, like a hyperlink. 
More information: [Links](#links)

`>>`		
Node Pointer: Embeds the specified node as though it were included inline using wrappers { } (see above)
More information: [Pointers](#pointers)

`|` 
Title Pipe. Placed immediately before a node link or node pointer (whitespace is ok), dynamically populates the linked node title.
Example and more info: [Dynamic Titles](#dynamic-titles)

`^`
Compact Node marker. Must be the first non-whitespace character on a line. Must include an ID in order to parse.
More information: [Compact Nodes](#compact-nodes)

`< >`
Timestamp wrapper. Parses user-defined datetime strings, with many default formats built in.
The first character inside the brackets may not be `!`, '-', or whitespace.
Example: 
More information: [Timestamps](#timestamps)

`::`
Metadata assignment operator. Accepts a user-defined key on the left, and values and timestamps on the right.
Metadata may appear anywhere in text. They attach to their containing (parent) node but also remember their location and can serve as anchors/bookmarks to their context. Keys must be single words (underscore permitted), values may be any characters, terminated with a semicolon or newline. The pipe character (`|`) separates multiple values for a single key.
Example: 
More information: [Metadata](#metadata)
  (Closing pass marker. See above)

## Dynamic Definitions : Syntax and Parameters

Dynamic definitions contain instructions for dynamically building nodes from the contents of other nodes. They can be written anywhere; it is not necessary to store the definition in the same file to which it refers. (Note that they cannot, however, be stored in the node they target, since they would overwrite themselves.)

Dynamic definitions are wrapped using double left and right square brackets. Note that there are no restrictions on spacing, indentation, newlines, or inclusion of other arbitrary text or whitespace. Dynamic definitions ignore whitespace and arbitrary text outside of defined parameters. The order of parameters within a definition is unimportant; they are evaluated as a group.

The dynamic definition below does not actually do anything. It rather lists every parameter along with an explanation of its use and purpose. For example uses, see [Dynamic Nodes](#dynamic-nodes)

## Operations

Built-in operations are bound to either hotkeys or to UI menus.

Hotkeys differ among operating systems and can be reassigned according to your preference by
modifiying
### Project Management 

Multiple Projects
Import Project
Reload Project
Reindex All Files
Rename File(s) from Meta
Delete This Node
Initialize Project
Pop Node
Move File to Other Project
### Navigation 

`h` 	Home  `
Go to the designated home page of the project. Define the home node in [project_settings](#project_settings)

`<` 	Navigate Back
Go to the previously visited node (web-browser-like navigation)

`>` 	Navigate Forward 
Go to the next visited node (web-browser-like navigation)

`e`		Node List :
Show a quick search bar of all nodes in the current project

`*`		Global Node List:
Show a quick search bar of all nodes in all known projects.
### Insertions 

`t` 	Timestamp:
Insert a timestamp at the cursor's location, in the project's default format. For setting timestamp format defaults, see [project_settings](#project_settings)

`i` 	ID:
Insert an arbitrary (unallocated) Node ID with metadata wrapper at the cursor position.
### Editing 

`g`: 	Editing History
View the editing history for the currently viewed file.
For more informatino see [File History](#file-history)

(menu)	Consolidate Metadata
Consolidates all metadata tags in the node of the current cursor position, into a single wrapper.
### Sublime Text Only 
Traverse Mode

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

```

"settings" : {
"line_numbers": false,
},

```

... to your Sublime project settings file. (Ignore the JSON syntax pass makers above beginning with `%%`
See [Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers) )
### Full Screen / Distraction Free Mode  

Since you can navigate entirely from within files, Urtext works great in Sublime's Distraction Free Mode. View -> Enter Distraction Free Mode.
### Disable Prompts for File Reload 

Urtext does a lot of writing to files on the fly, often when they are already open. To avoid seeing a dialog every time, add add the following to your Sublime project settings or User Preferences file:
```
"settings" : {
"always_prompt_for_file_reload": false,
},
```
### Remove Indent Guides  

Formatting plaintext using tab indentions can look messy if indent guides are on. To turn them off, add to your Sublime project settings file:
```
"settings" : { 
"draw_indent _guides": false,
}
```
### Save on Focus Lost  

Urtext recompiles your project every time a file changes. To make this more automatic, addto your Sublime settings file:
```
"settings" : { 
"save_on_focus_lost": true 
}
```
### Using a Sublime Project for an Urtext Project  

( see https://www.sublimetext.com/docs/3/projects.html )

You don't need to define a Sublime Project for the Urtext Project, but if you intend to do more than one thing at a time in Sublime, it's convenient to have one; you can then use Select Project -> Quick Switch Project (Ctrl-Super-P) to switch among them.


# Reference 	
## Projects

An Urtext project is a single folder. The folder must contain at least file with an Urtext Node ID.

To make an new empty project:
- make a new folder and open the folder in Sublime Text. 
- Select Urtext : Initialize Project from the Sublime Command Palette. 
- The folder how has one Urtext file and a `history` folder for tracking edits. (See [File History](#file-history) )
### Using/Adding Existing Files 

Once a folder contains at least one file with a node ID, you can add and use existing plaintext files in the project without any modification. However for most of the benefits of Urtext you must minimally an ID ([Node IDs](#node-ids)) in each file.

To do so, select `Urtext : Import Project` from the Sublime Command palette.

Note the append will occur without a confirmation dialog, so if you are just experimenting with this system, consider making a copy of your file folder so you can revert without having to manually remove the metadata.

## Nodes

A node is region, or set of regions, of a file, up to and including the entire file. A file is itself a node. All nodes can contain other nodes.

The identity of an Urtext node persists no matter its containing filename. This is accomplished by assigning each node a unique identifier of alphanumeric characters, providing over 46,000 possible nodes per project. 

Urtext generates IDs automatically on creation of new nodes. ID's can be changed without affecting functionality, though links must then be manually updated as well. 

It is possible to use files containing no IDs in an Urtext project, but then most of the features of Urtext are lost.


Node IDs are assigned in random order and have no special meaning except as a unique identifier. For more information see [Node IDs](#node-ids).

Types of nodes:

### File Nodes

The most basic node is a single file. It may or may not contain other nodes nested inside it.

To create a new file, press `Urtext-;`. A new file is created, named and saved automatically. It has whitespace on top and a metadata block at the bottom containing a node ID and (by default) a creation timestamp.

### Inline Nodes                                                                 

The syntax for inline nodes is to wrap the content in curly braces:
#### Example Inline Node
Create an inline nodes with `Ctrl-Shift-squiggly-brace. Inside the inserted double curly braces is a new node with an auto-generated ID.   

To wrap existing content into an inline node, first select the content and use the same keypress.

Nodes can be nested arbitrarily deep inside other nodes, whether the parent node is a file or another inline node. When syntax highlighting is active, inline node wrappers are tinted to showing nesting level:
#### Example first level
##### second level
###### third level
####### fourth level
######## fifth level
![./files/node-nesting-example.png][./files/node-nesting-example.png]


Note that every opening doubly curly bracket must be closed in the same file and requires an ID between its opening and closing brackets. The examples above use [Trailing Node IDs](#trailing-node-ids). You can also use regular [Metadata](#metadata) as at the bottom of this file.

Note that nodes at the file level ([File Nodes](#file-nodes)) do not use curly-braces, as their region boundaries are defined by the file itself.

For all purposes in Urtext, inline nodes' identity is unique from their containing file, parent nodes, and child nodes.
#### Uses for inline nodes 

such as adding comments/edits, tracking anchors and pointers in documents.  
Also that the title is the first line of text.

### Compact Nodes

For text content requiring only a single line, such as list items, very short notes and similar, use the caret character (`^`) as the first non-whitesoace character on a new line. This defines a new node as a child of the node in which the ^ character appears, with the closing wrapper being the end of the same line. 

Like all nodes, a compact node requires an ID. Like all nodes, it can contain metadata and even inline nodes, as long as the entire contents, including wrappers and metadata, are contained on a single line. (Note that "line" in this case refers to consecutive characters between explicit line breaks, and not to lines in the editor, which may be arbitrarily wrapped.)
#### Example Compact Node
##### Example inline node within the compact node.

### Node Titles 

By default, the full first non-whitespace line of any node is the node's title. This can be overridden using the `title` metadata key.
### Node IDs

The purpose of Node IDs is to uniquely identify each node in a project.

Nodes IDs are three characters long and incorporate all ten digits (0 - 9) and all letters a - z, resulting in over 46,000 possible unique identifiers per project.

Node IDs are generated automatically by Urtext; every newly created node is assigned an available unused ID as a metadata entry:

<- This is not just an example; it specifies the ID of this node.

Note that the node ID entry can appear anywhere in a node. If you want to keep node ID's out of the way, such as at the end or beginning of each node, or separate from the rest of your metadata, this will not affect their functionality.
#### Trailing Node IDs  

To keep IDs even more out of sight, they can also be specified as the last three characters of a node, without a key or a double-colon syntax. Syntax highlighting will then shade them to appear unobtrusive. This convention is used throughout most of this documentation. This only works for nodes wrapped in brackets, not for compact or file nodes.

Note that trailing node IDs must be preceded by a space.  

In Sublime Text, press Ctrl-Shift-P to create a new inline node using this convention.
IDs have no special meaning, do not represent the order of node creation within a project, and are not related to or "hashed from" node content. They are assigned in random order so the probability of accidentally creating two nodes with the same ID is minimal when using the project across many devices that may not always be in sync.

When an ID is deleted from a project, new nodes are later assigned to vacant node IDs.
#### Inserting a Node ID manually 

Control-Shift-I will insert a new and unused node anywhere in the project, in case you delete one or want to insert one manually.
Node IDs can also be user-created arbitrarily if for some reason you want to. If you do this, note that node IDs are case-insensitive.

If more than one Node ID appears in a node, only the first one is used as the Node's ID; the rest are treated (indexed) as regular metadata.
#### Duplicate Node IDs 	

If two nodes end up with the same ID, only one (the first one found) will be assigned the ID. The entire second file containing the node with the duplicate ID will contain a warning message. See [Errors and Warnings](#errors-and-warnings)

To correct the problem, it is necessary to manually change the duplicate ID to a new one. To ensure the corrected node ID is unique, it is recommended to use control-shift-I for this (as described above), after the rest of the project is compiled.
#### Generating a node ID manually 
If you accidentally delete a Node ID or need to insert one arbitrarily, press Urtext-i.



## Metadata
### General Syntax 

Every node can have an unlimited number of metadata entries. Metadata is structured in double-colon-separated key/value pairs, with the value (to the right of the colon) containing an optional timestamp. Examples:




Metadata gets indexed and becomes searchable and sortable from anywhere within the project. Metadata entries also "remember" their location, allowing them to serve as contextual markers or "bookmarks". 

Other than a few reserved key/value pairs, metadata is user-defined. Keys must be single words, though characters such as dash and underscore are allowed. Values may include spaces. Terminate metadata entries using either a new line or a semicolon. Using the semicolon option, several entries may be strung together on a single line:



Note that a timestamp anywhere in the value will be indexed as the timestamp for the whole metadata entry. If more than on timestamp appears in an entry, only the first one is indexed.
### Timestamps
#### Syntax and Format   

Text between two angled brackets (<  >) is parsed as a timestamp whenever the first character inside the brackets is not `!`, `-` or whitespace. To insert the current date and time anywhere, press Control-Shift-t: 

Timestamps are read and written utilizing Python's `strftime` directives. The following formats are included by default:

``` # (<- for info about this marker see [Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers) )

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

``` 

Additional formats can be added in the [project_settings](#project_settings) node.
Node timestamps are part of metadata (see [Metadata](#metadata)). 
Urtext also utilizes a "loose" parsing of inline timestamps, meaning they can be placed anywhere and will be recognized and parsed.
#### Tracking Node Dates and Times    

Reliance on the operating system's "created" or "modified" date metadata is avoided, since these values can be inadvertently overwritten during ordinary file system operations. Instead, new nodes receive by default a "timestamp" metadata key when created:
#### Time Zones 	  

Time zones are not required. If no time zone is present, Coordinated Universal Time (UTC) is added by default  for parsing and comparison purposes. To modify this default, set the `timezone` key in [project_settings](#project_settings) to another valid value.
### Case-sensitivity  

-   Values are not case-sensitive, except those with the following keys:

`title`             Manually overrides the node's title. 

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
You can give the same index number to multiple nodes; in this case they sort first by index, then by timestamp, newest first.

Unindexed nodes will display underneath indexed nodes, by timestamp, newest first.
#### `title` 

Provides a way to override the node title, which is by default the full first non-whitespace line.



## Dynamic Nodes

Dynamic nodes contain content built from the contents of other nodes. Dynamic content stays up to date with its source content at all times. 


Ctrl-Shift-] creates a new dynamic definition in Sublime.

In Pythonista or other editors, create them manually.


In Sublime this will be auto-populated using the shortcut above; however you can also replace it with the ID of another node. For example, if you want the contents to replace an existing node, assign this key the value of that node's ID. If you want it to populate new inline node, create that node and then copy/paste its ID. 



Dynamic are the same as any other node, except that their content is generated automatically from a Dynamic Definition. Dynamic Definitions are surrounded with double square brackets , with complete parameters and syntax listed here : [Dynamic Definitions : Syntax and Parameters](#dynamic-definitions-:-syntax-and-parameters). This section illustrates more generally the use and purpose of dynamic nodes, with examples.

Dynamic Definitions can be written anywhere; it is not necessary to store the definition in the same file to which it refers. (Note that they cannot, however, be stored in the node they target, since they would overwrite themselves.)

There are two main kinds of dynamic output: lists and collections: "Lists" are exactly that: lists of nodes, with each node displayed not more than once once. Lists can optionally expand into trees, showing the hierarchy of nested relationships from each root node in the list. Collections, on the other hand, show metadata entries with their context; the same node may appear many times in a colelction if it contains many metadata entries matching the queried parameters.

### Lists
####                 [](#)[: -->](#:--->)
== Current Projects ==[== Current Projects ==](#==-current-projects-==)
=== Reminders ===[=== Reminders ===](#===-reminders-===)
About Compact Nodes[About Compact Nodes](#about-compact-nodes)
About Urtext[About Urtext](#about-urtext)
Basic Syntax[Basic Syntax](#basic-syntax)
Case-sensitivity[Case-sensitivity](#case-sensitivity)
Collections[Collections](#collections)
Compact Nodes[Compact Nodes](#compact-nodes)
Compact Nodes[Compact Nodes](#compact-nodes)
Comparison To Other Tools[Comparison To Other Tools](#comparison-to-other-tools)
Dependencies and Installation[Dependencies and Installation](#dependencies-and-installation)
Description[Description](#description)
Details on the Sublime Implementation[Details on the Sublime Implementation](#details-on-the-sublime-implementation)
Disable Prompts for File Reload[Disable Prompts for File Reload](#disable-prompts-for-file-reload)
Documentation[Documentation](#documentation)
Download Dependencies from a Monorepo[Download Dependencies from a Monorepo](#download-dependencies-from-a-monorepo)
Download and Install Dependencies Manually[Download and Install Dependencies Manually](#download-and-install-dependencies-manually)
Duplicate Node IDs[Duplicate Node IDs](#duplicate-node-ids)
Note that the at the bottom of the node is the reserved key `def` which refers to the node containing the definition.
#### : -->                [](#)

-
: -->[](#)

-
== Current Projects ==: -->[== Current Projects ==](#==-current-projects-==)

-
=== Reminders ===: -->[=== Reminders ===](#===-reminders-===)

-
About Compact Nodes: -->[About Compact Nodes](#about-compact-nodes)

-
[Links](#links) or using [Traverse Mode](#traverse-mode).


Urtext will parse node timestamps along with inline timestamps into a project timeline. Press Ctrl-Shift-T or select Urtext: Show Timeline in the Sublime command palette. Each node and inline timestamp is shown in chronological order with nearby text. You can try it with this example project, but note that since many nodes in this document are undated, they have a default date of Thu., Jan. 01, 1970, 12:00AM.

As everywhere in a project, node IDs shown are links that can be opened using Ctrl-Shift-/.



You can extend node trees beyond the file level by using [Pointers](#pointers).

Thanks to the `anytree` module (https://pypi.org/project/anytree/) for the plaintext node tree diagrams.

### Collections

Collections are for "collecting" metadata entries, along with their context, in order to gain a range of views into the text content of a project. A common use for this would be to create a timeline from datetimestamps. Another use would be to collect all metadata entries of a given key, and optionally a given value, into a single view.
#### Example Collection 
id :: 001[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer):40 
Example Child Node Using a Node Pointer


id :: 002[Full Screen / Distraction Free Mode](#full-screen-/-distraction-free-mode):186 
Since you can navigate entirely from within files, Urtext works great in Sublime's Distraction Free Mode. View -> Enter Distraction Free Mode


id :: 003[Sublime Text Interface Tips](#sublime-text-interface-tips):137 
Here are some tips for best leveraging Sublime's great UI features.


id :: 004[Inline Nodes](#inline-nodes):1222 
For all purposes in Urtext, inline nodes' identity is unique from their containing file, parent nodes, and child nodes.


id :: 005[Timestamps](#timestamps):319 
Urtext also utilizes a "loose" parsing of inline timestamps, meaning they can be placed anywhere and will be recognized and parsed.


id :: 006[Requirements and Features](#requirements-and-features):2333 
- Version control (Git, for example).


id :: 00c[Home Node](#home-node):146 
The Home page is accessible anywhere in the project by pressing Ctrl-Shift-H. Specify the node ID you want this shortcut to jump to.


id :: 00e[Example Inline Node](#example-inline-node):22 
Example Inline Node


id :: 00i[Filename formats](#filename-formats):19 
Filename formats


id :: 00j[Links and Pointers](#links-and-pointers):87 
[Pointers](#pointers)


id :: 00k[Collections](#collections):361 
Collections are for "collecting" metadata entries, along with their context, in order to gain a range of views into the text content of a project. A common use for this would be to create a timeline from datetimestamps. Another use would be to collect all metadata entries of a given key, and optionally a given value, into a single view.


id :: 00l[project_settings](#project_settings):376 
This node now has special reserved metadata keys that will be parsed as follows:


id :: 00m[Sublime Text tools to help with linking](#sublime-text-tools-to-help-with-linking):653 
Links TO the current node FROM another node. When you select this command, a link to the current node will be copied to the clipboard. You can then paste the reference into the node you open in the quick panel.


id :: 00n[Timestamp Formats](#timestamp-formats):284 
Changing the default node_date_timestamp name and bevahior


id :: 00o[Web / HTTP(S)](#web-/-https):222 
Example: pressing Ctrl/Command-Shift-/ on this line below will open the link: http://github.com


id :: 00p[Files](#files):170 
Example:   ![./README.md][./README.md]


id :: 00q[Linking to outside resources](#linking-to-outside-resources):136 
Linking to outside resources


id :: 00t[Duplicate Pointers](#duplicate-pointers):286 
Here is the same example child node from above: [Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)


id :: 00u[Viewing Linked Relationships](#viewing-linked-relationships):1004 
These diagrams are displayed as Sublime "scratch" views, meaning they will never report as being dirty (unsaved). They are intended for one-time/temporary use and will not update when a node/file changes. To make permanent and dynamically updated diagrams, see [ MISSING LINK : e82 ] .


id :: 00v[Example Source Node 2](#example-source-node-2):66 
Example Source Node 2


id :: 00w[Traverse Mode](#traverse-mode):17 
This feature is currently implemented in Sublime Text only.


id :: 00x[Metadata](#metadata):25 
Metadata


id :: 00z[`index`](#`index`):489 
Unindexed nodes will display underneath indexed nodes, by timestamp, newest firs


id :: 013[About Urtext](#about-urtext):118 
About Urtext


id :: 014[In-Progress / Experimental / Wish List](#in-progress-/-experimental-/-wish-list):110 
Import/Export to/from: Markdown, HTML, pure plain text, JSON


id :: 015[Hiding Tabs](#hiding-tabs):190 
This preference can also be set on a per-(Sublime)-project basis. See the Sublime documentation


id :: 017[Example Source Node 1](#example-source-node-1):33 
Example Source Node 1


id :: 018[Reference: Key Bindings](#reference:-key-bindings):666 
ctrl+shift+-            Align selected lines to the right (120 character width)


id :: 01b[Example Source Node 3](#example-source-node-3):35 
Example Source Node 3


id :: 01c[Example Source Node 4](#example-source-node-4):35 
Example Source Node 4


id :: 01d[Syntax Highlighting](#syntax-highlighting):683 
Then change to the Urtext syntax by selecting it in View -> Syntax -> Urtext. To avoid having to do this for every file, select View -> Syntax -> Open All with Current Extension As ... -> Urtext. (You can undo this later by repeating the same but selecting Plain Text.


id :: 01e[Hiding Line Numbers](#hiding-line-numbers):337 
See [Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers)


id :: 01i[The Node Browser](#the-node-browser):626 
In the Node List, nodes are sorted by their time of creation, with most recent first. They can also be sorted by index (see [`index`](#`index`)).


id :: 01j[Nodes](#nodes):908 
[Node IDs](#node-ids)


id :: 01m[Filenames](#filenames):915 
This system preserves automatic numerical sorting within the filesystem, such that the most recent un-indexed nodes appear first. If you want to use another system, such as putting the title first, you can do so.


id :: 01n[Example Recursive Node Tree](#example-recursive-node-tree):93 
Pointers[Pointers](#pointers)


id :: 01q[Node IDs](#node-ids):379 
<- This is not just an example; it specifies the ID of this node.


id :: 01r[Example 1 : List](#example-1-:-list):724 
Here is the compiled node defined by the definition above. Changing the dynamic definition and/or the contents or metadata of the source nodes will update the dynamic node. Saving is necessary to trigger the update.


id :: 01u[Details on the Sublime Implementation](#details-on-the-sublime-implementation):958 
Some features in this documentation are built into the Urtext interpreter/compiler, while others are part of only the Sublime Text implementation. Features that are specific to Sublime are tagged with the keyword `sublime`.


id :: 01w[Opening Links](#opening-links):177 
Note that Urtext reads node regions on every save, so cursor location may be imprecise if the file has been altered since the last save.


id :: 01x[Projects, Structure and Compiling](#projects,-structure-and-compiling):614 [project_settings](#project_settings)


id :: 01y[iPhone/iPad/iOS](#iphone/ipad/ios):1567 
Syncing manually comes with the drawback that changes made on the iOS device will not themselves sync to Dropbox in the background. For instance, if changes are made to a file on iOS while not connected to the internet and Pythonista, the project will have to be explictly synced at a later time. So there remains the possibility that projects will get out of sync.


id :: 01z[Synchronator Setup](#synchronator-setup):50 
DOCUMENTATION COMING


id :: 023[Disable Prompts for File Reload](#disable-prompts-for-file-reload):346 
Urtext does a lot of writing to files on the fly, often when they are already open. To avoid seeing a dialog every time, add add the following to your Sublime project settings or User Preferences file:


id :: 029[Example 2 : Tree](#example-2-:-tree):324 
For more information on trees, see [ MISSING LINK : 00h ] 


id :: 02o[Home](#home):97 
[ MISSING LINK : jxp ] 


id :: 04s[Inserting a Node ID manually](#inserting-a-node-id-manually):163 
Control-Shift-I will insert a new and unused node anywhere in the project, in case you delete one or want to insert one manually


id :: 0l2[=== Reminders ===](#===-reminders-===):31 
=== Reminders ===


id :: 0y2[Links](#links):255 
To make a "hyperlink" from one node to another, use the right angle bracket (>) followed immediately by a node ID. Linking does not require a filename or any other information, only the node ID. Any other surrounding text is ignored.


id :: 1rc[Remove Indent Guides](#remove-indent-guides):257 
Formatting plaintext using tab indentions can look messy if indent guides are on. To turn them off, add to your Sublime project settings file:


id :: 2a3[Trailing Node IDs](#trailing-node-ids):69 
Trailing Node IDs


id :: 2fn[Dependencies and Installation](#dependencies-and-installation):860 
Close and reopen Sublime Text. Urtext is now ready to use.


id :: 3n6[User Interface Elements](#user-interface-elements):189 
[Traverse Mode](#traverse-mode)


id :: 3x3[Example Search Results](#example-search-results):70 



id :: 3xv[Sublime Text Only](#sublime-text-only):37 
Traverse Mode


id :: 4p9[Full Text Search](#full-text-search):271 
Fuzzy and Full Text Search are already implemented in many modern desktop text editors and some mobile text editors. However Urtext has a built-in search and index capability to avoid reliance on editors and environments.


id :: 4vu[Dynamic Titles](#dynamic-titles):314 
Titled links are updated at the single file level whenever that file is saved.


id :: 5pq[fifth level](#fifth-level):37 
fifth level


id :: 6cd[Installation and Setup (Desktop)](#installation-and-setup-desktop):1442 
[Sublime Text Interface Tips](#sublime-text-interface-tips)


id :: 6ct[Recursive Node Pointers](#recursive-node-pointers):1050 
See [Dynamic Definitions : Syntax and Parameters](#dynamic-definitions-:-syntax-and-parameters) for more information on how to generate trees like this in dynamic nodes.


id :: 6qj[third level](#third-level):43 
third level


id :: 774[Download and Install Dependencies Manually](#download-and-install-dependencies-manually):1227 
https://pypi.org/project/diff-match-patch/


id :: 7lx[Linking Between Projects](#linking-between-projects):341 
Following this link will change the project context to the named project and open its specified node.


id :: 7w6[Time Zones](#time-zones):266 
Time zones are not required. If no time zone is present, Coordinated Universal Time (UTC) is added by default  for parsing and comparison purposes. To modify this default, set the `timezone` key in [project_settings](#project_settings) to another valid value


id :: 80d[fourth level](#fourth-level):54 
fourth level


id :: 87g[Dynamic Definitions : Syntax and Parameters](#dynamic-definitions-:-syntax-and-parameters):942 
The dynamic definition below does not actually do anything. It rather lists every parameter along with an explanation of its use and purpose. For example uses, see [Dynamic Nodes](#dynamic-nodes)


id :: 8dw[General Syntax](#general-syntax):1181 
Note that a timestamp anywhere in the value will be indexed as the timestamp for the whole metadata entry. If more than on timestamp appears in an entry, only the first one is indexe


id :: 8e5[The symbol below is a Pass Marker, which tells Urtext to skip everything between it and the closing](#the-symbol-below-is-a-pass-marker,-which-tells-urtext-to-skip-everything-between-it-and-the-closing):399 
The symbol below is a Pass Marker, which tells Urtext to skip everything between it and the closing "END" marker. Use for embedding other syntaxes or to otherwise ignore syntax entirely. Here it enables us to document the Urtext syntax without actually using it correctly within this node. More information: | Embedded Syntaxes and Pass Markers >oy


id :: 8fv[second level](#second-level):37 
second level


id :: 9u0[Project Management](#project-management):197 
Move File to Other Project


id :: 9up[Example inline node within the compact node.](#example-inline-node-within-the-compact-node.):47 
Example inline node within the compact node.


id :: a5m[Urtext  Version: 0.5-alpha  Usage Guide and References](#urtext--version:-0.5-alpha--usage-guide-and-references):684 
- Control-Shift-h at any time to return to this "home" node.


id :: ac5[Reference](#reference):330 
| User Interface Elements >3


id :: arl[Download Dependencies from a Monorepo](#download-dependencies-from-a-monorepo):610 
Put the contents of the cloned/unzipped folder (important: not the folder itself) directly into your `Sublime Text 3/Lib/python3.3` folder.


id :: baq[Example : Fragment Exported to HTML](#example-:-fragment-exported-to-html):181 
defined


id :: bpk[Errors and Warnings](#errors-and-warnings):22 
Errors and Warnings


id :: bzv[Duplicate Node IDs](#duplicate-node-ids):497 
To correct the problem, it is necessary to manually change the duplicate ID to a new one. To ensure the corrected node ID is unique, it is recommended to use control-shift-I for this (as described above), after the rest of the project is compiled.


id :: c1x[: -->](#:--->):319 
-


id :: c3n[Using a Sublime Project for an Urtext Project](#using-a-sublime-project-for-an-urtext-project):376 
You don't need to define a Sublime Project for the Urtext Project, but if you intend to do more than one thing at a time in Sublime, it's convenient to have one; you can then use Select Project -> Quick Switch Project (Ctrl-Super-P) to switch among them.


id :: d7b[Example Compact Node](#example-compact-node):22 
Example Compact Node


id :: dce[Projects](#projects):386 
- The folder how has one Urtext file and a `history` folder for tracking edits. (See [File History](#file-history) )


id :: e1x[Operations](#operations):197 
modifiying


id :: e5j[Table of Contents](#table-of-contents):3095 
 └── Word Wrap in Traverse Mode[Word Wrap in Traverse Mode](#word-wrap-in-traverse-mode)


id :: eea[Python](#python):909 
Pass the current line contents and cursor position (within the line) to the UrtextProject. The method returns the best link match. Find the filename as described in[ MISSING LINK : h8c ]  and open it at the start_position returned from get_link(). See the open_urtext_node() function in the Sublime Text package for an example.


id :: ekz[File Nodes](#file-nodes):322 
To create a new file, press `Urtext-;`. A new file is created, named and saved automatically. It has whitespace on top and a metadata block at the bottom containing a node ID and (by default) a creation timestamp.


id :: ezg[Exporting](#exporting):721 
(source_id): The source node to export.


id :: fo2[Reserved Keys](#reserved-keys):115 
There are two reserved keys that Urtext interprets in a special way:


id :: frm[require an ID](#require-an-id):16 
require an ID


id :: h8z[Comparison To Other Tools](#comparison-to-other-tools):720 
Urtext consolidates content, structure and instructions (scripting) into a single compilable syntax. Although it can link documents or parts of documents together, unlike HTML, there is no additional code or markup "behind" the visible syntax. Everything the interpreter reads is visible to the user at all time


id :: hg7[Syntax and Format](#syntax-and-format):1434 
Additional formats can be added in the [project_settings](#project_settings) node


id :: hiz[become child nodes of their containing node.](#become-child-nodes-of-their-containing-node.):46 
become child nodes of their containing node.


id :: ia5[Uses for inline nodes](#uses-for-inline-nodes):176 
Also that the title is the first line of text.


id :: ipy[Using Multiple Projects at a Time](#using-multiple-projects-at-a-time):1522 
In Pythonista, use "Switch Projects" from the feature menu.


id :: iy8[Pythonista](#pythonista):124 
Use the `/` key when the cursor is on any line containing a link.


id :: j6t[Compact Nodes](#compact-nodes):313 
For nodes that can fit on a single line, such as items in a list, short phrases, word definitions, and so on, you can use a simplified node syntax. Begin the line with the caret symbol (^); the closing wrapper then becomes the next newline (the end of the same line). Like other nodes:


id :: k67[Search](#search):18 
Search


id :: k8p[Dynamic Nodes](#dynamic-nodes):1709 
[Collections](#collections)


id :: k8v[Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lo](#sublime-:-select-`urtext:-search`-from-the-command-pallete.-this-provides-an-input-panel-on-the-lo):272 
Sublime : select `Urtext: Search` from the command pallete. This provides an input panel on the lower edge of the screen. Dynamically search results will be shown in a scratch view as you enter search terms. Press ESC to cancel.  Results include links to source nodes.


id :: kpz[Compact Nodes](#compact-nodes):706 
Like all nodes, a compact node requires an ID. Like all nodes, it can contain metadata and even inline nodes, as long as the entire contents, including wrappers and metadata, are contained on a single line. (Note that "line" in this case refers to consecutive characters between explicit line breaks, and not to lines in the editor, which may be arbitrarily wrapped.)


id :: l36[Case-sensitivity](#case-sensitivity):404 
`timestamp_format`


id :: l60[Plaintext](#plaintext):95 
Plaintext


id :: lhs[Uses](#uses):448 
- any other writing or information management that can be done in text form


id :: ljr[Python](#python):86 
Python


id :: lmu[Pointers](#pointers):911 
- The tree can be displayed from any arbitrary starting point, whether or not its branches are within or beyond a particular file.


id :: lwg[User-Defined](#user-defined):19 
User-Defined


id :: m1r[](#):839 
Duplicate Node IDs[Duplicate Node IDs](#duplicate-node-ids)


id :: m58[Tracking Node Dates and Times](#tracking-node-dates-and-times):407 
Reliance on the operating system's "created" or "modified" date metadata is avoided, since these values can be inadvertently overwritten during ordinary file system operations. Instead, new nodes receive by default a "timestamp" metadata key when created:


id :: m9d[Example : Urtext Documentation Exported in Markdown to a File](#example-:-urtext-documentation-exported-in-markdown-to-a-file):282 
The following dynamic definition exports this entire documentation (from its root node [Urtext  Version: 0.5-alpha  Usage Guide and References](#urtext--version:-0.5-alpha--usage-guide-and-references) ) in Markdown format to a file called documentation.md:


id :: njo[JSON](#json):89 
JSON


id :: omh[Navigation](#navigation):472 
Show a quick search bar of all nodes in all known projects.


id :: ooe[Documentation](#documentation):295 
Documentation


id :: os4[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista):1193 
- (optional) To enabling launching or switching to Urtext using an app icon, use the Shortcuts app.


id :: osu[Sublime](#sublime):224 
Press Shift-Ctrl-/ on a line containing a link to open the node with the linked ID. If the link is to an inline node, Sublime will scroll to and center its starting point.


id :: oy5[Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers):228 
Note that no text content wrapped between pass markers will appear in Urtext dynamic output, since characters in other syntaxes would have unpredictable interactions.


id :: prp[File History](#file-history):1680 
Histories are stored in the /history folder inside the project, as .pkl ("pickle") files. This folder requires no user involvement. If using another version control tool such as Git, you may wish to add the /history folder to your .gitignore file, so that only explicitly committed versions of your project are visible in distributed repositories.


id :: pz3[`title`](#`title`):119 
Provides a way to override the node title, which is by default the full first non-whitespace 


id :: q8j[Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind th](#pythonista-:-use-the-"?"-urtext-button.-results-will-be-updated-in-real-time-in-the-view-behind-th):162 
Pythonista : Use the "?" Urtext Button. Results will be updated in real time in the view behind the search field. To exit, tap outside the search field.


id :: qjl[Dynamic Nodes - OLD](#dynamic-nodes---old):21 
Note that in order to work, the target node must exist; dynamic definitions do not create their target nodes.


id :: rfp[Generating a node ID manually](#generating-a-node-id-manually):122 
If you accidentally delete a Node ID or need to insert one arbitrarily, press Urtext-i.


id :: ri9[Dynamic Nodes - OLD](#dynamic-nodes---old):169 
Note that in order to work, the target node must exist; dynamic definitions do not create their target nodes.


id :: rij[Using/Adding Existing Files](#using/adding-existing-files):579 
Note the append will occur without a confirmation dialog, so if you are just experimenting with this system, consider making a copy of your file folder so you can revert without having to manually remove the metadata.


id :: rr3[Searching](#searching):25 
Searching


id :: sqq[Save on Focus Lost](#save-on-focus-lost):232 
Urtext recompiles your project every time a file changes. To make this more automatic, addto your Sublime settings file:


id :: tgp[Project Naming (Identification)](#project-naming-identification):364 
Unlike nodes, projects are uniquely identified by name. For this reason, each project must have an unique name within the running instance of Urtext. Projects can be named using the project_title key in the project's project_settings node. If no name is present, the project's name becomes its absolute path in the file system.


id :: ttt[This node is just here as a destination from the node pointer in  Syntax Quick-Reference](#this-node-is-just-here-as-a-destination-from-the-node-pointer-in--syntax-quick-reference):198 
Note it has the `exclude_from_tree` flag, which prevents it from showing up in the table of contents.


id :: twz[Lists](#lists):893 
Thanks to the `anytree` module (https://pypi.org/project/anytree/) for the plaintext node tree diagrams.


id :: ucj[About Compact Nodes](#about-compact-nodes):199 
 └── About Compact Nodes[About Compact Nodes](#about-compact-nodes)


id :: ue2[Node Titles](#node-titles):150 
By default, the full first non-whitespace line of any node is the node's title. This can be overridden using the `title` metadata ke


id :: uh9[TARGET( node or filename ) (recognized by pattern)](#target-node-or-filename--recognized-by-pattern):249 
LIMIT()


id :: uy4[Search Using Dynamic Nodes](#search-using-dynamic-nodes):299 
For example, the following definition targets node[Example Search Results](#example-search-results) (below) and populates it with all nodes containing the word "urtext".


id :: vze[== Current Projects ==](#==-current-projects-==):45 
== Current Projects ==


id :: wjj[Insertions](#insertions):283 
Insert an arbitrary (unallocated) Node ID with metadata wrapper at the cursor position.


id :: x0c[Other dynamic instructions](#other-dynamic-instructions):119 
Some dynamic instructions do things other than populate or modify contents of nodes.


id :: xba[Editing](#editing):276 
Consolidates all metadata tags in the node of the current cursor position, into a single wrapper.


id :: xci[Word Wrap in Traverse Mode](#word-wrap-in-traverse-mode):506 
Whenever Traverse Mode is enabled on a view, word wrap for that view is turned off altogether to prevent awkward wrapping of trees. It is restored when Traverse Mode is turned off.


id :: xlc[can have arbitrary other metadata](#can-have-arbitrary-other-metadata):35 
can have arbitrary other metadata


id :: xo9[Trailing Node IDs](#trailing-node-ids):520 
In Sublime Text, press Ctrl-Shift-P to create a new inline node using this conventio


id :: xor[Python](#python):426 
Python


id :: xsh[HTML](#html):83 
HTML


id :: xxx[](#):3908 
third level[third level](#third-level)


id :: y9t[Example first level](#example-first-level):38 
Example first level


id :: yin[tag_all](#tag_all):669 
Note that metadata tags do not actually get added to the inline text of the the children/descendants as a result of this instruction, only that they acquire the specified key/value metadata pair for all purposes metadata serves within Urtext.


id :: yv2[Description](#description):997 
Urtext has no built-in user interface; it only compiles and manages the files. Using Urtext in a text editor requires an additional wrapper to pass messages between the text editor and Urtext. Currently there is a package for Sublime Text (Mac/Windows/Linux) and a script for Pythonista (iOS).


id :: z7t[Quick Start, Guides and Examples](#quick-start,-guides-and-examples):248 
| Sublime Text Interface Tips >0


id :: znj[Basic Syntax](#basic-syntax):1809 
(Closing pass marker. See above)



## Links and Pointers
### Links   

To make a "hyperlink" from one node to another, use the right angle bracket (>) followed immediately by a node ID. Linking does not require a filename or any other information, only the node ID. Any other surrounding text is ignored.
#### Sublime Text tools to help with linking   


Two Sublime Command Palette commands can make linking quick and easy:

Urtext : Link To ...
Links from the currently viewed node to another node which you can select in the selection panel. When you select a node in the quick panel, a link to that node will be inserted at the cursor.

Urtext: Link From ...
Links TO the current node FROM another node. When you select this command, a link to the current node will be copied to the clipboard. You can then paste the reference into the node you open in the quick panel.
### Dynamic Titles  

Prepending a pipe character to any node link will populate the space between the pipe and link with the node's title, from its metadata or default title. Examples are found throughout this documentation. 

Titled links are updated at the single file level whenever that file is saved.
### Opening Links
#### Sublime 

Press Shift-Ctrl-/ on a line containing a link to open the node with the linked ID. If the link is to an inline node, Sublime will scroll to and center its starting point.
#### Pythonista  

Use the `/` key when the cursor is on any line containing a link.
Note that Urtext reads node regions on every save, so cursor location may be imprecise if the file has been altered since the last save.
### Linking to outside resources
#### Web / HTTP(S) 

HTTP(S) links are recognized automatically and will open in the default browser.    
Example: pressing Ctrl/Command-Shift-/ on this line below will open the link: http://github.com
#### Files 

Links to files can be made by writing ![ , followed immediately with a file path relative to the folder of the project:][ , followed immediately with a file path relative to the folder of the project:]
Example:   ![./README.md][./README.md]

### Pointers          

By preceding a link to a node with two right angle brackets instead of one, you can extend trees beyond the file level to create node relationships spanning many files. In addition to being a hyperlink, this connects the targeted node, and all of its subchildren, as descendants of the node containing the Pointer:

##### Example Child Node Using a Node Pointer
 

The example Pointer above becomes a child of this node, visible in the [Table of Contents](#table-of-contents) or using the other tree views described in [ MISSING LINK : 00h ] .

The advantages to Node Pointers are many, including:

- The tree represents a hierachy of actual content, rather than the files containing the content.

- The tree permits nesting both within and beyond file level.

- The tree can be displayed from any arbitrary starting point, whether or not its branches are within or beyond a particular file.
#### Duplicate Pointers  

Node Pointers may point more than once to the same node, so that content can be reused or referenced across multiple trees within the same project:

Here is the same example child node from above: 
#### Recursive Node Pointers  

If the tree of a Node Pointer includes to one of its own ancestors, the recursion will not be drawn again if it is already contained in the tree. Instead, the point of recursion will incidate "RECURSION", with a link to the Node ID of the node causing the recursion.

For example, this Node Pointer points back to the root node of the table of contents: 
##### Urtext  Version: 0.5-alpha  Usage Guide and ReferencesUrtext | Version: 0.5-alpha | Usage Guide and References
License: GNU General Public License 3.0

This is a documentation of Urtext, written in Urtext. If you're reading this as a `README.MD` (on Github, etc.), this file was generated from the text files in this repository. The repository is an Urtext project. Clone or download it to use it as both a reference and an example project. If you are reading this in an Urtext implementation, such as in Sublime Text, you can navigate the project directly. Most of the key commands utilize Control-Shift as the modifier. 
- Control-Shift-/ to follow any link
- Control-Shift-h at any time to return to this "home" node.
###### Table of Contents About Urtext[About Urtext](#about-urtext)
├── Description[Description](#description)
├── Comparison To Other Tools[Comparison To Other Tools](#comparison-to-other-tools)
├── Uses[Uses](#uses)
└── Requirements and Features[Requirements and Features](#requirements-and-features)
Quick Start, Guides and Examples[Quick Start, Guides and Examples](#quick-start,-guides-and-examples)
├── Installation and Setup (Desktop)[Installation and Setup (Desktop)](#installation-and-setup-desktop)
├── Basic Syntax[Basic Syntax](#basic-syntax)
├── Dynamic Definitions : Syntax and Parameters[Dynamic Definitions : Syntax and Parameters](#dynamic-definitions-:-syntax-and-parameters)
├── Operations[Operations](#operations)
│   ├── Project Management[Project Management](#project-management)
│   ├── Navigation[Navigation](#navigation)
│   ├── Insertions[Insertions](#insertions)
│   ├── Editing[Editing](#editing)
│   └── Sublime Text Only[Sublime Text Only](#sublime-text-only)
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
├── Projects[Projects](#projects)
│   └── Using/Adding Existing Files[Using/Adding Existing Files](#using/adding-existing-files)
├── Nodes[Nodes](#nodes)
│   ├── File Nodes[File Nodes](#file-nodes)
│   ├── Inline Nodes[Inline Nodes](#inline-nodes)
│   │   ├── Example Inline Node[Example Inline Node](#example-inline-node)
│   │   ├── Example first level[Example first level](#example-first-level)
│   │   │   └── second level[second level](#second-level)
│   │   │       └── third level[third level](#third-level)
│   │   │           └── fourth level[fourth level](#fourth-level)
│   │   │               └── fifth level[fifth level](#fifth-level)
│   │   └── Uses for inline nodes[Uses for inline nodes](#uses-for-inline-nodes)
│   ├── Compact Nodes[Compact Nodes](#compact-nodes)
│   │   └── Example Compact Node[Example Compact Node](#example-compact-node)
│   │       └── Example inline node within the compact node.[Example inline node within the compact node.](#example-inline-node-within-the-compact-node.)
│   ├── Node Titles[Node Titles](#node-titles)
│   └── Node IDs[Node IDs](#node-ids)
│       ├── Trailing Node IDs[Trailing Node IDs](#trailing-node-ids)
│       ├── Inserting a Node ID manually[Inserting a Node ID manually](#inserting-a-node-id-manually)
│       ├── Duplicate Node IDs[Duplicate Node IDs](#duplicate-node-ids)
│       └── Generating a node ID manually[Generating a node ID manually](#generating-a-node-id-manually)
├── Metadata[Metadata](#metadata)
│   ├── General Syntax[General Syntax](#general-syntax)
│   ├── Timestamps[Timestamps](#timestamps)
│   │   ├── Syntax and Format[Syntax and Format](#syntax-and-format)
│   │   ├── Tracking Node Dates and Times[Tracking Node Dates and Times](#tracking-node-dates-and-times)
│   │   └── Time Zones[Time Zones](#time-zones)
│   ├── Case-sensitivity[Case-sensitivity](#case-sensitivity)
│   └── Reserved Keys[Reserved Keys](#reserved-keys)
│       ├── `index`[`index`](#`index`)
│       └── `title`[`title`](#`title`)
├── Dynamic Nodes[Dynamic Nodes](#dynamic-nodes)
│   ├── Lists[Lists](#lists)
│   │   ├── [](#)
│   │   └── : -->[: -->](#:--->)
│   └── Collections[Collections](#collections)
│       └── Example Collection[Example Collection](#example-collection)
├── Links and Pointers[Links and Pointers](#links-and-pointers)
│   ├── Links[Links](#links)
│   │   └── Sublime Text tools to help with linking[Sublime Text tools to help with linking](#sublime-text-tools-to-help-with-linking)
│   ├── Dynamic Titles[Dynamic Titles](#dynamic-titles)
│   ├── Opening Links[Opening Links](#opening-links)
│   │   ├── Sublime[Sublime](#sublime)
│   │   └── Pythonista[Pythonista](#pythonista)
│   ├── Linking to outside resources[Linking to outside resources](#linking-to-outside-resources)
│   │   ├── Web / HTTP(S)[Web / HTTP(S)](#web-/-https)
│   │   └── Files[Files](#files)
│   └── Pointers[Pointers](#pointers)
│       ├── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
│       ├── Duplicate Pointers[Duplicate Pointers](#duplicate-pointers)
│       │   └── Example Child Node Using a Node Pointer[Example Child Node Using a Node Pointer](#example-child-node-using-a-node-pointer)
│       └── Recursive Node Pointers[Recursive Node Pointers](#recursive-node-pointers)
│           ├── ! RECURSION 3:
│           └── Example Recursive Node Tree[Example Recursive Node Tree](#example-recursive-node-tree)
├── Exporting[Exporting](#exporting)
│   ├── Example : Urtext Documentation Exported in Markdown to a File[Example : Urtext Documentation Exported in Markdown to a File](#example-:-urtext-documentation-exported-in-markdown-to-a-file)
│   └── Example : Fragment Exported to HTML[Example : Fragment Exported to HTML](#example-:-fragment-exported-to-html)
├── Filenames[Filenames](#filenames)
├── File History[File History](#file-history)
├── Errors and Warnings[Errors and Warnings](#errors-and-warnings)
├── Using Multiple Projects at a Time[Using Multiple Projects at a Time](#using-multiple-projects-at-a-time)
│   ├── Project Naming (Identification)[Project Naming (Identification)](#project-naming-identification)
│   └── Linking Between Projects[Linking Between Projects](#linking-between-projects)
└── User Interface Elements[User Interface Elements](#user-interface-elements)
    ├── The Node Browser[The Node Browser](#the-node-browser)
    └── Traverse Mode[Traverse Mode](#traverse-mode)
        └── Word Wrap in Traverse Mode[Word Wrap in Traverse Mode](#word-wrap-in-traverse-mode)
###### Quick Start, Guides and Examples  

####### Installation and Setup (Desktop)

For desktop use (PC/Mac/Linux) Urtext is implemented in Sublime Text.

1. Download Sublime Text. (https://www.sublimetext.com/).

2. Download Urtext and all its dependencies from the monorepo at `https://github.com/nbeversl/urtext_deps`. You can either download this repository as a .ZIP file and unzip it, or if you want to maintain version control, use `git clone --recurse-submodules https://github.com/nbeversl/urtext_deps`. Put the contents of the cloned/unzipped folder (important: not the folder itself) directly into your `Sublime Text 3/Lib/python3.3` folder.

3. Download the Sublime Urtext package at `https://github.com/nbeversl/urtext_sublime`. Place it in your Packages folder (Sublime Text 3/Packages)

4. Clone/download this documentation repository and open its folder in Sublime. It will automatically be read as an Urtext project.

Once the Sublime package is installed, it will always look for any files with the .txt extension in open folders and attempt to compile them into a project. To open an existing Urtext project, open the folder, a file in the folder, or a Sublime project that includes the folder, and any feature described in this documentation will work.

To make a new project, open an empty folder and select Select `Urtext : Initialize Project` from the Sublime Command Palette. For more information, see [Projects](#projects).

See also:

[Sublime Text Interface Tips](#sublime-text-interface-tips)

[Using Urtext in iOS with Pythonista](#using-urtext-in-ios-with-pythonista)
####### Basic Syntax

All text is plain content unless inside a timestamp wrapper, dynamic definition wrapper, or preceded by a metadata assignment operator and keyname.

`{  }` 
Inline Node Wrappers. Can appear anywhere. Can be nested aribrarily deep.
More information: [Inline Nodes](#inline-nodes)

`>`		
Node Link. Links to the specified node by ID, like a hyperlink. 
More information: [Links](#links)

`>>`		
Node Pointer: Embeds the specified node as though it were included inline using wrappers { } (see above)
More information: [Pointers](#pointers)

`|` 
Title Pipe. Placed immediately before a node link or node pointer (whitespace is ok), dynamically populates the linked node title.
Example and more info: [Dynamic Titles](#dynamic-titles)

`^`
Compact Node marker. Must be the first non-whitespace character on a line. Must include an ID in order to parse.
More information: [Compact Nodes](#compact-nodes)

`< >`
Timestamp wrapper. Parses user-defined datetime strings, with many default formats built in.
The first character inside the brackets may not be `!`, '-', or whitespace.
Example: 
More information: [Timestamps](#timestamps)

`::`
Metadata assignment operator. Accepts a user-defined key on the left, and values and timestamps on the right.
Metadata may appear anywhere in text. They attach to their containing (parent) node but also remember their location and can serve as anchors/bookmarks to their context. Keys must be single words (underscore permitted), values may be any characters, terminated with a semicolon or newline. The pipe character (`|`) separates multiple values for a single key.
Example: 
More information: [Metadata](#metadata)
  (Closing pass marker. See above)

####### Dynamic Definitions : Syntax and Parameters

Dynamic definitions contain instructions for dynamically building nodes from the contents of other nodes. They can be written anywhere; it is not necessary to store the definition in the same file to which it refers. (Note that they cannot, however, be stored in the node they target, since they would overwrite themselves.)

Dynamic definitions are wrapped using double left and right square brackets. Note that there are no restrictions on spacing, indentation, newlines, or inclusion of other arbitrary text or whitespace. Dynamic definitions ignore whitespace and arbitrary text outside of defined parameters. The order of parameters within a definition is unimportant; they are evaluated as a group.

The dynamic definition below does not actually do anything. It rather lists every parameter along with an explanation of its use and purpose. For example uses, see [Dynamic Nodes](#dynamic-nodes)

####### Operations

Built-in operations are bound to either hotkeys or to UI menus.

Hotkeys differ among operating systems and can be reassigned according to your preference by
modifiying
######## Project Management 

Multiple Projects
Import Project
Reload Project
Reindex All Files
Rename File(s) from Meta
Delete This Node
Initialize Project
Pop Node
Move File to Other Project
######## Navigation 

`h` 	Home  `
Go to the designated home page of the project. Define the home node in [project_settings](#project_settings)

`<` 	Navigate Back
Go to the previously visited node (web-browser-like navigation)

`>` 	Navigate Forward 
Go to the next visited node (web-browser-like navigation)

`e`		Node List :
Show a quick search bar of all nodes in the current project

`*`		Global Node List:
Show a quick search bar of all nodes in all known projects.
######## Insertions 

`t` 	Timestamp:
Insert a timestamp at the cursor's location, in the project's default format. For setting timestamp format defaults, see [project_settings](#project_settings)

`i` 	ID:
Insert an arbitrary (unallocated) Node ID with metadata wrapper at the cursor position.
######## Editing 

`g`: 	Editing History
View the editing history for the currently viewed file.
For more informatino see [File History](#file-history)

(menu)	Consolidate Metadata
Consolidates all metadata tags in the node of the current cursor position, into a single wrapper.
######## Sublime Text Only 
Traverse Mode

####### Sublime Text Interface Tips  

Here are some tips for best leveraging Sublime's great UI features.
######## Syntax Highlighting 

This package comes with a .YML file (`sublime_urtext.sublime_syntax`) defining the Urtext syntax, along with two color schemes that provide syntax highlighting. Syntax highlighting makes everything easier by showing depth of node nesting and dimming certain elements of the syntax. Select the Sixteen (for light) or Monokai (for dark) color schemes in Preferences -> Color Scheme ... 

Then change to the Urtext syntax by selecting it in View -> Syntax -> Urtext. To avoid having to do this for every file, select View -> Syntax -> Open All with Current Extension As ... -> Urtext. (You can undo this later by repeating the same but selecting Plain Text.)
######## Hiding Tabs	

If you prefer a clean, terminal-like view, hide tabs: View -> Hide Tabs
This preference can also be set on a per-(Sublime)-project basis. See the Sublime documentation.
######## Hiding Line Numbers  

For an extra-clean look, hide line numbers by adding:

```

"settings" : {
"line_numbers": false,
},

```

... to your Sublime project settings file. (Ignore the JSON syntax pass makers above beginning with `%%`
See [Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers) )
######## Full Screen / Distraction Free Mode  

Since you can navigate entirely from within files, Urtext works great in Sublime's Distraction Free Mode. View -> Enter Distraction Free Mode.
######## Disable Prompts for File Reload 

Urtext does a lot of writing to files on the fly, often when they are already open. To avoid seeing a dialog every time, add add the following to your Sublime project settings or User Preferences file:
```
"settings" : {
"always_prompt_for_file_reload": false,
},
```
######## Remove Indent Guides  

Formatting plaintext using tab indentions can look messy if indent guides are on. To turn them off, add to your Sublime project settings file:
```
"settings" : { 
"draw_indent _guides": false,
}
```
######## Save on Focus Lost  

Urtext recompiles your project every time a file changes. To make this more automatic, addto your Sublime settings file:
```
"settings" : { 
"save_on_focus_lost": true 
}
```
######## Using a Sublime Project for an Urtext Project  

( see https://www.sublimetext.com/docs/3/projects.html )

You don't need to define a Sublime Project for the Urtext Project, but if you intend to do more than one thing at a time in Sublime, it's convenient to have one; you can then use Select Project -> Quick Switch Project (Ctrl-Super-P) to switch among them.

. 
Instead of the table of contents being drawn recursively from this node, you can see the recursion point in the table of contents.

Note that if you view the entire tree with another node selected as root, one full iteration will still appear, with the point of recursion falling elsewhere in the tree. Below is the Table of Contents with [Pointers](#pointers) as root.
##### Example Recursive Node Tree           
Pointers[Pointers](#pointers)
See [Dynamic Definitions : Syntax and Parameters](#dynamic-definitions-:-syntax-and-parameters) for more information on how to generate trees like this in dynamic nodes.


## Exporting

Urtext can convert (export) nodes, and sets of nodes, to plaintext, Markdown and HTML. Results can be either output to a file or written back into another node within the same project. Like other dynamic functions, exporting is dynamic ; that is, when changes are made to the source nodes, exports are immediately updated, whether they are in a project node or an external file.

Exporting is not implemented in user-interface menus/buttons. Instead, export by utilizing dynamic definitions.

The export command has three components:

export : (format) : ( source_node_id )

(format) : One of `plaintext`, `markdown` or `html`
(source_id): The source node to export.
### Example : Urtext Documentation Exported in Markdown to a File  

The following dynamic definition exports this entire documentation (from its root node [Urtext  Version: 0.5-alpha  Usage Guide and References](#urtext--version:-0.5-alpha--usage-guide-and-references) ) in Markdown format to a file called documentation.md:
### Example : Fragment Exported to HTML  

The following Dynamic Definition exports the [Links and Pointers](#links-and-pointers) section of the documentation to HTML, into a node inside this one:
defined

## Filenames


Since node identities are independent of their containing filenames, you can use any naming convention you want. Urtext can also rename files automatically in convenient formats based on their title and/or index. Renaming by index is useful, for instance, if you want file-level nodes easily readable inside a file system, mobile app, or other file browser.

To rename a file, select "Rename File from Meta" from the command palette (Command-P). This will rename the file in one of the following schema:

If an index is present:

.txt

If no index is present:

.txt

This system preserves automatic numerical sorting within the filesystem, such that the most recent un-indexed nodes appear first. If you want to use another system, such as putting the title first, you can do so.

## File History

Urtext files, being in plaintext, can be versioned using tools such as Git, Subversion, Mercurial, and others. Those tools are intended mainly for coding, when it is generally considered bad practice to commit non-working/non-compiling iterations of a project. Though Urtext files do compile, their actual text content is not a factor in this, so is reasonable to track changes at all stages of a project, even at granular levels.

Though use of powerful version control tools is not discouraged, Urtext has its own, lighter versioning system that tracks edits in the background at discrete intervals so it is not necessary to make explicit "commits" to have access to file history. Urtext creates a single, linear, nondestructive history of each file's content, with each snapshot being a "diff", or record of changes since the previous snapshot. When a previous state is restored, no "checkout" or "rewind" occurs; rather, the newly restored state is appended to the end of the history. Therefore, in addition to functioning as version control, the feature can also be used as a non-destructive "undo/redo" editing history that saves state after the file is closed.

The default interval is 10 seconds, and can be modified in project_settings. 
To access a file's timeline, use Control-Shift-G in Sublime Text. 

Histories are stored in the /history folder inside the project, as .pkl ("pickle") files. This folder requires no user involvement. If using another version control tool such as Git, you may wish to add the /history folder to your .gitignore file, so that only explicitly committed versions of your project are visible in distributed repositories.

## Errors and Warnings

[Embedded Syntaxes and Pass Markers](#embedded-syntaxes-and-pass-markers)
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

=>"name or path of the other project[ MISSING LINK : idj ] 
(This link is only an example and is non-functioning)

Following this link will change the project context to the named project and open its specified node.


## User Interface Elements

Urtext is made to require minimal user interface elements. They mostly serve as conveniences that duplicate 




### The Node Browser

The Node browser shows a list of all nodes in the project. It can be implemented in plaintext using a dynamic definition such as: . However, 

also be implemented 

Opening the Node List

Ctrl-Shift-E 






In Sublime Text there is also the alternative of using the UI dropdown. Press Control-Shift-E or select "Urtext: Node List" from the Sublime command palette (Shift-Super-P). Here you can find a node by typing part of its title.

In the Node List, nodes are sorted by their time of creation, with most recent first. They can also be sorted by index (see [`index`](#`index`)).



### Traverse ModeTraverse Mode   




This feature is currently implemented in Sublime Text only.

You can navigate a node tree or list of nodes by turning on Traverse mode (Shift-Ctrl-R). This will open another pane next to the one you are currently in. As you navigate the nodeview in the left side with the cursor or mouse, the selected node shows on the right. Use Sublime's Focus Group navigation keys, or the mouse, to switch between left and right panes.

Toggle Traverse Mode off by pressing Shift-Ctrl-R again. The status bar at the bottom of the Sublime window indicates whether Traverse is on or off. 

Note that if Traverse mode is off, you can also open a link manually (Shift-Ctrl-/) as normal. 

This feature is not built into Urtext; it is a feature of the Sublime package only.
#### Word Wrap in Traverse Mode 

Since Traverse Mode splits the window into two or more panes, it is suggested to set Word Wrap Column to "Auto" in Sublime Settings. This will cause the edited views to wrap correctly no matter the screen or window/pane size, as well as in Sublime's Distraction Free Mode.

Whenever Traverse Mode is enabled on a view, word wrap for that view is turned off altogether to prevent awkward wrapping of trees. It is restored when Traverse Mode is turned off.


