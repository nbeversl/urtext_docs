 

# Urtext Introduction

## About Urtext

### Description

Urtext (pronounced /ˈʊrtekst/) is a syntax and interpreter for writing, connecting and organizing text.

Urtext's basic unit is a "node", which is a range or set of ranges of text within a file. A folder of nodes is a "project". The Urtext interpreter is aware of all the nodes in a project at once, so nodes can reference, modify, and organize one another, across hundreds or thousands of files. The | Basic Syntax >znj permits instructions embedded into the text itself. 

The present interpreter for Urtext is in Python and can be used wherever Python 3.3 or later runs. Equivalent or variant interpreters could be created in any language or editing environment. 

Urtext has no built-in user interface; it only compiles and manages the files. Using Urtext requires an implementation within a text editor or text view. Currently there is a package for Sublime Text (Mac/Windows/Linux) and a script for Pythonista (iOS).

### Comparison To Other Tools

Urtext shares some characteristics with markup languages such as Markdown and LaTeX, with the important difference that it is author-facing, rather than reader-facing. It is not primarily a document conversion or generation tool, though it can export to some other formats (currently Markdown and HTML). It is rather a tool for writing and organizing writing.

Urtext's syntax mixes content, structure and instructions all together. Unlike HTML or other markup languages, there is no additional code or markup "behind" the visible syntax. Everything the interpreter reads is visible to the author/user.

### Uses

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

### Features and Philosophy

#### Plain Text

Plaintext is fast, human-readable, flexible, cross-platform, device-portable, and future-proof. It can be easily diffed and version-controlled (using Git, for example). Using theming and syntax highlighting, Urtext forms a user interface out of its own syntax, without relying on graphic elements.

Urtext can also incorporate (embed) other plaintext syntaxes, including other markup languages and programming language syntaxes.

#### Freeform, Flexible Syntax

Urtext is like an inverse programming language. Whereas most programming languages provide a "comment" syntax to insert freeform text around the code, Urtext works the opposite way: all content is text unless it matches syntax for structural or instructional code.

Text can be supplemented with user-defined metadata independent of the file system's metadata (datetime stamps, comments, etc.). It can even be used as a flat-file database.

Similar to code projects, an Urtext project can be spread across dozens or thousands of files, with individual files providing "routes", or connections, to other other files or parts of files (nodes) via their node IDs. Text elements can be linked in tree-like, recursive (tangled), and other non-hierarchical ways.

However, the basics are very simple, and you can use only the parts you need.

#### Open source

- Usable across multiple platforms and devices.

- Decoupled from any particular text editor or interface ; it can be incorporated into any environment that runs Python, including any scriptable text editor or Python-scriptable environment capable of displaying a text editing view.

#### Extensible

Urtext Actions, Directives, and Extensions all inherit from base classes that can be extended to add or modify functionality, limited only by the power of the Python language. 

At present these features are undocumented, but can be understood, with a little Python knowledge, by reading the code.

#### Future Proof

No reliance on anything that may not exist in 5 or 1000 years. 

The interpreter/compiler could be implemented in any sufficiently capable language, current, past or future.

#### Local

The Urtext parser is made primarily to operate on files present locally on the device. It is not dependent on a cloud or other subscription service. 

Cloud services can be used to sync project files among devices if desired.

### Features

- Connect text among dozens, hundreds or thousands of files
- User-definable metadata
- Dynamic content that aggregates from the contents from elsewhere in the project(s).
- Package for Sublime Text 3/4 and an implementation for iOS using Pythonista 
- Manage, edit and cross-connect multiple projects within a single Urtext instance  
- Lightweight built-in versioning system that tracks edits at intervals.
- Direct interaction with file system is mostly unnecessary. Creating, naming, saving, and organizing files is handled for you.
- Urtext is designed to make direct interaction with file system mostly unnecessary. Creating, naming, saving, and organizing files is handled for you.

## Installation and Setup in Sublime Text

The Urtext package for Sublime Text utilizes Sublime's embedded Python interpreter both to run the Urtext interpreter/compiler and to add features to Sublime that make working with Urtext easy:

- binds many Urtext operations to the Sublime command palette
- adds key bindings (hotkeys) as shortcuts for some features
- leverages the built-in Sublime browser/palette for Urtext project navigation
- defines a syntax for use with Sublime's color schemes
- adds Urtext syntax highlighting to two of Sublime's default color schemes (Monokai and Sixteen)
- adds filebrowser-like project navigation using | Traverse Modes >a8q

Some features in this documentation are built into the Urtext interpreter/compiler, while others are part of only the Sublime Text implementation.

### Installation


- Install Sublime Text: https://www.sublimetext.com/ 

- The Sublime Urtext package is available on Sublime Package Control: Press ⌘/Ctrl + ⇧ + P to open the command palette. Type Install Package and press Enter. Then search for Urtext. Alternative, clone/download Sublime Urtext ( https://github.com/nbeversl/urtext_sublime ) and place it in your `Packages` folder.

- Urtext is now ready to use.

### Getting Started, Using Either the Demo or Reference Documentation

At this point, clone this repository and open either of its subfolders in Sublime Text:

#### Urtext Demo Project 

This walks you through using Urtext through friendly, progressive steps.

After opening this folder (or any file in it) in Sublime Text, position the cursor on this linke below and press Ctrl-Shift-/ which will take you to the start page:

=>"Sample Project"[ MISSING LINK : 8mw ] 

#### Reference Documentation 

This is a component-by-component guide for Urtext's features. After opening this folder in Sublime Text:
* Ctrl-Shift-H will take you to the node that generated the README file. 
* Scroll to the bottom and you'll find this node (this very text you are reading) at the end of the file.
* Click on the link below to browse the reference:

| Urtext: Reference Documentation >a5m

## About the README  _

The README.md file is an export of this file node (| Urtext Introduction >013). The repository contains a fuller reference guide and a "walkthrough" project, both fully functioning Urtext projects with which to experiment with Urtext's features. 

The documentation is in active development. It may be incomplete or behind features/functionality of Urtext. Edits and revisions are encouraged in the form of issues and pull requests (https://github.com/nbeversl/urtext-docs/pulls, https://github.com/nbeversl/urtext-docs/issues).[./README.md](./README.md) 