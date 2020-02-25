
Urtext Documentation



Version: 0.2.0-alpha
License: GNU General Public License 3.0



# About Urtext


# Setup


# Nodes


Think of a node as a region of paper with flexible and open-ended length.



## Inline Nodes


Nodes can be nested arbitrarily deep inside other nodes, whether the parent node is a file or another inline node. The syntax for inline nodes is to wrap the content in double curly braces:

.



Unlike a word processor, Urtext requires attention to syntax. Every opening doubly curly bracket must be closed in the same file and requires an ID metadata tag between its opening an closing brackets.

NOTE that file-level nodes "File Level Nodes") do not use curly-braces, as their boundaries are defined by the file itself.

For all purposes in Urtext, inline nodes' metadata and identity is unique from their containing file and parent nodes.


Compact Nodes ## Compact Nodes


For contents requiring only a single line, such as list items, very short notes, and similar entries, use the caret character (`^`) as the first non-whitesoace character on a new line. This defines a new node as a child of the node in which the ^ character appears, with the closing wrapper being the end of the same line. Note that, like all nodes, a compact node must contain an ID, and can contain any other metadata. It can even include inline nodes, as long as their entire contents, including wrapper and metadata, are contained on a single line.

(Note that "line" in this case refers to consecutive characters between explicit line breaks, and not to lines in the editor, which may be arbitrarily wrapped.)

### Example Compact Node






Split Nodes ## Split Nodes


A node region can be split into two separate nodes by placing the `%` character as the first character on a line. Each node must then have its own ID, which you can either generate manually (see Inserting a Node ID manually"Inserting a Node ID manually") or with the split node shortkey (below,"Shortkeys to Create Split Nodes").





Note using a `%` symbol at the file level (outside of an inline node wrapper) is equivalent to dividing the file into multiple file-level nodes; inline nodes generated inside any of these will be children only of their containing node, not of any other file-level nodes in the same file.


Generating a node ID manually ## Generating a node ID manually


Metadata ## Node Metadata


Metadata is data about the content, in the form of key/value pairs and timestamps. Other than a few reserved key/value pairs used for compiling, metadata is open for user-defined purposes. Keys and values of metadata tags are indexed automatically and searchable within the Urtext project (see"Project Metadata List"). 

Metadata regions in Urtext open with a forward-slash followed by two dashes and close with two dashes followed by a forward slash. Each metadata entry is a key/value pair, separated by a colon, with the value containing an optional timestamp. Examples:




The only required metadata is a node ID. Additional user-defined metadata can be added into the same region, and additional metadata regions can be inserted arbitrarily anywhere inside a node. You can also string several entries together on one line, separated by semicolons:



Note that: 

-   A colon separates the key from the value 

-   All three components are optional; any content preceding a colon (if one is present) is interpreted as a key; content following the (first) colon is interpreted as a value. If no colon is present, the entry is read as a key with an empty value.

-   A timestamp anywhere in the value will be indexed as the timestamp for the whole metadata entry. If more than on timestamp appears in an entry, only the first one is indexed.

-   Values are not case-sensitive, except for the values of the following keys:

title
notes
timestamp_format 
( used in the project_settings node only : see"project_settings")
filenames



Next topics:

Timestamps ### Timestamps


Reliance on the operating system's file-created or file-modified date metadata is avoided, since it can be too easily and involuntarily overwritten under ordinary file system operations, such as copying and moving files or folders. 

Text between two angled brackets (<  >) is interpreted as a timestamp. 

To insert a timestamp in Sublime, press Control-Shift-O. 

Node timestamps are part of metadata (see Metadata"Node Metadata"). Urtext also utilizes a "loose" parsing of inline timestamps, meaning they can be placed anywhere and will be recognized and parsed.

Timestamps are read and written utilizing Python's `strftime` directives. The default format is:

%%-PYTHON
`.%a., %b. %d, %Y, %I:%M %p`
%%-END

which creates timestamps like: <Tue., Jun. 04, 2019, 08:51 PM>. The format can be customized in the project_settings node (see project_settings"project_settings"). For more information on `strftime` directives and options, see https://docs.python.org/2/library/datetime.html#strftime-and-strptime-behavior.


Project Metadata List ### Project Metadata List



Like "The Node List", every project maintains a Metadata List, automatically written to a built-in file-level dynamic node. The Node ID `zzy` is reserved for the Metadata list. (See "Node Identity (Node IDs)" for more information on Node IDs). To see the metadata list for the documentation, for instance, see node >>


Project Metadata List  

Like "The Node List", every project maintains a Metadata List, automatically written to a built-in file-level dynamic node. The Node ID `zzy` is reserved for the Metadata list. (See "Node Identity (Node IDs)" for more information on Node IDs). To see the metadata list for the documentation, for instance, see node >>zzy.




Node list ## The Node List


Every project maintains a list of all its nodes. The Node List is automatically written to a built-in file-level dynamic node. (See "Dynamic Nodes" for more information). 






In Sublime Text there is also the alternative of using the UI dropdown. Press Control-Shift-E or select "Urtext: Node List" from the Sublime command palette (Shift-Super-P). Here you can find a node by typing part of its title.

In the Node List, nodes are sorted by their time of creation, with most recent first. They can also be sorted by index (see "index"). 

The Node ID `zzz` is reserved for the Node list. (See "Node Identity (Node IDs)" for more information.)




# Dynamic Nodes

## Description & Purpose
Dynamic nodes can compile and update content in real time from other nodes. Dynamic nodes can display complete contents or lists of titles of other nodes, as well as display tree diagrams of relationships among nodes, across many files.

## Syntax
Dynamic node definitions are enclosed in double square brackets and can be inserted into any node arbitrarily.


