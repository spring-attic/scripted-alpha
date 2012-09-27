Welcome to the Scripted project.

# What is Scripted?

Scripted is a fast and lightweight code editor with an initial focus on JavaScript editing.  Scripted is a web based editor
and the editor is served from a locally running node server instance.  The editor is actually the Eclipse Orion editor with
few additional bells and whistles. Anyone familiar with editing in Eclipse will immediately know many of the key bindings
the Scripted editor supports.

What are the key features?

- Fast startup, lightweight
- Syntax highlighting for JavaScript, HTML and CSS.
- Errors and warnings: 
-- JSLint is integrated to provide error/warning markers on JavaScript code.
-- AMD and commonjs module resolution: these is basic resolution where unresolved references will be marked as errors.
- Content assist:
-- Basic content assist for HTML, CSS
-- Type inferencing engine for JavaScript which is *also* aware of AMD/Commonjs module dependencies.
- Hovers: hovering over a JavaScript identifier will bring up the inferred type signature.
- Navigation: 
-- press F8 on an identifier (that the inferencer has understood) and the editor will navigate to the declaration.
-- this also works on module identifiers.
- Formatting: JSbeautify is integrated
- Sidepanel: alongside the main editor a sidepanel can be opened - right now this can be used to host a second editor.
- Key binding to external command: Key bindings in the editor can invoke external commands (less, mvn, etc)

# How do I try it out?

The only pre-req for trying it out is that you have node installed.

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

(you can use 'scripted' to launch it if you'd prefer to type more characters...)

Invoking scripted will cause the node server to start in the background and then a browser will open against that server, editing myfile.js

# Further reading


# What is the focus for Scripted during the next few weeks/months?

# Can I contribute?

Sure! Simply clone the repository:

git clone https://github.com/SpringSource/scripted

and you can start. The code is all JavaScript/HTML/CSS. 

There is a [public issuetracker](https://issuetracker.springsource.com/browse/SCRIPTED) and some of the simpler issues that 
might provide an easy way to get started with the codebase are tagged with the label help-wanted.  This list of issues is accessible [here](https://issuetracker.springsource.com/secure/IssueNavigator.jspa?reset=true&jqlQuery=project+%3D+SCRIPTED+AND+labels+%3D+help-wanted+AND+status+in+%28Open%2C+%22In+Progress%22%2C+Reopened%29+ORDER+BY+key+ASC%2C+priority+DESC)


