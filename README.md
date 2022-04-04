# scripted-alpha is no longer actively maintained by VMware, Inc.

# Welcome to Scripted

## What is Scripted?

Scripted is a fast and lightweight code editor with an initial focus on JavaScript editing.
Scripted is a browser based editor and the editor itself is served from a locally running Node.js
server instance.  

<center>
<img src="https://dist.springsource.org/release/SCRIPTED/screenshot2.png" width="736" height="451"/>
</center>

What are the key features?

- Fast startup, lightweight.
- Syntax highlighting for JavaScript, HTML and CSS.
- Errors and warnings: 
	- JSLint is integrated to provide error/warning markers on JavaScript code.
	- AMD and CommonJS module resolution: there is basic resolution where unresolved references will be marked as errors.
- Content assist:
	- Basic content assist for HTML, CSS
	- For JavaScript, content assist is driven by a type inferencing engine which is aware of AMD/CommonJS module 
dependencies and also uses JSDoc comments to help it understand the code.
- Hovers: hovering over a JavaScript identifier will bring up the inferred type signature.
- Navigation: 
	- press F8 on an identifier (that the inferencer has recognized) and the editor will navigate to the declaration.
	- this also works on module identifiers (e.g. in `define()` clauses)
- Formatting: JSbeautify is integrated
- Sidepanel: alongside the main editor a sidepanel can be opened - currently this can be used to host a second editor.
- Key binding to external command: Key bindings in the editor can invoke external commands (less, mvn, etc)

