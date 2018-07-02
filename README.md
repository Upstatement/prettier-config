# prettier-config

Upstatement's official [`prettier`](https://prettier.io) configuration.

## Installation

Install the package from [npm](https://www.npmjs.com/package/@upstatement/prettier-config) using `npm` or `yarn`:

```bash
npm install --save-dev @upstatement/prettier-config
```

## Usage

Create a `prettier.config.js` file in your project's root that re-exports the module:

```js
module.exports = require('@upstatement/prettier-config');
```

## Alternative 4 space config

Never fear! Just add an additional `.prettierrc` file with the following:

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

## How to test this module locally

Once you've cloned this repo, create a global link for this package:

```bash
npm link
```

Then in the project you want to use this config for, link-install this package:

```bash
npm link @upstatement/prettier-config
```

And finally in that project's `prettier.config.js`, include:

```js
module.exports = require('@upstatement/prettier-config');
```

## Running prettier with precommit

Install [husky](https://github.com/typicode/husky) and [pretty-quick](https://github.com/azz/pretty-quick) to use precommits to run prettier on your files:

```bash
npm install --save-dev husky pretty-quick
```

Then in your `package.json` file:

```json
"scripts": {
  "precommit": "pretty-quick --staged"
},
```
