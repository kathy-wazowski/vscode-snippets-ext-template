# vscode-snippets-ext-template README
This is a project will help you create your vscode snippets extensions easier and quicker.

For example,you want to add a `forof` snippet for JavaScript.
You only need to add an simple item in `snippets-src/snippets.json`,like this:

```json
{
    "forof": {
        "description": "For-Of Loop"
    }
}
```

Then create a `forof.js` file in `includes/js` folder to write the snippet body in it.

Like this:

```js
for (const ${ 1: iterator } of ${ 2: object }) {
    $0
}
```

After execute `npm run build` a fully configured `snippets.json` will create in `snippets` folder.


What make this possible  is that there's a `make_snippets.js` NodeJs scripts.
Which can read/parse `snippets.json` file.
1. add some need options.
2. include the snippet body from the configured `includes/js` folder.

Below is how we can call a `makeSnippets` function to make the configured snippets file

`makeSnippets('snippets.json', 'js', { scope: "javascript,typescript" });`

## Usage
### for New snippets extensions
just clone this repo and use as your base repo.

### for Exists snippets extensions
1. copy `snippets-src` folder to your project.
2. copy all your `snippets.json` from `snippets` older into `snippets-src` folder.
3. extrac your snippet code into new source file in a folder.
4. edit the make_snippets.js as needed.



