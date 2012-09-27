# Welcome to Scripted

## What is Scripted?

Scripted is a fast and lightweight code editor with an initial focus on JavaScript editing.  Scripted is a browser based editor
and the editor itself is served from a locally running node server instance.  The editor is actually the Eclipse Orion editor with
a few additional bells and whistles. Anyone familiar with editing in Eclipse will immediately know many of the key bindings
the Scripted editor supports.

What are the key features?

- Fast startup, lightweight.
- Syntax highlighting for JavaScript, HTML and CSS.
- Errors and warnings: 
	- JSLint is integrated to provide error/warning markers on JavaScript code.
	- AMD and commonjs module resolution: there is basic resolution where unresolved references will be marked as errors.
- Content assist:
	- Basic content assist for HTML, CSS
	- For JavaScript, content assist is driven by a type inferencing engine which is aware of AMD/Commonjs module 
dependencies and uses JSDoc comments to help it understand the code.
- Hovers: hovering over a JavaScript identifier will bring up the inferred type signature.
- Navigation: 
	- press F8 on an identifier (that the inferencer has recognized) and the editor will navigate to the declaration.
	- this also works on module identifiers (e.g. in <tt>define()</tt> clauses)
- Formatting: JSbeautify is integrated
- Sidepanel: alongside the main editor a sidepanel can be opened - currently this can be used to host a second editor.
- Key binding to external command: Key bindings in the editor can invoke external commands (less, mvn, etc)

Many of these are covered in this introductory screencast:

//TODO VIDEO//

# How do I try it out?

The only pre-req for trying it out is that you have node installed. Grab node from here: [[http://nodejs.org/]]

With node installed you can either clone the repository:

	git clone https://github.com/SpringSource/scripted

or grab a zip of the latest from here:

	https://github.com/SpringSource/scripted/zipball/master

If you have the zip, just unzip it then add the bin folder to your path:

Mac/Linux:

	export PATH=<pathToUnzippedScriptedOrClone>/bin:$PATH

Win:

	set PATH=<pathToUnzippedScriptedOrClone>\bin;%PATH%

then launch it:

	scr myfile.js

(you can use <tt>scripted</tt> to launch it if you'd prefer to type more characters...)

When working with Scripted, think about it like using <tt>vi</tt>/<tt>emacs</tt>. From wherever you are in your terminal window you can
can launch scripted and start editing a file.

Launching scripted will cause the node server to start in the background.

Here are some of the more vital key bindings to use once the editor is open:

- <tt>Cmd/Ctrl+h</tt> - open help to show all key bindings (or press '?' in the top right)
- <tt>Cmd/Ctrl+s</tt> - save!
- <tt>Cmd/Ctrl+Shift+E</tt> - open/close subeditor
- <tt>Cmd/Ctrl+Shift+F</tt> - open Find File dialog. Inside the dialog, you can search for files in the project by regular expression and:
-- <tt>Click</tt> a result to open it in main editor
-- <tt>Shift+Click</tt> a result to open it in sub-editor
-- <tt>Cmd/Ctrl+Click</tt> a result to open it in a new tab
- <tt>Cmd/Ctrl+F</tt> - in file search
- <tt>Ctrl+Space</tt> - content assist
- <tt>F8</tt> - navigate to declaration
- <tt>Shift+F8</tt> - open declaration in subeditor
- <tt>Cmd/Ctrl+F8</tt> - navigate to declaration in new tab

On the left hand side is a traditional navigator for opening different files. Above the editor is a breadcrumb, hover over a component to see other files in that directory.

The editor does support a degree of customization, see the section in the [User Guide](//TODO LINK//).

# Further reading

- [FAQ](https://github.com/SpringSource/scripted/wiki/FAQ)
- [Architecture](https://github.com/SpringSource/scripted/wiki/Architecture)

# What's next for Scripted?

//TODO DETAILS//
sidepanel
debugging
content assist


# Where can I ask questions, provide feedback or raise issues?

- The [google group](https://groups.google.com/forum/#!forum/scripted-editor) is open for questions and discussion
- The [issuetracker](https://issuetracker.springsource.com/browse/scripted) to raise issues or take a look and vote on existing issues.

# Can I contribute?

Sure! Just press *Fork* at the top of this github page and get coding. Before we accept pull requests we just need you to sign a simple contributor's
agreement (similar to other SpringSource projects) - which you can find [here](https://support.springsource.com/spring_committer_signup). Signing the contributor's agreement does not grant anyone commit rights to the main repository, but it does mean that we can accept your contributions, and you will get an author credit if we do. Active contributors might be asked to join the core team, and given the ability to merge pull requests.
Pull requests should ideally reference a JIRA ticket in the [issuetracker](https://issuetracker.springsource.com/browse/SCRIPTED) that details what the request is addressing.

The codebase is entirely JavaScript/HTML/CSS and the team uses Scripted to develop Scripted.

If you are keen to contribute but aren't sure what to work on, take a look at the [public issuetracker](https://issuetracker.springsource.com/browse/SCRIPTED) for inspiration.
The codebase is very new in places and isn't that tricky to get to grips with. Some of the simpler issues that might provide an easy way to get started with the codebase are tagged with the label help-wanted, see [here](https://issuetracker.springsource.com/secure/IssueNavigator.jspa?reset=true&jqlQuery=project+%3D+SCRIPTED+AND+labels+%3D+help-wanted+AND+status+in+%28Open%2C+%22In+Progress%22%2C+Reopened%29+ORDER+BY+key+ASC%2C+priority+DESC).
