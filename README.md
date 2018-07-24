# prettier-config

Upstatement's official [`prettier`](https://prettier.io) configuration.

## Installation

Requires **npm 5+**

```bash
npx install-peerdeps --dev @upstatement/prettier-config
```

## Usage

Create a `prettier.config.js` file at the root of your project that contains:

```js
module.exports = require('@upstatement/prettier-config');
```

## Alternative 4 space config

Just add an additional `.prettierrc` file with the following:

```json
{
  "overrides": [
    {
      "files": "*",
      "options": { "tabWidth": 4 }
    }
  ]
}
```

## Pre-commit Hook

As another line of defense, if you want Prettier to automatically fix your errors on commit, you can use [`pretty-quick`](https://github.com/azz/pretty-quick).

1.  `npm install --save-dev husky prettier pretty-quick`
2.  Update your `package.json` like this:

```json
{
  "scripts": {
    "precommit": "pretty-quick --staged"
  }
}
```

If you already have `lint-staged` running ESLint on precommit, you can just add `pretty-quick` with `&&`:

```json
{
  "scripts": {
    "precommit": "lint-staged && pretty-quick --staged"
  },
  "lint-staged": {
    "*.js": ["eslint --fix", "git add"]
  }
}
```

## Editor Integration

https://prettier.io/docs/en/editors.html

### Visual Studio Code

1.  Install Prettier extension: `View → Extensions` then find and install Prettier - Code formatter
2.  Reload the editor
3.  In your user settings `Code -> Preferences -> Settings` add `editor.formatOnSave: true`

### Sublime Text 3

TBD

### Atom

TBD

## Enforced Rules

Check out Prettier's config options [here](https://prettier.io/docs/en/options.html).

- ### Print Width

  Line wrap at 100 characters.

- ### Tab Width

  2 spaces per indentation-level.

- ### Tabs

  Indent lines with spaces, not tabs.

- ### Semicolons

  Always print semicolons at the ends of statements.

  ```js
  const greeting = 'hi';
  ```

- ### Quote

  Use single quotes instead of double quotes.

  ```js
  const quote = 'single quotes are better';
  ```

- ### Trailing Commas

  Use trailing commas wherever possible.

  ```js
  const obj = {
    a: 'hi',
    b: 'hey',
  };
  ```

- ### Bracket Spacing

  Print spaces between brackets in object literals.

  ```
  { foo: bar }
  ```

- ### JSX Brackets

  Put the `>` of a multi-line JSX element at the end of the last line instead of being alone on the next line (does not apply to self closing elements).

  ```
  <button
    className="prettier-class"
    id="prettier-id"
    onClick={this.handleClick}>
    Click Here
  </button>
  ```

- ### Arrow Function Parentheses

  Omit parens when possible.

  ```js
  x => x;
  ```
