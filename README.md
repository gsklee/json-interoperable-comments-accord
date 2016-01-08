JSONIC: JSON with Interoperable Comments
========================================

```json
{
	"scripts": {
		"init": "./commands/init",
		"test": "./commands/test"
	},
	"dependencies": {
		"babel-core": "^5.8.30",
		"bound-native-methods": "^0.1.6",
		"isomorphic-fetch": "^2.2.0",
		"react": "^0.14.0",
		"react-dom": "^0.14.0",
		"classnames": "^2.2.0",
		"redux": "^3.0.4",
		"react-redux": "^4.0.0"
	},
	"devDependencies": {
		"webpack": "^1.12.2",
		"babel-runtime": "^5.8.29",
		"babel-loader": "^5.3.2",
		"express": "^4.13.3",
		"webpack-dev-middleware": "^1.2.0",
		"webpack-hot-middleware": "^2.4.1",
		"babel-plugin-react-transform": "^1.1.1",
		"react-transform-hmr": "^1.0.1",
		"react-transform-catch-errors": "^1.0.0",
		"redbox-react": "^1.1.1"
	},
	"#comments": {
		"scripts": {
			"init": ["", "$ npm run init"],
			"test": ["", "$ npm test"]
		},
		"dependencies": {
			"babel-core": ["ECMAScript 2015+"],
			"react": ["React"],
			"redux": ["Redux"]
		},
		"devDependencies": {
			"webpack": ["Webpack"],
			"express": ["Development Server"],
			"babel-plugin-react-transform": ["Hot Reload"]
		}
	}
}
```
