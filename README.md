# Info for contributors

- The actual files to edit are in `src`. The `.js` files in the main directory are generated, as follows:
	- `wysie.js` is a concatenation of the files in `src`.
	- `wysie.es5.js` is `wysie.js` above, but transpiled using Babel
	- `wysie.min.js` is `wysie.es5.js` above, but minified (currently transpiling is a necessary step to minify ES6)
- The naming convention in `src` is:
	- The entry point is `wysie.js` 
	- Main components have a simple filename, without periods, e.g. `collection.js`.
	- Addons that could be omitted have a period in their name and start with the name of the file they are addons for. For example:
		- Files defining storage backends are named `storage.xxx.js` where `xxx` is the name of the backend. E.g. `storage.dropbox.js`, `storage.github.js` etc.
		- Files defining new input widgets are named `primitive.xxx.js` where `xxx` is a short description of the widget. E.g. `primitive.imgur.js`, `primitive.markdown.js` etc.
- To contribute, you first need to (one time stuff):
	- Install node
	- Run `npm install` to install the build tools (gulp & gulp plugins)
	- Clone `bliss` in a repo adjacent to the one you cloned wysie in. This is temporary, in the future Bliss will be bundled with wysie.
- Now, every time you work on wysie:
	- Run `gulp watch` to automatically build every time you save.
	- Run `python -m SimpleHTTPServer` to be able to use `http://` locally, since most APIs don't like the `file://` protocol and Chrome doesn't even allow AJAX on it.