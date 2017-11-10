# fin-hypergrid-browserify-template

Repo template to "require" the fin-hypergrid npm module and build a single .js file using gulp-browserify.

### Try it out

```bash
git clone https://github.com/openfin/fin-hypergrid-browserify-template.git my-proj
cd my-proj
npm install
gulp
open index.html
```

### What happened?

The above series of commands **downloads, builds,** and **runs** the demo:
* `git clone ...`
    * downloads the demo
* `cd ...`
    * change to the new directory
* `npm install`
    * install dev dependencies (such as [Browserify](https://www.npmjs.com/package/browserify)) used by gulp below to create the build
    * install external dependencies, only `fin-hypergrid` for this template, but you can add more as needed
* `gulp`
    * creates the `./build` directory (if not already there)
    * runs Browserify to create a single bundled file, `./build/index.js`, from:
       * your `./index.js`; and
       * the `fin-hypergrid` package, _etc._
* `open index.html` runs the demo page
    * uses the `file://` protocol (no server needed)
    * requests the bundled file (`build/index.js`) via a `<script>` tag
    * note that `open` is only available on macOS; on other systems manually open the file in a browser

### Try with the alpha version

To test your build with the alpha version of fin-hypergrid instead of the current version of the npm module,
change the **`fin-hypergrid`** dependency in the package.json file to
`"https://github.com/openfin/fin-hypergrid#alpha"` and then rebuild:

```bash
npm update
gulp
open index.html
```

### Try with a local build of Hypergrid

To test a local fork of Hypergrid instead of the current version,
change the **`fin-hypergrid`** dependency in the package.json file to
`file:../fin-hypergrid` or simply `"../fin-hypergrid"`
(assuming your fork is in a sister folder) and rebuild as above.

### Recommendations

For actual development iterations, we suggest enhancing the build file with a watcher (to rebuild and reload), linter, and minifier. See for example [fin-hypergrid/core/gulpfile.js](https://github.com/fin-hypergrid/core/blob/master/gulpfile.js).