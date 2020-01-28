
## Boilerplate for SCSS Project

- install nodejs: https://nodejs.org/en/
- create a project directory and open a terminal for directory
- run command `npm init --scope=@scope-name` to create a scoped package (ex: city-furniture) - this creates a package.json file: https://docs.npmjs.com/creating-node-js-modules
- for scoped 
- run command `npm install node-sass —save-dev` to install the css compiler into the developer-dependencies list of package.json
- run command `npm install clean-css —save-dev` to install the css minifier into the developer-dependencies list of package.json
- add the following scripts to package.json
```
"scripts": {
    "compile-styles": "node-sass --output-style expanded --source-map true --source-map-contents true --precision 6 styles.scss dist/styles.css",
    "css-minify": "cleancss --level 1 --format breaksWith=lf --source-map --source-map-inline-sources --output dist/styles.min.css dist/styles.css",
    "process-styles": "npm run compile-styles && npm run css-minify"
}
```
- run the command `npm run process-styles` to compile and minify the sass project structure
- create an account to https://www.npmjs.com/ in order to publish the package to npm
- inside the terminal write command `npm login` and enter the credentials and email
- update the package.json file with description, repository and scope or other missing attributes
- run command `npm publish` to publish the package
- increase the version number from packge.json based on semantic-versioning: https://docs.npmjs.com/about-semantic-versioning
- if something went wrong with project naming or structure, run command `npm unpublish` within 72 ours to unpublish (remove) the repository: https://docs.npmjs.com/unpublishing-packages-from-the-registry

## Use the package inside another project
- install the package using the command `npm install package-name`
- inside a scss file from the new project write the following:
```
$containerWidth: 500px;
$containerColor: yellow;

@import '../node_modules/example-scss-project/styles.scss';
```
- the above snippet overrides the variables values and import the style from the imported package
- an example of a scss project is available here: https://github.com/Gabi09/example-scss-project

### other resources:
- compile and minify a sass project: https://www.jamesedwards.name/npm-compile-sass
- overriding variables inside scss files: https://medium.com/@bajena3/a-story-about-overriding-scss-variables-and-the-default-keyword-eace1de34631
- creating a step-by-step npm package: https://dev.to/therealdanvega/creating-your-first-npm-package-2ehf