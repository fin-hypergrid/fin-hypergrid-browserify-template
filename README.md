# fin-hypergrid-browserify-template

Repo template to "require" the fin-hypergrid npm module and build a single .js file using gulp-browserify.

### Try it out

```bash
git clone https://github.com/openfin/fin-hypergrid-browserify-template.git
cd fin-hypergrid-browserify-template
npm install
gulp # uses Browserify to create build/index.js from index.js which "requires" fin-hypergrid
open index.html # includes the build file via a <script> tag
```

### Require the alpha

To test your build with the alpha version of fin-hypergrid instead of the current version:

In the package.json file, change

```javascript
  "dependencies": {
    "fin-hypergrid": "^1.3"
  }
```

to

```javascript
  "dependencies": {
    "fin-hypergrid": "https://github.com/openfin/fin-hypergrid#alpha"
  }
```

Then:

```bash
npm update
gulp
open index.html
```