# Trees


In Sublime, you can view a tree of node hierarchies in two ways:



Note that each branch of the resulting file tree contains Node ID that works like a link. You can navigate the links on the tree using Shift-Control-/ (see "Simple Links") or using "Traverse Mode".

File trees are displayed in Sublime's scratch views, meaning they will never report as being "dirty" (unsaved). They are intended for one-time/temporary use, will not have a filename, and will not update when a node/file changes. To make permanent and dynamically updated trees, see "Dynamic Nodes".

You can extend node trees beyond the file level by using "Pointers".

Thanks to the `anytree` module (https://pypi.org/project/anytree/) for the plaintext node tree diagrams.


# Links and Pointers




## Viewing Linked Relationships


Elaborate writing and reference systems such as wikis often linking nodes together in tangled and intricate ways. While Urtext cannot draw diagrams of this kind (called acyclic graphs) in plaintext, it can represent these relationships from the perspective of any one node: Position the cursor in the desired node and select "Urtext : Show Linked Relationships..." The currently selected node will be displayed as root; all nodes linking into this nodes, and recursively into those nodes, will be displayed above the root; all files linked from this node, and recursively from those nodes, will be displayed below. Circular references are represented up to one iteration.

These diagrams are displayed as Sublime "scratch" views, meaning they will never report as being dirty (unsaved). They are intended for one-time/temporary use and will not update when a node/file changes. To make permanent and dynamically updated diagrams, see "Dynamic Nodes".






## Linking to outside resources




## Pointers


You can extend trees beyond the file level to create node relationships spanning many files. Preceding a link to a node with two right angle brackets instead of one creates a Pointer. In addition to being a hyperlink, this connects the targeted node, and all of its subchildren, as children of the node containing the Pointer. Example:

Here is an example Child Node:

| Example Child Node Using a Node Pointer >>

Pointers          

You can extend trees beyond the file level to create node relationships spanning many files. Preceding a link to a node with two right angle brackets instead of one creates a Pointer. In addition to being a hyperlink, this connects the targeted node, and all of its subchildren, as children of the node containing the Pointer. Example:

Here is an example Child Node:

### Example Child Node Using a Node Pointer



The example Pointer above becomes a child of this node, visible in the "Table of Contents" or using the other tree views described in "Trees".

The advantages to Node Pointers are many, including:

- The tree represents a hierachy of actual content, rather than the files containing the content.

- The tree permits nesting both within and beyond file level.

- The tree can be displayed from any arbitrary starting point, whether or not its branches are within or beyond a particular file.


## Traverse Mode
Traverse Mode    

This feature is currently implemented in Sublime Text only.

You can navigate a node tree or list of nodes by turning on Traverse mode (Shift-Ctrl-R). This will open another pane next to the one you are currently in. As you navigate the nodeview in the left side with the cursor or mouse, the selected node shows on the right. Use Sublime's Focus Group navigation keys, or the mouse, to switch between left and right panes.

Toggle Traverse Mode off by pressing Shift-Ctrl-R again. The status bar at the bottom of the Sublime window indicates whether Traverse is on or off. 

Note that if Traverse mode is off, you can also open a link manually (Shift-Ctrl-/) as normal. 

This feature is not built into Urtext; it is a feature of the Sublime package only.




# Using Multiple Projects at a Time


To use multiple projects at once, Urtext utilizes a context manager. When you initially pass a path to Urtext, it looks recursively in all sub folders for additional projects. If it finds a compilable Urtext project in any one, it adds these to the context manager.  You can then freely switch among projects, either explicitly, or using links between the projects (described below). When switching projects, all Urtext's features, content and behavior, including links, compiling, and all functions linked to UI buttons, will operate in the context of the selected project. 

You can put all your Urtext projects into sub folders of a single path. Alternatively, you may put them anyplace in the file system and choose as your Urtext root a folder that encompasses them all. Compiling may take longer if Urtext has to search through many unused directories. 

The current implementations in Sublime and Pythonista use the context manager by default, even if you are only using a single project.

Recall that what defines a project is its folder. This is also what separates it from other projects. If you add other Urtext project folders into the initial path, they will all be accessible from the same project list.

To switch between projects in Sublime, select Urtext: Select Project from the command palette.
In Pythonista, use the | button.


# Converting and Exporting


Urtext can convert (export) nodes, and sets of nodes, to plaintext, Markdown and HTML. Results can be either output to a file or written back into another node within the same project. Like other dynamic functions, exporting is dynamic ; that is, when changes are made to the source nodes, exports are immediately updated, whether they are in a project node or an external file.

Exporting is not implemented in user-interface menus/buttons. Instead, export by utilizing dynamic definitions.

The export command has three components:

export : (format) : ( source_node_id )

(format) : One of `plaintext`, `markdown` or `html`
(source_id): The source node to export.


# Search


# Filenames



Since node identities are independent of their containing filenames, you can use any naming convention you want. Urtext can also rename files automatically in convenient formats based on their title and/or index. Renaming by index is useful, for instance, if you want file-level nodes easily readable inside a file system, mobile app, or other file browser.

To rename a file, select "Rename File from Meta" from the command palette (Command-P). This will rename the file in one of the following schema:

If an index is present:

<index> <title>.txt

If no index is present:

<node id> <title>.txt

This system preserves automatic numerical sorting within the filesystem, such that the most recent un-indexed nodes appear first. If you want to use another system, such as putting the title first, you can do so.


# Extension and Customization


Some features described in this document are specific to this Sublime Text implementation, (though they could be reproduced in any scriptable text editor), but most are features of Urtext itself. Where there is question, you can find out fairly be inspecting the code. Anything that is 
[ TO BE COMPLETED ]



