# Prettier Config

[![npm version](https://badge.fury.io/js/%40upstatement%2Fprettier-config.svg)](https://badge.fury.io/js/%40upstatement%2Fprettier-config)

My very opinionated prettier config. If you're not me you probably shouldn't use it.

## Table of Contents

- [Prettier Config](#prettier-config)
	- [Table of Contents](#table-of-contents)
	- [Installation](#installation)
	- [Editor Integration & Autoformatting](#editor-integration--autoformatting)
		- [VS Code](#vs-code)
		- [Sublime Text 3](#sublime-text-3)
		- [Atom](#atom)
	- [Pre-commit Hooks](#pre-commit-hooks)
	- [Publishing to npm](#publishing-to-npm)
	- [Enforced Rules](#enforced-rules)

## Installation

1. Make sure your project is using a Node version >= `10`

2. Install dependencies

		```sh
		npm install --save-dev @igoro00/prettier-config prettier@2.x.x

		# or

		yarn add --dev @igoro00/prettier-config prettier@2.x.x
		```

3. Create a `prettier.config.js` file at the root of your project with the following:

		```js
		module.exports = require('@igoro00/prettier-config');
		```

## [Editor Integration](https://prettier.io/docs/en/editors.html) & Autoformatting

### VS Code

1. Install the [Prettier extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode): `View → Extensions` then find and install `Prettier - Code formatter`
2. Reload the editor
3. Open your [settings JSON file](https://code.visualstudio.com/docs/getstarted/settings#_settings-file-locations) and add the following

		```json
		// Format on save with Prettier rules
		"editor.formatOnSave": true,
		// Tell the ESLint plugin to run on save
		"editor.codeActionsOnSave": {
			"source.fixAll.eslint": true
		},
		// Turn off Prettier format on save, use ESLint to format instead
		"[javascript]": {
			"editor.formatOnSave": false
		},
		"[vue]": {
			"editor.formatOnSave": false
		},
		"eslint.alwaysShowStatus": true,
		// An array of language identifiers specify the files to be validated
		"eslint.options": {
			"extensions": [".html", ".js", ".vue", ".jsx"]
		},
		```

### Sublime Text 3

[https://packagecontrol.io/packages/JsPrettier](https://packagecontrol.io/packages/JsPrettier)

### Atom

[https://atom.io/packages/prettier-atom](https://atom.io/packages/prettier-atom)

## Publishing to npm

Read npm's docs on [How to Update a Package](https://docs.npmjs.com/getting-started/publishing-npm-packages#how-to-update-a-package).

1. Checkout and pull the `master` branch

2. Run the release script to bump the version numbers (the script will create a commit and push up the release branch to GitHub for you)

	```shell
	./scripts/release
	```

	Use [semantic versioning](https://docs.npmjs.com/about-semantic-versioning/) to choose the appropriate version number.

3. Submit and merge a PR from the release branch into `master`

4. Make sure you're logged into npm from the command line using `npm whoami`. If you're not logged in, `npm login` with the credentials in 1pass

5. `npm publish`

## Enforced Rules

Check out all of Prettier's [configuration options](https://prettier.io/docs/en/options.html).

<details>
	<summary>Print Width</summary>

	Line wrap at 100 characters.

</details>

<details>
	<summary>Tabs</summary>

	Spaces are for separating words, not scope of code blocks!

</details>

<details>
	<summary>Semicolons</summary>

	Always print semicolons at the ends of statements.

	```js
	const greeting = 'hi';
	```

</details>

<details>
	<summary>Quote</summary>

	Use an actual quotes instead of apostrophes.

	```js
	const quote = "With double quotes you don't have to escape apostrophes. It's better, isn't it?";
	```

</details>

<details>
	<summary>Trailing Commas</summary>

	Always put trailing commas.

	```js
	const obj = {
		a: 'hi',
		b: 'hey',
	};
	```

</details>

<details>
	<summary>Bracket Spacing</summary>

	Print spaces between brackets in object literals.

	```js
	{ foo: bar }
	```

</details>