The editor is actually the [Eclipse Orion](https://www.eclipse.org/orion/) editor with a few additional bells and whistles.
Anyone familiar with editing in Eclipse will immediately know many of the key bindings
the Scripted editor supports.

Many of these are covered in this introductory screencast:<br>
<a href="https://dist.springsource.org/release/SCRIPTED/Scripted2.mov"><img align="center" src="https://dist.springsource.org/release/SCRIPTED/posterScripted2.png" width="428" height="263"/></a>

# How do I try it out?

The only pre-req for trying it out is that you have Node.js installed. Grab it from here: [https://nodejs.org/](https://nodejs.org).
The team has been testing with recent versions from 0.6 to 0.8.

Then you can grab the most recent packaged release from here:

[Version 0.2.0](https://dist.springsource.org/release/SCRIPTED/scripted_v0.2.0.zip)

OR you can live on the bleeding edge by either cloning the repository:

	git clone https://github.com/SpringSource/scripted

or grabbing the latest repo contents as a zip:

	https://github.com/SpringSource/scripted/zipball/master

Unpack whatever you have and then make sure the files in the bin folder are executable on mac/linux:

	chmod 755 bin/*

Then add the bin folder to your path:

Mac/Linux:

	export PATH=<pathToUnzipLocationOrClone>/bin:$PATH

Win:

	set PATH=<pathToUnzipLocationOrClone>\bin;%PATH%

then launch it:

	scr myfile.js

(you can use `scripted` to launch it if you'd prefer to type more characters...)

When working with Scripted, think about it like using `vi`/`emacs`. From wherever you are in your terminal window you 
can launch Scripted and start editing a file.

Launching scripted will cause the Node.js server to start in the background.

Here are some of the more vital key bindings to use once the editor is open:

- `Cmd/Ctrl+h` - open help to show all key bindings (or press '?' in the top right)
- `Cmd/Ctrl+s` - save!
- `Cmd/Ctrl+Shift+E` - open/close subeditor
- `Cmd/Ctrl+Shift+F` - open Find File dialog. Inside the dialog, you can search for files in the project by regular expression and:
   - `Click` a result to open it in main editor
   - `Shift+Click` a result to open it in sub-editor
   - `Cmd/Ctrl+Click` a result to open it in a new tab
- `Cmd/Ctrl+Shift+o` - open outline view. A dialog will present the functions and you can quickly navigate to them
- `Cmd/Ctrl+F` - in-file search
- `Ctrl+Space` - content assist
- `F8` - navigate to declaration
- `Shift+F8` - open declaration in subeditor
- `Cmd/Ctrl+F8` - navigate to declaration in new tab
- `Alt+Shift+F` - format

On the left hand side is a traditional navigator for opening different files. Above the editor is a breadcrumb, hover over a component to see other files in that directory.

The editor does support a degree of customization, see the section on the [Features](https://github.com/SpringSource/scripted/wiki/Features) page.

Scripted receives most testing in Chrome and Firefox, you may need one of those browsers in order to get the most out of it.

# Anything else I need to know before using it?

When you open Scripted on a file, it will attempt to infer the root of your project by locating the nearest `.git`/`.project` file
in the hierarchy. Knowing the root is important because that is the scope in which searching and dependency analysis is done. If
you don't have one of these markers for the root, you can create an empty `.scripted` file to indicate the root.

# Current status

As of Oct 2012 the project is at version 0.2. There is a long way to go but the team have been using Scripted to develop Scripted for a while now.

# Further reading

- [Features](https://github.com/SpringSource/scripted/wiki/Features)
- [FAQ](https://github.com/SpringSource/scripted/wiki/FAQ)
- [Troubleshooting](https://github.com/SpringSource/scripted/wiki/FAQ#wiki-Troubleshooting)
- [Architecture](https://github.com/SpringSource/scripted/wiki/Architecture)

# Where can I ask questions, provide feedback or raise issues?

- The [scripted-dev google group](https://groups.google.com/forum/#!forum/scripted-dev) is open for questions and discussion
- The [issuetracker](https://issuetracker.springsource.com/browse/scripted) to raise issues or take a look and vote on existing issues.

# What's next for Scripted?

- Even smarter inferencing, leading to better content assist and easier navigation.
- More panes for the side panel. Currently there is just an editor pane but we intend to include search results panes,
documentation, git information panes, perhaps code preview and simulated code execution panes. The intention will be
for Scripted to try and automatically manage these where possible, so all the content on screen is kept relevant
to the task at hand.
- Simple plugin system. 
- Debugging. Exploring integration with tools like Chrome Dev Tools and node inspector.

If you have more ideas for what you'd like to see, let us know via [Jira](https://issuetracker.springsource.com/browse/scripted) or 
our [scripted-dev](https://groups.google.com/forum/#!forum/scripted-dev) group.

# Can I contribute?

Sure! Just press *Fork* at the top of this github page and get coding. Before we accept pull requests we just need you to sign a simple contributor's
agreement (similar to other SpringSource projects) - which you can find [here](https://support.springsource.com/spring_committer_signup). Signing the contributor's agreement does not grant anyone commit rights to the main repository, but it does mean that we can accept your contributions, and you will get an author credit if we do. Active contributors might be asked to join the core team, and given the ability to merge pull requests.
Pull requests should ideally reference a JIRA ticket in the [issuetracker](https://issuetracker.springsource.com/browse/SCRIPTED) that details what the request is addressing.

The codebase is entirely JavaScript/HTML/CSS.

If you are keen to contribute but aren't sure what to work on, take a look at the [public issuetracker](https://issuetracker.springsource.com/browse/SCRIPTED) for inspiration.
The codebase is very new in places and isn't that tricky to get to grips with. Some of the simpler issues that might provide an easy way to get started with the codebase are tagged with the label help-wanted, see [here](https://issuetracker.springsource.com/secure/IssueNavigator.jspa?reset=true&jqlQuery=project+%3D+SCRIPTED+AND+labels+%3D+help-wanted+AND+status+in+%28Open%2C+%22In+Progress%22%2C+Reopened%29+ORDER+BY+key+ASC%2C+priority+DESC).

If you don't feel like coding but still want to contribute, please join the discussion on the issuetracker and scripted-dev group.
