## Nunjucks broswer usage test ##

### Relevant docs ###

- https://mozilla.github.io/nunjucks/api.html#browser-usage
- https://mozilla.github.io/nunjucks/templating.html


### Notes for myself ###

#### Steps to precompile templates ####

1. `npm install nunjucks-precompile`
2. create a `template` directory to keep your project structure clean
3. under the `template` directory, create a `html` file that contains your template code (e.g., `template/foo.html`)
4. run the `nunjucks-precompile` command in Terminal when your template code is ready for compilation
```bash
nunjucks-precompile template/foo.html >> template/foo.js
```
**REMEMBER TO COMPILE YOUR TEMPLATES EVERY TIME A CHANGE IS BEING INTRODUCED THERE**


#### To use the precompiled templates ####

- Step 1: include `nunjucks.js` as well as the compiled template (e.g., `template/foo.js`) in `index.html`
```html
<script type="text/javascript" src="https://mozilla.github.io/nunjucks/files/nunjucks.js"></script>
<script type="text/javascript" src="template/foo.js"></script>
```
- Step 2: render the template
```js
var data = {
  username: "Mavis"
};

nunjucks.render('template/foo.html', data, function(err, res) {
  // console.log("res = ",res);
  document.querySelector("#app").innerHTML = res;
});
```



